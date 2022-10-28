## Check if given version is pre-release.

[![semver-badge]][semver] [![cat-config-badge]][cat-config]

Given two versions, [`is_prerelease`] asserts that one is pre-release and the other is not.

```rust,edition2018
use semver::{Version, Error as SemVerError, Prerelease};

fn main() -> Result<(), SemVerError> {
    fn is_prerelease(ver: Version) -> bool {
        if ver.pre == Prerelease::EMPTY {
            false
        } else {
            true
        }
    }

    let version_1 = Version::parse("1.0.0-alpha")?;
    let version_2 = Version::parse("1.0.0")?;

    assert_eq!(is_prerelease(version_1), true);
    assert_eq!(is_prerelease(version_2), false);

    Ok(())
}
```

[`is_prerelease`]: https://docs.rs/semver/*/semver/struct.Version.html#method.is_prerelease
