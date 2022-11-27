# projectctl-templates

Repository of some [projectctl](https://github.com/leroyguillaume/projectctl) templates.

## Templates description

### rs-lib

Template of Rust library project.

`pre-commit`:
- runs `cargo check` (fails if code does'nt compile)
- runs `cargo fmt` (fails if code is not well formated)
- runs `cargo clippy` (fails on warn)
- checks if commit message matches [Conventional Commit](https://www.conventionalcommits.org/en/v1.0.0/) convention

GitHub Actions workflows:
- on each pull request:
  - checks if commit message matches [Conventional Commit](https://www.conventionalcommits.org/en/v1.0.0/) convention
  - runs `cargo fmt` (fails if code is not well formated)
  - runs `cargo clippy` (fails on warn)
  - runs `cargo test`
- on tag `v*`:
  - publish package on [crates.io](https://crates.io/) (a secret `CARGO_REGISTRY_TOKEN` that contains API token is required)

**Template variables:**
- `repository-url` (optional): URL to the Git repository
