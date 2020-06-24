# amazeeio/drupal_integrations

Add this project to any Drupal distribution based on drupal/core-composer-scaffold to enable it for use on Lagoon.

This project enables the following Lagoon integrations:

- Injects the Lagoon database credentials for the Drupal site
- Demonstrates how to turn on twig debugging on non-production Lagoon environments
- Sets the path to:
  - Configuration import / export directory
  - Private files
  - Temporary files
  - Twig cache files
- Establishes a secure, random hash salt for Drupal
- Prevents the user from updating Drupal core with Drush
- Configures the trusted host patterns to avoid a warning that is not applicable to Lagoon
- Ignores large cache directories (e.g. node modules and bower components)

## Enabling this project

This project must be enabled in the top-level composer.json file, or it will be ignored and will not perform any of its functions.
```
{
    ...
    "require": {
        "amazeeio/drupal_integrations"
    },
    ...
    "extra": {
        "drupal-scaffold": {
            "allowed-packages": [
                "amazeeio/drupal_integrations"
            ]
        }
    }
}
```

## Tests

Tests will run PHPCS across all files within the `assets` and `src` directories.

```
composer install
composer test
```

## Credits

Big thanks goes out to [Greg Anderson](https://github.com/greg-1-anderson) from [Pantheon](https://pantheon.io/) all his hard work that went into improving drupal's composer integration allows us to manage platform settings via a composer project.
