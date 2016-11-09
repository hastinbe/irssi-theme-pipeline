# pipeline

`pipeline` is an [Irssi][irssi] theme inspired by madcow and skeita

[![License](http://img.shields.io/:license-GPLv2-blue.svg)][license]

![pipeline][screenshot]

## Requirements

* [Irssi][irssi] - a terminal based IRC client.

#### Optional
* [adv_windowlist.pl][awl] - Adds a permanent advanced window list on the right or in a statusbar.
* [hilightwin.pl][hilightwin] - Print hilighted messages to window named "hilight".
* [usercount.pl][usercount] - Adds a usercount for a channel as a statusbar item.

***Note:*** the optional scripts are required to look like the screenshot.


## Installation

1. Put the theme into your `~/.irssi/` directory
2. In irssi do `/set theme pipeline`
3. That's it!

_It is recommended to do the optional steps below._

#### Optional

Download the above scripts and copy them into your `~/.irssi/scripts/`

In your shell:
```bash
mkdir ~/.irssi/scripts/autorun
cd ~/.irssi/scripts/autorun/
ln -s ../adv_windowlist.pl .
ln -s ../hilightwin.pl .
ln -s ../usercount.pl .
```

##### Load the scripts in irssi
```
/script load adv_windowlist.pl
/script load hilightwin.pl
/script load usercount.pl
```

##### Setup the hilight window
```
/window new split
/window name hilight
/window size 6
/window stick
/hilight -word REPLACE_WITH_YOUR_NICKNAME
```

##### Setup advanced window list
```
/statusbar window remove act
/set awl_block -18
/set awl_display_key $Q%K|%n$H$C$
```

##### Setup usercount script
```
/statusbar window add usercount
/set usercount_show_zero off
/set usercount_show_ircops on
/set usercount_show_halfops on
```

##### Lastly, save your setup!
```
/save
/layout save
```


## FAQ

* How to remove the '[Act:]' display? `/statusbar window remove act`
* How to restore the '[Act:]' display? `/statusbar window add -after lag -priority 10 act`


## License

pipeline is released under the [GNU General Public License v2][license]

Copyright (c) 2016 Beau Hastings

[license]:      /LICENSE
[irssi]:        https://github.com/irssi/irssi
[screenshot]:   /pipeline.png
[awl]:          https://github.com/irssi/scripts/blob/master/scripts/adv_windowlist.pl
[usercount]:    https://github.com/irssi/scripts/blob/master/scripts/usercount.pl
[hilightwin]:   https://github.com/irssi/scripts/blob/master/scripts/hilightwin.pl
