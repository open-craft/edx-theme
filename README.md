Overview
========

This is a custom Open edX LMS theme (comprehensive theme) used by Cloudera.
It is compatible with the Eucalyptus release of Open edX and newer.

Screenshots
========

![Alt text](/theme-index.jpg?raw=true "Index page screenshot")

Index page

![Alt text](/theme-courses.jpg?raw=true "Course catalogue page screenshot")

Course catalogue page

![Alt text](/theme-course-about.jpg?raw=true "Open edX Default Theme Screenshot")

Single course about page

![Alt text](/theme-register.jpg?raw=true "Open edX Default Theme Screenshot")

Register page

![Alt text](/theme-dashboard.jpg?raw=true "Open edX Default Theme Screenshot")

Dashboard page


Theme Authoring
===============

To customize your theme:
- Fork this repository.
- Clone it into the theme directory next to your edx-platform directory and rename the theme directory to your new theme's name.
- Edit the .scss file in static/sass/ and rename the file with your theme's name.
- Run `make build` to re-generate the lms/static/css/main.css and main.css.map files.
- Edit the lms.envs.json file in edx-platform and set 'USE_CUSTOM_THEME' to true, and 'THEME_NAME' to your theme's name.

License
=======

The code in this repo is licensed under the Apache 2.0 License.
See [LICENSE.txt](LICENSE.txt) for more info.
