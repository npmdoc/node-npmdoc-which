# npmdoc-which

#### api documentation for  [which (v1.2.14)](https://github.com/isaacs/node-which#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-which.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-which) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-which.svg)](https://travis-ci.org/npmdoc/node-npmdoc-which)

#### Like which(1) unix command. Find the first instance of an executable in the PATH.

[![NPM](https://nodei.co/npm/which.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/which)

- [https://npmdoc.github.io/node-npmdoc-which/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-which/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-which/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-which/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-which/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-which/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Isaac Z. Schlueter",
        "url": "http://blog.izs.me"
    },
    "bin": {
        "which": "./bin/which"
    },
    "bugs": {
        "url": "https://github.com/isaacs/node-which/issues"
    },
    "dependencies": {
        "isexe": "^2.0.0"
    },
    "description": "Like which(1) unix command. Find the first instance of an executable in the PATH.",
    "devDependencies": {
        "mkdirp": "^0.5.0",
        "rimraf": "^2.3.3",
        "tap": "^10.3.0"
    },
    "directories": {},
    "dist": {
        "shasum": "9a87c4378f03e827cecaf1acdf56c736c01c14e5",
        "tarball": "https://registry.npmjs.org/which/-/which-1.2.14.tgz"
    },
    "files": [
        "which.js",
        "bin/which"
    ],
    "gitHead": "ae4f02dfacb208fbb19beab08e7946c4e3d524dd",
    "homepage": "https://github.com/isaacs/node-which#readme",
    "license": "ISC",
    "main": "which.js",
    "maintainers": [
        {
            "name": "isaacs"
        }
    ],
    "name": "which",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git://github.com/isaacs/node-which.git"
    },
    "scripts": {
        "changelog": "bash gen-changelog.sh",
        "postversion": "npm run changelog && git add CHANGELOG.md && git commit -m 'update changelog - '${npm_package_version}",
        "test": "tap test/*.js --cov"
    },
    "version": "1.2.14"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
