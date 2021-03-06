# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

## [1.0.0-rc.0](https://github.com/CrowdHailer/raxx/tree/1.0.0-rc.0)([0.13.0](https://github.com/CrowdHailer/raxx/tree/0.13.0)) - 2017-10-16

## Changed

- `Raxx.Trailer` has been renamed to `Raxx.Tail`.
- `handle_trailers` has been renamed to `handle_tail`.
- `Raxx.Fragment` has been replaced by `Raxx.Data`.
- `handle_fragment` has been replaced by `handle_data`

## Removed
- Specific header modules that were prevously deprecated.
  - `Raxx.Connection`
  - `Raxx.ContentLength`
  - `Raxx.Location`
  - `Raxx.Referrer`
  - `Raxx.TransferEncoding`
  - `Raxx.UserAgent`

## [0.12.3](https://github.com/CrowdHailer/raxx/tree/0.12.3) - 2017-10-14

## Added
- Using `Raxx.Server` imports helper functions from `Raxx`.
- Using `Raxx.Server` aliases `Raxx.Request`.
- Using `Raxx.Server` aliases `Raxx.Response`.

## Removed
- Dependency on `Plug` is not needed.
- Support for Elixir 1.4, `Raxx.Router` had bugs.

## [0.12.2](https://github.com/CrowdHailer/raxx/tree/0.12.2) - 2017-10-11

## Added

- `Raxx.trailer/0` completes request without any extra metadata.
- `handle_request/2` added to `Raxx.Server` behaviour.
- Default implementations added to `Raxx.Server` callbacks.
- `Raxx.Router` will forward request to controllers based on request patterns.

## [0.12.1](https://github.com/CrowdHailer/raxx/tree/0.12.1) - 2017-09-24

## Fixed
- Cannot set HTTP headers with uppercase attribute.
- Cannot add an HTTP header twice.

## [0.12.0](https://github.com/CrowdHailer/raxx/tree/0.12.0) - 2017-08-31

## Changed
- Replace simple interface with a streaming interface through `Raxx.Server`.
  See full [article](https://hexdocs.pm/tokumei/interface-design-for-http-streaming.html#content).
- Build messages with `Raxx` module instead or `Raxx.Request` and `Raxx.Response`.
