[![npm version](https://badge.fury.io/js/sassvg.svg)](http://badge.fury.io/js/sassvg)
[![Code Climate](https://codeclimate.com/github/MattDiMu/sassvg/badges/gpa.svg)](https://codeclimate.com/github/MattDiMu/sassvg)
[![Test Coverage](https://codeclimate.com/github/MattDiMu/sassvg/badges/coverage.svg)](https://codeclimate.com/github/MattDiMu/sassvg)
[![Build Status](https://travis-ci.org/MattDiMu/sassvg.svg)](https://travis-ci.org/MattDiMu/sassvg)
[![dependencies](https://david-dm.org/MattDiMu/gulp-sassvg.svg)](https://david-dm.org/MattDiMu/gulp-sassvg)
[![devDependencies](https://david-dm.org/MattDiMu/gulp-sassvg/dev-status.svg)](https://david-dm.org/MattDiMu/gulp-sassvg)

# sassvg
Currently under development! Come back later :)

Here are currently only some ideas how to implement

# less support could look something like this:
.lessvg-data(@icon-name; @color: green){
  @fixed-data-string: "begin";
  @sassvg-arrow: " hallo, ich bin der string @{color} mit einer Farbe: @{color}";
  @sassvg-edge: " edge";
  @lessvg: ~"@{fixed-data-string}@{sassvg-@{icon-name}}";
}

.lessvg(@icon-name; @color: green){
 .lessvg-data(@icon-name, @color);
  background-image: url("@{lessvg}");
}

.test {
 .lessvg-data(arrow; blue);
  content: @lessvg;
}


.test2 { 
  .lessvg(arrow);
}


# stylus support could be achieved with hashs:
http://learnboost.github.io/stylus/docs/hashes.html


#fallback
a rework plugin or even better a (postcss)[] plugin could do the work by parsing the css-file, extracting inline-svgs (maybe a marker would help), creating pngs (grunticon-style), inlining them with the same selector and a .no-svg pre-selector
to avoid browsers downloading them, they should not be inlined, but created as png-files...conditional comments suck as other non-svg-browsers exist as well

To create the png at the right size, a default-size should be specified (overridable via option) and the affected selector parsed for any background-size values
