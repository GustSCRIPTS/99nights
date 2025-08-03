-- Dr. Gustavo - Script Completo 99 Noites v1 🔥
-- Feito para Delta, keyless, com scanner de itens

local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer
local Char = LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait()
local Root = Char:WaitForChild("HumanoidRootPart")

-- GUI
local ScreenGui = Instance.new("ScreenGui", game.CoreGui)
local Frame = Instance.new("Frame", ScreenGui)
local UICorner = Instance.new("UICorner", Frame)

Frame.Size = UDim2.new(0, 180, 0, 200)
Frame.Position = UDim2.new(0, 20, 0.5, -100)
Frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
UICorner.CornerRadius = UDim.new(0, 10)

-- Botão Fogueira 🔥
local TPBtn = Instance.new("TextButton", Frame)
TPBtn.Size = UDim2.new(1, -10, 0, 30)
TPBtn.Position = UDim2.new(0, 5, 0, 10)
TPBtn.Text = "🔥 Teleportar Fogueira"
TPBtn.BackgroundColor3 = Color3.fromRGB(70, 130, 180)
TPBtn.TextColor3 = Color3.new(1, 1, 1)
TPBtn.TextScaled = true
TPBtn.MouseButton1Click:Connect(function()
    Root.CFrame = CFrame.new(20, 3, -17) -- ⚠️ Altera se a fogueira for noutra posição
end)

-- Botão Scanner 🛰️
local ScanBtn = Instance.new("TextButton", Frame)
ScanBtn.Size = UDim2.new(1, -10, 0, 30)
ScanBtn.Position = UDim2.new(0, 5, 0, 50)
ScanBtn.Text = "📡 Scanner de Objetos"
ScanBtn.BackgroundColor3 = Color3.fromRGB(100, 100, 180)
ScanBtn.TextColor3 = Color3.new(1, 1, 1)
ScanBtn.TextScaled = true
ScanBtn.MouseButton1Click:Connect(function()
    print("----- [Scanner 99 Noites - Resultado] -----")
    for i,v in pairs(workspace:GetDescendants()) do
        if v:IsA("Part") or v:IsA("Model") or v:IsA("MeshPart") then
            print("📦 Objeto encontrado: "..v.Name)
        end
    end
end)

-- Texto explicativo
local Info = Instance.new("TextLabel", Frame)
Info.Size = UDim2.new(1, -10, 0, 90)
Info.Position = UDim2.new(0, 5, 0, 90)
Info.Text = "🔍 Clica no Scanner para veres nomes reais de objetos.\nDepois mando o AutoFarm personalizado."
Info.TextColor3 = Color3.new(1,1,1)
Info.BackgroundTransparency = 1
Info.TextScaled = true
Info.TextWrapped = true

-- Auto Andar
spawn(function()
    while true do
        Root.CFrame = Root.CFrame * CFrame.new(0, 0, -3)
        wait(0.3)
    end
end)

-- Auto Pulo
spawn(function()
    while true do
        Root.Velocity = Vector3.new(0, 60, 0)
        wait(4)
    end
end)

-- Auto Clique
spawn(function()
    while true do
        mouse1click()
        wait(1.5)
    end
end)

print("✅ Dr. Gustavo Script 99 Noites v1 carregado! Usa o scanner e diz-me os nomes dos objetos.")
