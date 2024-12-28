-- Script para Roblox com fundo preto e letras brancas, lista de jogadores, fly e observação

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local PlayerList = Instance.new("TextLabel")
local UpdateButton = Instance.new("TextButton")
local FlyButton = Instance.new("TextButton")
local ObserveButton = Instance.new("TextButton")

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.new(0, 0, 0) -- Fundo preto
Frame.Size = UDim2.new(1, 0, 1, 0)

PlayerList.Parent = Frame
PlayerList.Text = "Jogadores no servidor:\n"
PlayerList.TextColor3 = Color3.new(1, 1, 1) -- Letras brancas
PlayerList.Size = UDim2.new(1, 0, 0.8, 0)
PlayerList.Font = Enum.Font.SourceSans
PlayerList.TextScaled = true
PlayerList.TextWrapped = true

UpdateButton.Parent = Frame
UpdateButton.Text = "Atualizar"
UpdateButton.TextColor3 = Color3.new(1, 1, 1) -- Letras brancas
UpdateButton.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
UpdateButton.Size = UDim2.new(0.3, 0, 0.1, 0)
UpdateButton.Position = UDim2.new(0.35, 0, 0.85, 0)
UpdateButton.Font = Enum.Font.SourceSans
UpdateButton.TextScaled = true

FlyButton.Parent = Frame
FlyButton.Text = "Fly"
FlyButton.TextColor3 = Color3.new(1, 1, 1) -- Letras brancas
FlyButton.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
FlyButton.Size = UDim2.new(0.3, 0, 0.1, 0)
FlyButton.Position = UDim2.new(0.05, 0, 0.85, 0)
FlyButton.Font = Enum.Font.SourceSans
FlyButton.TextScaled = true

ObserveButton.Parent = Frame
ObserveButton.Text = "Observar"
ObserveButton.TextColor3 = Color3.new(1, 1, 1) -- Letras brancas
ObserveButton.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
ObserveButton.Size = UDim2.new(0.3, 0, 0.1, 0)
ObserveButton.Position = UDim2.new(0.65, 0, 0.85, 0)
ObserveButton.Font = Enum.Font.SourceSans
ObserveButton.TextScaled = true

local function updatePlayerList()
    PlayerList.Text = "Jogadores no servidor:\n"
    for _, player in pairs(game.Players:GetPlayers()) do
        PlayerList.Text = PlayerList.Text .. player.Name .. "\n"
    end
end

UpdateButton.MouseButton1Click:Connect(updatePlayerList)

local function enableFly()
    -- Código para habilitar fly
end

FlyButton.MouseButton1Click:Connect(enableFly)

local function observePlayers()
    -- Código para observar players
end

ObserveButton.MouseButton1Click:Connect(observePlayers)

game.Players.PlayerAdded:Connect(updatePlayerList)
game.Players.PlayerRemoving:Connect(updatePlayerList)

updatePlayerList()

