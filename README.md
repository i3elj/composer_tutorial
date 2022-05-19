# Guide to use Composer
Composer is a tool for managing php dependencies without breaking everything.

## How to install/update a package from [Packagist.org](https://packagist.org/)?
1. Create a `composer.json` file:
```json
{
  "require": {
    "monolog/monolog": "2.0.*"
  }
}
```
  this will ensure you always have the latest `monolog/molog` package >=2.0.0 &
<2.1 version on your project.

2. Install package:
```bash
php composer.phar update
```
  This will install all latest packages listed in your `composer.json` and it
will write their exact version to `composer.lock`. <br/>
  It's good practice to commit the `composer.lock` file, so that all developers
working on your project are locked with the same versions.

3. Installing from `composer.lock`:
```bash
php composer.phar install
```
  If there already is a `composer.lock` file, it means you or someone working
in the project already ran the `update` command.<br/>
  Therefore, if you are clonning a repo and it's have a `composer.lock` you
can simply use the command above so that every package installed is all
the same version which is listed in `composer.lock` file.

## Using `php composer.phar <command>` in a better way
If you want to use only `composer` as the composer command (assuming you
installed it locally), you just need to set an alias in your `.bashrc` file or
any other `*.rc` that you may use.
```bashrc
alias composer='./.local/bin/composer.phar'
```
  This will make the command `composer` behave as the same as `php .local/
bin/composer.phar`
