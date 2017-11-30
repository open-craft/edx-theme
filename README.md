Overview
========
This directory stores a default theme for an Open edX instance.

We've organized the tree to mimic the directory structure of the edX
codebase so that it's easy to tell where the files will end up upon
deploy. We'll use a special settings file to set the template and
staticfiles paths properly to point to these files.

![Alt text](/default_theme_screenshot.jpg?raw=true "Open edX Default Theme Screenshot")

Theme Authoring
===============
To customize your theme:
- Fork this repository.
- Clone it into the theme directory next to your edx-platform directory and rename the theme directory to your new theme's name.
- Upload your own image assets.
- Edit the .scss file in static/sass/ and rename the file with your theme's name.
- Edit the lms.envs.json file in edx-platform and set 'USE_CUSTOM_THEME' to true, and 'THEME_NAME' to your theme's name.


Custom templates
----------------

We try to minimise template customizations, because it makes upgrades difficult.  But to make upgrades easier, we record
the base template in a separate branch, for use when rebasing the theme.

The example below shows how to handle adding an example template to this repo:
```bash
git checkout pearsonx-upstream-templates
git -C path/to/edx-platform show open-release/zebrawood.1:lms/templates/example.html > lms/templates/example.html
git commit -am "Add upstream version of example.html."
```

Next, merge this branch into the `pearsonx` branch:
```bash
git checkout pearsonx
git merge pearsonx-upstream-templates
```

Then, we can customize the template as needed in the `pearsonx` branch.

Theme Upgrades
==============

When a new Open edX version is released, we need to update all templates in the upstream branch, so we can rebase the
customized themes on that branch.

Check out the new release in edx-platform and rsync any modified templates
```bash
git checkout pearsonx-upstream-templates
git -C path/to/edx-platform checkout open-release/zebrawood.1
rsync --links --existing --delete --recursive path/to/edx-platform/lms/templates lms/
git commit -am "Update upstream templates to the Zebrawood release."
```

To port the customisations to the latest release, we just need to merge:
```bash
git checkout pearsonx
git merge pearsonx-upstream-templates
```

License
=======

The code in this repo is licensed under the Apache 2.0 License.
See [LICENSE.txt](LICENSE.txt) for more info.
