# Team Fortress 2 Vehicles
This is a plugin that allows spawning driveable vehicles based on `prop_vehicle_driveable` in Team Fortress 2.

While this has been done before, this implementation is vastly different.
Instead of simulating user input on the vehicle through the entity I/O system, this implementation forwards your user input directly to the vehicle, making driving feel incredibly smooth.

This plugin bundles the required entity fixes and a few configurable nice-to-have features.

## Features
* Fully functioning vehicles based on `prop_vehicle_driveable`
* Vehicle sounds
* Entry and exit animations
* Physics collisions and damage against other players
* Highly customizable through plugin configuration and ConVars

## Dependencies
* SourceMod 1.10
* [DHooks with Detour Support](https://forums.alliedmods.net/showpost.php?p=2588686&postcount=589)
* [LoadSoundScript](https://github.com/haxtonsale/LoadSoundScript) (optional, used for vehicle sounds)

## Installation
1. Download the latest version from the [releases](https://github.com/Mikusch/tf-vehicles/releases) page
2. Extract the contents of the archive into your server directory
3. Type `sm plugins load vehicles` into your server console or restart your server

## Usage
There is a menu combining all of the plugin's features that can be accessed using `sm_vehicle`.

Additionally, you may use `sm_createvehicle` to create and `sm_destroyvehicle` to remove a vehicle. To remove all vehicles in the map, use `sm_destroyallvehicles`.

## Configuration
The `vehicles.cfg` allows you to add your own vehicles. Each vehicle requires at least a model, a vehicle script, and a vehicle type.

More documentation can be found in the [default configuration](/addons/sourcemod/configs/vehicles/vehicles.cfg).

**Example:**
```
"Vehicles"
{
	"0"
	{
		"name"			"hl2_jeep"
		"display_name"	"#Vehicle_HL2_Jeep"
		"model"			"models/buggy.mdl"
		"skin"			"0"
		"vehiclescript"	"scripts/vehicles/jeep_test.txt"
		"type"			"car_wheels"
	}
}
```

## Physics Damage
This plugin will automatically enable physics collisions and damage to allow vehicles to collide with other players.

If you intend to use these vehicles in a friendly environment without any combat aspects, make sure to set `sv_turbophysics` to `1`. It will allow vehicles to pass through other players.
