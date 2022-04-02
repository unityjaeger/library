## how to use very cool library

### Client
```lua
client:Character()
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
