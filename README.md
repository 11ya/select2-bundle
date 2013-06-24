## Current Version

This bundle allow usage any version of library that you wish. Original lib uses as a package with forced version and original files is symlinked.

Just go to https://github.com/ivaynberg/select2 and check tags.

## Installation

### Add bundle to your composer.json file

Set needed version and branch in `version` and `reference` of package.

``` js
// composer.json

{
    "repositories": {
        // ...

        "ivaynberg/select2": {
            "type": "package",
            "package": {
                "name": "ivaynberg/select2",
                "version": "3.4.0",
                "source": {
                    "url": "https://github.com/ivaynberg/select2.git",
                    "type": "git",
                    "reference": "tags/3.4.0"
                }
            }
        }
    },

    // ...

    "require": {
		// ...
        "fanforfun/select2-bundle": "dev-master"
    }
}
```

### Add bundle to your application kernel

``` php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Fanforfun\Select2Bundle\FanforfunSelect2Bundle(),
        // ...
    );
}
```

### Download the bundle using Composer

``` bash
$ php composer.phar update fanforfun/select2-bundle
```

### Install assets

Given your server's public directory is named "web", install the public vendor resources

``` bash
$ php app/console assets:install web
```

Optionally, use the --symlink attribute to create links rather than copies of the resources

``` bash
$ php app/console assets:install --symlink web
```

## Usage

Refer to the desired files in your twig/HTML template, e.g.

``` html
{% javascripts output='resources/js/*.js' '@FanforfunSelect2Bundle/Resources/public/select2.js' %}
    <script type="text/javascript" src="{{ asset_url }}"></script>
{% endjavascripts %}
```

and i18n

``` html
{% javascripts output='resources/js/*.js' '@FanforfunSelect2Bundle/Resources/public/select2_locale_%YOUR_LANGUAGE%.js' %}
    <script type="text/javascript" src="{{ asset_url }}"></script>
{% endjavascripts %}
```

and stylesheets

``` html
{% stylesheets filter='cssrewrite' output='resources/css/*.css' 'bundles/fanforfunleaflet/select2.css' %}
    <link href="{{ asset_url }}" rel="stylesheet" type="text/css" />
{% endstylesheets %}
```

## Licenses

Refer to the source code of the included files for license information

## References

1. http://symfony.com/

2. https://github.com/ivaynberg/select2

3. http://ivaynberg.github.io/select2/
