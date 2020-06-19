# GITHUB CURL ACTION

[![Travis][travis-image]][travis-url]
![License][license-image]
![Issues][issues-image]

## USAGE

This action accepts all types of cURL arguments, allows to execute from a simple cURL to a URL to a more complex one with user and parameters

### Docker

```bash
docker run enflo/curl-action {{ CURL ARGUMENTS }}
```

### GitHub Actions

#### Inputs

##### `curl`

**Required** cURL Parameters. Default `"toniflorithomar.cat"`.

#### Example usage

```bash
name: CURL CLI ACTION
on: push
jobs:
  curl:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - name: curl
      id: curl
      uses: enflo/curl-action@master
      with:
        curl: {{ CURL ARGUMENTS }}
    - name: use curl output
      run: cat ${{steps.curl.outputs.response}}
```

[travis-image]: https://travis-ci.com/enflo/curla-action.svg?branch=master
[travis-url]: https://travis-ci.com/enflo/curla-action
[license-image]: https://img.shields.io/static/v1?label=licence&message=MIT&color=Green
[issues-image]: https://img.shields.io/github/issues/enflo/curl-action