tripleo-dev
===========

description
-----------
a development environment for tripleo.

prerequisites
-------------
- you are on a bare-metal machine, running ubuntu quantal
- you have an ssh keypair configured whose public key exists in `~/.ssh/authorized_keys`
- you have cloned this repo: `git clone git@github.com:echohead/tripleo-dev.git`
- password-less sudo will make things way easier

running it
----------

Install a new tripleo environment from scratch:
```bash
# installs baremetal devstack on a vm
# and starts $num_bm_nodes vms
./bin/from_scratch
```

(TODO) Reset the baremetal vms, and 're-stack', preserving the bootstrap vm:
```bash
./bin/re-stack
```

