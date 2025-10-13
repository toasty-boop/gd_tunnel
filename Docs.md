# GD Docs

This file is about things I learnt about GD while I was recreating it in ROBLOX, and might come in handy if you ever need it.

The player in my game is precisely (2,2,0.03) in size.

# Variables

(NOTE THAT THE FOLLOWING INFORMATION IS ONLY IN 1X SPEED)

The player jumps around ~2.35 in jump_height, with 0.43 seconds of air time (0.35 seconds if mini)
Meaning, the gravity is around ~ (8*(jump_height * 2) / (air_time ^ 2))  AKA, around ~203.35316387236347 is subtracted every second.

To calculate the jump boost, just obtain -gravity * airtime / 2.15

To obtain speeds

local speeds = {
	[1] = 16.7364016736,
	[2] = 20.7522697796,
	[3] = 25.806451613,
	[4] = 31.1890838206,
	[5] = 38.3693045564,
}
