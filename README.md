## hi enjoy this stupid write thing

To start using rayfield, you must load the Rayfield library with:
```lua
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
```
If you want to enable configuration saving + loading, put:
### Rayfield:LoadConfiguration()
at the bottom of your code.
Now, let's make our Window, to do that, add this under "local Rayfield"
```lua
local Window = Rayfield:CreateWindow({
   Name = "Window",
   Icon = 0,
   LoadingTitle = "Title",
   LoadingSubtitle = "Subtitle",
   ShowText = "",
   Theme = "Default",
   ToggleUIKeybind = "K",
   DisableRayfieldPrompts = true,
   DisableBuildWarnings = true,
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil,
      FileName = "Your Hub Name"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink",
      RememberJoins = true
   },
   KeySystem = false,
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key",
      SaveKey = true,
      GrabKeyFromSite = false,
      Key = {"Hello"}
   }
})
```
