local zplace = tostring(game.PlaceId)

if zplace == "15049111150" then
    SPMain = true
elseif zplace == "16644455867" then
    SPPortal = true
elseif zplace == "17167990958" then
    RFMain = true
elseif zplace == "17167990958" then
    RFMain2 = true
elseif zplace == "16723079713" then
    RFDungeon = true
elseif zplace == "14206387098" or zplace == "14379170249" or zplace == "14390362970" then
    CAMain = true
elseif zplace == "8540168650" then
    SUMain = true
elseif zplace == "10704789056" then
    DwMain = true
end

--SPMain

if SPMain then
    
    
local startTime = os.time()

print('Game Loading: Second Piece - Main Game') 

repeat 
    task.wait() 
until game:IsLoaded()

local endTime = os.time()
local elapsedTime = endTime - startTime

print('Game Loaded: ' .. elapsedTime .. ' seconds')
print('Game Finished Loading')

local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
local SaveManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/barlossxi/barlossxi/main/ZAZA.lua"))()
local InterfaceManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/barlossxi/barlossxi/main/InterfaceManager.lua.txt"))()

local Window = Fluent:CreateWindow({
    Title = "Second Piece Premium Script",
    SubTitle = "by ZA HUB",
    TabWidth = 160,
    Size = UDim2.fromOffset(500, 370),
    Acrylic = true, -- The blur may be detectable, setting this to false disables blur entirely
    Theme = "Dark",
    MinimizeKey = Enum.KeyCode.LeftControl -- Used when theres no MinimizeKeybind
})

--Fluent provides Lucide Icons https://lucide.dev/icons/ for the tabs, icons are optional
local Tabs = {
    Main = Window:AddTab({ Title = "Main", Icon = "home" }),
    Bossz = Window:AddTab({ Title = "Boss", Icon = "swords" }),
    Event = Window:AddTab({ Title = "Event", Icon = "backpack" }),
    Skills = Window:AddTab({ Title = "Skills", Icon = "flame" }),
    Stats1 = Window:AddTab({ Title = "Stats", Icon = "bar-chart-2" }),
    Player = Window:AddTab({ Title = "Player", Icon = "baby" }),
    Island = Window:AddTab({ Title = "Island", Icon = "palmtree" }),
    Shop = Window:AddTab({ Title = "Shop", Icon = "shopping-cart" }),
    Fruit = Window:AddTab({ Title = "Devil Fruit", Icon = "cherry" }),
    Portals = Window:AddTab({ Title = "Portal", Icon = "fingerprint" }),
    Misc = Window:AddTab({ Title = "Misc", Icon = "boxes" }),
    Settings = Window:AddTab({
		Title = "Config", Icon = "settings"
	})
}

local aza = "ZA HUB Script"
local bza = tostring(game.PlaceId).."-"..tostring(game.Players.LocalPlayer.Name)
function saveSettings()
    local cza = game:GetService("HttpService")
    local dza = cza:JSONEncode(_G)
    if writefile then
        if isfolder(aza) then
            writefile(aza .. "\\" .. bza, dza)
        else
            makefolder(aza)
            writefile(aza .. "\\" .. bza, dza)
        end
    end
end
function loadSettings()
    local cza = game:GetService("HttpService")
    if isfile(aza .. "\\" .. bza) then
        _G = cza:JSONDecode(readfile(aza .. "\\" .. bza))
    end
end

local Options = Fluent.Options

do

Tabs.Main:AddParagraph({

        Title = "Main",

        Content = ""
    })
