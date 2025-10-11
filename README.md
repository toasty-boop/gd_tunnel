# gd_tunnel
I made this for a game in roblox, and was forced to make it public due to roblox banning the datastore on my game.

This API only works if I have my servers running, which is rarely, and is actually just a free cloudflare thing, cuz i'm broke.

Request body is application/json

# /download-level
Downloads a level's raw data

Here's an example of how to use /download-level:
{
  "level_id": "string"
}

# /obtain-levels/{path}
Uses GD browser's level search API

This just redirects you to [API]/obtain-levels/{path} to gdbrowser.com/api/{path}
Search up its documentation
