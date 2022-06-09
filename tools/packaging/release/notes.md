# Release 2.5.0-alpha2

## kata-containers Changes
### Shortlog
eb24e9715 release: Kata Containers 2.5.0-alpha2
d2df1209a docs: describe kata handling for core-scheduling
22b6a94a8 shim: add support for core scheduling
fe3c1d9cd docs: Update storage documentation link
6ecea84bc rustjail: get home dir using nix crate
38a318820 runk: Support `list` sub-command
6d0ff901a docs: Update vGPU use-case
9d27c1fce agent: ignore ESRCH error when destroying containers
9726f56fd runtime: force stop container after the container process exits
168f325c4 docs: Update configuration reference for snap documentation
b9fc24ff3 docs: update release process github token instructions
c1476a174 docs: update release process with latest workflow triggering
8b57bf97a workflows: add workflow_dispatch triggering to test-kata-deploy
002f2cd10 snap: Use helper script and cleanup
9b108d993 docs: Improve snap formatting
894f661cc docs: Add warning to snap build
d759f6c3e snap: Fix CH architecture check
56591804b docs: Improve snap build instructions
cb2b30970 snap: Build using destructive mode
60823abb9 docs: Move snap README
af2ef3f7a agent-ctl: introduce handle for iptables get/set
65f0cef16 kata-runtime: add iptables CLI to test http endpoint
3201ad083 shim-client: ensure we check resp status for Put/Post
0706fb28a kata-runtime: shmgmt: make url usage consistent
2a09378dd shim-client: add support for DoPut
640173cfc shim-mgmt: Add endpoint handler for interacting with iptables
0136be22c virtcontainers: plumb iptable set/get from sandbox to agent
bd50d463b agent: iptables: get/set handling for iptables
03176a9e0 proto: update generated code based on proto update
38ebbc705 proto: update to add set/get iptables
78d45b434 agent: return mount file content if parse mountinfo failed
2e04833fb docs: Update Intel QAT documentation links
7c4049aab osbuilder: add iptables package
648b8d0ae runk: Return error when tty is used without console socket
5205efd9b runk: Add Podman guide in README
590381574 agent: Pass standard I/O to container launched by runk
c7b3941c9 runk: Enable test for the agent built with standard-oci-runtime feature
6dbce7c3d agent: Remove unused import in console test
d862ca059 runk: Handle rootfs path in config.json properly
c95ba63c0 docs: Remove information related to Kata 1.x
34b80382b docs: Get rid of note related to networking.
dfad5728a docs: Mention --cni flag while invoking ctr
fff832874 clh: Update to v24.0
49361749e snap: Build and package rust version of virtiofsd
27d903b76 snap: Put the yq binary in the staging bin directory
d7b4ce049 snap: Remove unused variable
43de5440e snap: Fix unbound variable error
c9b291509 snap: Fix whitespace
122a85e22 agent: remove bin oci-kata-agent
35619b45a runk: merge oci-kata-agent into runk
10c13d719 qemu: remove virtiofsd option in qemu config
d20bc5a4d virtiofsd: build rust based virtiofsd from source for non-x86_64
8e7c5975c agent: fix direct-assigned volume stats
4428ceae1 runtime: direct-volume stats use correct name
ffdc065b4 runtime: direct-volume stats update to use GET parameter
f29595318 runtime: fix incorrect Action function for direct-volume stats
2a1d39414 runtime: Adding the correct detection of mediated PCIe devices
ce2e521a0 runtime: remove duplicate 'types' import
7a5ccd126 runtime: sync docstrings with function names
834f93ce8 docs: fix annotations example
f4994e486 runtime: allow annotation configuration to use_legacy_serial
c67b9d297 qemu: allow using legacy serial device for the console
44814dce1 qemu: treat console kernel params within appendConsole
24a2b0f6a docs: Remove clear containers reference in README
8052fe62f runtime: do not check for EOF error in console watcher
abad33eba kernel: Remove nemu.conf from packaging
e87eb13c4 tools: delete unused param from get_from_kata_deps callers
4b437d91f agent: Fix is_signal_handled failing parsing str to u64
e73b70baf runtime: Don't run unit tests verbose by default
f24a6e761 runtime: Consolidate flags setting in unit tests script
cf465feb0 runtime: Don't change test behaviour based on $CI or $KATA_DEV_MODE
34c4ac599 runtime: Remove redundant subcommands from go-test.sh
0aff5aaa3 runtime: Simplify package listing in go-test.sh
557c4cfd0 runtime: Don't chmod coverage files in Go tests
04c8b52e0 runtime: Remove HTML coverage option from go-test.sh
7f7691442 runtime: Add coverage.txt.tmp to gitignore
13c257700 runtime: Move go testing script locally
4f586d2a9 packaging: Add kernel config option for SGX in Gramine
7bc4ab68c ci: Don't run Docs URL Alive Check workflow on forks
b4b9068cb tools: Add QEMU patches for SGX numa support
88fb9b72e docs: Update runc containerd runtime
a475956ab workflows: Add support for building virtiofsd
71f59f3a7 local-build: Add support for building virtiofsd
c7ac55b6d dockerbuild: Install unzip
8e2042d05 tools: add script to pull virtiofsd
dbedea508 versions: Add virtiofsd entry
421064680 doc: Update log parser link
271933fec log-parser: fix some of the documentation
c7dacb121 log-parser: move the kata-log-parser from the tests repo
82ea01828 versions: Upgrade to Cloud Hypervisor v23.1
383be2203 agent: Add a macro to skip a loop easier
97d7b1845 runk: use custom Kill command to support --all option
475e3bf38 agent: add test coverage for functions find_process and online_resources


## Compatibility with CRI-O
Kata Containers 2.5.0-alpha2 is compatible with CRI-O 

## Compatibility with containerd
Kata Containers 2.5.0-alpha2 is compatible with contaienrd v1.5.2

## OCI Runtime Specification
Kata Containers 2.5.0-alpha2 support the OCI Runtime Specification [v1.0.0-rc5][ocispec]

## Compatibility with Kubernetes
Kata Containers 2.5.0-alpha2 is compatible with Kubernetes 1.23.1-00

## Libseccomp Notices
The `kata-agent` binaries inside the Kata Containers images provided with this release are
statically linked with the following [GNU LGPL-2.1][lgpl-2.1] licensed libseccomp library.

* [`libseccomp`][libseccomp]

The `kata-agent` uses the libseccomp v2.5.1 which is not modified from the upstream version.
However, in order to comply with the LGPL-2.1 (§6(a)), we attach the complete source code for the library.

If you want to use the `kata-agent` which is not statically linked with the library, you can build
a custom `kata-agent` that does not use the library from sources.
For the details, please check the [developer guide][custom-agent-doc].

## Kata Linux Containers image
Agent version: 2.5.0-alpha2

### Default Image Guest OS:
description: |
  Root filesystem disk image used to boot the guest virtual
  machine.
url: "https://github.com/kata-containers/kata-containers/tools/osbuilder"
architecture:
  aarch64:
    name: "ubuntu"
    version: "latest"
  ppc64le:
    name: "ubuntu"
    version: "latest"
  s390x:
    name: "ubuntu"
    version: "latest"
  x86_64:
    name: "clearlinux"
    version: "latest"
meta:
  image-type: "clearlinux"

### Default Initrd Guest OS:
description: |
  Root filesystem initrd used to boot the guest virtual
  machine.
url: "https://github.com/kata-containers/kata-containers/tools/osbuilder"
architecture:
  aarch64:
    name: "alpine"
    version: "3.15"
  ppc64le:
    name: "ubuntu"
    version: "20.04"
  s390x:
    name: "ubuntu"
    version: "20.04"
  x86_64:
    name: "alpine"
    version: "3.15"

## Kata Linux Containers Kernel
Kata Containers 2.5.0-alpha2 suggest to use the Linux kernel [v5.15.26][kernel]
See the kernel suggested [Guest Kernel patches][kernel-patches]
See the kernel suggested [Guest Kernel config][kernel-config]

## Installation

Follow the Kata [installation instructions][installation].

## Issues & limitations

More information [Limitations][limitations]

[kernel]: https://cdn.kernel.org/pub/linux/kernel/v5.x//linux-5.15.26.tar.xz
[kernel-patches]: https://github.com/kata-containers/kata-containers/tree/2.5.0-alpha2/tools/packaging/kernel/patches
[kernel-config]: https://github.com/kata-containers/kata-containers/tree/2.5.0-alpha2/tools/packaging/kernel/configs
[ocispec]: https://github.com/opencontainers/runtime-spec/releases/tag/v1.0.0-rc5
[libseccomp]: https://github.com/seccomp/libseccomp
[lgpl-2.1]: https://www.gnu.org/licenses/old-licenses/lgpl-2.1.html
[custom-agent-doc]: https://github.com/kata-containers/kata-containers/blob/main/docs/Developer-Guide.md#build-a-custom-kata-agent---optional
[limitations]: https://github.com/kata-containers/kata-containers/blob/2.5.0-alpha2/docs/Limitations.md
[installation]: https://github.com/kata-containers/kata-containers/blob/2.5.0-alpha2/docs/install
