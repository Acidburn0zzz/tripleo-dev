tripleo-dev
===========

description
-----------
automated development setup for tripleo.

prerequisites
-------------
- you are on a bare-metal machine, running ubuntu quantal
- you have an ssh keypair configured whose public key exists in `~/.ssh/authorized_keys`
- you have cloned this repo: `git clone git@github.com:echohead/tripleo-dev.git`
- password-less sudo will make things way easier

usage
-----

**first, edit required settings in ./localrc**

Install a new tripleo environment from scratch:
```bash
./bin/from_scratch
```

Reset the baremetal vms, and 're-stack', __preserving the bootstrap vm__:
this will also deploy heat stack 'all-components':
```bash
./bin/re-stack
```

Re-run starting from some point in the middle:
```bash
./bin/run-parts "^[3-9][0-9]"
```

ssh into the bootstrap node:
```
./bin/ssh_bootstrap
```


To re-run parts of the process individually, just run the corresponding part from /parts`:
```bash
$ tree parts
parts
├── 01-dependencies
├── 05-build-bootstrap-image
├── 10-build-demo-image
├── 15-new-bootstrap-node
├── 20-copy-demo-image
├── 25-new-baremetal-vms
├── 30-re-stack
└── 35-populate-bm-db
```
You can safely restart from any point in the process - the scripts are idempotent, provided localrc has not changed.
