# api documentation for  [gulp-add-src (v0.2.0)](https://github.com/urish/gulp-add-src)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-add-src.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-add-src) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-add-src.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-add-src)
#### Add more 'src' files at any point in the pipeline (gulp plugin)

[![NPM](https://nodei.co/npm/gulp-add-src.png?downloads=true)](https://www.npmjs.com/package/gulp-add-src)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-add-src/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gulp-add-src_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-add-src/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-add-src/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-add-src/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Uri Shaked"
    },
    "bugs": {
        "url": "https://github.com/urish/gulp-add-src/issues"
    },
    "dependencies": {
        "event-stream": "~3.1.5",
        "streamqueue": "^0.1.1",
        "through2": "~0.4.1",
        "vinyl-fs": "~0.3.11"
    },
    "description": "Add more 'src' files at any point in the pipeline (gulp plugin)",
    "devDependencies": {
        "gulp": "^3.6.2",
        "mocha": "^1.18.2"
    },
    "directories": {},
    "dist": {
        "shasum": "9e10294619f91a0e7f4217c4f5e51841bcdbef17",
        "tarball": "https://registry.npmjs.org/gulp-add-src/-/gulp-add-src-0.2.0.tgz"
    },
    "gitHead": "87bfcca62725a6bc19185f8e1bf60526277f546b",
    "homepage": "https://github.com/urish/gulp-add-src",
    "keywords": [
        "gulp",
        "gulpplugin",
        "gulpfriendly",
        "pipeline"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "urish",
            "email": "uri@urish.org"
        }
    ],
    "name": "gulp-add-src",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/urish/gulp-add-src.git"
    },
    "scripts": {
        "test": "mocha"
    },
    "version": "0.2.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gulp-add-src](#apidoc.module.gulp-add-src)
1.  [function <span class="apidocSignatureSpan">gulp-add-src.</span>append ()](#apidoc.element.gulp-add-src.append)
1.  [function <span class="apidocSignatureSpan">gulp-add-src.</span>prepend ()](#apidoc.element.gulp-add-src.prepend)



# <a name="apidoc.module.gulp-add-src"></a>[module gulp-add-src](#apidoc.module.gulp-add-src)

#### <a name="apidoc.element.gulp-add-src.append"></a>[function <span class="apidocSignatureSpan">gulp-add-src.</span>append ()](#apidoc.element.gulp-add-src.append)
- description and source-code
```javascript
function append() {
	var pass = through.obj();
	return es.duplex(pass, streamqueue({ objectMode: true }, pass, vinyl.src.apply(vinyl.src, arguments)));
}
```
- example usage
```shell
...
			].sort());
			done();
		});
	});

	it('should append files to an existing stream in order', function (done) {
		var stream = gulp.src(['index.js', 'test.js'])
			.pipe(addsrc.append(['package.json', 'README.md']));

		var allFiles = [];
		stream.on('error', done);
		stream.on('data', function (file) {
			allFiles.push(file.path);
		});
		stream.on('end', function() {
...
```

#### <a name="apidoc.element.gulp-add-src.prepend"></a>[function <span class="apidocSignatureSpan">gulp-add-src.</span>prepend ()](#apidoc.element.gulp-add-src.prepend)
- description and source-code
```javascript
function prepend() {
    var pass = through.obj();
    return es.duplex(pass, streamqueue({ objectMode: true }, vinyl.src.apply(vinyl.src, arguments), pass));
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
