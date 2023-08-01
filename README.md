# ``ansys-api-modelcenter`` gRPC Interface Package.

This repository provides the auto-generated gRPC Python interface files for the Ansys ModelCenter.

## Installation

Provided that these wheels have been published to public PyPI, they can be
installed with:

```
pip install ansys-api-modelcenter
```

## Build

To build the gRPC packages, run:

```
pip install build
python -m build
```

This will create both the source distribution containing just the protofiles
along with the wheel containing the protofiles and build Python interface
files.

## Manual Deployment

After building the packages, manually deploy them with:

```
pip install twine
twine upload dist/*
```

Note that this is automatically done through CI/CD.

## Automatic Deployment

This repository contains GitHub CI/CD that enables the automatic building of
source and wheel packages for these gRPC Python interface files. By default,
these are built on PRs, the main branch, and on tags when pushing. Artifacts
are uploaded for each PR.

To publicly release wheels to PyPI, ensure your branch is up-to-date and then
push tags.

```bash
git checkout release/{new_version}
git merge main
--> Bump the version
git push origin
git tag v{new_version}
git push origin v{{new_version}
```