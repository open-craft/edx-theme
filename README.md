Overview
========
This directory stores Unow's theming files for its edX instance.
We're storing the stuff here and then pulling it in to our instance
when we deploy.

The tree is organized to mimic the directory structure of the edX
codebase so that it's easy to tell where the files will end up upon
deploy. A special settings file is used to point the edx instance to
the theming files.

Theme Authoring
===============
The proposed theming solution for edX (see [this pull](https://github.com/edx/edx-platform/pull/1907)
for more details) provides a number of hooks for themes to adjust
both HTML and CSS to their liking.


License
=======

The code in this repo is licensed under the Apache 2.0 License.  See
[LICENSE.txt](LICENSE.txt) for more info.  The copyright for the Unow brands
and assets (e.g. logo) are held by Unow. The copyright for the Stanford brands
and assets (the repo still contain some of the images) are held by Stanford
University.

