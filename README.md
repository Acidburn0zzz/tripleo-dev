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

Install a new tripleo environment from scratch:
```bash
./bin/from_scratch
```

(TODO) Reset the baremetal vms, and 're-stack', __preserving the bootstrap vm__:
```bash
./bin/re-stack
```
(TODO) Deploy a heat stack onto baremetal vms:
```bash
./bin/heat-deploy <stack>
```

