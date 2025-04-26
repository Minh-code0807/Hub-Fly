local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local Button1 = Instance.new("TextButton")
local Button2 = Instance.new("TextButton")

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

Frame.Size = UDim2.new(0, 200, 0, 200)
Frame.Position = UDim2.new(0.5, -100, 0.5, -100)
Frame.AnchorPoint = Vector2.new(0.5, 0.5)
Frame.BackgroundColor3 = Color3.fromRGB(100, 100, 255)
Frame.Active = true
Frame.Draggable = true
Frame.Parent = ScreenGui

Button1.Size = UDim2.new(0, 100, 0, 50)
Button1.Position = UDim2.new(0.5, -50, 0, -60)
Button1.AnchorPoint = Vector2.new(0.5, 0.5)
Button1.BackgroundColor3 = Color3.fromRGB(255, 100, 100)
Button1.Text = "Thu nhỏ/Phóng to"
Button1.Parent = Frame

Button2.Size = UDim2.new(0, 100, 0, 50)
Button2.Position = UDim2.new(0.5, -50, 0, 60)
Button2.AnchorPoint = Vector2.new(0.5, 0.5)
Button2.BackgroundColor3 = Color3.fromRGB(100, 255, 100)
Button2.Text = "Chạy mã"
Button2.Parent = Frame

local isMinimized = false

Button1.MouseButton1Click:Connect(function()
    if isMinimized then
        Frame.Size = UDim2.new(0, 200, 0, 200)
    else
        Frame.Size = UDim2.new(0, 100, 0, 100)
    end
    isMinimized = not isMinimized
end)

Button2.MouseButton1Click:Connect(function()
    print("Đoạn mã 1 được chạy!")
    loadstring(game:HttpGet("https://raw.githubusercontent.com/AmareScripts/DeadRails/refs/heads/main/Bypass%25AntiCheat.lua"))()
    print("Đoạn mã 2 được chạy!")
    loadstring(game:HttpGet('https://raw.githubusercontent.com/GhostPlayer352/Test4/main/Vehicle%20Fly%20Gui'))()
end)
