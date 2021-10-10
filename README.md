Crewbit PHP-CS-Fixer Rules
===========================

## Installation

### Edit composer.json

```json:composer.json
{
    "repositories": {
        "crew-bit/php-cs-fixer-rules": {
            "type": "vcs",
            "url": "https://github.com/crew-bit/php-cs-fixer-rules"
        },
    },
    "minimum-stability": "dev"
}
```

### Install package

```bash
$ composer require --dev crew-bit/php-cs-fixer-rules
```

## Setup

### Configuration

Create `.php-cs-fixer.dist.php`:

```php:.php-cs-fixer.dist.php
<?php

declare(strict_types=1);

return (new PhpCsFixer\Config())
    ->setRiskyAllowed(true)
    ->setRules((new Crewbit\PhpCsFixer\Rules())->getRules())
    ->setFinder(PhpCsFixer\Finder::create()->exclude('vendor')->in(__DIR__ . '/app'));
```


### Gitignore

Add PHP-CS-Fixer cache file to `.gitignore`:

```.gitignore
+ /.php-cs-fixer.cache
```
