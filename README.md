local Players = game:GetService("Players")
local player = Players.LocalPlayer

-- Tạo GUI
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "ControlPanelGui"
ScreenGui.Parent = player:WaitForChild("PlayerGui")

local Frame = Instance.new("Frame")
Frame.Size = UDim2.new(0.3, 0, 0.3, 0)
Frame.Position = UDim2.new(0.35, 0, 0.35, 0)
Frame.BackgroundColor3 = Color3.fromRGB(220, 220, 220)
Frame.BorderSizePixel = 1
Frame.Active = true -- Cho phép kéo
Frame.Draggable = true -- Kích hoạt tính năng kéo
Frame.Parent = ScreenGui

-- Tạo chữ toàn màn hình
local FullScreenText = Instance.new("TextLabel")
FullScreenText.Size = UDim2.new(1, 0, 1, 0)
FullScreenText.Position = UDim2.new(0, 0, 0, 0)
FullScreenText.Text = ""
FullScreenText.Font = Enum.Font.SourceSansBold
FullScreenText.TextSize = 50
FullScreenText.TextColor3 = Color3.fromRGB(0, 0, 0)
FullScreenText.BackgroundTransparency = 1
FullScreenText.Visible = false
FullScreenText.Parent = ScreenGui

local function showFullScreenMessage(message)
    FullScreenText.Text = message
    FullScreenText.Visible = true
    task.delay(3, function()
        FullScreenText.Visible = false
    end)
end

-- Tạo nút "Phóng to / Thu nhỏ"
local ToggleButton = Instance.new("TextButton")
ToggleButton.Size = UDim2.new(0.4, 0, 0.2, 0)
ToggleButton.Position = UDim2.new(0.3, 0, 0.05, 0)
ToggleButton.Text = "Phóng to / Thu nhỏ"
ToggleButton.Font = Enum.Font.SourceSansBold
ToggleButton.TextSize = 18
ToggleButton.BackgroundColor3 = Color3.fromRGB(100, 200, 100)
ToggleButton.TextColor3 = Color3.fromRGB(255, 255, 255)
ToggleButton.Parent = Frame

local buttons = {} -- Danh sách các nút ngoại trừ nút "Phóng to / Thu nhỏ"

-- Tạo nút "Super Fly"
local SuperFlyButton = Instance.new("TextButton")
SuperFlyButton.Size = UDim2.new(0.4, 0, 0.2, 0)
SuperFlyButton.Position = UDim2.new(0.3, 0, 0.25, 0)
SuperFlyButton.Text = "Super Fly"
SuperFlyButton.Font = Enum.Font.SourceSansBold
SuperFlyButton.TextSize = 18
SuperFlyButton.BackgroundColor3 = Color3.fromRGB(100, 100, 200)
SuperFlyButton.TextColor3 = Color3.fromRGB(255, 255, 255)
SuperFlyButton.Parent = Frame
table.insert(buttons, SuperFlyButton)

-- Tạo nút "XuanVp HUD"
local XuanVpButton = Instance.new("TextButton")
XuanVpButton.Size = UDim2.new(0.4, 0, 0.2, 0)
XuanVpButton.Position = UDim2.new(0.3, 0, 0.5, 0)
XuanVpButton.Text = "XuanVp HUD"
XuanVpButton.Font = Enum.Font.SourceSansBold
XuanVpButton.TextSize = 18
XuanVpButton.BackgroundColor3 = Color3.fromRGB(200, 100, 100)
XuanVpButton.TextColor3 = Color3.fromRGB(255, 255, 255)
XuanVpButton.Parent = Frame
table.insert(buttons, XuanVpButton)

-- Tạo nút "Null Fire"
local NullFireButton = Instance.new("TextButton")
NullFireButton.Size = UDim2.new(0.4, 0, 0.2, 0)
NullFireButton.Position = UDim2.new(0.3, 0, 0.75, 0)
NullFireButton.Text = "Null Fire"
NullFireButton.Font = Enum.Font.SourceSansBold
NullFireButton.TextSize = 18
NullFireButton.BackgroundColor3 = Color3.fromRGB(150, 50, 250)
NullFireButton.TextColor3 = Color3.fromRGB(255, 255, 255)
NullFireButton.Parent = Frame
table.insert(buttons, NullFireButton)

-- Biến trạng thái để theo dõi trạng thái ẩn/hiện
local isMinimized = false

-- Xử lý sự kiện khi nhấn nút "Phóng to / Thu nhỏ"
ToggleButton.MouseButton1Click:Connect(function()
    isMinimized = not isMinimized -- Đổi trạng thái

    for _, button in ipairs(buttons) do
        button.Visible = not isMinimized -- Ẩn hoặc hiện các nút khác
    end

    if isMinimized then
        Frame.Size = UDim2.new(0.3, 0, 0.1, 0) -- Thu nhỏ kích thước của bảng
    else
        Frame.Size = UDim2.new(0.3, 0, 0.4, 0) -- Phóng to kích thước của bảng
    end
end)

-- Xử lý sự kiện khi nhấn nút "Super Fly"
SuperFlyButton.MouseButton1Click:Connect(function()
    showFullScreenMessage("Script Fly")
    -- CODE 1: Thêm đoạn mã đầu tiên của bạn vào đây
    loadstring(game:HttpGet("https://raw.githubusercontent.com/AmareScripts/DeadRails/refs/heads/main/Bypass%25AntiCheat.lua"))()

    -- CODE 2: Thêm đoạn mã thứ hai của bạn vào đây
    loadstring(game:HttpGet('https://raw.githubusercontent.com/GhostPlayer352/Test4/main/Vehicle%20Fly%20Gui'))()
end)

-- Xử lý sự kiện khi nhấn nút "XuanVp HUD"
XuanVpButton.MouseButton1Click:Connect(function()
    showFullScreenMessage("Script XuanVp")
    -- CODE: Thêm đoạn mã của bạn vào đây
    loadstring(game:HttpGet("https://raw.githubusercontent.com/XUANVNPRO/XuanVPHUB/refs/heads/main/XuanVPPHUB.lua.txt"))()
end)

-- Xử lý sự kiện khi nhấn nút "Null Fire"
NullFireButton.MouseButton1Click:Connect(function()
    showFullScreenMessage("Script Null Fire")
    -- CODE: Thêm đoạn mã của bạn vào đây
    loadstring(game:HttpGet('https://raw.githubusercontent.com/your-script-here/null-fire/main/script.lua'))()
end)
