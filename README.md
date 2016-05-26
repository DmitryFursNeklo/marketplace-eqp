#Magento Extension Quality Program Coding Standard

Magento EQP Coding Standard is a set of rules and sniffs for [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) tool.

It allows automatically check your code against some of the common Magento and PHP coding issues, like:
- raw SQL queries;
- SQL queries inside a loop;
- direct instantiation of Mage and Enterprise classes;
- unnecessary collection loading;
- excessive code complexity;
- use of dangerous functions;
- use of PHP superglobals;
- code style issues

and many others.

#Installation & Usage

Before starting using our coding standard install [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer).

Clone or download this repo somewhere on your computer or install it with [Composer](http://getcomposer.org/).
To do so, add the dependency to your `composer.json` file by running `composer require magento/marketplace-eqp`.

Add the standards directory to PHP_CodeSniffer installed paths:
```sh
$ phpcs --config-set installed_paths ./vendor/magento/marketplace-eqp
```

Select a standard to run with PHP_CodeSniffer. To check Magento extension run PHP_CodeSniffer:
```sh
$ phpcs --standard=MEQP1 /path/to/code
```
To check Magento 2 extension run:
```sh
$ phpcs --standard=MEQP2 /path/to/code
```
PHP_CodeSniffer will automatically scan Magento PHP files. To check design templates, you can specify `phtml` in the `--extensions` argument: `--extensions=php,phtml`.

#Dynamic Sniffs
Sniffs with complex logic, like MEQP2.Classes.CollectionDependency and MEQP2.SQL.CoreTablesModification, may require path to installed Magento2 instance. You can specify it using ```$ phpcs --config-set m2-path <path-to-magento2>``` command.

>Notice: Dynamic sniffs will not work without specified ```m2-path``` configuration option.
>Notice: Don't forget to clear cache folder in project root directory if you are running sniffs for other Magento version

#Requirements

PHP 5.6 and up.

#Contribution

Please feel free to contribute new sniffs or any fixes or improvements for the existing ones.