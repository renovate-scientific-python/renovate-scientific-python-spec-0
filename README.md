# [Renovate][renovate] configuration for [Scientific Python SPEC 0 - Minimum Supported Dependencies][spec-0]

## Usage

```json
{
  "extends": [
    "github>34j/renovate-scientific-python-spec-0"
  ]
}
```

## Details

From [SPEC 0 - Minimum Supported Dependencies][spec-0]:

> 1. Support for Python versions be dropped 3 years after their initial release.
> 2. Support for core package dependencies be dropped 2 years after their initial release.
>
> ```python
> core_packages = [
>     "numpy",
>     "scipy",
>     "matplotlib",
>     "pandas",
>     "scikit-image",
>     "networkx",
>     "scikit-learn",
>     "xarray",
>     "ipython",
>     "zarr",
> ]
> ```

- As Renovate does not support "narrowing" lower bounds, 2 or 3 years of [`minimumReleaseAge`][minimumReleaseAge] is used to slow down [`rangeStrategy: bump`][rangeStrategy] updates, instead of using [`rangeStrategy: widen`][rangeStrategy].
  - This should not affect `lockFileMaintenance` updates, since from the [Renovate documentation][minimumReleaseAge]:
    > The lockFileMaintenance update type does not provide release timestamps, as the package manager performs the required changes to update package(s).

- [`matchCurrentAge`](https://docs.renovatebot.com/configuration-options/#matchcurrentage) only takes into account the age of the **current** version, so it cannot be used here.
- [`separateMultipleMinor`][separateMultipleMinor] is used to separate updates for different minor versions for Python.

[renovate]: https://github.com/renovatebot/renovate
[spec-0]: https://scientific-python.org/specs/spec-0000/
[minimumReleaseAge]: https://docs.renovatebot.com/key-concepts/minimum-release-age/
[rangeStrategy]: https://docs.renovatebot.com/configuration-options/#rangestrategy
[separateMultipleMinor]: https://docs.renovatebot.com/configuration-options/#separatemultipleminor
