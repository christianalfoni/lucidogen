# Lucidogen

[![Build status][travis-image]][travis-url]
[![Commitizen friendly][commitizen-image]][commitizen-url]

[travis-image]: https://img.shields.io/travis/lucidogen/lucidogen.svg?style=flat
[travis-url]: https://travis-ci.org/lucidogen/lucidogen
[commitizen-image]: https://img.shields.io/badge/commitizen-friendly-brightgreen.svg?style=flat
[commitizen-url]: http://commitizen.github.io/cz-cli/

Monorepo for Lucidity app and other open source modules (blocks, dialog, crypt, etc).

## Packages

- [![NPM version][test-repo-image]][test-repo-npm] [@lucidogen/test-repo][test-repo-url]
  (blueprint for other packages)

[test-repo-url]: https://github.com/lucidogen/lucidogen/tree/next/packages/node_modules/@lucidogen/test-repo
[test-repo-image]: https://img.shields.io/npm/v/@lucidogen/test-repo.svg?style=flat
[test-repo-npm]: https://npmjs.org/package/@lucidogen/test-repo

### Release process

Review and merge PRs into `next` branch. To release a production ready version, you need
to add the commits from `next` to `master` with the following (github web interface does not
work as it makes branches diverge):

```sh
$ git checkout next
$ git pull
$ npm install # make sure any new dependencies are installed
$ npm install --no-save nodegit@0.20.3 # needed to test release
￼$ npm run release -- --dry-run # and check release notes
￼$ git checkout master
$ git pull
￼$ git merge --ff-only next
￼$ git push
```
