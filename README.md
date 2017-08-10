Overview
========

This is a custom Open edX LMS theme (comprehensive theme) used by [Harvard Continuing Education](http://www.extension.harvard.edu/academics/online-campus-courses).
It is compatible with the Ficus release of Open edX and newer.

Screenshots
===========



Theme Authoring
===============

To customize your theme:
- Fork this repository.
- Clone it into the theme directory next to your edx-platform directory and rename the theme directory to your new theme's name.
- Edit the .scss file in lms/static/sass/ and rename the file with your theme's name.
- Run `make build` to re-generate the lms/static/css/main.css and main.css.map files.
- Edit the lms.envs.json file in edx-platform and set `USE_CUSTOM_THEME` to true, and `THEME_NAME` to your theme's name.

License
=======

The code in this repo is licensed under the Apache 2.0 License.
See [LICENSE.txt](LICENSE.txt) for more info.
