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
