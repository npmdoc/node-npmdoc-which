# api documentation for  [which (v1.2.14)](https://github.com/isaacs/node-which#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-which.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-which) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-which.svg)](https://travis-ci.org/npmdoc/node-npmdoc-which)
#### Like which(1) unix command. Find the first instance of an executable in the PATH.

[![NPM](https://nodei.co/npm/which.png?downloads=true)](https://www.npmjs.com/package/which)

[![apidoc](https://npmdoc.github.io/node-npmdoc-which/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-which_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-which/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-which/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-which/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Isaac Z. Schlueter",
        "email": "i@izs.me",
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
            "name": "isaacs",
            "email": "i@izs.me"
        }
    ],
    "name": "which",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module which](#apidoc.module.which)
1.  [function <span class="apidocSignatureSpan">which.</span>sync (cmd, opt)](#apidoc.element.which.sync)



# <a name="apidoc.module.which"></a>[module which](#apidoc.module.which)

#### <a name="apidoc.element.which.sync"></a>[function <span class="apidocSignatureSpan">which.</span>sync (cmd, opt)](#apidoc.element.which.sync)
- description and source-code
```javascript
function whichSync(cmd, opt) {
  opt = opt || {}

  var info = getPathInfo(cmd, opt)
  var pathEnv = info.env
  var pathExt = info.ext
  var pathExtExe = info.extExe
  var found = []

  for (var i = 0, l = pathEnv.length; i < l; i ++) {
    var pathPart = pathEnv[i]
    if (pathPart.charAt(0) === '"' && pathPart.slice(-1) === '"')
      pathPart = pathPart.slice(1, -1)

    var p = path.join(pathPart, cmd)
    if (!pathPart && /^\.[\\\/]/.test(cmd)) {
      p = cmd.slice(0, 2) + p
    }
    for (var j = 0, ll = pathExt.length; j < ll; j ++) {
      var cur = p + pathExt[j]
      var is
      try {
        is = isexe.sync(cur, { pathExt: pathExtExe })
        if (is) {
          if (opt.all)
            found.push(cur)
          else
            return cur
        }
      } catch (ex) {}
    }
  }

  if (opt.all && found.length)
    return found

  throw getNotFoundError(cmd)
}
```
- example usage
```shell
...
which('node', function (er, resolvedPath) {
  // er is returned if no "node" is found on the PATH
  // if it is found, then the absolute path to the exec is returned
})

// sync usage
// throws if not found
var resolved = which.sync('node')

// Pass options to override the PATH and PATHEXT environment vars.
which('node', { path: someOtherPath }, function (er, resolved) {
  if (er)
    throw er
  console.log('found at %j', resolved)
})
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
