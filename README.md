# How to use
1. Clone the source tree [latest release](https://github.com/carlodefalco/mk/releases).
2. Extract the archive just downloaded with:
```bash
sudo tar xzvf mk-version.tar.gz -C /
```
3. Add the following lines to your `.bashrc` file (or equivalent):
```bash
# mk.
export mkPrefix=/opt/mox/mk
source ${mkPrefix}/etc/profile
module load gcc-glibc
module load package_name
```
4. Restart the shell.

Use `module avail` or `module spider` to check the available packages.

## Docker
A `Docker` image built on `Rocky Linux 9`
(`x86-64` architecture) with `mk` installed is available
[here](https://github.com/carlodefalco/mk/releases).

### TODO

Docker has deprecated and removed the `--squash` option.
We should use [multi-stage builds](https://docs.docker.com/build/building/multi-stage/) instead

## How to build from source

This is how the distro was built on `kami`

```
export mkPrefix=</path/to/modules>
cd mk/bootstrap
./bootstrap ${mkPrefix} 
source ${mkPrefix}/etc/profile
cd ../toolchains/gcc-glibc
make mkFlags="-v --jobs=90" install > gcc-glibc.log 
source ${mkPrefix}/etc/profile
module load gcc-glibc
cd ../../base/
make mkFlags="-v --jobs=90" install > base.log 
cd ../pkgs/
make mkFlags="-v --jobs=90" install > pkgs.log 
```
