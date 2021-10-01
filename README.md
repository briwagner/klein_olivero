# Klein Olivero Subtheme

As of Drupal 9.2, Olivero is still an experimental theme. It doesn't officially support sub-theming yet, but we're going to take that risk.

Requirements:
* Drupal ^9.2
* Olivero theme
* Node and npm
* <a href="https://github.com/nvm-sh/nvm">Node version manager</a> (recommended)

## Installation

For a composer-based workflow, modify the Drupal project's composer.json file to add the following in the "repositories" section:

        {
          "type": "package",
          "package": {
            "name": "briwagner/klein_olivero",
            "version": "1.0",
            "type": "drupal-theme",
            "source": {
              "url": "https://github.com/briwagner/klein_olivero.git",
              "type": "git",
              "reference": "master"
            }
          }
        }

1. Add project to composer (as shown above).
1. `composer require briwagner/klein_olivero`
1. Navigate to /themes/custom/klein_olivero
1. `npm install`
1. `npm run build`
1. Enable theme in Drupal

## Build Step for Front-end Assets

A basic npm script is included in package.json. It uses sass to compile sass files into css.

Sass files that start with an underscore should be imported in `global.scss` or another file. They will not be compiled and copied into the `dist/` folder.

Sasses files that should be copied into the `dist/` folder and made available to the web server should NOT begin with an underscore.