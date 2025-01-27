# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

----

## v4.7.0 => 2021-MAR-24

### Added

* Adobe 2021 to the testing matrix and supported engines

### Fixed

* Adobe 2021 issues with date formatting
* Watcher needed to use the root `.cfformat.json`

----

## v4.6.0 => 2021-FEB-18

### Added

* New method: `setAccessControlPolicy()` so you can add ACLs to buckets
* `getBucket()` has been updated to use the ListObjectsv2 API - which is recommended by AWS for more detailed information.
* Implements SigV4-signed requests thanks to @sbleon's amazing work!
* Added more formatting rules via cfformat
* Added a `gitattributes` for cross OS compatibilities
* Added a `markdownlint.json` for more control over markdown
* Added new package script : `format:watch` to format and watch :)

### Changed

* Updated tests to fire up in ColdBox 6
* Handles some cleanup of parameters which were being passed as resource strings ( which were then being encoded and blowing up ).
* Updated release recipe to match newer modules.

### Removed

* Cleanup of old cfml engine files
* Cleanup of old init code
* Removed some settings from test harness

----
## v4.5.0 => 2020-MAR-11

* `Feature` : `SV4Util` is now a singleton for added performance and more configuration expansion by adding the sdk reference
* `Improvement` : Better error messages when s3 goes :boom:
* `Bug` : Fix for ACF double encoding

----
## v4.4.0 => 2019-MAY-15

* Reworked SSL setup to allow for dynamic creation of the URL entry point
* Removed ACF11 officially, it is impossible to deal with their cfhttp junk! It works, but at your own risk.

----
## v4.3.0 => 2019-APR-05

* Removal of debugging code

----
## v4.2.1 => 2019-MAR-26

* Avoid double encoding on `copy`, `putObjectFile`, and `delete()` operations
* Consolidate ssl to use `variables` instead of `arguments`

----
## v4.2.0 => 2019-MAR-15

* ACF compatiblities
* Fixes for auth on folder commands
* New constructor args: `defaultDelimiter` for folder operations, `defaultBucketname` so you can set a default bucket for all bucket related operations.
* Avoid nasty error on bucket deletion
* Add new method `objectExists()` boolean check for objects
* Fix URI encoding on signatures for headers and query params

----
## v4.1.1 => 2019-MAR-26

* Left some dump/aborts

----
## v4.1.0 => 2019-MAR-13

* DigitalOcean Spaces compatiblity
* Region naming support, you can now pass the `awsRegion` argument to the constructor to select the AWS or DO region
* SSL is now the default for all operations
* Addition of two new constructor params: `awsRegion` and `awsDomain` to support regions and multi-domains for AWS and Digital Ocean
* Added log debugging to calls and signatures if LogBox is on `debug` level

----
## v4.0.1 => 2018-OCT-22

* Fixes to models location, oopsy!

----
## v4.0.0 => 2018-OCT-20

* AWS Region Support
* Migrated Module Layout to use Ortus Standard Module Layout
* Added testing for all ACF Engines
* Rework as generic Box module (compatibility change), you must move your `s3sdk` top level settings in ColdBox Config to `moduleSettings.s3sdk`
* `deleteBucket()` returns **false** if bucket doesn't exist instead of throwing an exception
* Few optimizations and documentation of the API

----
## v3.0.1

* Travis Updates and self-publishing

----
## v3.0.0

* Ugprade to ColdBox 4 standards
* Upgrade to latest Amazon S3 SDK standards
* Travis build process

----
## v2.0

* Original Spec as a ColdBox Plugin