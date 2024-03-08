
ASDF_INSTALL_TYPE ?= ref
ASDF_INSTALL_VERSION ?= main
ASDF_INSTALL_PATH ?= $(abspath ../test)
ASDF_DOWNLOAD_PATH ?= $(abspath ../tmp)

REF ?= main
PROTO_REPO := https://github.com/protocolbuffers/protobuf
PROTO_SOURCE := $(ASDF_DOWNLOAD_PATH)/protobuf/$(REF)
PROTO_PREFIX := $(ASDF_INSTALL_PATH)/$(REF)

CMAKE_OPTION := -DCMAKE_CXX_STANDARD=14

all:
	@echo ASDF_INSTALL_VERSION:$(ASDF_INSTALL_VERSION)
	@echo ASDF_INSTALL_TYPE:$(ASDF_INSTALL_TYPE)
	@echo ASDF_INSTALL_PATH:$(ASDF_INSTALL_PATH)
	@echo ASDF_DOWNLOAD_PATH:$(ASDF_DOWNLOAD_PATH)
	@echo PROTO_SOURCE:$(PROTO_SOURCE)
	@echo PROTO_PREFIX:$(PROTO_PREFIX)

list_all_versions:
	@git ls-remote --tags --refs "$(PROTO_REPO)" | \
		grep -o 'refs/tags/.*' | cut -d/ -f3- | \
		sed 's/^v//'

download:
	git clone $(PROTO_REPO) -b $(REF) --depth 1 $(PROTO_SOURCE)
	git submodule update --init --recursive $(PROTO_SOURCE)

install: $(PROTO_SOURCE)/cmake.tmpdir
	cd $< && \
		cmake $(PROTO_SOURCE) \
			$(CMAKE_OPTION) \
			-DCMAKE_INSTALL_PREFIX=$(PROTO_PREFIX)
	cmake --build $< --parallel 10 --config Release
	cmake --install $<
	rm -rf $<
	$(PROTO_PREFIX)/bin/protoc --version

%.tmpdir:
	mkdir -p $@
