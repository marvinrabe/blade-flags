# Blade Flags

[![Latest Version on Packagist](https://img.shields.io/packagist/v/marvinrabe/blade-flags.svg?style=flat-square)](https://packagist.org/packages/marvinrabe/blade-flags)
[![GitHub Tests Action Status](https://img.shields.io/github/actions/workflow/status/marvinrabe/blade-flags/run-tests.yml?branch=main)](https://github.com/marvinrabe/blade-flags/actions?query=workflow%3ATests+branch%3Amain)
[![Total Downloads](https://img.shields.io/packagist/dt/marvinrabe/blade-flags.svg?style=flat-square)](https://packagist.org/packages/marvinrabe/blade-flags)

A package to easily make use of country flags in your Laravel Blade views.

For a full list of available flags see [the SVG directory](resources/svg) or preview them at [flag-icons](https://flagicons.lipis.dev/). Flag SVGs are provided by [lipis/flag-icons](https://github.com/lipis/flag-icons).

## Requirements

- PHP 8.0 or higher
- Laravel 9.0 or higher

## Installation

```bash
composer require marvinrabe/blade-flags
```

## Blade Icons

Blade Flags uses Blade Icons under the hood. Please refer to [the Blade Icons readme](https://github.com/blade-ui-kit/blade-icons) for additional functionality. We also recommend to [enable icon caching](https://github.com/blade-ui-kit/blade-icons#caching) with this library.

## Configuration

Blade Flags also offers the ability to use features from Blade Icons like default classes, default attributes, etc. If you'd like to configure these, publish the `blade-flags.php` config file:

```bash
php artisan vendor:publish --tag=blade-flags-config
```

## Usage

Icons can be used as self-closing Blade components which will be compiled to SVG icons:

```blade
<x-flag-4x3-us/>
```

You can also pass classes to your icon components:

```blade
<x-flag-4x3-us class="w-6 h-6"/>
```

And even use inline styles:

```blade
<x-flag-4x3-us style="color: #555"/>
```

Or use the `@svg` directive:

```blade
@svg('flag-4x3-us', 'w-6 h-6', ['style' => 'color: #555'])
```

Flags are available in two aspect ratios. The 4x3 flags:

```blade
<x-flag-4x3-us/>
<x-flag-4x3-de/>
<x-flag-4x3-fr/>
```

And the 1x1 (square) flags:

```blade
<x-flag-1x1-us/>
<x-flag-1x1-de/>
<x-flag-1x1-fr/>
```

### Raw SVG Icons

If you want to use the raw SVG icons as assets, you can publish them using:

```bash
php artisan vendor:publish --tag=blade-flags --force
```

Then use them in your views like:

```blade
<img src="{{ asset('vendor/blade-flags/4x3-us.svg') }}" width="10" height="10"/>
```

## Credits

- Project structure based on [blade-ui-kit/blade-heroicons](https://github.com/blade-ui-kit/blade-heroicons) by [Dries Vints](https://driesvints.com)
- Flag SVGs from [lipis/flag-icons](https://github.com/lipis/flag-icons)

## License

Blade Flags is open-sourced software licensed under [the MIT license](LICENSE.md).
