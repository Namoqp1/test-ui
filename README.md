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

function CheckLV()
if not game.Players.LocalPlayer.PlayerGui:FindFirstChild("QuestUI") then
local MyLv = tonumber(game.Players.LocalPlayer.PlayerGui.MainUI.Interface.PlayerStatus.Frame.Level.TextLabel.Text:match('%d+'))
 if MyLv == 1 or MyLv <= 249 then
 Mon = "Bandit"
 CFQ = CFrame.new(-953.566528, 34.5999947, -552.164612, -0.0109250434, -3.3378329e-09, -0.999940336, 1.94075778e-09, 1, -3.35923622e-09, 0.999940336, -1.97734162e-09, -0.0109250434)
 elseif MyLv == 250 or MyLv <= 999 then
 Mon = "Clown Pirate"
 CFQ = CFrame.new(-71.5784531, 36.4347496, 50.7921715, 0.00707866857, 2.668971e-08, 0.999974966, -5.85915032e-08, 1, -2.62756199e-08, -0.999974966, -5.84040372e-08, 0.00707866857)
 elseif MyLv == 1000 or MyLv <= 2349 then
 Mon = "Marine"
 CFQ = CFrame.new(991.011414, 76.895134, 1324.57812, -0.998725414, -6.23391339e-09, -0.0504727885, -1.01550848e-08, 1, 7.74323752e-08, 0.0504727885, 7.78462379e-08, -0.998725414)
 elseif MyLv == 2350 or MyLv <= 5249 then
 Mon = "Monkey"
 CFQ = CFrame.new(770.010071, 38.3316078, -1225.74194, 0.0635694042, 1.09396325e-07, 0.997977436, 5.08351974e-08, 1, -1.12856149e-07, -0.997977436, 5.79065755e-08, 0.0635694042)
 elseif MyLv >= 5250 then
 Mon = "Snow Bandit"
 CFQ = CFrame.new(1823.45251, 42.9730377, -217.761673, 0.0171297863, -7.80924125e-08, -0.999853253, 2.29865922e-08, 1, -7.77100624e-08, 0.999853253, -2.16520633e-08, 0.0171297863)
 end
 end
 end
