# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

### Removed

### Changed

### Fixed

### Deprecated

### Developer

## [v0.5.5]

### Added

- Add missing dependency urllib3 to setup.py. ([181](https://github.com/radiantearth/radiant-mlhub/pull/181))
- Add a unit test to confirm asset save paths are getting formatted correctly with expected file extensions. ([186](https://github.com/radiantearth/radiant-mlhub/pull/186))

### Changed

- Performance improvements to Dataset.download() ([182](https://github.com/radiantearth/radiant-mlhub/pull/182))
- Enable INFO level logging by default in Dataset.download() ([182](https://github.com/radiantearth/radiant-mlhub/pull/182))

### Fixed

- Fix regression bug from PR #182. ([186](https://github.com/radiantearth/radiant-mlhub/pull/186))

### Developer

- Add flake8-logging-format package ([182](https://github.com/radiantearth/radiant-mlhub/pull/182))

## [v0.5.4]

Unreleased version.

## [v0.5.3]

### Added

- Added an optional asset_output_dir parameter so that the assets can be downloaded into a separate directory from the STAC Catalog if the user specifies and selects a separate asset output directory. ([149](https://github.com/radiantearth/radiant-mlhub/pull/149))

- Add datetime filter test to account for datasets that have start_datetime and end_datetime properties. ([165](https://github.com/radiantearth/radiant-mlhub/pull/165))

### Changed

- Update ADR and CONTRIBUTING docs ([164](https://github.com/radiantearth/radiant-mlhub/pull/164))

### Fixed

- Fix datetime comparisons in dataset downloader. ([162](https://github.com/radiantearth/radiant-mlhub/pull/162))

## [v0.5.2]

### Fixed

- Fix bugs in readthedocs. ([145](https://github.com/radiantearth/radiant-mlhub/pull/145))
- Fix use of tilde in setup.py document ([151](https://github.com/radiantearth/radiant-mlhub/pull/151))

## [v0.5.1]

### Changed

- Improve http requests retry strategy. ([115](https://github.com/radiantearth/radiant-mlhub/pull/115))
- Optimizing performance of Dataset.download() ([115](https://github.com/radiantearth/radiant-mlhub/pull/115))

## [v0.5.0]

### Added

- Add `Dataset.stac_catalog_size`, and `estimated_dataset_size` properties. ([#104](https://github.com/radiantearth/radiant-mlhub/pull/104))
- Add descriptive `__str__`  methods to model classes. ([#104](https://github.com/radiantearth/radiant-mlhub/pull/104))

### Removed

- Remove Python 3.7 support. ([#106](https://github.com/radiantearth/radiant-mlhub/pull/106))
- Remove `Dataset.total_archive_size` property, because of Dataset.download changes. ([#104](https://github.com/radiantearth/radiant-mlhub/pull/104))

### Changed

- Rewrite `Dataset.download()` plus more robust downloading and filtering options. ([#104](https://github.com/radiantearth/radiant-mlhub/pull/104))

### Fixed

- Remove outdated jupyter notebooks from the `examples/` folder. ([#104](https://github.com/radiantearth/radiant-mlhub/pull/104))

### Developer

- Remove `tox` from development environment. ([#104](https://github.com/radiantearth/radiant-mlhub/pull/104))
- Add Python 3.10 on Windows to CI test matrix. ([#104](https://github.com/radiantearth/radiant-mlhub/pull/104))

## [v0.4.1]

### Fixed

- Fix installation error by missing dependency: typing_extensions. ([#79](https://github.com/radiantearth/radiant-mlhub/pull/79))

### Developer

- Check for missing dependencies in CI job. ([#79](https://github.com/radiantearth/radiant-mlhub/pull/79))
- Allow ReadTheDocs builds to succeed if warnings are emitted ([#80](https://github.com/radiantearth/radiant-mlhub/pull/80))
- Update trove classifiers to include Python 3.10 and bump dev status to "Beta" ([#81](https://github.com/radiantearth/radiant-mlhub/pull/81))

## [v0.4.0]

### Added

- `client.list_models` and `client.get_model_by_id` to discover ML Models by ID or by listing. ([#71](https://github.com/radiantearth/radiant-mlhub/pull/71))
- `MLModel.list` and `MLModel.fetch` methods analogous to new client methods described
  above. ([#71](https://github.com/radiantearth/radiant-mlhub/pull/71))

### Developer

- Refactor of client and model python modules. ([#71](https://github.com/radiantearth/radiant-mlhub/pull/71))
- Configure Dependabot for automatic version upgrades of dev dependencies ([#74](https://github.com/radiantearth/radiant-mlhub/pull/74))
- Lock dev dependencies. ([#75](https://github.com/radiantearth/radiant-mlhub/pull/75))
- Remove Python 3.6 from `tox` config and add Python 3.10 ([#73](https://github.com/radiantearth/radiant-mlhub/pull/73))

## [v0.3.1]

### Fixed

- Use `HEAD` request instead of `GET` when initiating download ([#68](https://github.com/radiantearth/radiant-mlhub/pull/68))

## [v0.3.0]

### Added

- `tags` and `text` arguments to `Dataset.list` and `client.list_datasets` methods to allow
  filtering by datasets tags or free text search, respectively ([#60](https://github.com/radiantearth/radiant-mlhub/pull/60))
- `client.get_dataset_by_id` and `client.get_dataset_by_doi` methods to look up datasets by ID or
  DOI, respectively ([#58](https://github.com/radiantearth/radiant-mlhub/pull/58))
- `Dataset.fetch_by_id` and `Dataset.fetch_by_doi` methods analogous to new client methods described
  above ([#58](https://github.com/radiantearth/radiant-mlhub/pull/58))
- `py.typed` file included in package ([#62](https://github.com/radiantearth/radiant-mlhub/pull/62))

### Changed

- `client.get_dataset` first attempts to get dataset using `get_dataset_by_id` then falls back to
  using `get_dataset_by_doi` if unsuccessful
  ([#58](https://github.com/radiantearth/radiant-mlhub/pull/58))
- `Dataset.fetch` uses `client.get_dataset` to first attempt getting dataset by ID, then falling
  back to fetching by DOI if unsuccessful
  ([#58](https://github.com/radiantearth/radiant-mlhub/pull/58))
- Upgraded PySTAC dependency to `~=1.1..0` ([#63](https://github.com/radiantearth/radiant-mlhub/pull/63))

### Removed

- Support for Python 3.6 ([#61](https://github.com/radiantearth/radiant-mlhub/pull/58))

### Fixed

- Numerous type annotation issues ([#62](https://github.com/radiantearth/radiant-mlhub/pull/58))

### Deprecated

### Developer

- Set different API root URL using `MLHUB_ROOT_URL` environment variable ([#56](https://github.com/radiantearth/radiant-mlhub/pull/56))

## [v0.2.2]

### Fixed

- Documentation example in Authentication docs ([#53](https://github.com/radiantearth/radiant-mlhub/pull/53))

### Developer

- Moving to [One Flow](https://www.endoflineblog.com/oneflow-a-git-branching-model-and-workflow)
  branching strategy instead of Git Flow for simplicity
  ([#49](https://github.com/radiantearth/radiant-mlhub/issues/49))

## [v0.2.1]

### Fixed

* `api_key` argument from `Dataset.fetch` used by `Dataset` instance for downstream requests
  ([#48](https://github.com/radiantearth/radiant-mlhub/pull/48))
* `Dataset.download` errors when `api_key` argument is passed ([#48](https://github.com/radiantearth/radiant-mlhub/pull/48))

## [v0.2.0]

### Changed

* Pins PySTAC to v0.5.4 ([#43](https://github.com/radiantearth/radiant-mlhub/pull/43))

   Later versions automatically resolve links, which was leading to unnecessary network requests and
   issues with matching in VCR.py

### Fixed

* Allow user-defined `profiles` location ([#27](https://github.com/radiantearth/radiant-mlhub/issues/27))
* License file is now included in the distribution ([#37](https://github.com/radiantearth/radiant-mlhub/issues/37))

### Added

* Properties to get archive sizes without downloading (`Collection.archive_size` and
  `Dataset.total_archive_size`) ([#44](https://github.com/radiantearth/radiant-mlhub/pull/40))
* New attributes on `Dataset` class (`doi`, `citation`, and `registry_url`) ([#40](https://github.com/radiantearth/radiant-mlhub/pull/40))
* `Collection.registry_url` property to get the URL for the Collection's registry page ([#39](https://github.com/radiantearth/radiant-mlhub/pull/39))
* Available as `conda` package via `conda-forge` ([#34](https://github.com/radiantearth/radiant-mlhub/issues/29))

    ```console
    $ conda install -c conda-forge radiant-mlhub
    ```

### Developer

* Switch to using [pytest-recording](https://pypi.org/project/pytest-recording/) ([VCR.py] under the
  hood) for mocking API responses ([#43](https://github.com/radiantearth/radiant-mlhub/pull/43))

## [v0.1.3]

### Fixed

* New attributes in the `/dataset` response will no longer break the `Dataset` class
  ([#42](https://github.com/radiantearth/radiant-mlhub/pull/42))

## [v0.1.2]

### Fixed

* Implicit dependency on `typing_extensions` ([#29](https://github.com/radiantearth/radiant-mlhub/issues/29))

### Developer

* Manually caches properties instead of using `functools.cached_property`/`backports.cached_property`

## [v0.1.1]

### Added

* Ability to resume archive downloads([#24](https://github.com/radiantearth/radiant-mlhub/issues/24))
* Automatically retry requests that fail due to connection issues ([#24](https://github.com/radiantearth/radiant-mlhub/issues/24))

## [v0.1.0]

First working `alpha` release of the Radiant MLHub Python client. 

Includes support for:

* Configuring authentication using profiles or environment variables
* Listing datasets and collections
* Fetching datasets and collections by ID
* Downloading collection archives

[Unreleased]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.5.5...main>
[v0.5.5]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.5.3...v0.5.5>
[v0.5.3]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.5.2...v0.5.3>
[v0.5.2]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.5.1...v0.5.2>
[v0.5.1]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.5.0...v0.5.1>
[v0.5.0]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.4.1...v0.5.0>
[v0.4.1]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.4.0...v0.4.1>
[v0.4.0]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.3.1...v0.4.0>
[v0.3.1]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.3.0...v0.3.1>
[v0.3.0]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.2.2...v0.3.0>
[v0.2.2]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.2.1...v0.2.2>
[v0.2.1]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.2.0...v0.2.1>
[v0.2.0]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.1.3...v0.2.0>
[v0.1.3]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.1.2...v0.1.3>
[v0.1.2]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.1.1...v0.1.2>
[v0.1.1]: <https://github.com/radiantearth/radiant-mlhub/compare/v0.1.0...v0.1.1>
[v0.1.0]: <https://github.com/radiantearth/radiant-mlhub/tree/v0.1.0>

[VCR.py]: https://vcrpy.readthedocs.io/en/latest/usage.html
