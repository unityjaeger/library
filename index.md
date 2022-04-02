# how to use very cool library
## Main Script
```lua
local ESP = library:Import("ESP")
```
returns the library u want to import (check core script for all libraries)

## Client
```lua
local char = client:Character()
```
returns the Player Character
```lua
client:Root(function(root)
  print(root)
end)
```
returns the HumanoidRootPart if no function is given, if a function is given the function will be run while passing the HumanoidRootPart to the function
```lua
client:Humanoid(function(humanoid)
  print(humanoid)
end, true)
```
returns the Humanoid if no function is given, if a function is given the function will be run while passing the Humanoid to the function, 2nd argument is whether to check if the Humanoid is alive or not
```lua
client:Teleport(CFrame.new(0, 10, 0))
```
Teleports u to the passed cframe
```lua
client:Tween(CFrame.new(0, 10, 0), 120, function()
  print("arrived!")
end)
```
Tweens u to the passed cframe, with the 2nd argument being the speed and the 3rd argument being a function that if given, will fire upon arriving at the destination
```lua
client:Noclip(true)
```
toggles Noclip
```lua
client:Float(true)
```
toggles Float (no gravity midair)

## File Saving
```lua
local folder = file.Folder(name)
```
creates a folder if no folden exists, else it uses existing folder
```lua
local default = {
  example = true;
}
local data = folder:Get(default)
print(data.Data) --> {example = true}
default.example = false
data:Update(default)
print(data.Data --> {example = false}
```
:Get returns a file, if it doesnt exist it will create the file with the default argument, :Update sets the files data to the new table given

## Blocker
```lua
blocker:Block(game.Players.LocalPlayer.Idled)
blocker:Block(require(module).Function)
blocker:Block(game.ReplicatedStorage.RemoteEvent) --or RemoteFunction, both work
blocker:Block("RemoteEvent")
```
these are all the type of signals, functions, events that the Blocker can stop from calling
```lua
blocker:Unblock(game.Players.LocalPlayer.Idled)
--...
```
Unblocks given signal, function, event that is being Blocked

## ESP
```lua
local Settigns = {
  Color = Color3.fromRGB(255, 0, 0);
  Transparency = 1; --1 is fully visible, 0 is invisible
  TextSize = 18;
  Outline = true;
  OutlineColor = Color3.fromRGB(0, 255, 0);
  Font = "Monospace"; --Plex, UI, System, Monospace
  self.Distance = true; --show distance between part and u
  self.Health = true; --display health if the model has a humanoid
}

local base = esp.Base(Settings)
--add a renderer for all esp objects connected to this
base:Add(game.Players.LocalPlayer.Character, "Custom Name", game.Players.LocalPlayer.Character.Head)
--adds esp to the character, can give character or a part as 1st argument, 2nd argument is if u want a custom name, else it uses the part/character name, 3rd argument is from which part to align the esp position
Settings.TextSize = 24
base:UpdateSettings(Settings)
--self explanatory
base:Remove(game.Players.LocalPlayer.Character)
--forcefully remove a esp object
base:Purge()
--remove all esp objects
