# Public Zone Database

[![build status](https://img.shields.io/circleci/project/zonedb/zonedb/master.svg)](https://circleci.com/gh/zonedb/zonedb)
[![godoc](http://img.shields.io/badge/docs-GoDoc-blue.svg)](https://godoc.org/github.com/zonedb/zonedb)

The Public Zone Database (zonedb) contains a list and associated metadata of public [DNS zones](http://en.wikipedia.org/wiki/DNS_zone) (domain extensions). It attempts to be exhaustive, including current, retired, and withdrawn top-level domains and subdomains.

The intended use case is programs that interface with the [public domain name system](http://en.wikipedia.org/wiki/Domain_Name_System), including registry and registrar services. The data overlaps with and shares test cases with the [Public Suffix List](http://publicsuffix.org/) maintained by the [Mozilla Foundation](https://mozilla.org/). The source data was originally derived from the internal zone database in use at [Domainr](https://domainr.com/).

## Structure

The database consists of a list of zones (`zones.txt`) and associated metadata in JSON format.

### zones.txt

The `zones.txt` file is a UTF-8 encoded text file containing a list of domain names, one per line, followed by a newline (`\n`) character. The domain names in zones.txt are sorted according to the following rules:

1. Number of labels (top-level domains, followed by second- and third-level domains)
2. Parent domain (e.g. `uk`)
3. Subdomain (e.g. `co.uk`)

### Metadata

Each domain with associated metadata will have a JSON file in the `metadata` directory.

## Contributing

Fork this repository, make changes, and send a pull request.

### zonedb build tool

This database is generated and validated using the `zonedb` tool in this directory. To install, make sure you have a working [Go](https://golang.org) installation (1.4+) and run this command:

```shell
go get -u github.com/zonedb/zonedb/build/cmd/zonedb
```

You can also run the `zonedb` tool directly: `go run build/cmd/zonedb/main.go`

## License

This database is licensed under the [Open Database License (ODBl) version 1.0](http://opendatacommons.org/licenses/odbl/1.0/). See [LICENSE.md](https://github.com/domainr/zonedb/blob/master/LICENSE.md) for more information.

Copyright © 2008–2015 the Public Zone Database authors.
