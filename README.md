-- NATAN DEAD REAILS | v0.2.9
-- Para Delta Executor e compatível com celular

local OrionLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/shlexware/Orion/main/source"))()
local Window = OrionLib:MakeWindow({
    Name = "Natan | Dead Reails (0.2.9)",
    HidePremium = false,
    SaveConfig = false,
    IntroText = "Natan Dead Reails",
    IntroIcon = "rbxassetid://7733960981",
    Icon = "rbxassetid://7733960981"
})

-- Função: Unlock Mouse
function UnlockMouse()
    local UIS = game:GetService("UserInputService")
    UIS.MouseIconEnabled = true
    UIS.OverrideMouseIconBehavior = Enum.OverrideMouseIconBehavior.ForceShow
end

-- Função: Unlock Camera
function UnlockCamera()
    local player = game.Players.LocalPlayer
    if player then
        player.CameraMode = Enum.CameraMode.Classic
    end
end

-- Função: Remove Fog
function RemoveFog()
    local lighting = game:GetService("Lighting")
    lighting.FogEnd = 1000000
    lighting.FogStart = 0
end

-- Função: Full Bright
function FullBright()
    local lighting = game:GetService("Lighting")
    lighting.Brightness = 2
    lighting.ClockTime = 14
    lighting.FogEnd = 1000000
    lighting.GlobalShadows = false
end

-- Aba Visual
local tabVisual = Window:MakeTab({
    Name = "Visual",
    Icon = "rbxassetid://7734043500",
    PremiumOnly = false
})

tabVisual:AddToggle({
    Name = "Unlock Mouse",
    Default = false,
    Callback = function(v)
        if v then UnlockMouse() end
    end
})

tabVisual:AddToggle({
    Name = "Unlock Camera",
    Default = false,
    Callback = function(v)
        if v then UnlockCamera() end
    end
})

tabVisual:AddToggle({
    Name = "Remove Fog",
    Default = false,
    Callback = function(v)
        if v then RemoveFog() end
    end
})

tabVisual:AddToggle({
    Name = "Full Bright",
    Default = false,
    Callback = function(v)
        if v then FullBright() end
    end
})

-- Iniciar interface
OrionLib:Init()
