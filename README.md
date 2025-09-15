## THIS IS FOR PEOPLE WHO ALREADY KNOW WHAT THE FEATURES DO!!!

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

To create a tab, put this anywhere, as long as it's under the window.
```lua
local Tab = Window:CreateTab("Tab", 0)
```


To create a section, put this anywhere, as long as it's under the tab.
```lua
local Section = Tab:CreateSection("Section")
```
To update a section, you can:
```lua
Section:Set("Updated Section")
```
To create a divider, put this anywhere as long as it's under your tab.
```lua
local Divider = Tab:CreateDivider()
```
To update a divider:
```lua
Divider:Set(false)
```


If you want to change the Iterface's visibility, you can do these:

Setting visibility
```lua
Rayfield:SetVisibility(false)
```
Getting visibility
```lua
Rayfield:IsVisible()
```
Destroying Interface
```lua
Rayfield:Destroy()
```


For themes, you can use this:
```lua
Window.ModifyTheme('ThemeIdentifier')
```
Here are the available themes:
```
Theme Name - ThemeIdentifier

Default - Default
Amber Glow - AmberGlow
Amethyst - Amethyst
Bloom - Bloom
Dark Blue - DarkBlue
Green - Green
Light - Light
Ocean - Ocean
Serenity - Serenity
```
Let's start adding elements to our tabs, but before that, .you can use this to notify the user
```lua
Rayfield:Notify({
   Title = "Notif Title",
   Content = "Notif Content",
   Duration = 5,
   Image = 0,
})
```
Now, let's add elements.
Creating a button:
```lua
local Button = Tab:CreateButton({
   Name = "Button",
   Callback = function()
   
})
```
Updating a button:
```lua
Button:Set("Updated Button")
```

Creating a toggle:
```lua
local Toggle = Tab:CreateToggle({
   Name = "Toggle",
   CurrentValue = false,
   Flag = "Toggle_1",
   Callback = function(Value)
   
   end,
})
```
Updating a toggle:
```lua
Toggle:Set(false)
```

Creating a color picker
```lua
local ColorPicker = Tab:CreateColorPicker({
    Name = "Color Picker",
    Color = Color3.fromRGB(255,255,255),
    Flag = "color_picker_1",
    Callback = function(Value)

    end
})
```
Updating a color picker:
```lua
ColorPicker:Set(Color3.fromRGB(255,255,255)
```

Creating a slider
```lua
local Slider = Tab:CreateSlider({
   Name = "Slider",
   Range = {0, 100},
   Increment = 1,
   Suffix = "Studs",
   CurrentValue = 10,
   Flag = "Slider_1",
   Callback = function(Value)
   
   end,
})
```
Updating a slider
```lua
Slider:Set(67)
```

Creating a textbox (or input)
```lua
local Input = Tab:CreateInput({
   Name = "Input",
   CurrentValue = "",
   PlaceholderText = "Placeholder",
   RemoveTextAfterFocusLost = false,
   Flag = "Input_1",
   Callback = function(Text)

   end,
})
```
Updating a textbox (or input)
```lua
Input:Set("Updated")
```

Creating a dropdown
```lua
local Dropdown = Tab:CreateDropdown({
   Name = "Dropdown",
   Options = {"Option 1","Option 2"},
   CurrentOption = {"Option 1"},
   MultipleOptions = false,
   Flag = "dropdown_1",
   Callback = function(Options)

   end,
})
```
Updating a dropdown
```lua
Dropdown:Set({"Option 2"})
```
Refreshing a dropdown with new options
```lua
Dropdown:Refresh({"New Option 1","New Option 2"})
```

Creating a keybind
```lua
local Keybind = Tab:CreateKeybind({
   Name = "Keybind",
   CurrentKeybind = "Q",
   HoldToInteract = false,
   Flag = "Keybind_1",
   Callback = function(Keybind)
   
   end,
})
```
Updating a keybind
```lua
Keybind:Set("RightCtrl")
```


Now for last... Text-based elements

Creating a label
```lua
local Label = Tab:CreateLabel("Label Example", 0, Color3.fromRGB(255, 255, 255), false)
```
Updating a label
```lua
Label:Set("Updated Label), 0, Color3.fromRGB(67, 67, 67), false)
```
Creating a Paragraph
```lua
local Paragraph = Tab:CreateParagraph({Title = "Paragraph Example", Content = "Paragraph Example"})
```
Updating a Paragraph
```lua
Paragraph:Set({Title = "Paragraph Example", Content = "Paragraph Example"})
```
