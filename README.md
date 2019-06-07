#How to Set Up a TF2 Server for Scrims

I'll assume you are in possession of a factory new TF2 server and know how to access your server files.

This guide goes through a tftrue setup.

##Base Installation

Download tftrue from [http://tftrue.esport-tools.net/](http://tftrue.esport-tools.net/) and follow the installation directions.

tftrue comes with logs so you shouldn't need to do anything further regarding that.

I recommend using [https://cfg.tf/server/](https://cfg.tf/server/) to set up your `server.cfg`, but ensure that you have and/or consider the following commands:

`tf_preround_push_from_damage_enable`

Set this to 1 in order to have proper rollouts.

`tv_delaymapchange_protect`

Set this to 0 if you don't want to wait for stv to catch up and prevent you from changing maps immediately.  This can make your stvs end prematurely while watching them.
You can also take a look at the esea_base.cfg section on stv settings and make changes as you will.

`tftrue_logs_apikey`

Sets the API key to upload logs to logs.tf (requires mp_tournament). It will automatically flush the log before upload, so any content that is still in memory will be wrote to the log. 

`tftrue_logs_roundend`

Whether to upload logs at every round end or just when a team wins the map. Default is 0 (just when a team wins the map).

`tftrue_logs_accuracy`

Logs accuracy stats in the logs (shots fired/hit). It can potentially cause performance issues with some servers.
Default is 0 (disabled).

If you're curious about what other features tftrue offers there are some fun things and I recommend reading the website in more detail.


##Config files
Download the contents of this github.

Put the `esea` folder in your server's `/cfg` folder.  The `alias.cfg` file is an optional feature to have locally on your own computer for convenience.

Download the latest whitelist from whitelist.tf, put this file in your servers `/cfg` folder.

These configs are already set to execute the esea push config with 5 rounds and a 30 minute timelimit.

Open up `esea/esea_base.cfg` and ensure the line:

`mp_tournament_whitelist "cfg/esea_6v6_s30.txt"`

Matches the filename of your whitelist.

Edit other settings as desired.

Whenever you wish to scrim, simply enter either of the lines,

`"rcon exec esea/esea_push"` or
`"rcon exec esea/esea_koth"`

in your console for 5cp or koth respectively.

You can make aliases to make typing in console easier.

I've provided an example `aliases.cfg` you can use if you wish. Just add `exec aliases` to your `autoexec.cfg` or `custom.cfg` if you're using mastercomfig

My maps in the config might be out of date so just double check the list.


##MGE
Download `mgemod.zip` from [https://github.com/Lange/MGEMod/releases](https://github.com/Lange/MGEMod/releases).

Inside you'll see the `/addons` and `/map` folders, just extract the contents of the zip to your server directory where those same folders are and let it merge/overwrite what it will.

If you wish to have oihguv, you can find the map and spawn config files here: [https://www.teamfortress.tv/17233/mge-oihguv-sucks](https://www.teamfortress.tv/17233/mge-oihguv-sucks).

In order to have 2v2 for vanilla mge, rename your original

`mgemod_spawns.cfg` to `mgemod_spawns_1v1.cfg`, 

and your

`mgemod_spawns_2v2.cfg` to just `mgemod_spawns.cfg`.

Rename back and forth as necessary.

For oihguv you'll have to edit the spawn config yourself. There's information at the top of that file.
