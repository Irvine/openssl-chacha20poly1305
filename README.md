# OpenSSL additional feature: Support ChaCha20+Poly1305 cipher suites

For Debian and Ubuntu packages.

## How to make packages

### Debian 7 (wheezy)

```bash
# In some directory
git clone --depth 1 https://github.com/h-yamamo/openssl-chacha20poly1305
apt-get -d source openssl
tar xf openssl_1.0.1e.orig.tar.gz
cd openssl-1.0.1e
tar xf ../openssl_1.0.1e-2+deb7u21.debian.tar.gz
cp -av ../openssl-chacha20poly1305/wheezy/debian/* debian/
debuild -uc -us
```

### Debian 8 (jessie)

```bash
# In some directory
git clone --depth 1 https://github.com/h-yamamo/openssl-chacha20poly1305
apt-get -d source openssl
tar xf openssl_1.0.1t.orig.tar.gz
cd openssl-1.0.1t
tar xf ../openssl_1.0.1t-1+deb8u3.debian.tar.xz
cp -av ../openssl-chacha20poly1305/jessie/debian/* debian/
debuild -uc -us
```

### Debian 8 (jessie-backports)

```bash
# In some directory
git clone --depth 1 https://github.com/h-yamamo/openssl-chacha20poly1305
apt-get -d source openssl
tar xf openssl_1.0.2h.orig.tar.gz
cd openssl-1.0.2h
tar xf ../openssl_1.0.2h-1~bpo8+2.debian.tar.xz
cp -av ../openssl-chacha20poly1305/jessie-backports/debian/* debian/
debuild -uc -us
```

### Ubuntu 12.04 LTS (precise)

```bash
# In some directory
git clone --depth 1 https://github.com/h-yamamo/openssl-chacha20poly1305
apt-get -d source openssl
tar xf openssl_1.0.1.orig.tar.gz
cd openssl-1.0.1
tar xf ../openssl_1.0.1-4ubuntu5.36.debian.tar.gz
cp -av ../openssl-chacha20poly1305/precise/debian/* debian/
debuild -uc -us
```

### Ubuntu 14.04 LTS (trusty)

```bash
# In some directory
git clone --depth 1 https://github.com/h-yamamo/openssl-chacha20poly1305
apt-get -d source openssl
tar xf openssl_1.0.1f.orig.tar.gz
cd openssl-1.0.1f
tar xf ../openssl_1.0.1f-1ubuntu2.19.debian.tar.gz
cp -av ../openssl-chacha20poly1305/trusty/debian/* debian/
debuild -uc -us
```

### Ubuntu 16.04 LTS (xenial)

```bash
# In some directory
git clone --depth 1 https://github.com/h-yamamo/openssl-chacha20poly1305
apt-get -d source openssl
tar xf openssl_1.0.2g.orig.tar.gz
cd openssl-1.0.2g
tar xf ../openssl_1.0.2g-1ubuntu4.3.debian.tar.xz
cp -av ../openssl-chacha20poly1305/xenial/debian/* debian/
debuild -uc -us
```

Since May 11 2016, an **update test-certs patch required** to build
packages in **wheezy**, **precise** and **trusty**.
That certs patch named `Update-S-MIME-certificates.patch` is in the
debian-package-files of jessie.

Get from

`ftp.debian.org/debian/pool/main/o/openssl/openssl_1.0.1t-1+deb8u3.debian.tar.xz`

or some mirror site.

Before you build,
* copy `Update-S-MIME-certificates.patch` to `debian/patches/`
* add `Update-S-MIME-certificates.patch` to `debian/patches/series`
