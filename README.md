# HTTP Probe

<!-- markdownlint-disable-next-line MD033 -->
<img src="logo.png" alt="Logo" width="64" height="64" />

[![CI](https://github.com/cloudfra/httpprobe/actions/workflows/deploy.yaml/badge.svg)](https://github.com/cloudfra/httpprobe/actions/workflows/deploy.yaml) [![Go Reference](https://pkg.go.dev/badge/github.com/cloudfra/httpprobe.svg)](https://pkg.go.dev/github.com/cloudfra/httpprobe) [![codecov](https://codecov.io/gh/cloudfra/httpprobe/graph/badge.svg?token=UVApxhg6z7)](https://codecov.io/gh/cloudfra/httpprobe)


Simple HTTP/HTTPS health probe tool for Docker and Kubernetes health checks.

```bash
# Download (linux amd64, see Downloads for other builds)
curl -o httpprobe -O -L https://github.com/cloudfra/httpprobe/releases/download/v0.1.0/httpprobe-amd64; chmod +x httpprobe

# Host the current directory.
./httpprobe
```

## Features

* Zero-config required, hosts on port 80 or 8080 based on root and supports Cloud9's $PORT variable.
* HTTP and HTTPs serving
* Automatic HTTPs certificate generation
* Optional configuration by flags or YAML config file.
* Host local or HTTP served static files from:
  * Local directory (current directory is default)
  * ZIP archive
  * Tarball archive (.tar, .tar.bz2, .tar.gz, .tar.lz4, .tar.xz)
  * 7-zip
  * RAR
  * Git repository (HTTPS, SSH)
* Metrics export to Prometheus.
* Prebuild binaries for all major OSes.

## Downloads

|   OS   | Arch  | Link
|--------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------
|Linux   | amd64 | `curl -O -L https://github.com/cloudfra/httpprobe/releases/download/v0.1.0/httpprobe-amd64`
|Linux   | arm   | `curl -O -L https://github.com/cloudfra/httpprobe/releases/download/v0.1.0/httpprobe-arm`
|Linux   | arm64 | `curl -O -L https://github.com/cloudfra/httpprobe/releases/download/v0.1.0/httpprobe-arm64`
|Windows | amd64 | `$ProgressPreference = 'SilentlyContinue'; Invoke-WebRequest -Uri "https://github.com/cloudfra/httpprobe/releases/download/v0.1.0/httpprobe-amd64.exe" -OutFile "httpprobe-amd64.exe" -UseBasicParsing`
|macOS   | amd64 | `curl -O -L https://github.com/cloudfra/httpprobe/releases/download/v0.1.0/httpprobe-amd64-darwin`
|macOS   | arm64 | `curl -O -L https://github.com/cloudfra/httpprobe/releases/download/v0.1.0/httpprobe-arm64-darwin`

## Docker Images

* [httpprobe](https://hub.docker.com/r/cloudfra/httpprobe/tags)

```bash
docker pull docker.io/cloudfra/httpprobe
```

## Build

![example workflow](https://github.com/cloudfra/httpprobe/actions/workflows/deploy.yml/badge.svg) [![Go Report Card](https://goreportcard.com/badge/github.com/cloudfra/httpprobe)](https://goreportcard.com/report/github.com/cloudfra/httpprobe) [![Go Reference](https://pkg.go.dev/badge/github.com/cloudfra/httpprobe.svg)](https://pkg.go.dev/github.com/cloudfra/httpprobe) [![codecov](https://codecov.io/gh/cloudfra/httpprobe/branch/main/graph/badge.svg)](https://codecov.io/gh/cloudfra/httpprobe)

Install [Go 1.24 or newer](https://golang.org/dl/).

```bash
# Clone the Codebase
git clone git@github.com:cloudfra/httpprobe.git
# Build the Code
make -j$(nproc)
```

## Test

```bash
make test
make bench
```
