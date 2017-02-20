# Ansible Service Broker
[![Build Status](https://travis-ci.org/fusor/ansible-service-broker.svg?branch=master)](https://travis-ci.org/fusor/ansible-service-broker)
[![Code Climate](https://codeclimate.com/github/fusor/ansible-service-broker/badges/gpa.svg)](https://codeclimate.com/github/fusor/ansible-service-broker)
[![Issue Count](https://codeclimate.com/github/fusor/ansible-service-broker/badges/issue_count.svg)](https://codeclimate.com/github/fusor/ansible-service-broker)

An [Open Service Broker](https://github.com/openservicebrokerapi/servicebroker) implementation.

## Prerequisites

[glide](https://glide.sh/) is used for dependency management. Binaries are available on the
[releases page](https://github.com/Masterminds/glide/releases).

**Packages**

Our dependencies currently require development headers for btrfs and dev-mapper.

CentOS/RHEL/Fedora (sub dnf for Fedora):

`sudo yum install device-mapper-devel btrfs-progs-devel`

## Setup

```
mkdir -p $GOPATH/src/github.com/fusor
git clone https://github.com/fusor/ansible-service-broker.git $GOPATH/src/github.com/fusor/ansible-service-broker`
cd $GOPATH/src/github.com/fusor/ansible-service-broker && glide install
```

## Targets

- `make run`: Runs the broker with the default profile, configured via `/etc/dev.config.yaml`
- `make run-mock-registry`: Mock registry. Entirely separate binary.
- `make test`: Runs the test suite.

**Note**

Scripts found in `/test` can act as manual Service Catalog requests until a larger
user scenario can be scripted.
