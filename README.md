PHP-Minecraft-Rcon
==================
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/thedudeguy/PHP-Minecraft-Rcon/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/thedudeguy/PHP-Minecraft-Rcon/?branch=master)

Simple Rcon class for php.

## Installation
### Using Composer
This Rcon library may be installed by issuing the following command:
```bash
$ composer require thedudeguy/rcon
```
### Not Using Composer
If not using Composer, just place the Rcon.php file in your project and include it in your PHP script:
```php
require_once('Rcon.php');
```

## Example
For this script to work, rcon must be enabled on the server, by setting `enable-rcon=true` in the server's `server.properties` file. A password must also be set, and provided in the script.

```php
$host = 'some.minecraftserver.com'; // Server host name or IP
$port = 25575;                      // Port rcon is listening on
$password = 'server-rcon-password'; // rcon.password setting set in server.properties
$timeout = 3;                       // How long to timeout.

use Thedudeguy\Rcon;

$rcon = new Rcon($host, $port, $password, $timeout);

if ($rcon->connect())
{
  $rcon->sendCommand("say Hello World!");
}
```
