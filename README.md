## Rayfield

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


-----------------------------------------------------------------------------------------------------------------
## Sense ESP Library
To use Sense, you must first define it:
```lua
local Sense = loadstring(game:HttpGet('https://sirius.menu/sense'))()
```
You can change the configuration:
```lua
Sense.teamSettings.enemy.enabled = true
Sense.teamSettings.enemy.box = true
Sense.teamSettings.enemy.boxColor[1] = Color3.new(0, 0.25, 0.75)
``
Now, this is REQUIRED. You can put this anywhere, but it's recommended to put it at the end of your script (like rayfield's load config)
```lua
Sense.Load()
```
You can un-load it via **Sense.Unload()** if you want.
Anyways, now for the main configuration. Put this **under** Sense Loader, **above** Sense.Load
```lua
Sense = {
  whitelist = {}, -- When this table contains at least 1 user id, it will only show esp for those players.
  sharedSettings = {
      textSize = 13,
      textFont = 2,
      limitDistance = false, -- Set a maximum render distance
      maxDistance = 150,
      useTeamColor = false -- Change all colors to the players team color
  },
  teamSettings = {
      enemy = {
          enabled = false,
          box = false,
          boxColor = { Color3.new(1,0,0), 1 },
          --boxColor = { "Team Color", 1 }, -- Do this to change a single color to the team color
          boxOutline = true,
          boxOutlineColor = { Color3.new(), 1 },
          boxFill = false,
          boxFillColor = { Color3.new(1,0,0), 0.5 },
          healthBar = false,
          healthyColor = Color3.new(0,1,0),
          dyingColor = Color3.new(1,0,0),
          healthBarOutline = true,
          healthBarOutlineColor = { Color3.new(), 0.5 },
          healthText = false,
          healthTextColor = { Color3.new(1,1,1), 1 },
          healthTextOutline = true,
          healthTextOutlineColor = Color3.new(),
          box3d = false,
          box3dColor = { Color3.new(1,0,0), 1 },
          name = false,
          nameColor = { Color3.new(1,1,1), 1 },
          nameOutline = true,
          nameOutlineColor = Color3.new(),
          weapon = false,
          weaponColor = { Color3.new(1,1,1), 1 },
          weaponOutline = true,
          weaponOutlineColor = Color3.new(),
          distance = false,
          distanceColor = { Color3.new(1,1,1), 1 },
          distanceOutline = true,
          distanceOutlineColor = Color3.new(),
          tracer = false,
          tracerOrigin = "Bottom",
          tracerColor = { Color3.new(1,0,0), 1 },
          tracerOutline = true,
          tracerOutlineColor = { Color3.new(), 1 },
          offScreenArrow = false,
          offScreenArrowColor = { Color3.new(1,1,1), 1 },
          offScreenArrowSize = 15,
          offScreenArrowRadius = 150,
          offScreenArrowOutline = true,
          offScreenArrowOutlineColor = { Color3.new(), 1 },
          chams = false,
          chamsVisibleOnly = false,
          chamsFillColor = { Color3.new(0.2, 0.2, 0.2), 0.5 },
          chamsOutlineColor = { Color3.new(1,0,0), 0 },
      },
      friendly = {
          enabled = false,
          box = false,
          boxColor = { Color3.new(0,1,0), 1 },
          boxOutline = true,
          boxOutlineColor = { Color3.new(), 1 },
          boxFill = false,
          boxFillColor = { Color3.new(0,1,0), 0.5 },
          healthBar = false,
          healthyColor = Color3.new(0,1,0),
          dyingColor = Color3.new(1,0,0),
          healthBarOutline = true,
          healthBarOutlineColor = { Color3.new(), 0.5 },
          healthText = false,
          healthTextColor = { Color3.new(1,1,1), 1 },
          healthTextOutline = true,
          healthTextOutlineColor = Color3.new(),
          box3d = false,
          box3dColor = { Color3.new(0,1,0), 1 },
          name = false,
          nameColor = { Color3.new(1,1,1), 1 },
          nameOutline = true,
          nameOutlineColor = Color3.new(),
          weapon = false,
          weaponColor = { Color3.new(1,1,1), 1 },
          weaponOutline = true,
          weaponOutlineColor = Color3.new(),
          distance = false,
          distanceColor = { Color3.new(1,1,1), 1 },
          distanceOutline = true,
          distanceOutlineColor = Color3.new(),
          tracer = false,
          tracerOrigin = "Bottom",
          tracerColor = { Color3.new(0,1,0), 1 },
          tracerOutline = true,
          tracerOutlineColor = { Color3.new(), 1 },
          offScreenArrow = false,
          offScreenArrowColor = { Color3.new(1,1,1), 1 },
          offScreenArrowSize = 15,
          offScreenArrowRadius = 150,
          offScreenArrowOutline = true,
          offScreenArrowOutlineColor = { Color3.new(), 1 },
          chams = false,
          chamsVisibleOnly = false,
          chamsFillColor = { Color3.new(0.2, 0.2, 0.2), 0.5 },
          chamsOutlineColor = { Color3.new(0,1,0), 0 }
      }
  }
}
```
Okay, that's a long one... but that's the useful part of the library.
Game Functions, these are our game specific functions, you're required to modify these for games that use custom replication systems such as Phantom Forces.
```lua
function EspInterface.getWeapon(player)
    return "Unknown";
end

function EspInterface.isFriendly(player)
    return player.Team and player.Team == localPlayer.Team;
end

function EspInterface.getTeamColor(player)
    return player.Team and player.Team.TeamColor and player.Team.TeamColor.Color;
end

function EspInterface.getCharacter(player)
    return player.Character;
end

function EspInterface.getHealth(player)
    local character = player and EspInterface.getCharacter(player);
    local humanoid = character and findFirstChildOfClass(character, "Humanoid");
    if humanoid then
        return humanoid.Health, humanoid.MaxHealth;
    end
    return 100, 100;
end
```
And if you want ESP for a part in a game, you can do this, but, make sure the part exists.:
```lua
local object = Sense.AddInstance(workspace.Part, {
    --enabled = false, -- enable it here
    text = "{name}", -- Placeholders: {name}, {distance}, {position}
    textColor = { Color3.new(1,1,1), 1 },
    textOutline = true,
    textOutlineColor = Color3.new(),
    textSize = 13,
    textFont = 2,
    limitDistance = false,
    maxDistance = 150
})
object.options.enabled = false
```
