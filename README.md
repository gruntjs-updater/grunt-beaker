[![Build Status](https://travis-ci.org/kmulvey/grunt-beaker.svg?branch=master)](https://travis-ci.org/kmulvey/grunt-beaker)
[![Built with Grunt](https://cdn.gruntjs.com/builtwith.png)](http://gruntjs.com/)

Grunt Beaker
==========

Measure your file size and keep track of them over time.


### Why?

Over time you add more features, fix the bugs and generally add more code.  Understanding where all the growth is happening is imoprtant for maintaining your project. Grunt beaker maintains a json file with the date and filesize of files you tell it about and over time you can graph this data to see trends or to compare files against each other. 

Sample config:

```
'use strict';

module.exports = function(grunt) {

  // Project configuration.
  grunt.initConfig({
    beaker: {
      js: {
        src: 'tasks/',
        options: {
			collectData: true,
			version: 'beaker.json'
        }
      },
      calc: {
        src: 'tasks/',
        options: {
		    sma: 5,
			key: 'js',
			version: 'beaker.json'
        }
      }
    }
  });
  grunt.loadNpmTasks('grunt-beaker');
};

```



Sample output:

```
{
    "css": {
        "bootstrap-override.css": [
            {
                "1396357776000": 4632
            }
        ],
        "implementation.css": [
            {
                "1396357776000": 13742
            }
        ]
    }
}
```
