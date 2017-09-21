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


Custom templates
----------------

We try to minimise template customizations, because it makes upgrades difficult.  But to make upgrades easier, we record
the base template in a separate branch, for use when rebasing the theme.

The example below shows how to handle adding an example template to this repo:
```bash
git checkout cloudera-upstream-templates
git -C path/to/edx-platform show open-release/zebrawood.1:lms/templates/example.html > lms/templates/example.html
git commit -am "Add upstream version of example.html."
```

Next, merge this branch into the {{cloudera}} branch:
```bash
git checkout cloudera
git merge cloudera-upstream-templates
```

Then, we can customize the template as needed in the {{cloudera}} branch.

Theme Upgrades
==============

When a new Open edX version is released, we need to update all templates in the upstream branch, so we can rebase the
customized themes on that branch.

Check out the new release in edx-platform and rsync any modified templates
```bash
git checkout cloudera-upstream-templates
git -C path/to/edx-platform checkout open-release/zebrawood.1
rsync --links --existing --delete --recursive path/to/edx-platform/lms/templates lms/
git commit -am "Update upstream templates to the Zebrawood release."
```

To port the customisations to the latest release, we just need to merge:
```bash
git checkout cloudera
git merge cloudera-upstream-templates
```

License
=======

The code in this repo is licensed under the Apache 2.0 License.
See [LICENSE.txt](LICENSE.txt) for more info.
