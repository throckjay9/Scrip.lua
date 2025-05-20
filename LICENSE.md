-- LocalScript em StarterPlayerScripts

local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local player = Players.LocalPlayer

-- Criar a GUI
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "FF_GUI"
screenGui.ResetOnSpawn = false
screenGui.Parent = player:WaitForChild("PlayerGui")

-- Criar o Frame da GUI
local mainFrame = Instance.new("Frame")
mainFrame.Name = "MainFrame"
mainFrame.Size = UDim2.new(0.3, 0, 0.3, 0)
mainFrame.Position = UDim2.new(0.35, 0, 0.1, 0)
mainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
mainFrame.BackgroundTransparency = 0.2
mainFrame.BorderSizePixel = 0
mainFrame.Visible = false
mainFrame.Parent = screenGui

-- Título da GUI
local titleLabel = Instance.new("TextLabel")
titleLabel.Name = "TitleLabel"
titleLabel.Size = UDim2.new(1, 0, 0.2, 0)
titleLabel.Position = UDim2.new(0, 0, 0, 0)
titleLabel.BackgroundTransparency = 1
titleLabel.Text = "🔥 FREE FIRE MAX GUI 🔥"
titleLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
titleLabel.TextScaled = true
titleLabel.Font = Enum.Font.GothamBold
titleLabel.Parent = mainFrame

-- Botão Aimbot
local aimbotOn = false
local aimbotButton = Instance.new("TextButton")
aimbotButton.Size = UDim2.new(0.8, 0, 0.15, 0)
aimbotButton.Position = UDim2.new(0.1, 0, 0.25, 0)
aimbotButton.Text = "Ativar Aimbot"
aimbotButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
aimbotButton.TextColor3 = Color3.fromRGB(255, 255, 255)
aimbotButton.Font = Enum.Font.Gotham
aimbotButton.TextScaled = true
aimbotButton.Parent = mainFrame

aimbotButton.MouseButton1Click:Connect(function()
	aimbotOn = not aimbotOn
	aimbotButton.Text = aimbotOn and "Desativar Aimbot" or "Ativar Aimbot"
	print("Aimbot:", aimbotOn)
end)

-- Botão ESP Caixa
local espBoxOn = false
local espBoxButton = Instance.new("TextButton")
espBoxButton.Size = UDim2.new(0.8, 0, 0.15, 0)
espBoxButton.Position = UDim2.new(0.1, 0, 0.45, 0)
espBoxButton.Text = "Ativar ESP Caixa"
espBoxButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
espBoxButton.TextColor3 = Color3.fromRGB(255, 255, 255)
espBoxButton.Font = Enum.Font.Gotham
espBoxButton.TextScaled = true
espBoxButton.Parent = mainFrame

espBoxButton.MouseButton1Click:Connect(function()
	espBoxOn = not espBoxOn
	espBoxButton.Text = espBoxOn and "Desativar ESP Caixa" or "Ativar ESP Caixa"
	print("ESP Caixa:", espBoxOn)
end)

-- Botão ESP Linha
local espLineOn = false
local espLineButton = Instance.new("TextButton")
espLineButton.Size = UDim2.new(0.8, 0, 0.15, 0)
espLineButton.Position = UDim2.new(0.1, 0, 0.65, 0)
espLineButton.Text = "Ativar ESP Linha"
espLineButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
espLineButton.TextColor3 = Color3.fromRGB(255, 255, 255)
espLineButton.Font = Enum.Font.Gotham
espLineButton.TextScaled = true
espLineButton.Parent = mainFrame

espLineButton.MouseButton1Click:Connect(function()
	espLineOn = not espLineOn
	espLineButton.Text = espLineOn and "Desativar ESP Linha" or "Ativar ESP Linha"
	print("ESP Linha:", espLineOn)
end)

-- Toggle da GUI com tecla Q
local guiVisible = false
UserInputService.InputBegan:Connect(function(input, gameProcessed)
	if not gameProcessed and input.KeyCode == Enum.KeyCode.Q then
		guiVisible = not guiVisible
		mainFrame.Visible = guiVisible
	end
end)
