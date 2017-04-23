# npmtest-plotly.js

#### basic test coverage for  plotly.js (v1.26.1)  [![npm package](https://img.shields.io/npm/v/npmtest-plotly.js.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-plotly.js) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-plotly.js.svg)](https://travis-ci.org/npmtest/node-npmtest-plotly.js)

#### The open source javascript graphing library that powers plotly

[![NPM](https://nodei.co/npm/plotly.js.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/plotly.js)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-plotly.js/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-plotly.js/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-plotly.js/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-plotly.js/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-plotly.js/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-plotly.js/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-plotly.js/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-plotly.js/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-plotly.js/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-plotly.js/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-plotly.js/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-plotly.js/build/test-report.html](https://npmtest.github.io/node-npmtest-plotly.js/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-plotly.js/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-plotly.js/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-plotly.js/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-plotly.js/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-plotly.js/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-plotly.js/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-plotly.js/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-plotly.js/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "plotly.js",
    "version": "1.26.1",
    "description": "The open source javascript graphing library that powers plotly",
    "license": "MIT",
    "main": "./lib/index.js",
    "webpack": "./dist/plotly.js",
    "repository": {
        "type": "git",
        "url": "https://github.com/plotly/plotly.js.git"
    },
    "bugs": {
        "url": "https://github.com/plotly/plotly.js/issues"
    },
    "author": "Plotly, Inc.",
    "keywords": [
        "graphing",
        "plotting",
        "data",
        "visualization",
        "plotly"
    ],
    "scripts": {
        "preprocess": "node tasks/preprocess.js",
        "bundle": "node tasks/bundle.js",
        "header": "node tasks/header.js",
        "stats": "node tasks/stats.js",
        "build": "npm run preprocess && npm run bundle && npm run header && npm run stats",
        "cibuild": "npm run preprocess && node tasks/cibundle.js",
        "watch": "node tasks/watch.js",
        "lint": "eslint --version && eslint .",
        "lint-fix": "eslint . --fix || true",
        "docker": "node tasks/docker.js",
        "pretest": "node tasks/pretest.js",
        "test-jasmine": "karma start test/jasmine/karma.conf.js",
        "test-image": "node tasks/test_image.js",
        "test-image-gl2d": "node tasks/test_image.js gl2d_* --queue",
        "test-export": "node tasks/test_export.js",
        "test-syntax": "node tasks/test_syntax.js",
        "test-bundle": "node tasks/test_bundle.js",
        "test": "npm run test-jasmine && npm run test-bundle && npm run test-image && npm run test-image-gl2d && npm run test-syntax && npm run lint",
        "start-test_dashboard": "node devtools/test_dashboard/server.js",
        "start-image_viewer": "node devtools/image_viewer/server.js",
        "start": "npm run start-test_dashboard",
        "baseline": "node tasks/baseline.js",
        "preversion": "npm-link-check && npm dedupe && npm ls",
        "version": "npm run build && git add -A dist src build",
        "postversion": "node -e \"console.log('Version bumped and committed. If ok, run: git push && git push --tags')\""
    },
    "browserify": {
        "transform": [
            "glslify"
        ]
    },
    "dependencies": {
        "3d-view": "^2.0.0",
        "alpha-shape": "^1.0.0",
        "color-rgba": "^1.0.4",
        "convex-hull": "^1.0.3",
        "country-regex": "^1.1.0",
        "d3": "^3.5.12",
        "delaunay-triangulate": "^1.1.6",
        "es6-promise": "^3.0.2",
        "fast-isnumeric": "^1.1.1",
        "gl-contour2d": "^1.1.2",
        "gl-error2d": "^1.2.1",
        "gl-error3d": "^1.0.0",
        "gl-heatmap2d": "^1.0.3",
        "gl-line2d": "^1.4.1",
        "gl-line3d": "^1.1.0",
        "gl-mat4": "^1.1.2",
        "gl-mesh3d": "^1.2.0",
        "gl-plot2d": "^1.2.0",
        "gl-plot3d": "^1.5.4",
        "gl-pointcloud2d": "^1.0.0",
        "gl-scatter2d": "^1.2.2",
        "gl-scatter2d-sdf": "1.3.4",
        "gl-scatter3d": "^1.0.4",
        "gl-select-box": "^1.0.1",
        "gl-shader": "4.2.0",
        "gl-spikes2d": "^1.0.1",
        "gl-surface3d": "^1.3.0",
        "mapbox-gl": "^0.22.0",
        "matrix-camera-controller": "^2.1.3",
        "mouse-change": "^1.4.0",
        "mouse-wheel": "^1.0.2",
        "ndarray": "^1.0.18",
        "ndarray-fill": "^1.0.2",
        "ndarray-homography": "^1.0.0",
        "ndarray-ops": "^1.2.2",
        "regl": "^1.3.0",
        "right-now": "^1.0.0",
        "robust-orientation": "^1.1.3",
        "sane-topojson": "^2.0.0",
        "superscript-text": "^1.0.0",
        "tinycolor2": "^1.3.0",
        "topojson-client": "^2.1.0",
        "webgl-context": "^2.2.0",
        "world-calendars": "^1.0.3"
    },
    "devDependencies": {
        "brfs": "^1.4.3",
        "browserify": "^14.1.0",
        "browserify-transform-tools": "^1.7.0",
        "deep-equal": "^1.0.1",
        "ecstatic": "^2.1.0",
        "eslint": "^3.17.1",
        "falafel": "^2.0.0",
        "fs-extra": "^2.0.0",
        "fuse.js": "^2.6.1",
        "glob": "^7.0.0",
        "glslify": "^4.0.0",
        "gzip-size": "^3.0.0",
        "image-size": "^0.5.1",
        "jasmine-core": "^2.4.1",
        "karma": "^1.5.0",
        "karma-browserify": "^5.1.1",
        "karma-chrome-launcher": "^2.0.0",
        "karma-coverage": "^1.0.0",
        "karma-firefox-launcher": "^1.0.1",
        "karma-jasmine": "^1.1.0",
        "karma-jasmine-spec-tags": "^1.0.1",
        "karma-spec-reporter": "0.0.30",
        "karma-verbose-reporter": "0.0.6",
        "madge": "^1.6.0",
        "minimist": "^1.2.0",
        "node-sass": "^4.5.0",
        "npm-link-check": "^1.2.0",
        "open": "0.0.5",
        "prepend-file": "^1.3.1",
        "prettysize": "0.0.3",
        "read-last-lines": "^1.1.0",
        "requirejs": "^2.3.1",
        "through2": "^2.0.3",
        "uglify-js": "^2.8.12",
        "watchify": "^3.9.0",
        "xml2js": "^0.4.16"
    },
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
