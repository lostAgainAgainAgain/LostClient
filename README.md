# LostClient
-- Lost Client Basit GUI

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local TextBox = Instance.new("TextBox")
local Button = Instance.new("TextButton")
local DevButton = Instance.new("TextButton")
local DevFrame = Instance.new("Frame")
local DevText = Instance.new("TextLabel")
local CloseDevBtn = Instance.new("TextButton")

-- ScreenGui Ayarları
ScreenGui.Name = "LostClientGUI"
ScreenGui.ResetOnSpawn = false
ScreenGui.Parent = game.CoreGui

-- Frame Ayarları
Frame.Size = UDim2.new(0, 400, 0, 250)
Frame.Position = UDim2.new(0.5, -200, 0.5, -125)
Frame.BackgroundColor3 = Color3.new(0, 0, 0)
Frame.BorderSizePixel = 0
Frame.Parent = ScreenGui

-- Başlık
TextLabel.Size = UDim2.new(1, 0, 0, 50)
TextLabel.BackgroundTransparency = 1
TextLabel.Text = "Lost Client - Giriş"
TextLabel.TextColor3 = Color3.new(1, 1, 1)
TextLabel.Font = Enum.Font.GothamBold
TextLabel.TextSize = 30
TextLabel.Parent = Frame

-- Kullanıcı Adı Girişi
TextBox.Size = UDim2.new(1, -40, 0, 40)
TextBox.Position = UDim2.new(0, 20, 0, 80)
TextBox.PlaceholderText = "Kullanıcı Adınızı Girin"
TextBox.TextColor3 = Color3.new(1, 1, 1)
TextBox.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
TextBox.ClearTextOnFocus = false
TextBox.Parent = Frame

-- Giriş Butonu
Button.Size = UDim2.new(1, -40, 0, 40)
Button.Position = UDim2.new(0, 20, 0, 140)
Button.BackgroundColor3 = Color3.new(1, 1, 1)
Button.TextColor3 = Color3.new(0, 0, 0)
Button.Text = "Giriş Yap"
Button.Font = Enum.Font.GothamBold
Button.TextSize = 24
Button.Parent = Frame

-- Geliştiren Butonu
DevButton.Size = UDim2.new(0, 120, 0, 30)
DevButton.Position = UDim2.new(1, -130, 1, -40)
DevButton.BackgroundColor3 = Color3.new(0, 0, 0)
DevButton.TextColor3 = Color3.new(1, 1, 1)
DevButton.Text = "Geliştiren"
DevButton.Font = Enum.Font.Gotham
DevButton.TextSize = 20
DevButton.Parent = Frame

-- Geliştiren Ekranı (Başlangıçta gizli)
DevFrame.Size = UDim2.new(1, 0, 1, 0)
DevFrame.BackgroundColor3 = Color3.new(0, 0, 0)
DevFrame.Visible = false
DevFrame.Parent = ScreenGui

DevText.Size = UDim2.new(1, -40, 1, -80)
DevText.Position = UDim2.new(0, 20, 0, 20)
DevText.BackgroundTransparency = 1
DevText.TextColor3 = Color3.new(1, 1, 1)
DevText.Text = "Bu GUI ChatGPT tarafından hazırlandı.\n\nSiyah-Beyaz tasarım tercih edildi.\n\nKullanıcı adı: LostAgainAgainAgain"
DevText.Font = Enum.Font.Gotham
DevText.TextSize = 24
DevText.TextWrapped = true
DevText.Parent = DevFrame

CloseDevBtn.Size = UDim2.new(0, 50, 0, 30)
CloseDevBtn.Position = UDim2.new(1, -60, 0, 10)
CloseDevBtn.BackgroundColor3 = Color3.new(1, 1, 1)
CloseDevBtn.TextColor3 = Color3.new(0, 0, 0)
CloseDevBtn.Text = "X"
CloseDevBtn.Font = Enum.Font.GothamBold
CloseDevBtn.TextSize = 24
CloseDevBtn.Parent = DevFrame

-- Buton Fonksiyonları
Button.MouseButton1Click:Connect(function()
    local username = TextBox.Text
    if username == "" then
        TextLabel.Text = "Lütfen kullanıcı adınızı girin!"
        return
    end
    TextLabel.Text = "Hoşgeldin, "..username.."!"
    -- Buraya doğrulama veya başka işlemler eklenebilir
end)

DevButton.MouseButton1Click:Connect(function()
    DevFrame.Visible = true
    Frame.Visible = false
end)

CloseDevBtn.MouseButton1Click:Connect(function()
    DevFrame.Visible = false
    Frame.Visible = true
end)
