function itemequip(ToolSe)
    if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
        tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
        wait(.1)
        game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
    end
end

if not game:IsLoaded() then game.Loaded:Wait() end
repeat wait() until game.Players
repeat wait() until game.Players.LocalPlayer
repeat wait() until game.ReplicatedStorage
repeat wait() until game.ReplicatedStorage:FindFirstChild("Remotes");
repeat wait() until game.Players.LocalPlayer:FindFirstChild("PlayerGui");
repeat wait() until game.Players.LocalPlayer.PlayerGui:FindFirstChild("Main");

wait(1)


if not game:IsLoaded() then repeat game.Loaded:Wait() until game:IsLoaded() end

if game:GetService("Players").LocalPlayer.PlayerGui.Main:FindFirstChild("ChooseTeam") then
    repeat wait()
        if game:GetService("Players").LocalPlayer.PlayerGui:WaitForChild("Main").ChooseTeam.Visible == true then
            if _G.Team == "Pirate" then
                for i, v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Activated)) do                                                                                                
                    v.Function()
                end
            elseif _G.Team == "Marine" then
                for i, v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.Activated)) do                                                                                                
                    v.Function()
                end
            else
                for i, v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Activated)) do                                                                                                
                    v.Function()
                end
            end
        end
    until game.Players.LocalPlayer.Team ~= nil and game:IsLoaded()
end

local id = game.PlaceId
if id == 2753915549 then
    OldWolrd = true;
elseif id == 4442272183 then
    SecondSea = true;
elseif id == 7449423635 then
    ThirdSea = true;
end

game:GetService("ReplicatedStorage").Assets.GUI.DamageCounter.Enabled = false 
AttackRandomType = 1

local library = loadstring(game:HttpGet('https://raw.githubusercontent.com/Xenferxxzz/Ruok/main/README.md'))()

local window = library:new({textsize = 13.5,font = Enum.Font.RobotoMono,name = "Kenei UI",color = Color3.fromRGB(0,255,255)})

local Main_1_Page = window:page({name = "Main 1"})
local Main_2_Page = window:page({name = "Main 2"})

local Main_1_left = Main_1_Page:section({name = "General",side = "left",size = 1000})
local Main_1_right = Main_1_Page:section({name = "General",side = "right",size = 250})

local Main_2_left = Main_2_Page:section({name = "Main",side = "left",size = 250})
local Main_2_right = Main_2_Page:section({name = "Main",side = "left",size = 250})

Main_1_left:toggle({
    name = "Toggle",
    def = false,
    callback = function(value)
        getgenv().LevelFarm = value
end})

-- CheckQuest Level

function CheckQuest()
    local MYLEVEL = game:GetService("Players").LocalPlayer.Data.Level.Value
    if OldWolrd then
        if MYLEVEL == 1 or MYLEVEL <= 9 then
            Ms = "Bandit [Lv. 5]"
            NameQuest = "BanditQuest1"
            QuestLv = 1
            NameQ = "Bandit"
            CFrameQ = CFrame.new(1060.0158691406, 16.424287796021, 1547.9769287109)
            CFramePuk = CFrame.new(1073.86414, 16.2736206, 1612.17163, -0.695649207, 0, -0.718381643, 0, 1, 0,
                0.718381643, 0, -0.695649207)
            NM = 'Windmill'
        elseif MYLEVEL == 10 or MYLEVEL <= 14 then
            Ms = "Monkey [Lv. 14]"
            NameQuest = "JungleQuest"
            QuestLv = 1
            NameQ = "Monkey"
            CFrameQ = CFrame.new(-1601.52808, 36.9774551, 152.812317, -0.0892550573, -7.99012057e-08, -0.996008813,
                -4.66281733e-08, 1, -7.60429089e-08, 0.996008813, 3.96548572e-08, -0.0892550573)
            CFramePuk = CFrame.new(-1609.71216, 39.8521576, 123.384674, 0.708323717, 6.74341152e-08, 0.705887735,
                -1.86098941e-08, 1, -7.68568071e-08, -0.705887735, 4.13030072e-08, 0.708323717)
        elseif MYLEVEL == 15 or MYLEVEL <= 29 then
            magbring = 240
            Ms = "Gorilla [Lv. 20]"
            NameQuest = "JungleQuest"
            QuestLv = 2
            NameQ = "Gorilla"
            CFrameQ = CFrame.new(-1600.24353, 36.8521347, 153.224792, 0.0664860159, 1.09421023e-07, -0.997787356,
                9.55680779e-09, 1, 1.10300476e-07, 0.997787356, -1.68691017e-08, 0.0664860159)
            CFramePuk = CFrame.new(-1260.29321, 18.6214619, -398.3508, 0.816335142, 5.76316722e-07, -0.577578545,
                8.32609999e-08, 1, 1.11549434e-06, 0.577578545, -9.58707005e-07, 0.816335142)
        elseif MYLEVEL == 30 or MYLEVEL <= 39 then
            Ms = "Pirate [Lv. 35]"
            NameQuest = "BuggyQuest1"
            QuestLv = 1
            NameQ = "Pirate"
            CFrameQ = CFrame.new(-1141.07483, 4.10001802, 3831.5498, 0.965929627, -0, -0.258804798, 0, 1, -0,
                0.258804798, 0, 0.965929627)
            CFramePuk = CFrame.new(-1141.07483, 4.10001802, 3831.5498, 0.965929627, -0, -0.258804798, 0, 1, -0,
                0.258804798, 0, 0.965929627)
        elseif MYLEVEL == 40 or MYLEVEL <= 59 then
            Ms = "Brute [Lv. 45]"
            NameQuest = "BuggyQuest1"
            QuestLv = 2
            NameQ = "Brute"
            CFrameQ = CFrame.new(-1141.07483, 4.10001802, 3831.5498, 0.965929627, -0, -0.258804798, 0, 1, -0,
                0.258804798, 0, 0.965929627)
            CFramePuk = CFrame.new(-1144.44861, 90.5594559, 4307.25928, -0.998438537, 0, 0.0558618344, 0, 1, 0,
                -0.0558618344, 0, -0.998438537)
        elseif MYLEVEL == 60 or MYLEVEL <= 74 then
            Ms = "Desert Bandit [Lv. 60]"
            NameQuest = "DesertQuest"
            QuestLv = 1
            NameQ = "Desert Bandit"
            CFrameQ = CFrame.new(894.488647, 5.14000702, 4392.43359, 0.819155693, -0, -0.573571265, 0, 1, -0,
                0.573571265, 0, 0.819155693)
            CFramePuk = CFrame.new(894.488647, 5.14000702, 4392.43359, 0.819155693, -0, -0.573571265, 0, 1, -0,
                0.573571265, 0, 0.819155693)
        elseif MYLEVEL == 75 or MYLEVEL <= 89 then
            Ms = "Desert Officer [Lv. 70]"
            NameQuest = "DesertQuest"
            QuestLv = 2
            NameQ = "Desert Officer"
            CFrameQ = CFrame.new(894.488647, 5.14000702, 4392.43359, 0.819155693, -0, -0.573571265, 0, 1, -0,
                0.573571265, 0, 0.819155693)
            CFramePuk = CFrame.new(1580.03198, 4.61375761, 4366.86426)
        elseif MYLEVEL == 90 or MYLEVEL <= 99 then
            Ms = "Snow Bandit [Lv. 90]"
            NameQuest = "SnowQuest"
            QuestLv = 1
            NameQ = "Snow Bandit"
            CFrameQ = CFrame.new(1384.01538, 87.272789, -1296.28137, 0.462413222, -7.79864777e-08, -0.88666451,
                -1.42050363e-08, 1, -9.53630916e-08, 0.88666451, 5.6692258e-08, 0.462413222)
            CFramePuk = CFrame.new(1372.84326, 105.990303, -1422.19507, 0.719091773, -2.12436309e-08, 0.694915235,
                9.82151036e-08, 1, -7.10619616e-08, -0.694915235, 1.19351228e-07, 0.719091773)
        elseif MYLEVEL == 100 or MYLEVEL <= 119 then
            Ms = "Snowman [Lv. 100]"
            NameQuest = "SnowQuest"
            QuestLv = 2
            NameQ = "Snowman"
            CFrameQ = CFrame.new(1384.01538, 87.272789, -1296.28137, 0.462413222, -7.79864777e-08, -0.88666451,
                -1.42050363e-08, 1, -9.53630916e-08, 0.88666451, 5.6692258e-08, 0.462413222)
            CFramePuk = CFrame.new(1220.92712, 138.011871, -1489.01208, 0.389352709, -7.53626693e-07, 0.921088696,
                1.45705499e-07, 1, 7.56600116e-07, -0.921088696, -1.60376572e-07, 0.389352709)
        elseif MYLEVEL == 120 or MYLEVEL <= 149 then
            Ms = "Chief Petty Officer [Lv. 120]"
            NameQuest = "MarineQuest2"
            QuestLv = 1
            NameQ = "Chief Petty Officer"
            CFrameQ = CFrame.new(-5034.64893, 28.6520348, 4324.53369, -0.0616381466, 5.83357576e-08, 0.998098552,
                -1.59750098e-08, 1, -5.9433436e-08, -0.998098552, -1.96080023e-08, -0.0616381466)
            CFramePuk = CFrame.new(-4863.61328, 22.6520348, 4306.39307, 0.536051273, 7.00434066e-09, -0.844185412,
                -5.8011751e-10, 1, 7.92878918e-09, 0.844185412, -3.76051057e-09, 0.536051273)
        elseif MYLEVEL == 150 or MYLEVEL <= 174 then
            Ms = "Sky Bandit [Lv. 150]"
            NameQuest = "SkyQuest"
            QuestLv = 1
            NameQ = "Sky Bandit"
            CFrameQ = CFrame.new(-4843.2041, 717.669617, -2623.13159, -0.775086224, -1.6359829e-08, -0.631855488,
                -4.10942462e-08, 1, 2.45178793e-08, 0.631855488, 4.49690951e-08, -0.775086224)
            CFramePuk = CFrame.new(-4970.74219, 294.544342, -2890.11353, -0.994874597, -8.61311165e-08, -0.101116329,
                -9.10836278e-08, 1, 4.43614923e-08, 0.101116329, 5.33441664e-08, -0.994874597)
        elseif MYLEVEL == 175 or MYLEVEL <= 189 then
            Ms = "Dark Master [Lv. 175]"
            NameQuest = "SkyQuest"
            QuestLv = 2
            NameQ = "Dark Master"
            CFrameQ = CFrame.new(-4843.2041, 717.669617, -2623.13159, -0.775086224, -1.6359829e-08, -0.631855488,
                -4.10942462e-08, 1, 2.45178793e-08, 0.631855488, 4.49690951e-08, -0.775086224)
            CFramePuk = CFrame.new(-5239.94629, 392.217102, -2208.18335, 0.969297886, -5.95604988e-09, -0.245889395,
                3.87897714e-09, 1, -8.93151775e-09, 0.245889395, 7.70350184e-09, 0.969297886)
        elseif MYLEVEL == 190 or MYLEVEL <= 209 then
            Ms = "Prisoner [Lv. 190]"
            NameQuest = "PrisonerQuest"
            QuestLv = 1
            NameQ = "Prisoner"
            CFrameQ = CFrame.new(5307.95166015625, 1.6809712648391724, 475.1698913574219)
            CFramePuk = CFrame.new(5029.708984375, 68.67806243896484, 445.857177734375)
        elseif MYLEVEL == 210 or MYLEVEL <= 249 then
            Ms = "Dangerous Prisoner [Lv. 210]"
            NameQuest = "PrisonerQuest"
            QuestLv = 2
            NameQ = "Dangerous Prisoner"
            CFrameQ = CFrame.new(5307.95166015625, 1.6809712648391724, 475.1698913574219)
            CFramePuk = CFrame.new(5673.51758, 68.6786652, 783.757629, -0.0514698699, 7.78369369e-08, 0.998674572,
                8.35602094e-08, 1, -7.36337e-08, -0.998674572, 7.96595359e-08, -0.0514698699)
        elseif MYLEVEL == 250 or MYLEVEL <= 299 then
            Ms = "Toga Warrior [Lv. 250]"
            NameQuest = "ColosseumQuest"
            QuestLv = 1
            NameQ = "Toga Warrior"
            CFrameQ = CFrame.new(-1575.72961, 7.38933659, -2983.39453, 0.52762109, -1.48187587e-06, 0.849479854,
                2.69328297e-07, 1, 1.57716818e-06, -0.849479854, -6.0335816e-07, 0.52762109)
            CFramePuk = CFrame.new(-1819.12415, 7.28907108, -2744.02539, 0.547199547, 2.10840998e-08, -0.837002158,
                -1.27399286e-10, 1, 2.51067309e-08, 0.837002158, -1.36317579e-08, 0.547199547)
        elseif MYLEVEL == 300 or MYLEVEL <= 324 then
            Ms = "Military Soldier [Lv. 300]"
            NameQuest = "MagmaQuest"
            QuestLv = 1
            NameQ = "Military Soldier"
            CFrameQ = CFrame.new(-5316.33887, 12.236989, 8517.67285, 0.499506682, -5.08374072e-08, -0.86631006,
                -1.30872131e-08, 1, -6.62286652e-08, 0.86631006, 4.44192452e-08, 0.499506682)
            CFramePuk = CFrame.new(-5419.0752, 10.9255161, 8464.50488, -0.637788415, -4.55103836e-05, 0.770211577,
                7.05542743e-06, 1, 6.49305366e-05, -0.770211577, 4.68461185e-05, -0.637788415)
        elseif MYLEVEL == 325 or MYLEVEL <= 374 then
            Ms = "Military Spy [Lv. 325]"
            NameQuest = "MagmaQuest"
            QuestLv = 2
            NameQ = "Military Spy"
            CFrameQ = CFrame.new(-5316.33887, 12.236989, 8517.67285, 0.499506682, -5.08374072e-08, -0.86631006,
                -1.30872131e-08, 1, -6.62286652e-08, 0.86631006, 4.44192452e-08, 0.499506682)
            CFramePuk = CFrame.new(-5805.42041, 99.5276108, 8782.36719, -0.316935152, -6.4923519e-08, 0.948447227,
                4.12987404e-08, 1, 8.2252896e-08, -0.948447227, 6.52385026e-08, -0.316935152)
        elseif MYLEVEL == 375 or MYLEVEL <= 399 then
            Ms = "Fishman Warrior [Lv. 375]"
            NameQuest = "FishmanQuest"
            QuestLv = 1
            NameQ = "Fishman Warrior"
            CFrameQ = CFrame.new(61122.2422, 18.4716377, 1568.84778, 0.971045971, -1.77007031e-08, 0.238892734,
                4.80190776e-09, 1, 5.45760841e-08, -0.238892734, -5.18487475e-08, 0.971045971)
            CFramePuk = CFrame.new(60898.043, 18.4828224, 1550.9906, -0.0750192106, -4.46996573e-09, 0.997182071,
                3.6461556e-10, 1, 4.51002746e-09, -0.997182071, 7.0192685e-10, -0.0750192106)
            if    (getgenv().LevelFarm  or  _G.Settings["Auto Farm Level"]) and
                (CFrameQ.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",
                    Vector3.new(61163.8516, 5.43263245, 1819.78418, 1, 6.89280011e-09, 9.74497786e-14, -6.89280011e-09,
                        1, 3.38349579e-08, -9.72165599e-14, -3.38349579e-08, 1))
            end
        elseif MYLEVEL == 400 or MYLEVEL <= 449 then
            Ms = "Fishman Commando [Lv. 400]"
            NameQuest = "FishmanQuest"
            QuestLv = 2
            NameQ = "Fishman Commando"
            CFrameQ = CFrame.new(61122.2422, 18.4716377, 1568.84778, 0.971045971, -1.77007031e-08, 0.238892734,
                4.80190776e-09, 1, 5.45760841e-08, -0.238892734, -5.18487475e-08, 0.971045971)
            CFramePuk = CFrame.new(61885.4063, 18.4828224, 1500.37195, 0.722261012, 4.84021889e-08, -0.691620588,
                1.27929427e-08, 1, 8.33434299e-08, 0.691620588, -6.90435726e-08, 0.722261012)
            if    (getgenv().LevelFarm  or  _G.Settings["Auto Farm Level"])and
                (CFrameQ.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",
                    Vector3.new(61163.8516, 5.43263245, 1819.78418, 1, 6.89280011e-09, 9.74497786e-14, -6.89280011e-09,
                        1, 3.38349579e-08, -9.72165599e-14, -3.38349579e-08, 1))
            end
        elseif MYLEVEL == 450 or MYLEVEL <= 474 then
            Ms = "God's Guard [Lv. 450]"
            NameQuest = "SkyExp1Quest"
            QuestLv = 1
            NameQ = "God's Guard"
            CFrameQ = CFrame.new(-4721.28369, 845.277161, -1954.95154, -0.979754269, -1.72096932e-08, 0.200205252,
                -2.52417198e-09, 1, 7.36076018e-08, -0.200205252, 7.16119786e-08, -0.979754269)
            CFramePuk = CFrame.new(-4630.00635, 866.902954, -1936.76331, -0.656243384, 9.12737941e-12, 0.754549265,
                3.58402819e-09, 1, 3.10498938e-09, -0.754549265, 4.74195483e-09, -0.656243384)
            if    (getgenv().LevelFarm  or  _G.Settings["Auto Farm Level"])and
                (CFrameQ.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance", Vector3.new(
                    -4607.82275, 872.54248, -1667.55688))
            end
        elseif MYLEVEL == 475 or MYLEVEL <= 524 then
            Ms = "Shanda [Lv. 475]"
            NameQuest = "SkyExp1Quest"
            QuestLv = 2
            NameQ = "Shanda"
            CFrameQ = CFrame.new(-7861.79736, 5545.49316, -379.920776, 0.504107952, -1.41941534e-08, -0.863640666,
                -1.31181936e-08, 1, -2.40923566e-08, 0.863640666, 2.34745521e-08, 0.504107952)
            CFramePuk = CFrame.new(-7682.69775, 5607.36279, -445.691833, 0.786274791, -4.48163426e-08, -0.617877364,
                -4.81674345e-09, 1, -7.86622607e-08, 0.617877364, 6.48263239e-08, 0.786274791)
            if    (getgenv().LevelFarm  or  _G.Settings["Auto Farm Level"])and
                (CFrameQ.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance", Vector3.new(
                    -7894.6176757813, 5547.1416015625, -380.29119873047))
            end
        elseif MYLEVEL == 525 or MYLEVEL <= 549 then
            Ms = "Royal Squad [Lv. 525]"
            NameQuest = "SkyExp2Quest"
            QuestLv = 1
            NameQ = "Royal Squad"
            CFrameQ = CFrame.new(-7902.23242, 5635.96387, -1411.96741, -0.0435957126, -2.13718043e-09, 0.999049246,
                4.23562352e-10, 1, 2.15769735e-09, -0.999049246, 5.1722604e-10, -0.0435957126)
            CFramePuk = CFrame.new(-7579.42285, 5628.39111, -1540.75073, -0.0374937952, 1.17099557e-08, 0.999296963,
                -3.30279164e-08, 1, -1.29574085e-08, -0.999296963, -3.34905081e-08, -0.0374937952)
        elseif MYLEVEL == 550 or MYLEVEL <= 624 then
            Ms = "Royal Soldier [Lv. 550]"
            NameQuest = "SkyExp2Quest"
            QuestLv = 2
            NameQ = "Royal Soldier"
            CFrameQ = CFrame.new(-7902.23242, 5635.96387, -1411.96741, -0.0435957126, -2.13718043e-09, 0.999049246,
                4.23562352e-10, 1, 2.15769735e-09, -0.999049246, 5.1722604e-10, -0.0435957126)
            CFramePuk = CFrame.new(-7834.84717, 5681.36182, -1790.76782, -0.102890432, 3.28112684e-08, 0.994692683,
                -6.45397762e-08, 1, -3.96622966e-08, -0.994692683, -6.82781121e-08, -0.102890432)
        elseif MYLEVEL == 625 or MYLEVEL <= 649 then
            Ms = "Galley Pirate [Lv. 625]"
            NameQuest = "FountainQuest"
            QuestLv = 1
            NameQ = "Galley Pirate"
            CFrameQ = CFrame.new(5254.52734, 38.5011368, 4049.80127, -0.0732342899, 2.23174847e-08, -0.997314751,
                1.2052287e-07, 1, 1.35274023e-08, 0.997314751, -1.19208565e-07, -0.0732342899)
            CFramePuk = CFrame.new(5597.58936, 41.5013657, 3960.55371, -0.584786832, 4.98908861e-08, 0.811187029,
                4.10757259e-08, 1, -3.18919575e-08, -0.811187029, 1.4670098e-08, -0.584786832)
        elseif MYLEVEL >= 650 then
            Ms = "Galley Captain [Lv. 650]"
            NameQuest = "FountainQuest"
            QuestLv = 2
            NameQ = "Galley Captain"
            CFrameQ = CFrame.new(5254.52734, 38.5011368, 4049.80127, -0.0732342899, 2.23174847e-08, -0.997314751,
                1.2052287e-07, 1, 1.35274023e-08, 0.997314751, -1.19208565e-07, -0.0732342899)
            CFramePuk = CFrame.new(5705.8252, 52.241478, 4890.11035, -0.969319642, 4.40228476e-09, 0.245803744,
                -7.88622412e-09, 1, -4.90088397e-08, -0.245803744, -4.94436954e-08, -0.969319642)
        end
    end
    if SecondSea then
        if MYLEVEL == 700 or MYLEVEL <= 724 then
            Ms = "Raider [Lv. 700]"
            NameQuest = "Area1Quest"
            QuestLv = 1
            NameQ = "Raider"
            CFrameQ = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601,
                -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
            CFramePuk = CFrame.new(-737.026123, 39.1748352, 2392.57959)
        elseif MYLEVEL == 725 or MYLEVEL <= 774 then
            Ms = "Mercenary [Lv. 725]"
            NameQuest = "Area1Quest"
            QuestLv = 2
            NameQ = "Mercenary"
            CFrameQ = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601,
                -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
            CFramePuk = CFrame.new(-938.497314, 80.9546738, 1443.98608, 0.231955677, 0, 0.972726345, -0, 1, -0,
                -0.972726345, 0, 0.231955677)
        elseif MYLEVEL == 775 or MYLEVEL <= 874 then
            Ms = "Swan Pirate [Lv. 775]"
            NameQuest = "Area2Quest"
            QuestLv = 1
            NameQ = "Swan Pirate"
            CFrameQ = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771,
                1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
            CFramePuk = CFrame.new(967.233276, 141.309494, 1210.06384, 0.999673784, 5.40161649e-09, -0.0255404469,
                -7.62258967e-09, 1, -8.68617107e-08, 0.0255404469, 8.7028063e-08, 0.999673784)
        elseif MYLEVEL == 875 or MYLEVEL <= 899 then
            Ms = "Marine Lieutenant [Lv. 875]"
            NameQuest = "MarineQuest3"
            QuestLv = 1
            NameQ = "Marine Lieutenant."
            CFrameQ = CFrame.new(-2443.04639, 73.0161057, -3220.30225, -0.854058921, -6.13997599e-08, -0.520176232,
                -1.30658604e-08, 1, -9.65840883e-08, 0.520176232, -7.56919505e-08, -0.854058921)
            CFramePuk = CFrame.new(-2967.00757, 72.9661407, -2972.7478, 0.977851391, 8.27619218e-08, -0.209300488,
                -6.95268412e-08, 1, 7.05923142e-08, 0.209300488, -5.44767893e-08, 0.977851391)
        elseif MYLEVEL == 900 or MYLEVEL <= 949 then
            Ms = "Marine Captain [Lv. 900]"
            NameQuest = "MarineQuest3"
            QuestLv = 2
            NameQ = "Marine Captain"
            CFrameQ = CFrame.new(-2443.04639, 73.0161057, -3220.30225, -0.854058921, -6.13997599e-08, -0.520176232,
                -1.30658604e-08, 1, -9.65840883e-08, 0.520176232, -7.56919505e-08, -0.854058921)
            CFramePuk = CFrame.new(-1818.36401, 93.3760834, -3203.57788, 0.315930545, 4.84752114e-08, 0.948782325,
                1.37578589e-08, 1, -5.56731905e-08, -0.948782325, 3.06420738e-08, 0.315930545)
        elseif MYLEVEL == 950 or MYLEVEL <= 974 then
            Ms = "Zombie [Lv. 950]"
            NameQuest = "ZombieQuest"
            QuestLv = 1
            NameQ = "Zombie"
            CFrameQ = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742,
                4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
            CFramePuk = CFrame.new(-5736.03516, 126.031998, -728.026184, 0.0818082988, -5.90035434e-08, 0.996648133,
                3.5947787e-09, 1, 5.89069167e-08, -0.996648133, -1.23634614e-09, 0.0818082988)
        elseif MYLEVEL == 975 or MYLEVEL <= 999 then
            Ms = "Vampire [Lv. 975]"
            NameQuest = "ZombieQuest"
            QuestLv = 2
            NameQ = "Vampire"
            CFrameQ = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742,
                4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
            CFramePuk = CFrame.new(-6028.23584, 6.40270138, -1295.4563, 0.667547405, 0, 0.744567394, -0, 1.00000012, -0,
                -0.744567394, 0, 0.667547405)
        elseif MYLEVEL == 1000 or MYLEVEL <= 1049 then
            Ms = "Snow Trooper [Lv. 1000]"
            NameQuest = "SnowMountainQuest"
            QuestLv = 1
            NameQ = "Snow Trooper"
            CFrameQ = CFrame.new(605.670532, 401.422028, -5370.10107, 0.459257662, -9.56824509e-10, -0.888303101,
                5.98925964e-10, 1, -7.67489405e-10, 0.888303101, -1.79552401e-10, 0.459257662)
            CFramePuk = CFrame.new(544.207947, 401.422028, -5309.08887, 0.503866196, -2.06684501e-08, 0.86378175,
                1.27917943e-09, 1, 2.31816841e-08, -0.86378175, -1.05755351e-08, 0.503866196)
        elseif MYLEVEL == 1050 or MYLEVEL <= 1099 then
            Ms = "Winter Warrior [Lv. 1050]"
            NameQuest = "SnowMountainQuest"
            QuestLv = 2
            NameQ = "Winter Warrior"
            CFrameQ = CFrame.new(605.670532, 401.422028, -5370.10107, 0.459257662, -9.56824509e-10, -0.888303101,
                5.98925964e-10, 1, -7.67489405e-10, 0.888303101, -1.79552401e-10, 0.459257662)
            CFramePuk = CFrame.new(1240.86279, 461.108154, -5191.104, 0.528719008, -7.18234645e-08, 0.848796904,
                2.89169716e-10, 1, 8.44378363e-08, -0.848796904, -4.4398444e-08, 0.528719008)
        elseif MYLEVEL == 1100 or MYLEVEL <= 1124 then
            Ms = "Lab Subordinate [Lv. 1100]"
            NameQuest = "IceSideQuest"
            QuestLv = 1
            NameQ = "Lab Subordinate"
            CFrameQ = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528,
                1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
            CFramePuk = CFrame.new(-5833.63379, 48.4371948, -4510.4458, 0.0372838341, 5.56001822e-09, -0.999304712,
                -6.95599089e-09, 1, 5.30436006e-09, 0.999304712, 6.75338763e-09, 0.0372838341)
        elseif MYLEVEL == 1125 or MYLEVEL <= 1174 then
            Ms = "Horned Warrior [Lv. 1125]"
            NameQuest = "IceSideQuest"
            QuestLv = 2
            NameQ = "Horned Warrior"
            CFrameQ = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528,
                1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
            CFramePuk = CFrame.new(-6168.15918, 42.7079964, -6020.96826, -0.744210601, 2.41774178e-09, -0.667945027,
                -2.3336304e-09, 1, 6.21975493e-09, 0.667945027, 6.18754425e-09, -0.744210601)
        elseif MYLEVEL == 1175 or MYLEVEL <= 1199 then
            Ms = "Magma Ninja [Lv. 1175]"
            NameQuest = "FireSideQuest"
            QuestLv = 1
            NameQ = "Magma Ninja"
            CFrameQ = CFrame.new(-5429.68359, 15.9517593, -5296.70215, 0.919959962, -6.00166317e-08, -0.392012328,
                2.29238974e-08, 1, -9.93018858e-08, 0.392012328, 8.23673076e-08, 0.919959962)
            CFramePuk = CFrame.new(-5404.85449, 22.8623676, -5896.09033, -0.519595861, 4.74720929e-09, 0.854412138,
                1.52255595e-08, 1, 3.70304742e-09, -0.854412138, 1.49329917e-08, -0.519595861)
        elseif MYLEVEL == 1200 or MYLEVEL <= 1249 then
            Ms = "Lava Pirate [Lv. 1200]"
            NameQuest = "FireSideQuest"
            QuestLv = 2
            NameQ = "Lava Pirate"
            CFrameQ = CFrame.new(-5429.68359, 15.9517593, -5296.70215, 0.919959962, -6.00166317e-08, -0.392012328,
                2.29238974e-08, 1, -9.93018858e-08, 0.392012328, 8.23673076e-08, 0.919959962)
            CFramePuk = CFrame.new(-5075.1958, 16.1485081, -4814.36133, -0.800640523, -1.06090866e-07, 0.599145055,
                -6.59776447e-08, 1, 8.89041587e-08, -0.599145055, 3.16500923e-08, -0.800640523)
        elseif MYLEVEL == 1250 or MYLEVEL <= 1274 then
            Ms = "Ship Deckhand [Lv. 1250]"
            NameQuest = "ShipQuest1"
            QuestLv = 1
            NameQ = "Ship Deckhand"
            CFrameQ = CFrame.new(1038.67456, 125.057098, 32911.3477, 0.120709591, 5.22710089e-08, -0.992687881,
                7.9174507e-09, 1, 5.36187876e-08, 0.992687881, -1.43318593e-08, 0.120709591)
            CFramePuk = CFrame.new(1215.14063, 125.057114, 33050.7188, 0.527230442, 2.61814961e-08, 0.849722326,
                -5.66963045e-08, 1, 4.36674741e-09, -0.849722326, -5.04783984e-08, 0.527230442)
        elseif MYLEVEL == 1275 or MYLEVEL <= 1299 then
            Ms = "Ship Engineer [Lv. 1275]"
            NameQuest = "ShipQuest1"
            QuestLv = 2
            NameQ = "Ship Engineer"
            CFrameQ = CFrame.new(1038.67456, 125.057098, 32911.3477, 0.120709591, 5.22710089e-08, -0.992687881,
                7.9174507e-09, 1, 5.36187876e-08, 0.992687881, -1.43318593e-08, 0.120709591)
            CFramePuk = CFrame.new(862.985413, 40.4428635, 32867.9492, -0.847809434, 8.49998827e-08, -0.530301034,
                2.99658929e-08, 1, 1.1237865e-07, 0.530301034, 7.93847335e-08, -0.847809434)
        elseif MYLEVEL == 1300 or MYLEVEL <= 1324 then
            Ms = "Ship Steward [Lv. 1300]"
            NameQuest = "ShipQuest2"
            QuestLv = 1
            NameQ = "Ship Steward"
            CFrameQ = CFrame.new(969.268311, 125.057121, 33245.2695, -0.85863924, -4.77058464e-08, -0.512580395,
                -1.49134394e-08, 1, -6.80880134e-08, 0.512580395, -5.08187057e-08, -0.85863924)
            CFramePuk = CFrame.new(923.611511, 129.555984, 33442.3125, 0.997516274, 9.71936913e-08, 0.0704362914,
                -9.52239958e-08, 1, -3.13219992e-08, -0.0704362914, 2.45369804e-08, 0.997516274)
        elseif MYLEVEL == 1325 or MYLEVEL <= 1349 then
            Ms = "Ship Officer [Lv. 1325]"
            NameQuest = "ShipQuest2"
            QuestLv = 2
            NameQ = "Ship Officer"
            CFrameQ = CFrame.new(969.268311, 125.057121, 33245.2695, -0.85863924, -4.77058464e-08, -0.512580395,
                -1.49134394e-08, 1, -6.80880134e-08, 0.512580395, -5.08187057e-08, -0.85863924)
            CFramePuk = CFrame.new(882.275574, 181.057739, 33354.1797, 0.845816016, -3.71928088e-08, -0.533474684,
                1.28583932e-09, 1, -6.7679359e-08, 0.533474684, 5.65583242e-08, 0.845816016)
        elseif MYLEVEL == 1350 or MYLEVEL <= 1374 then
            Ms = "Arctic Warrior [Lv. 1350]"
            NameQuest = "FrostQuest"
            QuestLv = 1
            NameQ = "Arctic Warrior"
            CFrameQ = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226,
                -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
            CFramePuk = CFrame.new(5995.9292, 57.0727844, -6184.98926, 0.706337512, 5.23128296e-09, -0.707875192,
                -2.2285974e-08, 1, -1.48474424e-08, 0.707875192, 2.62629936e-08, 0.706337512)
        elseif MYLEVEL == 1375 or MYLEVEL <= 1424 then
            Ms = "Snow Lurker [Lv. 1375]"
            NameQuest = "FrostQuest"
            QuestLv = 2
            NameQ = "Snow Lurker"
            CFrameQ = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226,
                -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
            CFramePuk = CFrame.new(5516.27539, 60.5209846, -6830.82764, 0.219563305, -7.8544824e-09, 0.975598276,
                4.69439376e-09, 1, 6.99444236e-09, -0.975598276, 3.04411962e-09, 0.219563305)
        elseif MYLEVEL == 1425 or MYLEVEL <= 1449 then
            Ms = "Sea Soldier [Lv. 1425]"
            NameQuest = "ForgottenQuest"
            QuestLv = 1
            NameQ = "Sea Soldier"
            CFrameQ = CFrame.new(-3053.97339, 236.846283, -10146.1484, -0.999963522, -2.10707256e-08, -0.00854360498,
                -2.09657198e-08, 1, -1.23802275e-08, 0.00854360498, -1.22006529e-08, -0.999963522)
            CFramePuk = CFrame.new(-3026.54834, 29.5403671, -9758.74316, -0.999909937, 1.71713896e-08, -0.0134194754,
                1.68009748e-08, 1, 2.7715517e-08, 0.0134194754, 2.74875607e-08, -0.999909937)
        elseif MYLEVEL >= 1450 then
            Ms = "Water Fighter [Lv. 1450]"
            NameQuest = "ForgottenQuest"
            QuestLv = 2
            NameQ = "Water Fighter"
            CFrameQ = CFrame.new(-3053.97339, 236.846283, -10146.1484, -0.999963522, -2.10707256e-08, -0.00854360498,
                -2.09657198e-08, 1, -1.23802275e-08, 0.00854360498, -1.22006529e-08, -0.999963522)
            CFramePuk = CFrame.new(-3262.00098, 298.699615, -10553.6943, -0.233570755, -4.57538185e-08, 0.972339869,
                -5.80986068e-08, 1, 3.30992194e-08, -0.972339869, -4.87605725e-08, -0.233570755)
        end
    end
    if ThirdSea then
        if MYLEVEL == 1500 or MYLEVEL <= 1524 then
            Ms = "Pirate Millionaire [Lv. 1500]"
            NameQuest = "PiratePortQuest"
            QuestLv = 1
            NameQ = "Pirate Millionaire"
            CFrameQ = CFrame.new(-288.998016, 43.7932205, 5577.68994, -0.943210304, -8.05650799e-08, 0.332196265,
                -9.89928779e-08, 1, -3.85495724e-08, -0.332196265, -6.92454165e-08, -0.943210304)
            CFramePuk = CFrame.new(-91.8906479, 75.3287811, 5647.7002, 0.571274579, 8.47636343e-08, -0.820758998,
                -9.5655281e-08, 1, 3.66955462e-08, 0.820758998, 5.75466998e-08, 0.571274579)
        elseif MYLEVEL == 1525 or MYLEVEL <= 1574 then
            Ms = "Pistol Billionaire [Lv. 1525]"
            NameQuest = "PiratePortQuest"
            QuestLv = 2
            NameQ = "Pistol Billionaire"
            CFrameQ = CFrame.new(-288.998016, 43.7932205, 5577.68994, -0.943210304, -8.05650799e-08, 0.332196265,
                -9.89928779e-08, 1, -3.85495724e-08, -0.332196265, -6.92454165e-08, -0.943210304)
            CFramePuk = CFrame.new(-740.71814, 130.458511, 5869.8623, 0.26613301, -6.96497509e-08, 0.963936329,
                -2.79989738e-08, 1, 7.99857816e-08, -0.963936329, -4.82760854e-08, 0.26613301)
        elseif MYLEVEL == 1575 or MYLEVEL <= 1599 then
            Ms = "Dragon Crew Warrior [Lv. 1575]"
            NameQuest = "AmazonQuest"
            QuestLv = 1
            NameQ = "Dragon Crew Warrior"
            CFrameQ = CFrame.new(5834.86035, 51.3513641, -1103.34705, -0.919929087, 6.43650253e-08, 0.392084718,
                7.08298344e-08, 1, 2.02354311e-09, -0.392084718, 2.96328135e-08, -0.919929087)
            CFramePuk = CFrame.new(6498.88623, 51.4962921, -1011.49811, -0.844736993, -1.62814184e-09, -0.535181701,
                4.04657037e-08, 1, -6.69137634e-08, 0.535181701, -7.81810314e-08, -0.844736993)
        elseif MYLEVEL == 1600 or MYLEVEL <= 1624 then
            Ms = "Dragon Crew Archer [Lv. 1600]"
            NameQuest = "AmazonQuest"
            QuestLv = 2
            NameQ = "Dragon Crew Archer"
            CFrameQ = CFrame.new(5834.86035, 51.3513641, -1103.34705, -0.919929087, 6.43650253e-08, 0.392084718,
                7.08298344e-08, 1, 2.02354311e-09, -0.392084718, 2.96328135e-08, -0.919929087)
            CFramePuk = CFrame.new(6608.45605, 378.396393, 235.665527, -0.647212744, -5.41171872e-08, 0.762309432,
                -5.96274674e-08, 1, 2.0366441e-08, -0.762309432, -3.22731637e-08, -0.647212744)
        elseif MYLEVEL == 1625 or MYLEVEL <= 1649 then
            Ms = "Female Islander [Lv. 1625]"
            NameQuest = "AmazonQuest2"
            QuestLv = 1
            NameQ = "Female Islander"
            CFrameQ = CFrame.new(5445.11426, 601.603638, 751.129517, -0.346766561, 5.00326642e-08, -0.937951446,
                4.48732145e-08, 1, 3.67525779e-08, 0.937951446, -2.93443314e-08, -0.346766561)
            CFramePuk = CFrame.new(4758.92871, 730.33374, 800.998047, -0.100775175, -5.07539504e-08, -0.994909227,
                -2.28484591e-08, 1, -4.86993095e-08, 0.994909227, 1.78244619e-08, -0.100775175)
        elseif MYLEVEL == 1650 or MYLEVEL <= 1699 then
            Ms = "Giant Islander [Lv. 1650]"
            NameQuest = "AmazonQuest2"
            QuestLv = 2
            NameQ = "Giant Islander"
            CFrameQ = CFrame.new(5445.11426, 601.603638, 751.129517, -0.346766561, 5.00326642e-08, -0.937951446,
                4.48732145e-08, 1, 3.67525779e-08, 0.937951446, -2.93443314e-08, -0.346766561)
            CFramePuk = CFrame.new(4736.1333, 601.373596, -123.942299, -0.651415646, 1.13692966e-08, -0.758721054,
                1.02050288e-08, 1, 6.2230785e-09, 0.758721054, -3.6889598e-09, -0.651415646)
        elseif MYLEVEL == 1700 or MYLEVEL <= 1724 then
            Ms = "Marine Commodore [Lv. 1700]"
            NameQuest = "MarineTreeIsland"
            QuestLv = 1
            NameQ = "Marine Commodore"
            CFrameQ = CFrame.new(2180.83911, 28.7054462, -6739.44824, 0.977863014, 6.92042956e-09, -0.20924598,
                -1.01339639e-08, 1, -1.42855736e-08, 0.20924598, 1.60898246e-08, 0.977863014)
            CFramePuk = CFrame.new(2447, 73.1255493, -7470, 1, 4.06989891e-08, 4.79087976e-15, -4.06989891e-08, 1,
                2.86651343e-08, -3.62423799e-15, -2.86651343e-08, 1)
        elseif MYLEVEL == 1725 or MYLEVEL <= 1774 then
            Ms = "Marine Rear Admiral [Lv. 1725]"
            NameQuest = "MarineTreeIsland"
            QuestLv = 2
            NameQ = "Marine Rear Admiral"
            CFrameQ = CFrame.new(2180.83911, 28.7054462, -6739.44824, 0.977863014, 6.92042956e-09, -0.20924598,
                -1.01339639e-08, 1, -1.42855736e-08, 0.20924598, 1.60898246e-08, 0.977863014)
            CFramePuk = CFrame.new(3660.3833, 160.524063, -6971.11328, 0.771100104, -4.33134666e-08, -0.636713922,
                -7.22266069e-09, 1, -7.67736665e-08, 0.636713922, 6.37989501e-08, 0.771100104)
        elseif MYLEVEL == 1775 or MYLEVEL <= 1800 then
            Ms = "Fishman Raider [Lv. 1775]"
            NameQuest = "DeepForestIsland3"
            QuestLv = 1
            NameQ = "Fishman Raider"
            CFrameQ = CFrame.new(-10582.7578, 331.762634, -8758.56543, 0.911287963, 8.23484143e-08, -0.411769718,
                -7.27268628e-08, 1, 3.90346848e-08, 0.411769718, -5.62511859e-09, 0.911287963)
            CFramePuk = CFrame.new(-10615.6611, 331.762634, -8446.38574, 0.30275172, -4.96152719e-09, -0.953069448,
                -2.92618618e-09, 1, -6.13537132e-09, 0.953069448, 4.64635308e-09, 0.30275172)
        elseif MYLEVEL == 1800 or MYLEVEL <= 1824 then
            Ms = "Fishman Captain [Lv. 1800]"
            NameQuest = "DeepForestIsland3"
            QuestLv = 2
            NameQ = "Fishman Captain"
            CFrameQ = CFrame.new(-10582.7578, 331.762634, -8758.56543, 0.911287963, 8.23484143e-08, -0.411769718,
                -7.27268628e-08, 1, 3.90346848e-08, 0.411769718, -5.62511859e-09, 0.911287963)
            CFramePuk = CFrame.new(-11040.3467, 331.762634, -8957.75684, -0.990780294, -5.54384094e-08, 0.135478467,
                -4.7334634e-08, 1, 6.30372483e-08, -0.135478467, 5.60432376e-08, -0.990780294)
        elseif MYLEVEL == 1825 or MYLEVEL <= 1849 then
            Ms = "Forest Pirate [Lv. 1825]"
            NameQuest = "DeepForestIsland"
            QuestLv = 1
            NameQ = "Forest Pirate"
            CFrameQ = CFrame.new(-13233.2686, 332.378143, -7627.66455, -0.905921221, 2.69652856e-09, 0.423446268,
                2.31737229e-09, 1, -1.41026579e-09, -0.423446268, -2.96307007e-10, -0.905921221)
            CFramePuk = CFrame.new(-13479, 332.378143, -7905, 1, -1.27257813e-08, 2.41825958e-15, 1.27257813e-08, 1,
                -8.67651977e-08, -1.3141047e-15, 8.67651977e-08, 1)
        elseif MYLEVEL == 1850 or MYLEVEL <= 1899 then
            Ms = "Mythological Pirate [Lv. 1850]"
            NameQuest = "DeepForestIsland"
            QuestLv = 2
            NameQ = "Mythological Pirate"
            CFrameQ = CFrame.new(-13233.2686, 332.378143, -7627.66455, -0.905921221, 2.69652856e-09, 0.423446268,
                2.31737229e-09, 1, -1.41026579e-09, -0.423446268, -2.96307007e-10, -0.905921221)
            CFramePuk = CFrame.new(-13676.1553, 469.788086, -6999.65527, 0.693832397, -2.62738986e-08, 0.720136523,
                -4.52658462e-08, 1, 8.00970454e-08, -0.720136523, -8.8171511e-08, 0.693832397)
        elseif MYLEVEL == 1900 or MYLEVEL <= 1924 then
            Ms = "Jungle Pirate [Lv. 1900]"
            NameQuest = "DeepForestIsland2"
            QuestLv = 1
            NameQ = "Jungle Pirate"
            CFrameQ = CFrame.new(-12682.1279, 390.860687, -9901.89746, 0.00872628205, 1.59673574e-09, -0.999961913,
                -5.25600941e-09, 1, 1.55092938e-09, 0.999961913, 5.2422755e-09, 0.00872628205)
            CFramePuk = CFrame.new(-12107, 331.738281, -10549, 1, -2.50327403e-09, -6.22370418e-15, 2.50327403e-09, 1,
                8.81249651e-09, 6.20164405e-15, -8.81249651e-09, 1)
        elseif MYLEVEL == 1925 or MYLEVEL <= 1974 then
            Ms = "Musketeer Pirate [Lv. 1925]"
            NameQuest = "DeepForestIsland2"
            QuestLv = 2
            NameQ = "Musketeer Pirate"
            CFrameQ = CFrame.new(-12682.1279, 390.860687, -9901.89746, 0.00872628205, 1.59673574e-09, -0.999961913,
                -5.25600941e-09, 1, 1.55092938e-09, 0.999961913, 5.2422755e-09, 0.00872628205)
            CFramePuk = CFrame.new(-13485.2305, 432.682373, -9857.01074, 0.994504631, 1.2369239e-08, -0.104692325,
                -8.4907642e-10, 1, 1.1008283e-07, 0.104692325, -1.09388999e-07, 0.994504631)
        elseif MYLEVEL == 1975 or MYLEVEL <= 1999 then
            Ms = "Reborn Skeleton [Lv. 1975]"
            NameQuest = "HauntedQuest1"
            QuestLv = 1
            NameQ = "Reborn Skeleton"
            CFrameQ = CFrame.new(-9482.11035, 142.104828, 5566.32861, 0.0620567501, -4.18429273e-08, -0.998072624,
                -3.89895867e-08, 1, -4.43479706e-08, 0.998072624, 4.1666528e-08, 0.0620567501)
            CFramePuk = CFrame.new(-8762.33496, 142.104828, 6015.7627, -0.999993861, -2.26600214e-08, 0.00350279221,
                -2.28456738e-08, 1, -5.29611519e-08, -0.00350279221, -5.30408499e-08, -0.999993861)
        elseif MYLEVEL == 2000 or MYLEVEL <= 2024 then
            Ms = "Living Zombie [Lv. 2000]"
            NameQuest = "HauntedQuest1"
            QuestLv = 2
            NameQ = "Living Zombie"
            CFrameQ = CFrame.new(-9482.11035, 142.104828, 5566.32861, 0.0620567501, -4.18429273e-08, -0.998072624,
                -3.89895867e-08, 1, -4.43479706e-08, 0.998072624, 4.1666528e-08, 0.0620567501)
            CFramePuk = CFrame.new(-10099.1494, 138.626678, 5930.86279, 0.241616711, -9.62791873e-08, -0.970371783,
                5.61582709e-08, 1, -8.52357971e-08, 0.970371783, -3.39000081e-08, 0.241616711)
        elseif MYLEVEL == 2025 or MYLEVEL <= 2049 then
            Ms = "Demonic Soul [Lv. 2025]"
            NameQuest = "HauntedQuest2"
            QuestLv = 1
            NameQ = "Demonic Soul"
            CFrameQ = CFrame.new(-9514.25195, 172.104828, 6077.22998, 0.0446508788, -7.60616636e-09, 0.999002635,
                7.97889257e-08, 1, 4.04755696e-09, -0.999002635, 7.95286255e-08, 0.0446508788)
            CFramePuk = CFrame.new(-9513.54199, 172.104828, 6143.45459, -0.777332306, -2.16450324e-08, -0.62909019,
                -5.07872073e-08, 1, 2.83480883e-08, 0.62909019, 5.39856195e-08, -0.777332306)
        elseif MYLEVEL == 2050 or MYLEVEL <= 2074 then
            Ms = "Posessed Mummy [Lv. 2050]"
            NameQuest = "HauntedQuest2"
            QuestLv = 2
            NameQ = "Posessed Mummy"
            CFrameQ = CFrame.new(-9514.25195, 172.104828, 6077.22998, 0.0446508788, -7.60616636e-09, 0.999002635,
                7.97889257e-08, 1, 4.04755696e-09, -0.999002635, 7.95286255e-08, 0.0446508788)
            CFramePuk = CFrame.new(-9580.24609, 5.79254198, 6190.47852, 0.462460369, 5.16216367e-08, -0.886639953,
                -7.72594788e-08, 1, 1.79240605e-08, 0.886639953, 6.0212173e-08, 0.462460369)
        elseif MYLEVEL == 2075 or MYLEVEL <= 2099 then
            Ms = "Peanut Scout [Lv. 2075]"
            NameQuest = "NutsIslandQuest"
            QuestLv = 1
            NameQ = "Peanut Scout"
            CFrameQ = CFrame.new(-2103.18872, 38.1041794, -10193.7656, 0.7310462, 2.46138327e-08, 0.682327926,
                -5.02823738e-09, 1, -3.06860635e-08, -0.682327926, 1.90020231e-08, 0.7310462)
            CFramePuk = CFrame.new(-2221.45996, 38.103817, -10086.0762, -0.994582355, 2.09503472e-08, 0.103951879,
                2.41223095e-08, 1, 2.92565758e-08, -0.103951879, 3.16056337e-08, -0.994582355)
        elseif MYLEVEL == 2100 or MYLEVEL <= 2124 then
            Ms = "Peanut President [Lv. 2100]"
            NameQuest = "NutsIslandQuest"
            QuestLv = 2
            NameQ = "Peanut President"
            CFrameQ = CFrame.new(-2103.18872, 38.1041794, -10193.7656, 0.7310462, 2.46138327e-08, 0.682327926,
                -5.02823738e-09, 1, -3.06860635e-08, -0.682327926, 1.90020231e-08, 0.7310462)
            CFramePuk = CFrame.new(-2171.88647, 88.2396011, -10531.9512, 0.691500723, 5.31482591e-08, -0.722375751,
                -2.70291771e-08, 1, 4.7700329e-08, 0.722375751, -1.34595908e-08, 0.691500723)
        elseif MYLEVEL == 2125 or MYLEVEL <= 2149 then
            Ms = "Ice Cream Chef [Lv. 2125]"
            NameQuest = "IceCreamIslandQuest"
            QuestLv = 1
            NameQ = "Ice Cream Chef"
            CFrameQ = CFrame.new(-820.991455, 65.8195343, -10965.4316, 0.832442105, 3.44203599e-08, -0.554112017,
                -3.14893249e-08, 1, 1.48116621e-08, 0.554112017, 5.11876364e-09, 0.832442105)
            CFramePuk = CFrame.new(-761.110657, 164.200974, -10929.7031, -0.903523564, -2.8124143e-08, 0.428538442,
                -5.52620127e-09, 1, 5.39766987e-08, -0.428538442, 4.64010306e-08, -0.903523564)
        elseif MYLEVEL == 2150 or MYLEVEL <= 2199 then
            Ms = "Ice Cream Commander [Lv. 2150]"
            NameQuest = "IceCreamIslandQuest"
            QuestLv = 2
            NameQ = "Ice Cream Commander"
            CFrameQ = CFrame.new(-820.991455, 65.8195343, -10965.4316, 0.832442105, 3.44203599e-08, -0.554112017,
                -3.14893249e-08, 1, 1.48116621e-08, 0.554112017, 5.11876364e-09, 0.832442105)
            CFramePuk = CFrame.new(-683.515137, 97.7532196, -11270.5254, -0.249526113, -3.42524373e-08, -0.968368053,
                -4.59147245e-08, 1, -2.35401334e-08, 0.968368053, 3.85884746e-08, -0.249526113)
        elseif MYLEVEL == 2200 or MYLEVEL <= 2224 then
            Ms = "Cookie Crafter [Lv. 2200]"
            NameQuest = "CakeQuest1"
            QuestLv = 1
            NameQ = "Cookie Crafter"
            CFrameQ = CFrame.new(-2021.28113, 37.7982178, -12027.1602, 0.876975715, 2.42050024e-08, 0.480534643,
                -1.83145179e-08, 1, -1.69469878e-08, -0.480534643, 6.06133632e-09, 0.876975715)
            CFramePuk = CFrame.new(-2362.1604, 37.7981148, -12116.2031, 0.428214997, 1.03298156e-07, 0.903676867,
                -1.24923467e-08, 1, -1.08389123e-07, -0.903676867, 3.51248026e-08, 0.428214997)
        elseif MYLEVEL == 2225 or MYLEVEL <= 2249 then
            Ms = "Cake Guard [Lv. 2225]"
            NameQuest = "CakeQuest1"
            QuestLv = 2
            NameQ = "Cake Guard"
            CFrameQ = CFrame.new(-2021.28113, 37.7982178, -12027.1602, 0.876975715, 2.42050024e-08, 0.480534643,
                -1.83145179e-08, 1, -1.69469878e-08, -0.480534643, 6.06133632e-09, 0.876975715)
            CFramePuk = CFrame.new(-1560.17944, 37.7981339, -12440.5781, -0.560352206, 1.90654585e-08, -0.828254402,
                6.60573107e-08, 1, -2.16719656e-08, 0.828254402, -6.68561952e-08, -0.560352206)
        elseif MYLEVEL == 2250 or MYLEVEL <= 2274 then
            Ms = "Baking Staff [Lv. 2250]"
            NameQuest = "CakeQuest2"
            QuestLv = 1
            NameQ = "Baking Staff"
            CFrameQ = CFrame.new(-1929.3186, 37.7981339, -12843.3857, -0.994816065, 6.2958283e-09, 0.101690687,
                6.02614314e-09, 1, -2.95921043e-09, -0.101690687, -2.33106734e-09, -0.994816065)
            CFramePuk = CFrame.new(-1874.04688, 74.015831, -13002.7959, 0.958144426, -9.20437699e-08, -0.286285222,
                1.05663617e-07, 1, 3.21261275e-08, 0.286285222, -6.10314004e-08, 0.958144426)
        elseif MYLEVEL == 2275 or MYLEVEL <= 2299 then
            Ms = "Head Baker [Lv. 2275]"
            NameQuest = "CakeQuest2"
            QuestLv = 2
            NameQ = "Head Baker"
            CFrameQ = CFrame.new(-1929.3186, 37.7981339, -12843.3857, -0.994816065, 6.2958283e-09, 0.101690687,
                6.02614314e-09, 1, -2.95921043e-09, -0.101690687, -2.33106734e-09, -0.994816065)
            CFramePuk = CFrame.new(-2205.25171, 108.351257, -12784.6475, 0.999649942, 1.09295986e-08, -0.0264567528,
                -9.22357479e-09, 1, 6.46055156e-08, 0.0264567528, -6.43388702e-08, 0.999649942)
        elseif MYLEVEL == 2300 or MYLEVEL <= 2324 then
            Ms = "Cocoa Warrior [Lv. 2300]"
            NameQuest = "ChocQuest1"
            QuestLv = 1
            NameQ = "Cocoa Warrior"
            CFrameQ = CFrame.new(231.562515, 24.7342396, -12196.9277, 0.996608198, -4.87148775e-08, -0.0822927728,
                4.61355079e-08, 1, -3.32453354e-08, 0.0822927728, 2.93359523e-08, 0.996608198)
            CFramePuk = CFrame.new(-26.0082874, 24.7343502, -12253.001, -0.17375651, 7.9442728e-08, 0.984788656,
                1.18449632e-08, 1, -7.85798946e-08, -0.984788656, -1.98898231e-09, -0.17375651)
        elseif MYLEVEL == 2325 or MYLEVEL <= 2349 then
            Ms = "Chocolate Bar Battler [Lv. 2325]"
            NameQuest = "ChocQuest1"
            QuestLv = 2
            NameQ = "Chocolate Bar Battler"
            CFrameQ = CFrame.new(231.562515, 24.7342396, -12196.9277, 0.996608198, -4.87148775e-08, -0.0822927728,
                4.61355079e-08, 1, -3.32453354e-08, 0.0822927728, 2.93359523e-08, 0.996608198)
            CFramePuk = CFrame.new(715.227661, 64.5699463, -12601.4971, 0.375136077, -3.84623213e-08, 0.926969767,
                1.12107639e-08, 1, 3.69556403e-08, -0.926969767, -3.47135498e-09, 0.375136077)
        elseif MYLEVEL == 2350 or MYLEVEL <= 2374 then
            Ms = "Sweet Thief [Lv. 2350]"
            NameQuest = "ChocQuest2"
            QuestLv = 1
            NameQ = "Sweet Thief"
            CFrameQ = CFrame.new(147.670837, 24.7938328, -12775.2656, -0.274139136, 7.20163911e-08, -0.961690068,
                7.48291242e-08, 1, 5.35544693e-08, 0.961690068, -5.72810492e-08, -0.274139136)
            CFramePuk = CFrame.new(59.2454491, 57.2388878, -12634.1523, 0.97673136, -3.85135479e-08, 0.214466438,
                3.43798909e-08, 1, 2.30041923e-08, -0.214466438, -1.50955834e-08, 0.97673136)
        elseif MYLEVEL == 2375 or MYLEVEL <= 2400 then
            Ms = "Candy Rebel [Lv. 2375]"
            NameQuest = "ChocQuest2"
            QuestLv = 2
            NameQ = "Candy Rebel"
            CFrameQ = CFrame.new(147.670837, 24.7938328, -12775.2656, -0.274139136, 7.20163911e-08, -0.961690068,
                7.48291242e-08, 1, 5.35544693e-08, 0.961690068, -5.72810492e-08, -0.274139136)
            CFramePuk = CFrame.new(72.7375183, 24.7938499, -12939.2383, -0.87948513, 9.16761138e-08, -0.47592634,
                7.88268579e-08, 1, 4.69590802e-08, 0.47592634, 3.78403309e-09, -0.87948513)
        elseif MYLEVEL == 2400 or MYLEVEL <= 2425 then
            Ms = "Candy Pirate [Lv. 2400]"
            NameQuest = "CandyQuest1"
            QuestLv = 1
            NameQ = "Candy Pirate"
            CFrameQ = CFrame.new(-1151.48987, 16.1422901, -14445.6904, -0.316594511, -6.85698254e-08, -0.948560953, -2.05343067e-08, 1, -6.54346692e-08, 0.948560953, -1.23821675e-09, -0.316594511)
            CFramePuk = CFrame.new(-1408.46521, 16.1423531, -14552.2041, 0.90175873, -8.17216943e-08, -0.432239741, 7.81264475e-08, 1, -2.60746162e-08, 0.432239741, -1.02563433e-08, 0.90175873)
    elseif MYLEVEL >=  2426 then
            Ms = "Snow Demon [Lv. 2425]"
            NameQuest = "CandyQuest1"
            QuestLv = 2
            NameQ = "Snow Demon"
            CFrameQ = CFrame.new(-1151.48987, 16.1422901, -14445.6904, -0.316594511, -6.85698254e-08, -0.948560953, -2.05343067e-08, 1, -6.54346692e-08, 0.948560953, -1.23821675e-09, -0.316594511)
            CFramePuk = CFrame.new(-777.070862, 23.5809536, -14453.0078, 0.33384338, 0, -0.942628562, 0, 1, 0, 0.942628562, 0, 0.33384338)
        end
    end
end

function TP(gotoCFrame)
    pcall(function()
        game.Players.LocalPlayer.Character.Humanoid.Sit = false
    end)
    if (game:GetService("Players")["LocalPlayer"].Character:WaitForChild('HumanoidRootPart').Position -
        gotoCFrame.Position).Magnitude <= 250 then
        pcall(function()
            tween:Cancel()
        end)
        game:GetService("Players")["LocalPlayer"].Character:WaitForChild('HumanoidRootPart').CFrame = gotoCFrame
    else
        local tween_s = game:service "TweenService"
        local info = TweenInfo.new(
            (game:GetService("Players")["LocalPlayer"].Character:WaitForChild('HumanoidRootPart').Position -
                gotoCFrame.Position).Magnitude / 300, Enum.EasingStyle.Linear)
        local tween, err = pcall(function()
            tween = tween_s:Create(game.Players.LocalPlayer.Character:WaitForChild('HumanoidRootPart'), info, {
                CFrame = gotoCFrame
            })
            tween:Play()
        end)
        if not tween then
            return err
        end
    end
end

-- Level Farm
spawn(function()
    while wait() do
        if getgenv().LevelFarm then
            pcall(function()         
                CheckQuest()
                    if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameQ) then
                        StartMagnet = false
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                    end
                    if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                        StartMagnet = false
                        CheckQuest()
                        repeat wait() 
                            TP(CFrameQ)  
                        until (CFrameQ.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not getgenv().LevelFarm 
                        if (CFrameQ.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
                        if game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                                wait(0.5)
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NameQuest,QuestLv)
                                wait(0.5)
                            end             
                        end
                    elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                        CheckQuest()
                        if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                                    if v.Name == Ms then
                                        repeat wait()
                                            
                                            if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameQ) then
                                                if not game.Players.LocalPlayer.Character:FindFirstChild('HasBuso') then
                                                    game.ReplicatedStorage.Remotes.CommF_:InvokeServer('Buso')
                                                end
                                                itemequip("Combat") 
                                                StartMagnet = true               
                                                if AttackRandomType == 1 then
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 20, 1))
                                                elseif AttackRandomType == 2 then
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 1, 10))
                                                elseif AttackRandomType == 3 then
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(1, 1, -10))
                                                elseif AttackRandomType == 4 then
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(10, 1, 0))
                                                elseif AttackRandomType == 5 then
                                                    TP(v.HumanoidRootPart.CFrame * CFrame.new(-10, 1, 0))
                                                end
                                                PosMon = v.HumanoidRootPart.CFrame
                                                v.HumanoidRootPart.Size = Vector3.new(60,60,60)
                                                v.HumanoidRootPart.CanCaillde = false
                                            
                                            else
                                                StartMagnet = false
                                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                                            end
                                        until not getgenv().LevelFarm   or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                        
                                    end
                                end
                            end
                        else
                            StartMagnet = false
                            if game:GetService("ReplicatedStorage"):FindFirstChild(Ms) then
                                TP(game:GetService("ReplicatedStorage"):FindFirstChild(Ms).HumanoidRootPart.CFrame)
                            else
                                TP(CFramePuk)
                            end
                        end
                    end
                end)
            end    
        end
    end)

    spawn(function()
        game:GetService("RunService").Heartbeat:Connect(function() CheckQuest()
            pcall(function()
                for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                    if getgenv().LevelFarm and StartMagnet and v.Name == Ms and (v.HumanoidRootPart.Position - PosMon.Position).Magnitude <= 350 then
                        v.HumanoidRootPart.CFrame = PosMon
                        v.HumanoidRootPart.CanCollide = false
                        v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                        if v.Humanoid:FindFirstChild("Animator") then
                            v.Humanoid.Animator:Destroy()
                        end
                        sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
                    end
                end
            end)
        end)
    end)

    -- Noclip function

    spawn(function()
        pcall(function()
            game:GetService("RunService").Stepped:Connect(function()
                if getgenv().LevelFarm then
                    if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
                        local Noclip = Instance.new("BodyVelocity")
                        Noclip.Name = "BodyClip"
                        Noclip.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
                        Noclip.MaxForce = Vector3.new(100000,100000,100000)
                        Noclip.Velocity = Vector3.new(0,0,0)
                    end
                else	
                    if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
                        game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
                    end
                end
            end)
        end)
    end)

    ------Fast attack
    local plr = game.Players.LocalPlayer
        
    local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
    local CbFw2 = CbFw[2]
    
    function GetCurrentBlade() 
        local p13 = CbFw2.activeController
        local ret = p13.blades[1]
        if not ret then return end
        while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
        return ret
    end
    function AttackNoCD() 
        local AC = CbFw2.activeController
        for i = 1, 1 do 
            local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
                plr.Character,
                {plr.Character.HumanoidRootPart},
                60
            )
            local cac = {}
            local hash = {}
            for k, v in pairs(bladehit) do
                if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                    table.insert(cac, v.Parent.HumanoidRootPart)
                    hash[v.Parent] = true
                end
            end
            bladehit = cac
            if #bladehit > 0 then
                local u8 = debug.getupvalue(AC.attack, 5)
                local u9 = debug.getupvalue(AC.attack, 6)
                local u7 = debug.getupvalue(AC.attack, 4)
                local u10 = debug.getupvalue(AC.attack, 7)
                local u12 = (u8 * 798405 + u7 * 727595) % u9
                local u13 = u7 * 798405
                (function()
                    u12 = (u12 * u9 + u13) % 1099511627776
                    u8 = math.floor(u12 / u9)
                    u7 = u12 - u8 * u9
                end)()
                u10 = u10 + 1
                debug.setupvalue(AC.attack, 5, u8)
                debug.setupvalue(AC.attack, 6, u9)
                debug.setupvalue(AC.attack, 4, u7)
                debug.setupvalue(AC.attack, 7, u10)
                pcall(function()
                    for k, v in pairs(AC.animator.anims.basic) do
                        v:Play()
                    end                  
                end)
                if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                    game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
                end
            end
        end
    end 
    
    
    require(game.ReplicatedStorage.Util.CameraShaker):Stop()
    spawn(function()
        while wait() do
            pcall(function()
                if  getgenv().LevelFarm then
                    repeat task.wait(.1)
                        AttackNoCD()
                    until not  getgenv().LevelFarm
                end
            end)
        end
    end)
