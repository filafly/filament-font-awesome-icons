<p class="filament-hidden" align="center">
    <img src="images/filafly-filament-font-awesome-icons.png" alt="Banner" style="width: 100%; max-width: 800px;" />
</p>

# Filament FontAwesome Icons

A FontAwesome icon set implementation for Filament 3.x, providing a comprehensive set of FontAwesome icons that seamlessly integrate with Filament's interface.

## Installation

You can install the package via composer:

```bash
composer require filafly/filament-font-awesome-icons
```

After the package is installed, you must register the plugin in your Filament Panel provider:

```php
use Filafly\FilamentFontAwesomeIcons\FontAwesomeIcons;

public function panel(Panel $panel): Panel
{
    return $panel
        ->plugins([
            FontAwesomeIcons::make(),
        ]);
}
```

## Icon Styles

FontAwesome icons come in multiple styles that you can switch between. Available styles include:

- Regular (default)
- Thin
- Light
- Bold
- Fill
- Duotone

You can change the style using the following methods:

```php
// Set to thin style
FontAwesomeIcons::make()->thin();

// Set to light style
FontAwesomeIcons::make()->light();

// Set to regular style (default)
FontAwesomeIcons::make()->regular();

// Set to bold style
FontAwesomeIcons::make()->bold();

// Set to fill style
FontAwesomeIcons::make()->fill();

// Set to duotone style
FontAwesomeIcons::make()->duotone();
```

## Override Specific Icons
If you need to override certain icons to use a different style, you can use either icon aliases or direct icon names.

### Using Icon Aliases
Use the `overrideStyleForAlias` method with a [Filament Icon Alias](https://filamentphp.com/docs/3.x/support/icons#available-icon-aliases). This method works with either a single icon key (string) or multiple icon keys (array).

```php
// Override a single icon key
FontAwesomeIcons::make()->overrideStyleForAlias('tables::actions.filter', 'thin');

// Override multiple icon keys at once
FontAwesomeIcons::make()->overrideStyleForAlias([
    'tables::actions.filter',
    'actions::delete-action',
], 'thin');
```

### Using Icon Names
Use the `overrideStyleForIcon` method with the actual FontAwesome icon name. Like the alias method, this works with either a single icon name or multiple names.

```php
// Override a single icon
FontAwesomeIcons::make()->overrideStyleForIcon('font-awesome-user', 'thin');

// Override multiple icons at once
FontAwesomeIcons::make()->overrideStyleForIcon([
    'font-awesome-user',
    'font-awesome-caret-up',
], 'thin');
```

## License
The MIT License (MIT). Please see [License](LICENSE.md) for more information.