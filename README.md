local DrRayLibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/AZYsGithub/DrRay-UI-Library/main/DrRay.lua"))()
 
local window = DrRayLibrary:Load("SETRUMV", "Default")

local tab = DrRayLibrary.newTab("universal ", "ImageIdHere")

tab.newButton("FLY", "click", function()
 --ARCEUS X FLY V2 SCRIPT
loadstring("\108\111\97\100\115\116\114\105\110\103\40\103\97\109\101\58\72\116\116\112\71\101\116\40\40\39\104\116\116\112\115\58\47\47\103\105\115\116\46\103\105\116\104\117\98\117\115\101\114\99\111\110\116\101\110\116\46\99\111\109\47\109\101\111\122\111\110\101\89\84\47\98\102\48\51\55\100\102\102\57\102\48\97\55\48\48\49\55\51\48\52\100\100\100\54\55\102\100\99\100\51\55\48\47\114\97\119\47\101\49\52\101\55\52\102\52\50\53\98\48\54\48\100\102\53\50\51\51\52\51\99\102\51\48\98\55\56\55\48\55\52\101\98\51\99\53\100\50\47\97\114\99\101\117\115\37\50\53\50\48\120\37\50\53\50\48\102\108\121\37\50\53\50\48\50\37\50\53\50\48\111\98\102\108\117\99\97\116\111\114\39\41\44\116\114\117\101\41\41\40\41\10\10")()
end)

tab.newButton("Teleport", "ui", function() loadstring(game:HttpGet('https://raw.githubusercontent.com/Infinity2346/Tect-Menu/main/Teleport%20Gui.lua'))()
end)

tab.newButton("aimbot", "30 fov", function()
 local fov = 30
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")
local Players = game:GetService("Players")
local Cam = game.Workspace.CurrentCamera
 
local FOVring = Drawing.new("Circle")
FOVring.Visible = true
FOVring.Thickness = 2
FOVring.Color = Color3.fromRGB(128, 0, 128) -- Purple color
FOVring.Filled = false
FOVring.Radius = fov
FOVring.Position = Cam.ViewportSize / 2
 
local function updateDrawings()
    local camViewportSize = Cam.ViewportSize
    FOVring.Position = camViewportSize / 2
end
 
local function onKeyDown(input)
    if input.KeyCode == Enum.KeyCode.Delete then
        RunService:UnbindFromRenderStep("FOVUpdate")
        FOVring:Remove()
    end
end
 
UserInputService.InputBegan:Connect(onKeyDown)
 
local function lookAt(target)
    local lookVector = (target - Cam.CFrame.Position).unit
    local newCFrame = CFrame.new(Cam.CFrame.Position, Cam.CFrame.Position + lookVector)
    Cam.CFrame = newCFrame
end
 
local function getClosestPlayerInFOV(trg_part)
    local nearest = nil
    local last = math.huge
    local playerMousePos = Cam.ViewportSize / 2
 
    for _, player in ipairs(Players:GetPlayers()) do
        if player ~= Players.LocalPlayer then
            local part = player.Character and player.Character:FindFirstChild(trg_part)
            if part then
                local ePos, isVisible = Cam:WorldToViewportPoint(part.Position)
                local distance = (Vector2.new(ePos.x, ePos.y) - playerMousePos).Magnitude
 
                if distance < last and isVisible and distance < fov then
                    last = distance
                    nearest = player
                end
            end
        end
    end
 
    return nearest
end
 
RunService.RenderStepped:Connect(function()
    updateDrawings()
    local closest = getClosestPlayerInFOV("Head")
    if closest and closest.Character:FindFirstChild("Head") then
        lookAt(closest.Character.Head.Position)
    end
end)
end)

tab.newButton("Op esp", "ESP", function() loadstring(game:HttpGet("https://raw.githubusercontent.com/PawsThePaw/Neutron.lua/main/MainNeutron.lua"))() 
end)

tab.newButton("animaciones avatar", "ui", function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/H20CalibreYT/SystemBroken/main/script"))()
end)

tab.newButton("KeyBoard", "click", function() loadstring(game:HttpGet("https://raw.githubusercontent.com/advxzivhsjjdhxhsidifvsh/mobkeyboard/main/main.txt", true))()
end)

tab.newButton("hitbox", "click", function() loadstring(game:HttpGet(('https://pastebin.com/raw/wr4TYJRW'),true))()
end)

tab.newButton("shaders", "ui", function() loadstring(game:HttpGet(('https://pastefy.app/xXkUxA0P/raw'),true))()
end)

tab.newButton("cabeza hit", "expand", function()
 _G.HeadSize = 10
_G.Disabled = true
game:GetService('RunService').RenderStepped:connect(function()
if _G.Disabled then
for i,v in next, game:GetService('Players'):GetPlayers() do
if v.Name ~= game:GetService('Players').LocalPlayer.Name then
pcall(function()
v.Character.Head.Size = Vector3.new(_G.HeadSize,_G.HeadSize,_G.HeadSize)
v.Character.Head.Transparency = 1
v.Character.Head.BrickColor = BrickColor.new("Red")
v.Character.Head.Material = "Neon"
v.Character.Head.CanCollide = false
v.Character.Head.Massless = true
end)
end
end
end
end)
end)

tab.newButton("boozy FPS", "CLICK", function()
_G.Ignore = {}
_G.Settings = {
    Players = {
        ["Ignore Me"] = true,
        ["Ignore Others"] = true,
        ["Ignore Tools"] = true
    },
    Meshes = {
        NoMesh = false,
        NoTexture = false,
        Destroy = false
    },
    Images = {
        Invisible = true,
        Destroy = false
    },
    Explosions = {
        Smaller = true,
        Invisible = false, -- Not for PVP games
        Destroy = false -- Not for PVP games
    },
    Particles = {
        Invisible = true,
        Destroy = false
    },
    TextLabels = {
        LowerQuality = true,
        Invisible = false,
        Destroy = false
    },
    MeshParts = {
        LowerQuality = true,
        Invisible = false,
        NoTexture = false,
        NoMesh = false,
        Destroy = false
    },
    Other = {
        ["FPS Cap"] = 240, -- true to uncap
        ["No Camera Effects"] = true,
        ["No Clothes"] = true,
        ["Low Water Graphics"] = true,
        ["No Shadows"] = true,
        ["Low Rendering"] = true,    
        ["Low Quality Parts"] = true,
        ["Low Quality Models"] = true,
        ["Reset Materials"] = true,
    }
}
loadstring(game:HttpGet("https://raw.githubusercontent.com/CasperFlyModz/discord.gg-rips/main/FPSBooster.lua"))()
end)

tab.newButton("flappy bird", "wiii", function()
loadstring(game:HttpGet("https://pastebin.com/raw/rux7UL8L"))();
end)

local tab = DrRayLibrary.newTab("games ui", "1000061848")

tab.newButton("what is a better this", "buy all", function()
loadstring(game:HttpGet(('https://raw.githubusercontent.com/BaconBossScript/Crazy/main/Crazy'),true))()
end)

tab.newButton("alwi hub", "buy all", function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/Imalwibest/Imalwibest/main/wynerdV2.lua",true))()
end)

tab.newButton("doors", "ui", function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/KINGHUB01/BlackKing-obf/main/Doors%20Blackking%20And%20BobHub"))()
end)

tab.newButton("Survive the killer ", "ui", function()
loadstring(game:HttpGet('https://raw.githubusercontent.com/ProjectpopCat/YS_TheGamesEvent/main/SurviveTheKiller.lua'))()
end)

tab.newButton("Slap battles", "ui", function()
loadstring(game:HttpGet("https://rawscripts.net/raw/Slap-Battles-Open-source-for-9484", true))()
end)

tab.newButton("break in 2", "admin panel", function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/RScriptz/RobloxScripts/main/BreakIn2.lua"))()
end)

tab.newButton("Funky friday", "ui", function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/ltseverydayyou/uuuuuuu/main/Funky%20Friday/BotPlayer.lua"))();
end)

tab.newButton("murder mistery", "ui", function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/s-o-a-b/nexus/main/loadstring"))()
end)

tab.newButton("Prisión life comands", "commands", function()
loadstring(game:HttpGet('https://raw.githubusercontent.com/elliexmln/PrizzLife/main/pladmin.lua'))()
end)

tab.newButton("Prisión life animations", "ui", function()
loadstring("\108\111\97\100\115\116\114\105\110\103\40\103\97\109\101\58\72\116\116\112\71\101\116\40\34\104\116\116\112\115\58\47\47\114\97\119\46\103\105\116\104\117\98\117\115\101\114\99\111\110\116\101\110\116\46\99\111\109\47\103\48\48\108\88\112\108\111\105\116\101\114\47\103\48\48\108\88\112\108\111\105\116\101\114\47\109\97\105\110\47\70\101\37\50\48\98\121\112\97\115\115\34\44\32\116\114\117\101\41\41\40\41\10")()
end)
