name: Lint HORNET
on: [push, pull_request]
jobs:
  build:
    name: Lint HORNET
    runs-on: ubuntu-latest
    steps:
      - name: Set up Go 1.14
        uses: actions/setup-go@v1
        with:
          go-version: 1.14
        id: go

      - uses: actions/checkout@v2
      - name: Run golangci-lint
        uses: actions-contrib/golangci-lint@v1
        run: run --new-from-rev=HEAD~1
