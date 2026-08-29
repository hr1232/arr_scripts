These are Bash scripts to manage large Sonarr/Radarr media libraries.

newtag
------
  This one is designed to be run as a Connect Script in Sonarr or Radarr.
  Whenever a new movie or episode is added, it will add a tag to the series
  or movie, thereby marking it for later conversion by convert.
  Just add it as a Custom Script under Settings-->Connect and also make
  sure that your Sonarr/Radarr user has execute privileges. If you run
  Sonarr/Radarr on Docker also make sure that the settings-file is available
  inside the container.
  In Radarr your have to activate the events:
    - On File Import
    - On File Upgrade
  In Sonarr this will work aswell. However, it is better to use this one
  instead (not all three! just this one!):
    - On Import Complete
  The difference is simple. "On File Import/Upgrade" runs after every file.
  With season releases in Sonarr, that would mean several script runs for a
  multi-episode-import. "On Import Complete" runs just one, after all
  episodes of your import have been processed.

sonarr-airdate
--------------
  Sonarr will consider all episode without airdates not to be released, yet.
  While that works mostly as intended, it is preventing ended series with
  poorly curated data to be downloaded completely.
  This script will find those episodes that don't have an airdate and print
  them out nicely so you can fill in the missing data on TheTVDB.

sonarr-orphan
-------------
  Metadata for Sonarr is provided from TheTVDB. While that is mostly very
  well curated, sometimes episodes or specials get renamed/removed/renumbered.
  This can lead to the situation, that you end up with orphand files on your
  harddrive (e.g. last episode of a season is a Christmas special and gets
  moved to specials-season after it was already downloaded).
  This is where sonarr-orphan comes in. It lists all orphand files in your
  collection, ordered by show, season and episode. That way you can easily
  find those poor little orphans and deal with them.
  
