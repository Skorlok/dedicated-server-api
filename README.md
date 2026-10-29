ManiaPlanet dedicated server SDK
================================

[![Latest Stable Version](https://poser.pugx.org/skorlok/dedicated-server-api/v/stable)](https://packagist.org/packages/skorlok/dedicated-server-api)
[![License](https://poser.pugx.org/skorlok/dedicated-server-api/license)](https://packagist.org/packages/skorlok/dedicated-server-api)

This library allows you to connect to a ManiaPlanet dedicated server through its XML-RPC interface.

This package is a fork of [maniaplanet/dedicated-server-api](https://github.com/maniaplanet/dedicated-server-api) by Nadeo, maintained **exclusively for [eXpansion](https://github.com/Skorlok/eXpansion)**. It uses classes from eXpansion and ManiaLive, so it can't be used on its own. The namespace is unchanged (`Maniaplanet\`), so it can't be installed together with `maniaplanet/dedicated-server-api`.

Installation
------------

You don't need to install it: it is installed by Composer as a dependency of eXpansion.

Requirements:
* PHP >= 5.3
* `ext-mbstring`
* `ext-simplexml`
* `ext-xmlrpc` is optional: without it, a pure PHP implementation of XML-RPC is used.

Usage
-----

In an eXpansion or ManiaLive plugin, the connection to the dedicated server is available in `$this->connection`. Each method of `Maniaplanet\DedicatedServer\Connection` is an XML-RPC method of the dedicated server:

```php
$this->connection->chatSendServerMessage('Hello everyone!');

foreach ($this->connection->getPlayerList() as $player) {
    echo $player->login, PHP_EOL;
}
```

License
-------

LGPL v3, see [LICENSE](LICENSE). Original work by Nadeo.
