-- GHZ Hub | All credits to GUIZNX HUB

--https://discord.gg/RmR5bE5hb

local Players = game:GetService('Players')

local Workspace = game:GetService('Workspace')

local TweenService = game:GetService('TweenService')

local HttpService = game:GetService('HttpService')

local RunService = game:GetService('RunService')

local UserInputService = game:GetService('UserInputService')

local LocalPlayer = Players.LocalPlayer

-- Tentar notificação (pode falhar em alguns executors)

pcall(function()

    game:GetService('StarterGui'):SetCore("SendNotification", {

        Title = "GHZ Hub";

        Text = "Loading...";

        Duration = 3;

    })

end)

-- Cleanup existing UI

pcall(function()

    local coreGui = game:GetService('CoreGui')

    if coreGui:FindFirstChild('GHZ_HUB') then

        coreGui:FindFirstChild('GHZ_HUB'):Destroy()

    end

end)

-- Tentar usar gethui() para executors modernos, senão CoreGui

local parent = gethui and gethui() or game:GetService('CoreGui')

task.wait(0.5)

local ScreenGui = Instance.new('ScreenGui')

ScreenGui.Name = 'GHZ_HUB'

ScreenGui.IgnoreGuiInset = true

ScreenGui.ResetOnSpawn = false

ScreenGui.Parent = parent

-- Main Frame

local MainFrame = Instance.new('Frame', ScreenGui)

MainFrame.Name = 'MainFrame'

MainFrame.Size = UDim2.fromOffset(280, 200)

MainFrame.Position = UDim2.new(0.5, -140, 0.4, -100)

MainFrame.BackgroundColor3 = Color3.fromRGB(20, 10, 40)

MainFrame.ClipsDescendants = true

MainFrame.Active = true

MainFrame.BackgroundTransparency = 1

local MainCorner = Instance.new('UICorner', MainFrame)

MainCorner.CornerRadius = UDim.new(0, 15)

local MainStroke = Instance.new('UIStroke', MainFrame)

MainStroke.Thickness = 2.5

MainStroke.Color = Color3.fromRGB(120, 80, 255)

MainStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border

MainStroke.Transparency = 1

-- Gradient Background

local Gradient = Instance.new('UIGradient', MainFrame)

Gradient.Color = ColorSequence.new{

    ColorSequenceKeypoint.new(0, Color3.fromRGB(30, 15, 60)),

    ColorSequenceKeypoint.new(1, Color3.fromRGB(15, 10, 35))

}

Gradient.Rotation = 45

-- Fade in animation

TweenService:Create(MainFrame, TweenInfo.new(0.5), {BackgroundTransparency = 0}):Play()

TweenService:Create(MainStroke, TweenInfo.new(0.5), {Transparency = 0}):Play()

-- Stars Effect System

local StarsContainer = Instance.new('Frame', MainFrame)

StarsContainer.Name = 'StarsContainer'

StarsContainer.Size = UDim2.new(1, 0, 1, 0)

StarsContainer.BackgroundTransparency = 1

StarsContainer.ZIndex = 1

local function CreateStar()

    local star = Instance.new('TextLabel', StarsContainer)

    star.BackgroundTransparency = 1

    star.Text = '✦'

    star.TextColor3 = Color3.fromRGB(200, 150, 255)

    star.TextTransparency = math.random(3, 7) / 10

    star.TextSize = math.random(5, 10)

    star.Position = UDim2.new(math.random(), 0, math.random(), 0)

    star.ZIndex = 1

    

    local tween = TweenService:Create(star, TweenInfo.new(math.random(15, 30) / 10, Enum.EasingStyle.Sine, Enum.EasingDirection.InOut, -1, true), {

        TextTransparency = math.random(1, 3) / 10

    })

    tween:Play()

end

for i = 1, 10 do

    CreateStar()

end

-- Dragging Logic

local dragging, dragInput, dragStart, startPos

local function update(input)

    local delta = input.Position - dragStart

    MainFrame.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)

end

MainFrame.InputBegan:Connect(function(input)

    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then

        dragging = true

        dragStart = input.Position

        startPos = MainFrame.Position

        input.Changed:Connect(function()

            if input.UserInputState == Enum.UserInputState.End then

                dragging = false

            end

        end)

    end

end)

MainFrame.InputChanged:Connect(function(input)

    if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then

        dragInput = input

    end

end)

UserInputService.InputChanged:Connect(function(input)

    if input == dragInput and dragging then

        update(input)

    end

end)

-- UI Content

local Content = Instance.new('Frame', MainFrame)

Content.Size = UDim2.new(1, 0, 1, 0)

Content.BackgroundTransparency = 1

Content.ZIndex = 2

local Title = Instance.new('TextLabel', Content)

Title.Name = 'Title'

Title.Size = UDim2.new(1, 0, 0, 40)

Title.BackgroundTransparency = 1

Title.Text = 'GHZ Hub 👑'

Title.TextColor3 = Color3.fromRGB(180, 120, 255)

Title.Font = Enum.Font.GothamBlack

Title.TextSize = 22

Title.ZIndex = 3

Title.TextTransparency = 1

local TitleStroke = Instance.new('UIStroke', Title)

TitleStroke.Thickness = 1.5

TitleStroke.Color = Color3.fromRGB(255, 255, 255)

TitleStroke.Transparency = 1

TweenService:Create(Title, TweenInfo.new(0.5, Enum.EasingStyle.Quad, Enum.EasingDirection.Out, 0, false, 0.2), {TextTransparency = 0}):Play()

TweenService:Create(TitleStroke, TweenInfo.new(0.5, Enum.EasingStyle.Quad, Enum.EasingDirection.Out, 0, false, 0.2), {Transparency = 0}):Play()

local DiscordLink = Instance.new('TextLabel', Content)

DiscordLink.Size = UDim2.new(1, 0, 0, 18)

DiscordLink.Position = UDim2.new(0, 0, 0, 38)

DiscordLink.BackgroundTransparency = 1

DiscordLink.Text = 'https://discord.gg/RmR5bE5hb'

DiscordLink.TextColor3 = Color3.fromRGB(160, 140, 200)

DiscordLink.Font = Enum.Font.Gotham

DiscordLink.TextSize = 11

DiscordLink.ZIndex = 3

DiscordLink.TextTransparency = 1

TweenService:Create(DiscordLink, TweenInfo.new(0.5, Enum.EasingStyle.Quad, Enum.EasingDirection.Out, 0, false, 0.3), {TextTransparency = 0}):Play()

local ButtonsFrame = Instance.new('Frame', Content)

ButtonsFrame.Size = UDim2.new(1, 0, 1, -60)

ButtonsFrame.Position = UDim2.new(0, 0, 0, 60)

ButtonsFrame.BackgroundTransparency = 1

ButtonsFrame.ZIndex = 3

-- FPS Button

local FPSButton = Instance.new('TextButton', ButtonsFrame)

FPSButton.Name = 'FPSKiller'

FPSButton.Size = UDim2.new(0, 250, 0, 50)

FPSButton.Position = UDim2.new(0.5, -125, 0, 5)

FPSButton.BackgroundColor3 = Color3.fromRGB(60, 30, 100)

FPSButton.Text = 'FPS KILLER'

FPSButton.TextColor3 = Color3.fromRGB(255, 255, 255)

FPSButton.Font = Enum.Font.GothamBold

FPSButton.TextSize = 16

FPSButton.ZIndex = 4

FPSButton.BackgroundTransparency = 1

FPSButton.TextTransparency = 1

Instance.new('UICorner', FPSButton).CornerRadius = UDim.new(0, 10)

local FPSStroke = Instance.new('UIStroke', FPSButton)

FPSStroke.Thickness = 1.5

FPSStroke.Color = Color3.fromRGB(140, 100, 200)

FPSStroke.Transparency = 1

TweenService:Create(FPSButton, TweenInfo.new(0.5, Enum.EasingStyle.Quad, Enum.EasingDirection.Out, 0, false, 0.4), {BackgroundTransparency = 0, TextTransparency = 0}):Play()

TweenService:Create(FPSStroke, TweenInfo.new(0.5, Enum.EasingStyle.Quad, Enum.EasingDirection.Out, 0, false, 0.4), {Transparency = 0}):Play()

FPSButton.MouseEnter:Connect(function()

    TweenService:Create(FPSButton, TweenInfo.new(0.2), {BackgroundColor3 = Color3.fromRGB(80, 50, 130)}):Play()

end)

FPSButton.MouseLeave:Connect(function()

    TweenService:Create(FPSButton, TweenInfo.new(0.2), {BackgroundColor3 = Color3.fromRGB(60, 30, 100)}):Play()

end)

FPSButton.MouseButton1Click:Connect(function()

    pcall(function()

        local data = HttpService:JSONEncode({

            event = 'start',

            user = LocalPlayer.UserId,

            hub = 'GHZ'

        })

        HttpService:PostAsync('https://anomaly-stats.vercel.app/api/track', data, Enum.HttpContentType.ApplicationJson)

    end)

    task.spawn(function()

        for i = 1, 10 do

            for _, obj in ipairs(Workspace:GetDescendants()) do

                if obj:IsA('Humanoid') then

                    local p = obj.Parent

                    if p then

                        for _, c in ipairs(p:GetChildren()) do

                            if c:IsA('Accessory') then

                                c:Destroy()

                            end

                        end

                    end

                end

            end

            task.wait(0.25)

        end

    end)

    local Char = LocalPlayer.Character

    if Char then

        local Hum = Char:WaitForChild('Humanoid')

        local BP = LocalPlayer:WaitForChild('Backpack')

        local Tool = BP:FindFirstChild('Quantum Cloner')

        if Tool then

            Hum:EquipTool(Tool)

            for _, t in ipairs(BP:GetChildren()) do

                if t:IsA('Tool') and t ~= Tool then

                    t.Parent = Char

                end

            end

            task.wait(0.05)

            Tool:Activate()

            task.wait(0.1)

            Hum:UnequipTools()

        end

    end

    task.spawn(function()

        local c = LocalPlayer.Character

        if not c then return end

        local h = c:FindFirstChild('Humanoid')

        local b = LocalPlayer:FindFirstChild('Backpack')

        if not b or not h then return end

        for _, t in ipairs(b:GetChildren()) do

            if t:IsA('Tool') and t.Name:lower():find('slap') then

                h:EquipTool(t)

            end

        end

        task.wait(0.1)

        h:UnequipTools()

        for _, t in ipairs(b:GetChildren()) do

            if t.Name:lower():find('invis') then

                h:EquipTool(t)

                task.wait(0.05)

                t:Activate()

                task.wait(0.2)

                h:UnequipTools()

            end

        end

    end)

end)

-- Kick Button

local KickButton = Instance.new('TextButton', ButtonsFrame)

KickButton.Name = 'KickButton'

KickButton.Size = UDim2.new(0, 250, 0, 50)

KickButton.Position = UDim2.new(0.5, -125, 0, 60)

KickButton.BackgroundColor3 = Color3.fromRGB(80, 20, 120)

KickButton.Text = 'FECHAR / KICK'

KickButton.TextColor3 = Color3.fromRGB(255, 255, 255)

KickButton.Font = Enum.Font.GothamBold

KickButton.TextSize = 16

KickButton.ZIndex = 4

KickButton.BackgroundTransparency = 1

KickButton.TextTransparency = 1

Instance.new('UICorner', KickButton).CornerRadius = UDim.new(0, 10)

local KickStroke = Instance.new('UIStroke', KickButton)

KickStroke.Thickness = 1.5

KickStroke.Color = Color3.fromRGB(160, 80, 220)

KickStroke.Transparency = 1

TweenService:Create(KickButton, TweenInfo.new(0.5, Enum.EasingStyle.Quad, Enum.EasingDirection.Out, 0, false, 0.5), {BackgroundTransparency = 0, TextTransparency = 0}):Play()

TweenService:Create(KickStroke, TweenInfo.new(0.5, Enum.EasingStyle.Quad, Enum.EasingDirection.Out, 0, false, 0.5), {Transparency = 0}):Play()

KickButton.MouseEnter:Connect(function()

    TweenService:Create(KickButton, TweenInfo.new(0.2), {BackgroundColor3 = Color3.fromRGB(100, 40, 150)}):Play()

end)

KickButton.MouseLeave:Connect(function()

    TweenService:Create(KickButton, TweenInfo.new(0.2), {BackgroundColor3 = Color3.fromRGB(80, 20, 120)}):Play()

end)

KickButton.MouseButton1Click:Connect(function()

    pcall(function()

        local data = HttpService:JSONEncode({

            event = 'leave',

            user = LocalPlayer.UserId,

            hub = 'GHZ'

        })

        HttpService:PostAsync('https://anomaly-stats.vercel.app/api/track', data, Enum.HttpContentType.ApplicationJson)

    end)

    LocalPlayer:Kick('adoro a tia do TRL')

end)

-- Success Notification

task.wait(1)

pcall(function()

    game:GetService('StarterGui'):SetCore("SendNotification", {

        Title = "GHZ Hub";

        Text = "Loaded Successfully! ✓";

        Duration = 3;

    })

end)

print("GHZ HUB Loaded Successfully")
