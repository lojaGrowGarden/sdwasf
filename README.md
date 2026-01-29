local Window = Rayfield:CreateWindow({
   Name = "baiano Hub",
   Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "carregando dados do script",
   LoadingSubtitle = "by baiano",
   ShowText = "Baiano Hub", -- for mobile users to unhide rayfield, change if you'd like
   Theme = "Amethyst", -- Check https://docs.sirius.menu/rayfield/configuration/themes

   ToggleUIKeybind = "K", -- The keybind to toggle the UI visibility (string like "K" or Enum.KeyCode)

   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },

   Discord = {
      Enabled = true, -- Prompt the user to join your Discord server if their executor supports it
      Invite = "https://discord.gg/DSBWkunrxA", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },

   KeySystem = true, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key system",
      Note = "No method of obtaining the key is provided", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"baiano"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})



local maintab = Window:CreateTab("maintab", "rewind")
Rayfield:Notify({
   Title = "script funcionando",
   Content = "criado por baiano",
   Duration = 6.5,
   Image = 4483362458,
})
local hello word button = maintab:CreateButton({
   Name = "hello word",
   Callback = function()
  print("hello word")
   end,
})

local Players = game:GetService("Players")
local player = Players.LocalPlayer

local SPEED_NORMAL = 16
local JUMP_NORMAL = 50

local SPEED_FLY = 100   -- velocidade alta
local JUMP_FLY = 150    -- pulo alto

local fly = Tab:CreateToggle({
   Name = "Fly (speed + jump)",
   CurrentValue = false,
   Flag = "fly",
   Callback = function(Value)
      local character = player.Character or player.CharacterAdded:Wait()
      local humanoid = character:WaitForChild("Humanoid")

      if Value then
         humanoid.WalkSpeed = SPEED_FLY
         humanoid.JumpPower = JUMP_FLY
      else
         humanoid.WalkSpeed = SPEED_NORMAL
         humanoid.JumpPower = JUMP_NORMAL
      end
   end,
})

local Players = game:GetService("Players")
local player = Players.LocalPlayer

local Players = game:GetService("Players")
local player = Players.LocalPlayer

local Slider = maintab:CreateSlider({
   Name = "WalkSpeed",
   Range = {50-200},
   Increment = 10,
   Suffix = "Bananas",
   CurrentValue = 20,
   Flag = "WalkSpeed",
   Callback = function(Value)
      local character = player.Character or player.CharacterAdded:Wait()
      local humanoid = character:WaitForChild("Humanoid")

      humanoid.WalkSpeed = Value
   end,
})
