### GD Recreation [BETA] is NOT affilated by Geometry dash or Robtop.

# gd_tunnel
I have created this repo as a documentation for my [roblox game!](https://www.roblox.com/games/130195943844260)

The API mentioned only works if I have my servers running, which is rarely, and is actually just a free cloudflare tunnel, cuz i'm broke.

## USAGE

Request body is application/json

### /download-level
Downloads a level's raw data

### POST

To use this, you should have a table with "level_id" as a key, with a string. Like this:

{
  
  "level_id": "string"

}

### /obtain-levels/{path}
Uses GD browser's level search API

### GET

This just redirects you to [API]/obtain-levels/{path} to gdbrowser.com/api/{path}
Search up its documentation for actual documentation!
