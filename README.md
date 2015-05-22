# Nested-ember-browserify

This repo demonstrates an issue where an ember app consumes an ember addon that uses ember-browserify. Outside of adding the [dummy addon](https://github.com/asakusuma/uses-ember-browserify) to package.json, this repo is unchanged from the output of the standard `ember app` generator.

The [dummy addon](https://github.com/asakusuma/uses-ember-browserify) add just one file, [an initializer](https://github.com/asakusuma/uses-ember-browserify/blob/master/app/initializers/ember-browserify-test.js) that pulls in underscore at runtime.

If you run `ember build` in the app, you should get the following error:

```
$ ember build
version: 0.2.5
Build failed.
Path or pattern "browserify/browserify.js" did not match any files
Error: Path or pattern "browserify/browserify.js" did not match any files
    at Object.multiGlob (/Users/akusuma/workspace/opensource/nested-ember-browserify/node_modules/ember-cli/node_modules/broccoli-kitchen-sink-helpers/index.js:202:13)
    at Class.module.exports.CachingWriter.extend.addFiles (/Users/akusuma/workspace/opensource/nested-ember-browserify/node_modules/ember-cli/node_modules/broccoli-sourcemap-concat/concat-with-maps.js:74:13)
    at Class.module.exports.CachingWriter.extend.updateCache (/Users/akusuma/workspace/opensource/nested-ember-browserify/node_modules/ember-cli/node_modules/broccoli-sourcemap-concat/concat-with-maps.js:52:12)
    at /Users/akusuma/workspace/opensource/nested-ember-browserify/node_modules/ember-cli/node_modules/broccoli-sourcemap-concat/node_modules/broccoli-caching-writer/index.js:92:34
    at lib$rsvp$$internal$$tryCatch (/Users/akusuma/workspace/opensource/nested-ember-browserify/node_modules/ember-cli/node_modules/rsvp/dist/rsvp.js:489:16)
    at lib$rsvp$$internal$$invokeCallback (/Users/akusuma/workspace/opensource/nested-ember-browserify/node_modules/ember-cli/node_modules/rsvp/dist/rsvp.js:501:17)
    at lib$rsvp$$internal$$publish (/Users/akusuma/workspace/opensource/nested-ember-browserify/node_modules/ember-cli/node_modules/rsvp/dist/rsvp.js:472:11)
    at lib$rsvp$asap$$flush (/Users/akusuma/workspace/opensource/nested-ember-browserify/node_modules/ember-cli/node_modules/rsvp/dist/rsvp.js:1290:9)
    at process._tickCallback (node.js:355:11)
```