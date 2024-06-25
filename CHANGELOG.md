# CHANGELOG

## Unreleased

## 0.6.0

- **BREAKING** [#181](https://github.com/contentful-userland/contentful.ex/pull/181) Resolve all link fields found within "items" in an API response, and replace the links with actual entities, if available from the "includes" section of API response. Inspired by https://github.com/contentful/contentful.js/blob/master/ADVANCED.md#link-resolution

Note: BREAKING CHANGE, 'assets' field on Entry struct is no longer populated. All Assets for an Entry are now embedded directly within 'fields' instead

## 0.5.0

- [#97](https://github.com/contentful-userland/contentful.ex/pull/97) switches underlying http adapter to `tesla` for higher flexibility. Thank you @OldhamMade
- tests against Elixir 1.13 and updates required elixir version to 1.11

## 0.4.1

- [#75](https://github.com/contentful-labs/contentful.ex/issue/75) fixes an issue concerning malformed docs, thanks @OldhamMade

## 0.4.0

- [#49](https://github.com/contentful-labs/contentful.ex/pull/49) Adds extended query syntax for building more complex queries, as suggested by @ryansch in [#38](https://github.com/contentful-labs/contentful.ex/issues/38)
- adds testing against Elixir 1.10.4

## 0.3.2

- [#47](https://github.com/contentful-labs/contentful.ex/pull/47) Handle bitstring case when resolving assets (thanks @aspala)

## 0.3.1

- [#37](https://github.com/contentful-labs/contentful.ex/issues/37) Fixed an error preventing correct entity resolution for assets (thanks @OldhamMade)
- [#44](https://github.com/contentful-labs/contentful.ex/issues/44) Adds missing common properties to content types, assets entries (thanks @OldhamMade)
- [#36](https://github.com/contentful-labs/contentful.ex/issues/36) Added dependabot for keeping dependencies up to date
- [#9](https://github.com/contentful-labs/contentful.ex/issues/9) Added the ability to specify an endpoint other than the Delivery API
- Improved some README sections about how to query certain entities

## 0.3.0

### Features

- Introduced a DSL that can be composed into queries
- Solved the `include` removal by readding it (#20)
  - Also allows for resolving assets included in entries

### Chores

- Deleted most Context(s) module code
- Updated the docs with more working examples

## 0.2.0

Note: This release is incompatible with previous releases as this lacks the `include` functionality, specifically.

### Features

- Reworked the way data can be queried from the CDA endpoint
- Split up the modules into mapping to different Contentful APIs
- Introduced a way to stream the CDA API endpoints instead of relying on pagination
- Added

### Chores

- Added badges and `ex_doc` integration (published via [hex.pm](https://hex.pm))
- Updated the docs with examples

## 0.1.1

### Fixed

- Fixed issue on empty includes
- Fixed compatibility with Elixir 1.4

## 0.1.0

### Added

- Added some spec coverage for all endpoints and include resolution
- Added Linter tool

### Changed

- Improved syntax conventions
- Refactored Include Resolution into it's own module

## 0.0.1 [INITIAL RELEASE]

### Added

- Added all CDA Endpoints
- Added Basic Include Resolution
