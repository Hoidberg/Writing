<h1 align="center">Snippets</h1>

```lua
local s = "the quick fox jumps over the lazy dog"
local t = {}

for i,v in utf8.graphemes(s) do 
	local graphemes = s:sub(i, v) 
	table.insert(t, v, string.upper(graphemes))
end

print(table.concat(t, " "))
```
