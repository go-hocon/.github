<p align="center"><img src="https://raw.githubusercontent.com/go-hocon/brand/main/social/go-hocon.png" alt="go-hocon" width="640"></p>

<h1 align="center">go-hocon</h1>
<p align="center"><strong>HOCON (Typesafe Config) parser in pure Go — substitutions, includes, units, a JSON superset.</strong></p>

<p align="center">
  🌐 <a href="https://go-hocon.github.io">Website</a> ·
  📚 <a href="https://go-hocon.github.io/docs/">Documentation</a>
</p>

<p align="center">
  <a href="https://go-hocon.github.io/docs/"><img alt="Docs" src="https://img.shields.io/badge/docs-mkdocs--material-4F46E5?style=flat-square"></a>
  <a href="https://github.com/go-hocon/hocon/blob/main/LICENSE"><img alt="License: BSD-3-Clause" src="https://img.shields.io/badge/license-BSD--3--Clause-blue?style=flat-square"></a>
  <img alt="Go 1.26.4+" src="https://img.shields.io/badge/go-1.26.4%2B-00ADD8?style=flat-square&logo=go&logoColor=white">
  <img alt="Coverage 100%" src="https://img.shields.io/badge/coverage-100%25-1a7f37?style=flat-square">
</p>

---

go-hocon is a pure-Go (CGO_ENABLED=0) parser for HOCON, the Human-Optimized Config Object Notation used by Typesafe Config. HOCON is a superset of JSON that adds unquoted keys and strings, = as an alias for :, optional commas and root braces, # and // comments, dotted-path keys, deep merging of duplicate keys, array and value concatenation, ${path} / ${?path} substitutions with environment fallback, += self-append, include directives and duration / size unit suffixes. Includes and environment lookups run through injectable seams, so callers and tests never need touch the filesystem or process environment. Typed accessors read dotted paths and Render serialises back to HOCON or JSON. Standard library only, 100% coverage, six arches and WebAssembly.

## Repositories

| Repo | What it is |
|------|------------|
| [**hocon**](https://github.com/go-hocon/hocon) | the engine library |
| [**docs**](https://github.com/go-hocon/docs) | MkDocs Material documentation, versioned with [mike], served at [/docs/](https://go-hocon.github.io/docs/) |
| [**go-hocon.github.io**](https://github.com/go-hocon/go-hocon.github.io) | the Hugo landing page |
| [**brand**](https://github.com/go-hocon/brand) | logos and brand assets |

## Principles

- **Pure Go, zero cgo.** `CGO_ENABLED=0`; imports the Go standard library only. Cross-compiles to the
  six 64-bit Go targets (amd64, arm64, riscv64, loong64, ppc64le, s390x) and WebAssembly, linking into a static binary.
- **Faithful to the HOCON / Typesafe Config specification.**
- **An engine, not a service.** A small, stable Go API you embed — validated
  against the reference [`puppetlabs/ruby-hocon`](https://github.com/puppetlabs/ruby-hocon)
  gem, and part of a wider family of pure-Go config/data-format engines
  alongside [go-eyaml](https://github.com/go-eyaml) and
  [go-augeas](https://github.com/go-augeas).
- **100% test coverage** including error branches, enforced as a CI gate.

BSD-3-Clause.

[mike]: https://github.com/jimporter/mike
