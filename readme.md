# Overview
- only tagged releases can trigger builds
    - this way we are able to quickly revert by specifying a previous release

# Versioning
- use npm version [major|minor|patch|premajor|preminor|prepatch|prerelease [--preid=[alpha|beta|rc]]]
    - a typical release flow would be
        1. npm version prerelease --preid=alpha (early user testing in staging)
        2. npm version prerelease --preid=beta (final user testing in staging and or incremental rollout prod testing to small user selection)
        3. npm version prerelease --preid=rc (stable branch used for incremental rollout to larger user selection or full test day)
    - each time a prerelease version is bumped the version number will increment
        - EX. npm version prerelease --preid=alpha => (v0.0.1-alpha.0)
        - next npm version prerelease --preid=alpha => (v0.0.1-alpha.1)