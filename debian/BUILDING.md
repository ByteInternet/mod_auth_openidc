# mod_auth_openidc

* [Original project](https://github.com/pingidentity/mod_auth_openidc)
* [Original README](https://github.com/pingidentity/mod_auth_openidc/blob/master/README.md)

## Branch layout

* upstream - copy of `master` branch of the original repo
* debian/wheezy - branch with a debian directory to build a package on wheezy
* patch-queue/debian/wheezy - branch with patches on the original source

## Creating a patch

* [Keeping debian/patches on a patch-queue branch](https://honk.sigxcpu.org/piki/development/debian_packages_in_git/)
* Create a commit on branch patch-queue/debian/wheezy with the changes.
* `gbp pq export`
* Commit the created patches
* `git-dch --debian-branch=debian/wheezy --release --commit`


## Building a package

On branch debian/wheezy:

```
git-buildpackage --git-pbuilder --git-dist=wheezy --git-arch=amd64 --git-debian-branch=debian/wheezy --git-tag
```


