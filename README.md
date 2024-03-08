<div align="center">

# asdf-build-protobuf [![Build](https://github.com/ajiyoshi-vg/asdf-build-protobuf/actions/workflows/build.yml/badge.svg)](https://github.com/ajiyoshi-vg/asdf-build-protobuf/actions/workflows/build.yml) [![Lint](https://github.com/ajiyoshi-vg/asdf-build-protobuf/actions/workflows/lint.yml/badge.svg)](https://github.com/ajiyoshi-vg/asdf-build-protobuf/actions/workflows/lint.yml)

[build-protobuf](https://github.com/ajiyoshi-vg/asdf-build-protobuf) plugin for the [asdf version manager](https://asdf-vm.com).

</div>

# Contents

- [Dependencies](#dependencies)
- [Install](#install)
- [Contributing](#contributing)
- [License](#license)

# Dependencies

- `bash`, `curl`, `tar`, and [POSIX utilities](https://pubs.opengroup.org/onlinepubs/9699919799/idx/utilities.html).
- `cmake`: to build protobuf

# Install

Plugin:

```shell
asdf plugin add build-protobuf
# or
asdf plugin add build-protobuf https://github.com/ajiyoshi-vg/asdf-build-protobuf.git
```

build-protobuf:

```shell
# Show all installable versions
asdf list-all build-protobuf

# Install specific version
asdf install build-protobuf latest

# Set a version globally (on your ~/.tool-versions file)
asdf global build-protobuf latest

# Now build-protobuf commands are available
build-protobuf --help
```

Check [asdf](https://github.com/asdf-vm/asdf) readme for more instructions on how to
install & manage versions.

# Contributing

Contributions of any kind welcome! See the [contributing guide](contributing.md).

[Thanks goes to these contributors](https://github.com/ajiyoshi-vg/asdf-build-protobuf/graphs/contributors)!

# License

See [LICENSE](LICENSE) © [ajiyoshi-vg](https://github.com/ajiyoshi-vg/)
