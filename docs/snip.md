<h1 align="center">Snippets</h1>

```lua
local test = "the quick fox jumps over the lazy dog"
local t = {}

for first, last in utf8.graphemes(test) do 
	local graphemes = s:sub(first, last) 
	table.insert(t, last, string.upper(graphemes))
end

print(table.concat(t, " "))
```
