# pytest-order Release Notes

## Unreleased

## [Version 0.9.2](https://pypi.org/project/pytest-order/0.9.2/) (2020-11-13)
Friday the 13th release.

### Changes
- changed definition of classes in before/after markers (now uses `::` as
  delimiter)

### Fixes
- fixed handling of before/after markers in different classes and modules 
- fixed handling of names in dependencies - did not match the actual
  behavior of `pytest-dependency`

## [Version 0.9.1](https://pypi.org/project/pytest-order/0.9.1/) (2020-11-11)
This is a bugfix only release.

### Fixes
- fixed handling of relative markers in classes
- fixed handling of dependencies (could have been added twice) 

## [Version 0.9.0](https://pypi.org/project/pytest-order/0.9.0/) (2020-11-08)
This is the last major version that will support Python 2 - Python 2 support
will be dropped in version 1.0. There is no timeline for that release, as there
are currently no new features planned - further development will be
demand-driven.

### Changes
- removed support for pytest 3.6 (it still may work, just isn't tested anymore)

### Added
- added configuration option for sparse sorting, e.g. the possibility to
  fill gaps between ordinals with unordered tests (see also 
  [this issue](https://github.com/ftobia/pytest-ordering/issues/14) in
  `pytest-ordering`) 
- ignore ordering if it would break a dependency defined by the
  `pytest-dependency` plugin
- experimental: added configuration option for ordering all dependencies
  defined by the `pytest-dependency` plugin
- added ``index`` keyword for ordering as alternative to raw number

### Fixed
- correctly handle combined index and dependency attributes
  
### Infrastructure
- added list of open issues in `pytest-ordering` with respective state
  in `pytest-order` 
 
## [Version 0.8.1](https://pypi.org/project/pytest-order/0.8.1/) (2020-11-02)

### Added
- added configuration option for sorting scope,
  see [#2](https://github.com/mrbean-bremen/pytest-order/issues/2)

## [Version 0.8.0](https://pypi.org/project/pytest-order/0.8.0/) (2020-10-30)
This release is mostly related to the consolidation of infrastructure
(documentation build and tests in CI build) and documentation.  

### Fixes
- fixed the handling of unknown marker attributes (test had been skipped)

### Infrastructure
- added automatic documentation build on change 
- added Python 3.9, pypy3 and pytest 6.0 and 6.1 to CI builds
- use GitHub Actions for CI builds to speed them up, added Windows CI builds
- added regression test for ``pytest-xdist`` 
  (imported from [PR #52](https://github.com/ftobia/pytest-ordering/pull/52))

## [Version 0.7.1](https://pypi.org/project/pytest-order/0.7.1/) (2020-10-24)
Update after renaming the repository and the package.

### Changes
- renamed repository and package from ``pytest-ordering2`` to ``pytest-order``
- changed the used marker from ``run`` to ``order``, removed all additional
  markers (see [#38](https://github.com/ftobia/pytest-ordering/issues/38))
  
### Documentation
- use separate documentation pages for release and development versions

## [Version 0.7.0](https://pypi.org/project/pytest-ordering2/0.7.0/) (2020-10-22)
Imported version from [pytest-ordering](https://github.com/ftobia/pytest-ordering), 
including some PRs (manually merged).

### Added
- added support for markers like run(before=...), run(after=),
  run("first") etc.
  (imported from [PR #37](https://github.com/ftobia/pytest-ordering/pull/37))
- added ``--indulgent-ordering`` to request that the sort from
  pytest-ordering be run before other plugins.  This allows the built-in
  ``--failed-first`` implementation to override the ordering.
  (imported from [PR #50](https://github.com/ftobia/pytest-ordering/pull/50))
- include LICENSE file in distribution
  (imported from [PR #68](https://github.com/ftobia/pytest-ordering/pull/68))

### Infrastructure
- added more pytest versions, fix pytest-cov compatibility issue,
  remove Python 3.4, add Python 3.8
  (imported from [PR #74](https://github.com/ftobia/pytest-ordering/pull/74))
- moved documentation to [GitHub Pages](https://mrbean-bremen.github.io/pytest-order/)
