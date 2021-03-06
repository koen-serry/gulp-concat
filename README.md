![status](https://secure.travis-ci.org/wearefractal/gulp-concat.png?branch=master)

## Information

<table>
<tr> 
<td>Package</td><td>gulp-concat</td>
</tr>
<tr>
<td>Description</td>
<td>Concatenates files</td>
</tr>
<tr>
<td>Node Version</td>
<td>>= 0.4</td>
</tr>
</table>

## Usage

```javascript
var concat = require('gulp-concat');

gulp.task('scripts', function() {
  gulp.src('./lib/*.js')
    .pipe(concat("all.js"))
    .pipe(gulp.dest('./dist/'))
});
```

This will concat files by your operating systems newLine. It will take the base directory from the first file that passes through it.

To change the newLine simply pass an object as the second argument to concat with newLine being whatever (\r\n if you want to support any OS to look at it)

In order to output to multiple files the following syntax can be used:

```javascript
var concat = require('gulp-concat');

gulp.task('scripts', function() {
  gulp.src('./lib/*.js')
    .pipe(concat({
    	"part1.js": ['a.js','b.js'],
    	"part2.js": ['a.js','c.js']
    }))
    .pipe(gulp.dest('./dist/'))
});
```
Which will result in part1.js containing contents of a and b (in that order).

## LICENSE

(MIT License)

Copyright (c) 2013 Fractal <contact@wearefractal.com>

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
