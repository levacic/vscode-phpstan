[![](https://vsmarketplacebadge.apphb.com/version-short/levacic.vscode-phpstan.svg)](https://marketplace.visualstudio.com/items?itemName=levacic.vscode-phpstan)
[![](https://vsmarketplacebadge.apphb.com/installs-short/levacic.vscode-phpstan.svg)](https://marketplace.visualstudio.com/items?itemName=levacic.vscode-phpstan)
[![](https://vsmarketplacebadge.apphb.com/rating-short/levacic.vscode-phpstan.svg)](https://marketplace.visualstudio.com/items?itemName=levacic.vscode-phpstan)

<p align="center">
  <br />
  <img src="https://puu.sh/zkXAe/e727a924d6.png" alt="Image Sample 1" />
</p>

## Note

This is a fork of [OhMyMndy/vscode-phpstan](https://github.com/OhMyMndy/vscode-phpstan) created in order to avoid forcing the analysis level if there is a `phpstan.neon` or `phpstan.neon.dist` file present - as in that case, we want to control everything through that file, including the analysis level.

This is just a hack, there's a lot of other stuff not up-to-date here (e.g. dependencies), the lock file is not in sync with the main `package.json`, and I'm just gonna leave it like this for now because the hack solves my immediate problem of having to manually configure the extension for each individual project, rather than having the extension provide sane behavior by default.

## Note

Because [calvinbaart/vscode-phpstan](https://github.com/calvinbaart/vscode-phpstan) seems not supported anymore, I have continued development through this fork

## What is this

[PHPStan](https://github.com/phpstan/phpstan) is a static analysis tool for PHP. This extension integrates the output of PHPStan in VSCode allowing the developer to find errors quicker.

## Installation

PHPStan is required to use this extension. By default the plugin will search the global vendor folder and the workspace vendor folders.
The COMPOSER_HOME environment variable can be set to change where the plugin searches.
This path can be manually set using the ``phpstan.path`` setting.

PHPStan can be installed globally using:

```bash
composer global require phpstan/phpstan
```

or locally using:

```bash
composer require --dev phpstan/phpstan
```

## Commands

PHPStan includes an explorer-context command called "PHPStan: Scan for Errors". This command works on both directories and files.

<p align="center">
  <br />
  <img src="https://puu.sh/ApEKt/e7eabb4b1c.png" alt="Image Sample 2" />
</p>

## Configuration

vscode-phpstan-extension provides the following configuration properties and defaults:

```json
"phpstan.enabled": true,
"phpstan.path": null,
"phpstan.level": "max",
"phpstan.memoryLimit": "2048M",
"phpstan.projectFile": null,
"phpstan.excludeFiles": [],
"phpstan.options": []
```

``<workspacefolder>/phpstan.neon`` and ``<workspacefolder>/phpstan.neon.dist`` will be used when phpstan.projectFile is set to null.
phpstan.options can be used to pass extra parameters to the phpstan commandline call.
