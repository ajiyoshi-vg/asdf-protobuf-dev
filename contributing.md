# Contributing

Testing Locally:

```shell
asdf plugin test <plugin-name> <plugin-url> [--asdf-tool-version <version>] [--asdf-plugin-gitref <git-ref>] [test-command*]

# TODO: adapt this
asdf plugin test build-protobuf https://github.com/ajiyoshi-vg/asdf-build-protobuf.git "build-protobuf --help"
```

Tests are automatically run in GitHub Actions on push and PR.
