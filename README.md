These are Bash scripts to manage my Sonarr/Radarr media library.

sonarr-airdate
--------------
  Sonarr will consider all episode without airdates not to be released, yet.
  While that works mostly as intended, it is preventing ended series with
  poorly curated data to be downloaded completely.
  This script will find those episodes that don't have an airdate and print
  them out nicely so you can fill in the missing data on TheTVDB.

sonarr-newflag
--------------
  This one is designed to be run as a Sonarr Connect Script. Whenever a new
  episode is added, it will add a tag to the series, thereby marking it for
  later conversion by sonar-convert.

sonarr-orphan
-------------
  Metadata for Sonarr is provided from TheTVDB. While that is mostly very
  well curated, sometimes episodes or specials get renamed/removed/renumbered.
  This can lead to the situation, that you end up with orphand files on your
  harddrive (e.g. last episode of a season is a Christmas special and gets
  removed after it was already downloaded).
  This is where sonarr-orphan comes in. It lists all orphand files in your
  collection, ordered by show, season and episode. That way you can easily
  find those poor little orphans and deal with them.
  
