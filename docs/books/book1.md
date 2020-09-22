<h1 align="center">Snippets</h1>

<p>Line Spacer</p>

```lua
local s = "the quick fox jumps over the lazy dog"
local t = {}

for i,v in utf8.graphemes(s) do 
	local graphemes = s:sub(i, v) 
	table.insert(t, v, string.upper(graphemes))
end

print(table.concat(t, " "))
```

<p>Luckometer</p>

```lua
while wait(0.5) do
	local chance = math.random()
	if math.floor(chance) == 1 then
		print("lucky")
	else
		print("unlucky")
	end
end
```

<p>CharacterMesh Remover</p>

```lua
local RunService = game:GetService("RunService")

RunService.RenderStepped:Connect(function()
	-- check if the script is in the players character
	if script.Parent:IsA("Model") and script.Parent:FindFirstChild("Humanoid") then
		for _,v in ipairs(script.Parent:GetChildren()) do
			if v:IsA("CharacterMesh") then
				v:Destroy()
			end
		end
		script:Destroy()
	end
end)
```

<p>Mouse Changer</p>

```lua
local ICONS = {
	FirstPersonIcon = "rbxassetid://5380228628",
	ThirdPersonIcon = "rbxassetid://5380234202"
}

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")

local player = Players.LocalPlayer
local camera = workspace.CurrentCamera
local head = game.Players.LocalPlayer.Character:WaitForChild("Head")
local mouse = player:GetMouse()

local function IsFirstPerson()
     return (head.CFrame.p - camera.CFrame.p).Magnitude < 4.5
end

RunService.RenderStepped:Connect(function()
	if not IsFirstPerson() then
		mouse.Icon = ICONS.ThirdPersonIcon
	elseif IsFirstPerson() then
		mouse.Icon = ICONS.FirstPersonIcon
	end
end)
```
