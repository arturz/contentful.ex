# Contentful Elixir SDK

Elixir SDK for the [Contentful](https://www.contentful.com) Content APIs.

[![Elixir CI](https://github.com/contentful-labs/contentful.ex/workflows/Elixir%20CI/badge.svg)](https://github.com/contentful-labs/contentful.ex/actions?query=workflow%3A%22Elixir+CI%22)
[![Coverage Status](https://coveralls.io/repos/github/contentful-labs/contentful.ex/badge.svg?branch=main)](https://coveralls.io/github/contentful-labs/contentful.ex?branch=main)
[![Hex.pm](https://img.shields.io/hexpm/v/contentful?style=flat)](https://hex.pm/packages/contentful)
[![License](https://img.shields.io/github/license/contentful-labs/contentful.ex?style=flat)](./LICENSE.txt)

[Contentful](https://www.contentful.com) provides a content infrastructure for digital teams to power content in websites, apps, and devices. Unlike a CMS, Contentful was built to integrate with the modern software stack. It offers a central hub for structured content, powerful management and delivery APIs, and a customizable web app that enable developers and content creators to ship digital products faster.

## API Overview

### Contentful Delivery API (CDA)

The official docs can be found here: https://www.contentful.com/developers/docs/references/content-delivery-api/.

The API provides the content for Contenful apps. It's read only and the recommended way to deliver large amounts of content.

### Contentful Management API (CMA)

The official docs can be found here: https://www.contentful.com/developers/docs/references/content-management-api/.

The API provides the capability to manage content you have stored with Contentful.

### Contentful Preview API (CPA)

The official docs can be found here: https://www.contentful.com/developers/docs/references/content-preview-api/.

The Preview API can be used to access the latest versions and drafts of your content. It maintains compatibility with the Contentful Delivery API.

## Installation

1. Add contentful to your list of dependencies in `mix.exs`:

```elixir
  def deps do
    [{:contentful, "~> 0.4.0"}]
  end
```

2. Ensure contentful is started before your application:

```elixir
  def application do
    [applications: [:contentful]]
  end
```

## Usage

For the usage, see the [documentation published to hex](https://hexdocs.pm/contentful/Contentful.html).

### Local documentation

In case you want to compile the docs locally, run:

```bash
$ mix docs

# to view, we recommend:
$ cd doc && python -m SimpleHTTPServer # or any other quick way to serve static content locally
```

then open [`http://localhost:8000`](http://localhost:8000).

## Contributing & Development

1. Fork the repository
2. Create your feature branch on your fork (`git checkout -b my-new-feature`)
3. Make your changes
4. Run tests (`mix test`) and static analysis (`mix credo --strict`)
5. Commit your changes (`git commit -am 'Add some feature'`)
6. Push to your branch (`git push origin my-new-feature`)
7. Create a Pull Request on this original repository

### Notes on setup

This library makes use of the Contentful APIs. It helps to [have an account](https://www.contentful.com/sign-up/#small) and to setup a secrets file for testing:

```bash
$ cat config/secrets.dev.exs
config :contentful, delivery: [
  access_token: "<my_cda_access_token>",
  environment: "master",
  space_id: "<my_space_id>"
]

# for testing
$ cat config/secrets.test.exs
config :contentful, delivery: [
  access_token: "<my_cda_access_token>",
  environment: "testing",
  space_id: "<my_space_id>"
]
```

We freeze requests by using `exVCR`, in case you want to rebuild these files, make sure that test assertions match.
