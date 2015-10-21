Snoopy Build Project
====================
[![Build Status](https://img.shields.io/travis/socrata-platform/snoopy-build.svg)][travis]
[![Coverage Status](https://img.shields.io/coveralls/socrata-platform/snoopy-build.svg)][coveralls]

[travis]: https://travis-ci.org/socrata-platform/snoopy-build
[coveralls]: https://coveralls.io/r/socrata-platform/snoopy-build

A project for building Snoopy Logger packages using FPM-Cookery.

This project currently builds for Ubuntu 14.04 only.

***Why not use Omnibus?***

Up until
[recently](https://github.com/RoboticCheese/snoopy-omnibus/tree/43bd4428438c2d6171baecc1037fdb22eca2e38e),
this project did. But an Omnibus pipeline is pretty heavyweight, especially
for a simple application with no dependencies. A build can be completed much
faster by bypassing Omnibus', e.g., installing RBEnv and compiling a fresh
Ruby.

Requirements
============

This project is distributed as a Chef cookbook that contains an FPM-Cookery
recipe which can then be built automatically using Test Kitchen.

You must have a sane Ruby 1.9+ environment with Bundler installed. Ensure all
the required gems are installed:

```shell
bundle install
```

Usage
=====
This project comes with a Test Kitchen config that handles all the builds
automatically for the supported platforms. Normally, the CI server will kick
off a Kitchen run, which will build the package, install it, verify the
results, and publish the new package to PackageCloud.io.

Should the need arise, `fpm-cook` commands can still be run manually from
the recipe directory in `files/default/fpm-recipes/snoopy/`.

Attributes
==========
The included attributes file controls the build version and revision to use
for the package, defaulting to the most recent version of snoopy released and a
build of 1.

    default['snoopy_build']['build_version']
    default['snoopy_build']['build_revision']

Contributing
============

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Add tests for the new feature; ensure they pass (`rake`)
4. Commit your changes (`git commit -am 'Add some feature'`)
5. Push to the branch (`git push origin my-new-feature`)
6. Create a new Pull Request

License & Authors
=================
- Author: Jonathan Hartman <jonathan.hartman@socrata.com>

Copyright 2015 Socrata, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
