local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "RC2 Remake",
   Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "Rayfield Interface Suite",
   LoadingSubtitle = "by Sirius",
   ShowText = "Rayfield", -- for mobile users to unhide rayfield, change if you'd like
   Theme = "Default", -- Check https://docs.sirius.menu/rayfield/configuration/themes

   ToggleUIKeybind = "K", -- The keybind to toggle the UI visibility (string like "K" or Enum.KeyCode)

   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "RC2 Remake"
   },

   Discord = {
      Enabled = false, -- Prompt the user to join your Discord server if their executor supports it
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },

   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

Rayfield:Notify({
    Title = "Game Version/info",
    Content = "This was made for beta V.18. You may want to change keybind to open on settings.",
    Duration = 6.5,
    Image = "info",
 })



 local currentTime = os.time()  -- Get the current time in seconds since epoch
local currentDate = os.date("*t", currentTime)  -- Convert to table for easier manipulation

-- Check if today is December 25th
if currentDate.month == 12 and currentDate.day == 25 then
    -- Show Christmas notification using Rayfield UI
    Rayfield:Notify({
        Title = "Merry Christmas! 🎄",
        Content = "Wishing you a joyful and festive day! 🎅",
        Duration = 6.5,  -- Set the duration for how long the notification lasts
        Image = "candy-cane",  -- Optional: Use a custom image for Christmas (replace with an actual ID)
    })
end

local currentTime = os.time()  -- Get the current time in seconds since epoch
local currentDate = os.date("*t", currentTime)  -- Convert to table for easier manipulation

-- Check if today is January 1st
if currentDate.month == 1 and currentDate.day == 1 then
    -- Show New Year notification using Rayfield UI
    Rayfield:Notify({
        Title = "Happy New Year! 🎉",
        Content = "Wishing you a year full of joy and success! 🎆",
        Duration = 6.5,  -- Set the duration for how long the notification lasts
        Image = "party-popper",  -- Optional: Use a custom image for New Year's (replace with an actual ID)
    })
end


local Tab = Window:CreateTab("Client Side/Config", 4483362458) -- Title, Image
 local Section = Tab:CreateSection("Server Stuff")

  local Paragraph = Tab:CreateParagraph({Title = "Methods", Content = "Keep the switch disabled if your server allow you teleporting without issues, else enable to use car method(requires to sit on YOUR car seat). And if you want to teleport to other place, teleport back to your seat(in teleports tab). Also you may want to use Snowstorm to jump and ragdoll in open spaces, then teleport with player method, you may want to spam click."})
 local Toggle = Tab:CreateToggle({
    Name = "Teleport Method(Car seat/Player)",
    CurrentValue = true,
    Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        USE_LEGACY_PLAYER_TELEPORT = Value
    end,
 })

  -- Pega os valores atuais do clima uma única vez
  local weatherState = workspace.ServerData.WeatherState
  local currentClouds = weatherState.Value
  local currentFog = weatherState.Foggy.Value
  local currentRain = weatherState.Raining.Value

  -- Cria os sliders com os valores iniciais
  Tab:CreateSlider({
      Name = "Clouds",
      Range = {0, 1},
      Increment = 0.1,
      Suffix = "Clouds",
      CurrentValue = currentClouds,
      Flag = "Clouds",
      Callback = function(Value)
          weatherState.Value = Value
      end,
  })

  Tab:CreateSlider({
      Name = "Fog",
      Range = {0, 1},
      Increment = 0.1,
      Suffix = "Fog",
      CurrentValue = currentFog,
      Flag = "Fog",
      Callback = function(Value)
          weatherState.Foggy.Value = Value 
      end,
  })

  Tab:CreateSlider({
      Name = "Rain",
      Range = {0, 1},
      Increment = 0.1,
      Suffix = "Rain",
      CurrentValue = currentRain,
      Flag = "Rain",
      Callback = function(Value)
          weatherState.Raining.Value = Value 
      end,
  })
 local Toggle = Tab:CreateToggle({
    Name = "Edited Weather",
    CurrentValue = false,
    Flag = "EditedWeather",
    Callback = function(Value)
        workspace.ServerData.WeatherState:SetAttribute("Edited", Value)
    end,
 })

 local Toggle = Tab:CreateToggle({
    Name = "Snowed Out",
    CurrentValue = false,
    Flag = "SnowedOut",
    Callback = function(Value)
        workspace.ServerData.WeatherState:SetAttribute("SnowedOut", Value)
    end,
 })

 local Toggle = Tab:CreateToggle({
    Name = "Snowstorm",
    CurrentValue = false,
    Flag = "Snowstorm",
    Callback = function(Value)
        workspace.ServerData.WeatherState:SetAttribute("Snowstorm", Value)
    end,
 })

 local Toggle = Tab:CreateToggle({
    Name = "Frozen Time",
    CurrentValue = false,
    Flag = "FrozenTime",
    Callback = function(Value)
        workspace.ServerData.FrozenTime.Value = Value
    end,
 })

 local Button = Tab:CreateButton({
    Name = "ClockPass",
    Callback = function()
        game:GetService("Players").LocalPlayer.Values._ClockPass.Value = 1
        end,
 })
 local Slider = Tab:CreateSlider({
    Name = "Drown Damage",
    Range = {0, 100},
    Increment = 1,
    Suffix = "DD",
    CurrentValue = 10,
    Flag = "DD", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        workspace.ServerData.Configuration.DrownDamage.Value = Value
        end,
 })

 local Button = Tab:CreateButton({
    Name = "Kill(Keep Items)",
    Callback = function()
        game:GetService("ReplicatedStorage"):WaitForChild("Events"):WaitForChild("RequestCharacterReset"):FireServer()
    end,
 })


local Players = game:GetService("Players")
local player = Players.LocalPlayer


        for i, v in pairs(workspace.Plots:GetChildren()) do
            local ownerObject = v:FindFirstChild("Owner")
            
            if ownerObject and ownerObject:IsA("ObjectValue") then
                -- Convertendo valores para string e removendo espaços
                local ownerValue = tostring(ownerObject.Value):gsub("^%s*(.-)%s*$", "%1")  -- Remove espaços antes e depois
                local playerName = tostring(game.Players.LocalPlayer.Name):gsub("^%s*(.-)%s*$", "%1")  -- Remove espaços antes e depois
                
                -- Comparação direta
                if ownerValue == playerName then
                    print("You own:", v.Name)
                    _G.ownedPlot = v
                end
            end
        end

-- Function to find a seat owned by the player
local function findDriverSeat(vehicle)
    for _, part in ipairs(vehicle:GetDescendants()) do
        if part:IsA("VehicleSeat") or part:IsA("Seat") then
            if part:FindFirstChild("Owner") then
                if part.Owner.Value == player or tostring(part.Owner.Value) == tostring(player.UserId) then
                    return part
                end
            elseif vehicle:FindFirstChild("Owner") then
                return part
            end
        end
    end
    return nil
end

-- Function to get the player's vehicle seat
local function getMyVehicleSeat()
    if not workspace:FindFirstChild("Vehicles") then return nil end

    for _, vehicle in ipairs(workspace.Vehicles:GetChildren()) do
        if vehicle:IsA("Model") and vehicle:FindFirstChild("Owner") then
            local ownerValue = vehicle.Owner
            if ownerValue and (ownerValue.Value == player or tostring(ownerValue.Value) == tostring(player.UserId)) then
                local seat = findDriverSeat(vehicle)
                if seat then return seat end
            end
        end
    end
    return nil
end

local function getSeatWeld()
    local mySeat = getMyVehicleSeat()
    if mySeat then
        local weld = mySeat:FindFirstChild("SeatWeld")
        if weld then
            return weld
        end
    end
    return nil
end

local function updateWeldPart0(newPart)
    local weld = getSeatWeld()
    if weld and newPart then
        weld.Part0 = newPart
        weld.C0 = CFrame.new(0, 0, 0)
        print("Weld atualizado para o novo Part0.")
    elseif not weld then
        warn("Weld (SeatWeld) não encontrado!")
    elseif not newPart then
        warn("Novo Part0 não encontrado!")
    end
end

local function teleportToLocation(target)
    if not target then return end

    local player = game.Players.LocalPlayer
    local hrp = player.Character and player.Character:FindFirstChild("HumanoidRootPart")

    if USE_LEGACY_PLAYER_TELEPORT and hrp then
        -- Se "target" já for um CFrame, usar diretamente
        if typeof(target) == "CFrame" then
            hrp.CFrame = target
        elseif typeof(target) == "Instance" and target:IsA("BasePart") then
            hrp.CFrame = target.CFrame
        end
    else
        updateWeldPart0(target)
    end
end

-- Function to get the current identity level
local function getIdentityLevel()
    return syn and syn.get_thread_identity and syn.get_thread_identity() or getidentity and getidentity() or 3
end

-- Check if the identity level is 4 or higher
local identityLevel = getIdentityLevel()
local exploitSupported = identityLevel >= 4

if not exploitSupported then
    Rayfield:Notify({
        Title = "Warning",
        Content = "Your exploit's execution level is insufficient. Some features may not work correctly.",
        Duration = 8.5,
        Image = "alert-circle",
    })
end
 -- Create the main tabs
local Tab = Window:CreateTab("Perfect Hit", 4483362458) -- Tab for Perfect Hit settings

-- Add a paragraph explaining the differences
local Paragraph = Tab:CreateParagraph({
    Title = "Perfect Hit", 
    Content = "If you see 2 Perfect Hits, it means your exploit supports both methods. However, if you only see one, it means your exploit doesn't support the required functions."
})

-- If exploit functions are available, create the toggle
local enabled = false  -- Default state is disabled

if exploitSupported then
    local Toggle = Tab:CreateToggle({
        Name = "Perfect Hit",
        CurrentValue = false,
        Flag = "PH", -- Flag to save state
        Callback = function(Value)
            enabled = Value -- Update the enabled state based on the toggle value
            print("Attack Modification:", enabled and "ON" or "OFF")
        end,
    })

    -- Hook the RemoteEvent
    local mt = getrawmetatable(game)
    local oldNamecall = mt.__namecall

    local success, _ = pcall(function()
        setreadonly(mt, false)
    end)

    if not success then
        Rayfield:Notify({
            Title = "Warning",
            Content = "Your exploit doesn't support setreadonly. Perfect Hit may not work as expected.",
            Duration = 8.5,
            Image = "message-circle-warning",
        })
    end

    mt.__namecall = function(self, ...)
        local method = getnamecallmethod()
        local args = {...}

        if enabled and method == "FireServer" and tostring(self) == "Attack" then
            if type(args[1]) == "table" then
                args[1].Alpha = 1 -- Full damage
                args[1].ResponseTime = 0 -- Instant hit
                --print("Intercepted Attack: Alpha set to 1, ResponseTime set to 0")
            end
            return oldNamecall(self, table.unpack(args))
        end

        return oldNamecall(self, ...)
    end

    -- Attempt to set the metatable back to read-only
    pcall(function()
        setreadonly(mt, true)
    end)
end

-- Create the keybind version (for exploits without required functions)
local Keybind = Tab:CreateKeybind({
    Name = "Perfect Hit (Keybind)",
    CurrentKeybind = "P",
    HoldToInteract = false,
    Flag = "PoorPH", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Keybind)
        if exploitSupported then
            Rayfield:Notify({
                Title = "Warning",
                Content = "Your exploit supports advanced methods. Use the toggle instead.",
                Duration = 8.5,
                Image = "message-circle-warning",
            })
            return
        end
        local ohTable1 = {
            ["Alpha"] = 1,
            ["ResponseTime"] = 0.76456
        }
        game:GetService("ReplicatedStorage").Events.Tools.Attack:FireServer(ohTable1)
    end,
})

-- Add a paragraph explaining the differences
local Paragraph = Tab:CreateParagraph({
    Title = "The differences", 
    Content = "The toggle version can be turned on or off, and you can leave it enabled if you'd like. The keybind version is for exploits that lack the required functions, so you need to press a key to make it work. In this case, click on a tree, rock, or water, and while the power bar is on screen, pressing the key will complete the action with a perfect hit."})

local TabF = Window:CreateTab("Auto Fish", 4483362458) -- Create a new tab for grab settings
local rotationConnection = nil -- Store the rotation connection
local Paragraph = TabF:CreateParagraph({
    Title = "Warning", 
    Content = "This is only for the fishing minigame."
})

local Toggle = TabF:CreateToggle({
    Name = "Auto-Fish",
    CurrentValue = false,
    Flag = "AutoFishToggle",
    Callback = function(Value)
        local fish = game:GetService("Players").LocalPlayer.PlayerGui.UserGui.CatchFrame.Fish
        
        local function fireSide(side)
            game:GetService("ReplicatedStorage"):WaitForChild("Events"):WaitForChild("Tools")
                :WaitForChild("ChangeFishPull"):FireServer({ Side = side })
        end

        -- Disconnect any existing connection when toggling
        if rotationConnection then
            rotationConnection:Disconnect()
            rotationConnection = nil
        end

        if Value then
            local function handleRotation()
                local rotation = math.floor(fish.Rotation % 360)
                if rotation < 0 then rotation = 360 + rotation end

                if rotation == 0 then
                    fireSide("Left")
                elseif rotation == 180 then
                    fireSide("Right")
                elseif rotation == 90 then
                    fireSide("Top")
                elseif rotation == 270 then
                    fireSide("Bottom")
                end
            end

            -- Store the new connection
            rotationConnection = fish:GetPropertyChangedSignal("Rotation"):Connect(handleRotation)
        end
    end,
})


--[[
  AutoFish + AutoGrab Simplificado
  Requer Rayfield (ou outra lib de UI)
--]]
--[[ TODO
-- Serviços
local Players          = game:GetService("Players")
local ReplicatedStorage= game:GetService("ReplicatedStorage")
local RunService       = game:GetService("RunService")
local localPlayer      = Players.LocalPlayer
local player  = Players.LocalPlayer
local gui     = player:WaitForChild("PlayerGui")
local userGui = gui:WaitForChild("UserGui")
local catchFrame = userGui:WaitForChild("CatchFrame")
local MAX_DISTANCE    = 20

-- flag e conexão para o loop de teleporte
local autoTeleportEnabled = false
local teleportConn

-- Função que checa se está dentro do alcance
local function isNearPlayer(part)
    if not localPlayer.Character then return false end
    local root = localPlayer.Character:FindFirstChild("HumanoidRootPart")
    return root and (root.Position - part.Position).Magnitude <= MAX_DISTANCE
end

-- Função de teleporte de um modelo para o plot do jogador
local function teleportToPlot(item)
    if not (_G.ownedPlot and _G.ownedPlot.Plot) then return end
    local plotCFrame = _G.ownedPlot.Plot.CFrame
    item:SetPrimaryPartCFrame(plotCFrame)
end
-- Toggle na UI
local Toggle = TabF:CreateToggle({
    Name         = "Auto-Teleport to Plot (within range)",
    CurrentValue = false,
    Flag         = "AutoTeleportToPlotInRange",
    Callback     = function(state)
        autoTeleportEnabled = state
 
        if state then
            teleportConn = RunService.Heartbeat:Connect(function()
                if not autoTeleportEnabled or not localPlayer.Character then return end
 
                for _, item in ipairs(workspace.Grab:GetChildren()) do
                    if item:IsA("Model") and item.PrimaryPart then
                        -- só teleportar se estiver dentro do alcance
                        if isNearPlayer(item.PrimaryPart) then
                            teleportToPlot(item)
                        end
                    end
                end
            end)
 
        else
            if teleportConn then
                teleportConn:Disconnect()
                teleportConn = nil
            end
        end
    end,
 })
-- Configurações AutoGrab
local COOLDOWN_GRAB   = 0.5
local TARGET_FOLDER   = workspace:WaitForChild("Grab")
local autoGrabEnabled = false

-- Funções AutoGrab
local function isNearPlayer(part)
    if not localPlayer.Character then return false end
    local root = localPlayer.Character:FindFirstChild("HumanoidRootPart")
    return root and (root.Position - part.Position).Magnitude <= MAX_DISTANCE
end

local function findMeshOrPart(parent)
    for _, c in ipairs(parent:GetDescendants()) do
        if c:IsA("BasePart") then return c end
    end
end

local function iniciarAutoGrab()
    coroutine.wrap(function()
        while autoGrabEnabled do
            for _, item in ipairs(TARGET_FOLDER:GetChildren()) do
                if not autoGrabEnabled then break end
                if item:IsA("Model") then
                    local owner = item:FindFirstChild("Owner")
                    if owner and (
                       (owner:IsA("StringValue") and owner.Value == localPlayer.Name) or
                       (owner:IsA("ObjectValue") and owner.Value == localPlayer)
                    ) then
                        local part = findMeshOrPart(item)
                        if part and isNearPlayer(part) then
                            pcall(function()
                                ReplicatedStorage.Events.GrabHandler:InvokeServer(part, "Grab", part.Position)
                                print("Grabbed:", item.Name)
                            end)
                            task.wait(COOLDOWN_GRAB)
                        end
                    end
                end
            end
            task.wait(1)
        end
    end)()
end


-- ===================================================================
-- AutoFish por Zona (versão simplificada)
-- ===================================================================

-- Ferramentas de pesca
local function getTools()
    return ReplicatedStorage:WaitForChild("Events"):WaitForChild("Tools")
end

local folderName = "FLF"
local existingFolder = workspace:FindFirstChild(folderName)

-- Delete the old folder
if existingFolder then
    existingFolder:Destroy()
end

local FFolder = Instance.new("Folder", workspace)-- Parte de referência
FFolder.Name = "FLF"
--local basePart = workspace.MouseIgnore.FishZones.VeilLake:GetChildren()[3] -- substitua "BasePart" pelo nome da sua parte

    -- Criar a nova parte
    local newPart = Instance.new("Part")
    newPart.Size = Vector3.new(4, 1, 4) -- tamanho opcional
    newPart.Anchored = true
    newPart.CanCollide = false
    newPart.Transparency = 1
    newPart.CanTouch = false
    newPart.CanQuery = false
    newPart.Position = Vector3.new(-665.43896484375, 94.5, 1951.5361328125) -- 5 studs acima
    newPart.Name = "VeilLake"
    newPart.Parent = FFolder

-- Parte de referência
--local basePart1 = workspace.MouseIgnore.Water.WaterZones.Swamp -- substitua "BasePart" pelo nome da sua parte

    -- Criar a nova parte
    local newPart = Instance.new("Part")
    newPart.Size = Vector3.new(4, 1, 4) -- tamanho opcional
    newPart.Anchored = true
    newPart.CanCollide = false
    newPart.Transparency = 1
    newPart.CanTouch = false
    newPart.CanQuery = false
    newPart.Position = Vector3.new(1288.9095458984375, -3.566533088684082, 2044.602294921875) 
    newPart.Name = "Swamp"
    newPart.Parent = FFolder

-- Parte de referência
--local basePart2 = workspace.Map.Rosewell.MagmaExitNoDespawn -- substitua "BasePart" pelo nome da sua parte

    -- Criar a nova parte
    local newPart = Instance.new("Part")
    newPart.Size = Vector3.new(4, 1, 4) -- tamanho opcional
    newPart.Anchored = true
    newPart.CanCollide = false
    newPart.Transparency = 1
    newPart.CanTouch = false
    newPart.CanQuery = false
    newPart.Position = Vector3.new(-7504.20947265625, -4.584564208984375, -2419.97607421875)
    newPart.Name = "Sarcophagus"
    newPart.Parent = FFolder
--local basePart3 = workspace.MouseIgnore.Water.WaterZones.CrystalPond -- substitua "BasePart" pelo nome da sua parte

    -- Criar a nova parte
    local newPart = Instance.new("Part")
    newPart.Size = Vector3.new(4, 1, 4) -- tamanho opcional
    newPart.Anchored = true
    newPart.CanCollide = false
    newPart.Transparency = 1
    newPart.CanTouch = false
    newPart.CanQuery = false
    newPart.Position = Vector3.new(-7481.18505859375, -627, 1105.9532470703125) -- 5 studs acima
    newPart.Name = "Crystal"
    newPart.Parent = FFolder

    -- Criar a nova parte
    local newPart = Instance.new("Part")
    newPart.Size = Vector3.new(4, 1, 4) -- tamanho opcional
    newPart.Anchored = true
    newPart.CanCollide = false
    newPart.Transparency = 1
    newPart.CanTouch = false
    newPart.CanQuery = false
    newPart.Position = Vector3.new(-16.649139404296875, -553.4144897460938, 1622.4593505859375) -- 5 studs acima
    newPart.Name = "LushCave"
    newPart.Parent = FFolder
    -- Criar a nova parte
    local newPart = Instance.new("Part")
    newPart.Size = Vector3.new(4, 1, 4) -- tamanho opcional
    newPart.Anchored = true
    newPart.CanCollide = false
    newPart.Transparency = 1
    newPart.CanTouch = false
    newPart.CanQuery = false
    newPart.Position = Vector3.new(350.1985778808594, 206.875, 3612.182861328125) -- 5 studs acima
    newPart.Name = "Jungle"
    newPart.Parent = FFolder

    -- Criar a nova parte
    local newPart = Instance.new("Part")
    newPart.Size = Vector3.new(4, 1, 4) -- tamanho opcional
    newPart.Anchored = true
    newPart.CanCollide = false
    newPart.Transparency = 1
    newPart.CanTouch = false
    newPart.CanQuery = false
    newPart.Position = Vector3.new(3239.537109375, 0, -2120.1630859375) -- 5 studs acima
    newPart.Name = "SmallCoral"
    newPart.Parent = FFolder

    -- Criar a nova parte
    local newPart = Instance.new("Part")
    newPart.Size = Vector3.new(4, 1, 4) -- tamanho opcional
    newPart.Anchored = true
    newPart.CanCollide = false
    newPart.Transparency = 1
    newPart.CanTouch = false
    newPart.CanQuery = false
    newPart.Position = Vector3.new(-2795.35009765625, 0, 584.9410400390625) -- 5 studs acima
    newPart.Name = "BigCoral"
    newPart.Parent = FFolder

    local newPart = Instance.new("Part")
    newPart.Size = Vector3.new(4, 1, 4) -- tamanho opcional
    newPart.Anchored = true
    newPart.CanCollide = false
    newPart.Transparency = 1
    newPart.CanTouch = false
    newPart.CanQuery = false
    newPart.Position = Vector3.new(-7207.99365234375, -610.065673828125, -2828.533935546875) -- 5 studs acima
    newPart.Name = "Magma"
    newPart.Parent = FFolder

-- Tabela de zonas
local locais = {
    CrystalPond = {
        Lugar    = FFolder.Crystal,
        hitPosition = Vector3.new(-7488.06005859375, -644.4749755859375, 1084.1500244140625), --fix
        toggle      = false
    },
    BigCoral = {
        Lugar    = FFolder.BigCoral,
        hitPosition = Vector3.new(-2795.201416015625, -5.974999904632568, 581.2570190429688), --fix
        toggle      = false
    },
    SmallCoral = {
        Lugar    = FFolder.SmallCoral,
        hitPosition = Vector3.new(3239.78369140625, -5.974999904632568, -2123.648193359375),
        toggle      = false
    },
    Jungle = {
        Lugar    = FFolder.Jungle, 
        hitPosition = Vector3.new(352.3348083496094, 208.94345092773438, 3609.23583984375), 
        toggle      = false
    },
    LushCave = {
        Lugar    = FFolder.LushCave,
        hitPosition = Vector3.new(-14.756388664245605, -551.389404296875, 1618.079345703125), --fix
        toggle      = false
    },
    Sarcophagus = {
        Lugar    = FFolder.Sarcophagus,
        hitPosition = Vector3.new(-7511.8154296875, -5.974999904632568, -2423.219970703125),
        toggle      = false
    },
    Swamp = {
        Lugar    = FFolder.Swamp,
        hitPosition = Vector3.new(1300.220947265625, -6.04153299331665, 2046.1671142578125), --fix
        toggle      = false
    },
    Veillake = {
        Lugar    = FFolder.VeilLake,
        hitPosition = Vector3.new(-662.387451171875, 89.349609375, 1950.559814453125), --fix
        toggle      = false
    }
}

-- Função de pesca simplificada
local function iniciarPesca(localNome)
    local dados = locais[localNome]
    coroutine.wrap(function()
        local tools = getTools()
        while dados.toggle do
            -- 1) Teleporta
            local hrp = localPlayer.Character and localPlayer.Character:FindFirstChild("HumanoidRootPart")
            if hrp then
                teleportToLocation(dados.Lugar)
        end
            task.wait(1)

            -- 3) Charge (lançar isca)
            pcall(function()
                tools.Charge:FireServer({HitPosition = dados.hitPosition})
            end)

            -- 4) Aguarda “morder” — use um timeout fixo
            task.wait(1.5)

            -- 5) Attack (puxar peixe)
            pcall(function()
                tools.Attack:FireServer({Alpha = 1, ResponseTime = 2})
            end)

            -- 6) Aguarda cooldown antes da próxima pescaria
            repeat task.wait(0.1) until catchFrame.Visible
            repeat task.wait(2) until not catchFrame.Visible
        end
    end)()
end

TabF:CreateParagraph({
    Title   = "AutoFish each zone",
    Content = "Equip your Fishing Rod and toggle zones below. Simplified timing replaces GUI-checks."
})

-- Cria toggles por zona
for nome, dados in pairs(locais) do
    TabF:CreateToggle({
        Name         = "Auto "..nome,
        CurrentValue= false,
        Flag         = "Toggle"..nome,
        Callback     = function(state)
            dados.toggle    = state
            autoGrabEnabled = state

            if state then
                iniciarPesca(nome)
                iniciarAutoGrab()
            end
        end
    })
end
--]]

local Tab1 = Window:CreateTab("Resources", 4483362458)

local UserInputService = game:GetService("UserInputService")
local players = game:GetService("Players")
local player = players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local grabFolder = workspace:WaitForChild("Grab") -- Folder containing the parts to grab
local selectedOption = "Sell" -- Initial selected option
local autoSellEnabled = false -- Auto-sell toggle state

-- UI Elements
local Paragraph = Tab1:CreateParagraph({
    Title = "Teleport and How to use", 
    Content = "Choose here an option to where teleport, enable the switch and remember it will only teleport if you press the Teleport Keybind(can change to other key) key while holding an object"
})
-- Função para encontrar o modelo (Model) que contém o _Grab
local function findModelOfGrab()
    --print("Procurando _Grab dentro de workspace.Grab...")
    for _, part in ipairs(grabFolder:GetDescendants()) do
        if part.Name == "_Grab" then
            --print("_Grab encontrado: ", part:GetFullName())
            local current = part
            while current.Parent do
                current = current.Parent
                if current:IsA("Model") then
                    --print("Model encontrado: ", current:GetFullName())
                    return current
                end
            end
            --print("Nenhum Model encontrado acima de _Grab.")
        end
    end
    --print("_Grab não encontrado em nenhum descendente.")
    return nil
end

-- Function to teleport the parent or part based on selected option
local function teleportParentOrPart()
    if not _G.TeleportItemEnabled then
        return
    end

    local player = game.Players.LocalPlayer
    local humroot = player.Character and player.Character:FindFirstChild("HumanoidRootPart")
    local teleportPlayer = _G.TeleportPlayerEnabled
    local targetModel = findModelOfGrab()  -- Always get the current model
    
    if not targetModel then
        return  -- No model to teleport
    end

    local targetCFrame = nil

    if selectedOption == "Your Plot" then
        targetCFrame = _G.ownedPlot.Plot.CFrame * CFrame.new(0, 5, 0)
    elseif selectedOption == "Sell" then
        targetCFrame = CFrame.new(927.2778930664062, 29.87200355529785, -703.7294921875)
    elseif selectedOption == "Enchant" then
        local enchantAltar = workspace.Map.Caves.NovaCaveSystem.Layer3.Model:FindFirstChild("EnchantAltar")
        if enchantAltar and enchantAltar:IsA("Model") then
            -- Use the model's primary part if it exists, otherwise find the first BasePart
            local part = enchantAltar.PrimaryPart or enchantAltar:FindFirstChildWhichIsA("BasePart")
            if part then
                targetCFrame = part.CFrame * CFrame.new(0, 3, 0) -- Slightly above the altar
            end
        end
    elseif selectedOption == "Sawmill" then
        for _, obj in pairs(_G.ownedPlot.Objects:GetChildren()) do
            if obj.Name:match("Sawmill") and obj:FindFirstChild("Hitbox") then
                for _, child in pairs(obj.Sawmill:GetChildren()) do
                    if child.Name == "Model" and child:IsA("Model") then
                        child:Destroy()
                    end
                end
                targetCFrame = obj.Hitbox.CFrame
                break
            end
        end
    elseif selectedOption == "Furnace" then
        for _, obj in pairs(_G.ownedPlot.Objects:GetChildren()) do
            if obj.Name:match("Furnace") and obj:FindFirstChild("Hitbox") then
                targetCFrame = obj.Hitbox.CFrame
                break
            end
        end
    elseif selectedOption == "Vi's Lab" then
        local violet = workspace.Npcs:FindFirstChild("Violet")
        if violet and violet:IsA("Model") then
            targetCFrame = violet:GetPivot()
        end
    elseif selectedOption == "Nautic Finds Sellary" then
        targetCFrame = workspace.Map.Structures.Nautic_Sellary.SellZone.Area.CFrame
    elseif selectedOption == "Sifter" then
        targetCFrame = _G.ownedPlot.Objects.Sifter.Hitbox.CFrame * CFrame.new(0, 5, 0)
    elseif selectedOption == "Polisher" then
        targetCFrame = _G.ownedPlot.Objects.Polisher.InsideHitbox.CFrame
    end

    if targetCFrame then
        -- Ensure model has a PrimaryPart
        if not targetModel.PrimaryPart then
            local firstPart = targetModel:FindFirstChildWhichIsA("BasePart")
            if firstPart then
                targetModel.PrimaryPart = firstPart
            else
                warn("No BasePart in model, teleport canceled.")
                return
            end
        end

        -- Store player's original position if teleporting player
        local originCFrame = teleportPlayer and humroot and humroot.CFrame

        -- Teleport the model
        targetModel:SetPrimaryPartCFrame(targetCFrame)

        -- Handle auto-sell if needed
        if selectedOption == "Sell" and autoSellEnabled then
            Sell()
        end

        -- Teleport player if needed
        if teleportPlayer and originCFrame then
            if humroot then
                humroot.CFrame = targetCFrame
                task.delay(0.5, function()
                    if player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
                        player.Character.HumanoidRootPart.CFrame = originCFrame
                    end
                end)
            end
        end
    end
end

local keybindTeleport = Tab1:CreateKeybind({
   Name = "Teleport Keybind",
   CurrentKeybind = "LeftAlt", -- Pode ser "Q", "E", "F", etc.
   HoldToInteract = false,
   Flag = "TeleportKeybind",
   Callback = function()
       if _G.TeleportItemEnabled then
           teleportParentOrPart()
       end
   end,
})

local Dropdown = Tab1:CreateDropdown({
    Name = "Teleport Where?",
    Options = {"Sell", "Your Plot", "Sawmill", "Furnace", "Enchant", "Vi's Lab", "Nautic Finds Sellary", "Sifter", "Polisher"},
    CurrentOption = "Sell",
    MultipleOptions = false,
    Flag = "DragDrop",
    Callback = function(Option)

        if type(Option) == "table" then
            selectedOption = Option[1]
        else
            selectedOption = Option
        end
    end,
})

_G.TeleportPlayerEnabled = false -- or false, depending on toggle state
_G.TeleportItemEnabled = false

local Toggle = Tab1:CreateToggle({
    Name = "Toggle Teleport",
    CurrentValue = false,
    Flag = "TeleportItem", -- Identifier for saving configuration
    Callback = function(Value)
        _G.TeleportItemEnabled = Value -- Update the toggle state based on the button value
    end,
})

local teleportToggle = Tab1:CreateToggle({
    Name = "Teleport Player",
    CurrentValue = false,
    Flag = "TeleportPlayer", -- optional
    Callback = function(Value)
        _G.TeleportPlayerEnabled = Value
    end,
})


--[[ Add Auto Sell Toggle
local AutoSellToggle = Tab1:CreateToggle({
    Name = "Auto Sell When Teleporting to Sell",
    CurrentValue = false,
    Flag = "AutoSellToggle",
    Callback = function(Value)
        autoSellEnabled = Value
    end,
})

-- Function to sell items
function Sell()
    local args = {
	"Deal",
	1
}
workspace:WaitForChild("Map"):WaitForChild("Structures"):WaitForChild("Nova_Sellary"):WaitForChild("TalkPart"):WaitForChild("Interact"):FireServer(unpack(args))

end
--]]




local Button = Tab1:CreateButton({
    Name = "Teleport player to enchant",
    Callback = function()
        local enchantAltar = workspace.Map.Caves.NovaCaveSystem.Layer3.Model:FindFirstChild("EnchantAltar")
        if enchantAltar and enchantAltar:IsA("Model") then
            local part = enchantAltar.PrimaryPart or enchantAltar:FindFirstChildWhichIsA("BasePart")
            if part then
                teleportToLocation(part.CFrame * CFrame.new(0, 3, 0))
            else
                Rayfield:Notify({
                    Title = "Error",
                    Content = "Could not find a valid part in the EnchantAltar model.",
                    Duration = 5,
                    Image = "alert-circle"
                })
            end
        else
            Rayfield:Notify({
                Title = "Error",
                Content = "EnchantAltar not found in the expected location.",
                Duration = 5,
                Image = "alert-circle"
            })
        end
    end,
 })

local Paragraph = Tab1:CreateParagraph({
    Title = "Teleport to a Tree/Ore", 
    Content = "Select any of the options below and be teleported. You may want to use the script above to teleport items to your Plot."
})

local function fetchOptionsFromFolder(folder)
    local options = {}

    -- Fetch names of models inside the folder
    for _, item in ipairs(folder:GetChildren()) do
            table.insert(options, item.Name)
    end

    return options
end

local function updateTreeOptions(currentSelection)
    local treesFolder = game:GetService("ReplicatedStorage").Content.Trees
    local treeOptions = {}
    local uniqueTreeNames = {}

    -- Helper function to remove numbers at the end of tree names
    local function getBaseTreeName(name)
        -- Remove numbers from the end of the tree name (e.g., "Festive Tree 1" -> "Festive Tree")
        return name:gsub("%s%d+$", "")
    end

    -- Populate treeOptions
    for _, tree in ipairs(treesFolder:GetChildren()) do
            local baseTreeName = getBaseTreeName(tree.Name)
            if not uniqueTreeNames[baseTreeName] then
                table.insert(treeOptions, baseTreeName)
                uniqueTreeNames[baseTreeName] = true
        end
    end

    -- Check if the currentSelection is valid, if not, reset it to the first option
    if currentSelection and not table.find(treeOptions, currentSelection) then
        return treeOptions, treeOptions[1]
    end

    return treeOptions, currentSelection or treeOptions[1]
end

local function updateOreOptions(currentSelection)
    local oresFolder = game:GetService("ReplicatedStorage").Content.Ores
    local oreOptions = fetchOptionsFromFolder(oresFolder)

    -- Check if the currentSelection is valid, if not, reset it to the first option
    if currentSelection and not table.find(oreOptions, currentSelection) then
        return oreOptions, oreOptions[1]
    end

    return oreOptions, currentSelection or oreOptions[1]
end

-- Create Dropdown for Trees
local TreeDropdown = Tab1:CreateDropdown({
    Name = "Select Tree",
    Options = updateTreeOptions(), 
    CurrentOption = {updateTreeOptions()[1]},
    MultipleOptions = false,
    Flag = "DDT",
    Callback = function(Option)
        local selectedTreeName = Option[1]
    end,
})

-- Create Dropdown for Ores
local OreDropdown = Tab1:CreateDropdown({
    Name = "Select Ore",
    Options = updateOreOptions(), 
    CurrentOption = {updateOreOptions()[1]},
    MultipleOptions = false,
    Flag = "ORE_DDT",
    Callback = function(Option)
        local selectedOreName = Option[1]
    end,
})

-- Button to teleport to the selected tree
local TeleportTreeButton = Tab1:CreateButton({
    Name = "Teleport to Selected Tree",
    Callback = function()
        local selectedTreeName = TreeDropdown.CurrentOption[1] -- Gets the currently selected tree from the dropdown
 
        -- Search for the selected tree in both locations
        local selectedTree
        local treeLocations = {
            game:GetService("ReplicatedFirst").HiddenTrees,
            workspace.WorldSpawn.Trees
        }
 
        for _, location in ipairs(treeLocations) do
            selectedTree = location:FindFirstChild(selectedTreeName)
            if selectedTree then
                break -- Stop searching once the tree is found
            end
        end
 
        if selectedTree then
            local branchPart = selectedTree:FindFirstChild("Hittable") and selectedTree.Hittable:FindFirstChild("Branch")
            local part = selectedTree:FindFirstChild("Hittable") and selectedTree.Hittable:FindFirstChild("Part")
            local targetPart = branchPart or part
 
            if targetPart then
                local player = game.Players.LocalPlayer
                teleportToLocation(targetPart)
            else
                --warn("No 'Branch' or 'Part' found in the tree: " .. selectedTreeName)
            end
        else
            Rayfield:Notify({
                Title = "Something went wrong",
                Content = "Seems like this tree still don't exist in the server, you may want to teleport to the tree zone to it spawn",
                Duration = 6.5,
                Image = "triangle-alert",
             })
        end
    end,
 })
 
-- Button to teleport to the selected ore
local TeleportOreButton = Tab1:CreateButton({
    Name = "Teleport to Selected Ore",
    Callback = function()
        local selectedOreName = OreDropdown.CurrentOption[1] -- Gets the currently selected ore from the dropdown
 
        -- Search for the selected ore in both locations
        local selectedOre
        local oreLocations = {
            game:GetService("ReplicatedFirst").HiddenOres,
            workspace.WorldSpawn.Ores
        }
 
        for _, location in ipairs(oreLocations) do
            selectedOre = location:FindFirstChild(selectedOreName)
            if selectedOre then
                break -- Stop searching once the ore is found
            end
        end
 
        if selectedOre then
            local hitboxPart = selectedOre:FindFirstChild("Hitbox")
            if hitboxPart then
                local player = game.Players.LocalPlayer
                    teleportToLocation(hitboxPart)            
                else
                --warn("No 'Hitbox' found in the ore: " .. selectedOreName)
            end
        else
            Rayfield:Notify({
                Title = "Something went wrong",
                Content = "Seems like this ore still don't exist in the server, you may want to teleport to the ore zone for it spawn",
                Duration = 6.5,
                Image = "triangle-alert",
             })
            end
    end,
 })


 local Tab2 = Window:CreateTab("Teleports", 4483362458) -- Title, Image
local Button = Tab2:CreateButton({
    Name = "Teleport to Vehicle Seat",
    Callback = function()
            local seat = getMyVehicleSeat()
    if seat then
        seat.CanTouch = true
    end

        local player = game.Players.LocalPlayer
        if seat and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            player.Character.HumanoidRootPart.CFrame = seat.CFrame + Vector3.new(0, 3, 0) -- teleport slightly above the seat
        else
            warn("Seat not found or player character invalid.")
        end
    end,
})

 local Button = Tab2:CreateButton({
    Name = "Tween to Plot",
    Callback = function()
        
        local TweenService = game:GetService("TweenService")
        local player = game.Players.LocalPlayer
        local character = workspace.Live:FindFirstChild(player.Name) -- Obtém o personagem do jogador local em workspace.Live
        local humanoidRootPart = character:WaitForChild("HumanoidRootPart")
        
        -- Define a posição alvo para o tween, que será a posição da plot do jogador
        local targetPosition = _G.ownedPlot.Plot.Position + Vector3.new(0, 3, 0) -- Ajuste conforme necessário
        
        -- Cria informações do Tween
        local tweenInfo = TweenInfo.new(
            2, -- Duração do tween em segundos
            Enum.EasingStyle.Quad, -- Estilo de easing
            Enum.EasingDirection.Out -- Direção do easing
        )
        
        -- Cria o tween para mover o personagem
        local tween = TweenService:Create(humanoidRootPart, tweenInfo, {CFrame = CFrame.new(targetPosition)})
        
        -- Inicia o tween
        tween:Play()
        
        -- Limpeza após o tween completar
        tween.Completed:Connect(function()
            --print("Tween completed, you reached the destination!")
        end)
end
         })

local player = game.Players.LocalPlayer

-- Function to get the current list of NPC names
local function updateNPCOptions()
    local npcList = {} -- Table to store NPC names
    local npcsFolder = workspace:FindFirstChild("Npcs") -- Get the Npcs folder
    if npcsFolder then
        for _, npc in ipairs(npcsFolder:GetChildren()) do
            if npc:IsA("Model") then
                table.insert(npcList, npc.Name) -- Add NPC name to the list
            end
        end
    end
    return npcList
end

-- Create the dropdown for teleporting to NPCs
local NPCDropdown = Tab2:CreateDropdown({
   Name = "Teleport to NPCs",
   Options = updateNPCOptions(), -- Using the list of options generated
   CurrentOption = {updateNPCOptions()[1]}, -- Set the first option as default
   MultipleOptions = false,
   Flag = "NPC_DDT", -- Unique flag for this dropdown
   Callback = function(Option)
       local selectedNPCName = Option[1] -- Get the selected NPC name
       local selectedNPC = workspace.Npcs:FindFirstChild(selectedNPCName) -- Find the corresponding NPC

       if selectedNPC and selectedNPC:IsA("Model") then
           local targetCFrame

           if selectedNPC.PrimaryPart then
               -- Use the PrimaryPart if it's set
               targetCFrame = selectedNPC.PrimaryPart
           else
               -- Fallback: use the model's center position
               targetCFrame = selectedNPC:GetPivot()
           end

           -- Now teleport to that CFrame
           teleportToLocation(targetCFrame) -- You may want to offset the Y a bit (e.g., +Vector3.new(0, 5, 0)) to avoid clipping
       else
           -- warn("The selected NPC could not be found or is not a model.")
       end
   end,
})

-- Optionally, if you want to refresh the dropdown options later
-- NPCDropdown:Set(updateNPCOptions()) -- Call this to refresh the options whenever needed

local player = game.Players.LocalPlayer

-- Function to get the current list of plot names
local function updatePlotOptions()
    local plotList = {} -- Table to store plot names
    local plotsFolder = workspace:FindFirstChild("Plots") -- Get the Plots folder
    if plotsFolder then
        for _, plot in ipairs(plotsFolder:GetChildren()) do
            if plot:IsA("Model") and plot:FindFirstChild("Plot") then
                table.insert(plotList, plot.Name) -- Add plot name to the list
            end
        end
    else
       -- warn("Plots folder not found in workspace.")
    end
    return plotList
end

-- Create the dropdown for teleporting to plots
local PlotDropdown = Tab2:CreateDropdown({
   Name = "Teleport to Plots",
   Options = updatePlotOptions(), -- Using the list of options generated
   CurrentOption = {updatePlotOptions()[1]}, -- Set the first option as default
   MultipleOptions = false,
   Flag = "PLOT_DDT", -- Unique flag for this dropdown
   Callback = function(Option)
       local selectedPlotName = Option[1] -- Get the selected plot name
       local selectedPlot = workspace.Plots:FindFirstChild(selectedPlotName) -- Find the corresponding plot

       if selectedPlot and selectedPlot:FindFirstChild("Plot") then
           -- Teleport the player to the CFrame of the plot
           teleportToLocation(selectedPlot.Plot) -- Teleport the player to the plot's CFrame
       else
         --updateWeldPart0(selectedPlot.Plots)--  warn("The selected plot could not be found or does not have a 'Plot' child.")
       end
   end,
})

-- Optionally, if you want to refresh the dropdown options later
-- PlotDropdown:Set(updatePlotOptions()) -- Call this to refresh the options whenever needed

local player = game.Players.LocalPlayer

-- Function to get the current list of player names (excluding local player)
local function updatePlayerOptions()
    local playerList = {}
    local localPlayerName = game.Players.LocalPlayer.Name
    local liveFolder = workspace:FindFirstChild("Live")
    
    if liveFolder then
        for _, livePlayer in ipairs(liveFolder:GetChildren()) do
            -- Only add if it's a Model, has HumanoidRootPart, and is not the local player
            if livePlayer:IsA("Model") and 
               livePlayer:FindFirstChild("HumanoidRootPart") and 
               livePlayer.Name ~= localPlayerName then
                
                table.insert(playerList, livePlayer.Name)
            end
        end
    end
    
    return playerList
end

-- Create the dropdown for teleporting to players
local PlayerDropdown = Tab2:CreateDropdown({
   Name = "Teleport to Players",
   Options = updatePlayerOptions(), -- Initial options
   CurrentOption = {"Select a player"}, -- Default option
   MultipleOptions = false,
   Flag = "PLAYER_DDT",
   Callback = function(Option)
       -- Callback not needed here as we're using a separate button
   end,
})

-- Function to update the player dropdown
local function updatePlayerDropdown()
    local options = updatePlayerOptions()
    if #options > 0 then
        -- Store current selection if any
        local currentSelection = PlayerDropdown.CurrentOption[1] ~= "No players found" and PlayerDropdown.CurrentOption[1] or nil
        
        -- Update options
        PlayerDropdown:Refresh(options)
        
        -- Try to restore selection if it still exists in the new options
        if currentSelection and table.find(options, currentSelection) then
            PlayerDropdown:Set({currentSelection})
        end
    else
        PlayerDropdown:Refresh({"No players found"})
    end
end

-- Update the dropdown every 5 seconds with better error handling
spawn(function()
    while true do
        local success, err = pcall(updatePlayerDropdown)
        if not success then
            warn("Failed to update player dropdown:", err)
        end
        wait(5)
    end
end)

-- Create a button to teleport to the selected player
local TeleportButton = Tab2:CreateButton({
   Name = "Teleport to Selected Player",
   Callback = function()
       if not PlayerDropdown.CurrentOption or PlayerDropdown.CurrentOption[1] == "No players found" then
           Rayfield:Notify({
               Title = "Error",
               Content = "No player selected or no players found.",
               Duration = 3,
               Image = "alert-circle",
           })
           return
       end
       
       local selectedPlayerName = PlayerDropdown.CurrentOption[1]
       local selectedPlayer = workspace.Live:FindFirstChild(selectedPlayerName)
       
       if selectedPlayer and selectedPlayer:FindFirstChild("HumanoidRootPart") then
           teleportToLocation(selectedPlayer.HumanoidRootPart)
       else
           Rayfield:Notify({
               Title = "Error",
               Content = "Could not find the selected player.",
               Duration = 3,
               Image = "alert-circle",
           })
       end
   end,
})

-- Initial update
updatePlayerDropdown()


-- Function to get all location names in workspace.MouseIgnore.Locations
local function updateLocationOptions()
   local locationList = {} -- Table to store location names
   local locationsFolder = workspace.MouseIgnore:FindFirstChild("Locations") -- Get the Locations folder
   
   if locationsFolder then
       for _, location in ipairs(locationsFolder:GetChildren()) do
           if location:IsA("Model") or location:IsA("Part") then -- Check if the child is a Model or Part
               table.insert(locationList, location.Name) -- Add the location name to the list
           end
       end
   else
       -- warn("Locations folder not found in workspace.MouseIgnore.")
   end

   return locationList -- Return the list of location names
end

-- Create the dropdown for locations
local LocationDropdown = Tab2:CreateDropdown({
   Name = "Select Location",
   Options = updateLocationOptions(), -- Using the list of options generated
   CurrentOption = {updateLocationOptions()[1]}, -- Set the first option as default (if it exists)
   MultipleOptions = false,
   Flag = "LocationDropdown", -- Unique flag for this dropdown
   Callback = function(Option)
       local selectedLocationName = Option[1] -- Get the selected location name
       local selectedLocation = workspace.MouseIgnore.Locations:FindFirstChild(selectedLocationName) -- Find the corresponding location

       if selectedLocation then
           -- Do something with the selected location, e.g., teleport the player
           local player = game.Players.LocalPlayer
           if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
               teleportToLocation(selectedLocation) -- Teleport the player to the location's position
           else
               --updateWeldPart0(selectedLocation) 
           end
       else
           -- warn("The selected location could not be found.")
       end
   end,
})

local player = game.Players.LocalPlayer
local selectedFishZoneName = nil -- Variable to hold the selected fish zone name
-- Function to get the current list of fish zone options
local function updateFishZoneOptions()
    local fishZoneList = {}
    local fishZonesFolder = FFolder

    if fishZonesFolder then
        for _, child in ipairs(fishZonesFolder:GetChildren()) do
            if child:IsA("Folder") and child:FindFirstChildWhichIsA("Part") then
                table.insert(fishZoneList, child.Name)
            elseif child:IsA("Part") then
                table.insert(fishZoneList, child.Name)
            end
        end
    end

    return fishZoneList
end

-- Create the dropdown for selecting fish zones
local FishZoneDropdown = Tab2:CreateDropdown({
    Name = "Select Fish Zone",
    Options = updateFishZoneOptions(), -- Using the list of options generated
    CurrentOption = {updateFishZoneOptions()[1]}, -- Set the first option as default
    MultipleOptions = false,
    Flag = "FISH_ZONE_DDT", -- Unique flag for this dropdown
    Callback = function(Option)
        selectedFishZoneName = Option[1] -- Store the selected fish zone name in the variable
    end,
})

-- Create a button to teleport to the selected fish zone
TeleportToFishZoneButton = Tab2:CreateButton({
    Name = "Teleport to Selected Fish Zone",
    Callback = function()
        if selectedFishZoneName then
            local zone = FFolder:FindFirstChild(selectedFishZoneName)

            local target = nil
            if zone:IsA("Part") then
                target = zone
            elseif zone:IsA("Folder") then
                target = zone:FindFirstChildWhichIsA("Part")
            end

            if target then
                teleportToLocation(target)
            else
                warn("No valid part found to teleport to!")
            end
        else
            warn("No fish zone selected.")
        end
    end,
})
