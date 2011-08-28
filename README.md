# MPDSync

MPDSync is a simple way to synchronize multiple MPD servers so that they're
all playing the same thing, at the same time, with the same playlist.

Don't know what MPD is? Check it out here: [http://mpd.wikia.com](http://mpd.wikia.com)


## Requirements

* Two or more MPD servers (duh!) which have identical music databases, like a network share
* Python 2.6+
* python-mpd


## Setup

One MPD server will be considered the master and all the others will be slaves. This 
configuration is saved in settings.json (an example is provided for you). 
Once that's taken care of, all you have to is run the mpdsync.py file!

Upon startup, MPDSync will propagate the playlist and player state from the master 
to all of the slaves. Then, MPDSync waits for the master server to do something, 
such as modify the playlist, and then makes the same changes to the slaves.


## TODO
*   Due to timing issues with a network and MPD's idle command, the music isn't 
    perfectly synced. Hopefully this can be fixed without forking MPD...
*   Adjusting the volume on the master ought to proportionally adjust the volume 
    on all of the slaves
