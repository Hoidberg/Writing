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
