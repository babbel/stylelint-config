# Changelog

## 1.0.6

- Publish package using OIDC trust

## 1.0.5

- Add `write` permission to the GitHub Actions publish workflow to be able to create releases

## 1.0.4

- Change how NPM user access token is being added into our GitHub Actions workflow environment
- Upgrade dependencies to latest versions

## 1.0.3

- Fix improper GitHub Actions workflow variable: `vars.NPM_USER_ACCESS_TOKEN_SECRET_ARN` -> `vars.NPM_USER_ACCESS_TOKEN`

## 1.0.2

- Fix missing OIDC write permission in GitHub Actions publish workflow. This prevents proper package publishing.
- Upgrade Bun package manager version from `1.1.34` to `1.1.37`
- Upgrade dependencies to latest versions

## 1.0.1

- Fix publish by fetching NPM user access token from AWS secrets manager
- Enable `check:package-version` script execution during CI to enforce version bumps for every pull request
- Add missing MIT license file to repository
- Add [`MAINTAINERS.md`](./MAINTAINERS.md)

## 1.0.0

- First public release
