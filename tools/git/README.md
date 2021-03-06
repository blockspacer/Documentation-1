Git
========================================

build with sources
----------------------------------------

Got reason of the problem, it was gnutls package.
It's working weird behind a proxy. But openssl is
working fine even in weak network. So workaround is
that we should compile git with openssl. To do this, run the following commands:

```
$ sudo apt-get install build-essential fakeroot dpkg-dev
$ mkdir ~/git-openssl
$ cd ~/git-openssl
$ sudo apt-get source git
$ sudo apt-get build-dep git
$ sudo apt-get install libcurl4-openssl-dev
$ dpkg-source -x git_1.7.9.5-1.dsc
$ cd git-1.7.9.5
```

(Remember to replace 1.7.9.5 with the actual version of git in your system.)

Then, edit debian/control file (run the command: gksu gedit debian/control) and
replace all instances of libcurl4-gnutls-dev with libcurl4-openssl-dev.

Then build the package (if it's failing on test, you can remove the line TEST=test from the file debian/rules):

```
$ sudo dpkg-buildpackage -rfakeroot -b
```

Install new package:

```
i386: sudo dpkg -i ../git_1.7.9.5-1_i386.deb
x86_64: sudo dpkg -i ../git_1.7.9.5-1_amd64.deb
```
