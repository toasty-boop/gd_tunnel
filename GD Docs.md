# GD Docs

This file is about things I learnt about GD while I was recreating it in ROBLOX, and might come in handy if you ever need it.

### NOTE: The player in my game is precisely (2,2,0.03) in size. This makes the "studs per sec" go double the speed.



# Variables

## Speed

0.5x speed (Or 2nd speed portal in-game) = 16.7364016736 studs per sec (considering player size), or 8.3682008368 gd blocks per sec.

1x speed (Or 1st speed portal in-game) = 20.7522697796 studs per sec (considering player size), or 10.3761348898 gd blocks per sec.

2x speed (Or 3rd speed portal in-game) = 25.806451613 studs per sec (considering player size), or 12.9032258065 gd blocks per sec.

3x speed (Or 4th speed portal in-game) = 31.1890838206 studs per sec (considering player size), or 15.5945419103 gd blocks per sec.

4x speed (Or 5th speed portal in-game) = 38.3693045564 studs per sec (considering player size), or 19.1846522782 gd blocks per sec.

## Delta

Delta was used in my roblox game to mantain a balance between lag. This is because my game's speed would vary with lag, otherwise——Which would be terrible.
To obtain the delta, I used roblox's "Run Service".RenderStepped(dt) function.

(EXAMPLE)
dt = delta * timewarp
		
Although this is good enough, (ONLY) android slows the game down the more lag you have. I recreated this by capping the dt at 1/30, meaning more dt will not count.

if 1 / delta < 30 then
	dt = 1 / 30
end

Variables:

Cube:
Gravity: 14.4 units per second, or 1.2 units per frame (with 12 FPS)

Ship: 

Gravity: -69.8 units per second, or -5.8 units per frame (with 12 FPS)
Jump Height: 112 units per second, or 9.33333333333 units per frame (with 12 FPS)
Max Gravity Speed: -29 units per frame
Max Jump Speed 36 units per frame

# Downloading and loading.

### GD uses this exact API to download levels! (http://www.boomlings.com/database/downloadGJLevel22.php)

To actually obtain requests from online levels, you have to establish these things. (Some aren't required, but I really don't care.)

payload = {
        "gameVersion": "22",
        "binaryVersion": "35",
        "gdw": "0",
        "levelID": level_id,
        "secret": "Wmfd2893gb7"
    }

### Make sure you set user agent to an empty string. Otherwise, cloudflare WILL prevent the request from being made. Also, use the post request type!!

Next, It will give you something like this;

1:123456:2:My Level:3:PlayerName:4:H4sIAAAAA...==:9:100:10:50

Imagine the request as a weirdly encoded table; Everything before the first ":" is the key, and everything before the second ":" is the data. Repeats. Sooo.. This request would be decoded as so;
{
	1 = "123456",
	2 = "My Level",
	3 = "PlayerName",
	4 = "H4sIAAAAA..,
	9 = "100",
	10 = "50",
}

I won't get into much detail what much means, but all we need is the number 4, since it's the raw encoded level data.

### To fully decode it, You will need to base64 decode the level data, and then zlib decompress it.

After that, it's as simple as just sending the result off to roblox studio.

## Textures

I used Geometry dash's gamesheet images to obtain all of my textures. You may find them [here!](https://github.com/toasty-boop/gd_tunnel/tree/main/ingame_textures)
