# Installing McXtrace 3.0 from preconfigured source code

* Download and build the McXtrace source code for Unix systems:
```bash
wget http://downloads.mcxtrace.org/mcxtrace-3.0/unix/mcxtrace-3.0-UNIX-src.tar.gz
(or curl -O or fetch or...)
```
* Unpack the "metapackage" tarball
```bash
tar xzf mcxtrace-3.0-UNIX-src.tar.gz
cd mcxtrace-3.0-UNIX-src/
```
* Unpack the individual subpackages
```bash
find . -name \*tar.gz -exec tar xzf \{\} \;
```
* Next, compile the individual packages you want (minimum set is mcxtrace-3.0-src mcxtrace-comps-3.0-src) using e.g.
```bash
cd mcxtrace-3.0-src
cmake -DCMAKE_TOOLCHAIN_FILE=cmake/toolchains/freebsd64.cmake -Denable_mcxtrace=1
make
sudo make install
```

You will of course have to install needed dependencies along the way, we suggest having a look at BUILD_DEPENDENCIES.TXT and the getdeps_ scripts from the top of the repo for inspiration.

Also, we provide experimental deployment scripts for [FreeBSD 12](fetch_install_mcxtrace-3.0-freebsd-12.sh) and [TrueOS 18.6](fetch_install_mcxtrace-3.0-trueos-18.6.sh)
