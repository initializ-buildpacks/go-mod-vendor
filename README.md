# Go Mod Vendor Cloud Native Buildpack

The Go Mod Vendor CNB executes the [`go mod vendor`](https://golang.org/cmd/go/#hdr-Modules__module_versions__and_more) command in the app's working directory to create a vendored copy of dependencies.

## Integration

The Go Mod Vendor CNB doesn't provide any dependencies directly. To execute the `go mod vendor` command, the buildpack requires the `go` dependency, which can be supplied by a buildpack like the [Go Distribution CNB](https://github.com/initializ-buildpacks/go-dist).

## Usage

To package this buildpack for distribution:
```
$ ./scripts/package.sh
```
By default, this script packages the buildpack's Go source using GOOS=linux. You can specify another value as the first argument to `package.sh`.

## `buildpack.yml` Configuration

The Go Mod Vendor buildpack doesn't support configurations via `buildpack.yml`.

## Go Version

This buildpack will request the latest minor version of the `major.minor` version it finds in the `go.mod` file from the `go-dist` buildpack.

