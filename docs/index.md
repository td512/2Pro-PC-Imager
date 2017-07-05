## So what is this?

This is a set of iPXE based scripts designed to boot Windows, and various Linuxes

## How do I run it?

Easy! Clone this repo into `/var/www/html` (or where ever you put your HTTPd docroot), generate a bootscript chaining `${server}${port}/init/init.ipxe`, and watch as the magic happens!

## How do I create a bootscript?

Easy. Visit [rom-o-matic](https://rom-o-matic.eu/), select `UNDI only`, and once you're finished with your bootscript, hit `Proceed >>`, and upload the file to `/tftpboot`, (or where ever you put TFTPd's root). Don't forget to set DHCP options 66 and 67! If you forget to do this, PXE won't work.

## I don't know what my bootscript should look like, can you show me?

Sure, here's what mine looks like.

```
#!ipxe
ifconf
echo DHCP...
dhcp
chain http://10.10.10.80:81/init/init.ipxe
```

Easy as that.

## Found a bug, or need help?

Report it over [here](https://github.com/td512/2Pro-PC-Imager), and one of my minions (probably me) will help you along

## How do I contribute?

Clone my repo, make your changes, and make a pull request. Be sure to tag it with `bugfix` or `improvement`.
