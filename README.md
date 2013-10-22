# grunt-premailer

> Grunt wrapper task for [Premailer](https://github.com/alexdunae/premailer/)


##Requirements

This plugin is a [Grunt](http://gruntjs.com/)  wrapper around the [Premailer](https://github.com/alexdunae/premailer/) Ruby gem developed by Alex Dunae. In order to run it you will need the following packages installed on your system:

* Node.js >= 0.8.11 ([install wiki](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager))
* Grunt-cli >= 0.1.7 and Grunt >=0.4.1 (`npm install grunt-cli -g`)
* Ruby >= 1.8.7 ([installers](http://www.ruby-lang.org/en/downloads/))
* Premailer >= 1.7.3 (`gem install premailer` and, most of the time, `gem install hpricot`)

## Getting Started

This plugin requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-premailer --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-premailer');
```

## The "premailer" task

### Overview
In your project's Gruntfile, add a section named `premailer` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  premailer: {
    options: {
      // Task-specific options go here.
    },
    your_target: {
      // Target-specific file lists and/or options go here.
    },
  },
})
```

### Options

#### options.mode
Type: `String`
Default value: `'html'`

Output format. Either `'html'` (HTML formatted email) or `'txt'` (plaintext email).

#### options.baseUrl
Type: `String`
Default value: `''`

Base URL to append to relative links.

#### options.queryString
Type: `String`
Default value: `''`

Query string to append to links.

#### options.css
Type: `Array`
Default value: `[]`

Additional CSS stylesheets to process.

#### options.removeClasses
Type: `Boolean`
Default value: `false`

Removes HTML classes.

#### options.lineLength
Type: `Number`
Default value: `65`

Line length for plaintext version.

#### options.ioException
Type: `Boolean`
Default value: `false`

Aborts on I/O errors.

#### options.verbose
Type: `Boolean`
Default value: `false`

Prints additional information at runtime.

### Usage Examples

#### Default Options
In this example, the default options are used to inline CSS styles in into the markup.

```js
grunt.initConfig({
  premailer: {
    simple: {
      options: {},
      files: {
        'dest/email.html': ['src/email.html']
      }
    }
  }
})
```

#### Custom Options
In this example, custom options are used to append a query string (such as a google campaign click tracking) to every link.

```js
grunt.initConfig({
  premailer: {
    withqs: {
      options: {
        queryString: 'utm_source=premailer&utm_medium=email&utm_campaign=test'
      },
      files: {
        'dest/email.html': ['src/email.html']
      }
    }
  }
})
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History

0.1.0 - Initial release