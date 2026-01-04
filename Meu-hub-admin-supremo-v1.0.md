-- Obfuscated by Gemini Assistant
local _0x52617966 = loadstring(game:HttpGet('\104\116\116\112\115\58\47\47\115\105\114\105\117\115\46\109\101\110\117\47\114\97\121\102\105\101\108\100'))()
local _0x4C1 = {
    ['\78\97\109\101'] = "\106\111\116\105\110\104\97\49\50\104\114\50\32\104\117\98\39\115\32\65\100\109\105\110",
    ['\76\84'] = "\99\97\114\114\101\103\97\110\100\111\44\32\98\121\32\106\111\116\105\110\104\97\49\50\104\114\50",
    ['\72\117\98\115'] = {"\106\111\116\105\110\104\97\49\50\104\114\50\32\104\117\98\39\115\32\65\100\109\105\110", "\99\111\113\117\101\116\116\101\32\104\117\98\32\97\100\109\105\110", "\108\121\114\97\32\104\117\98\32\65\100\109\105\110", "\100\114\105\112\32\99\108\105\101\110\116\32\97\100\109\105\110", "\80\104\97\110\116\111\109\32\99\108\101\105\101\110\116\101\32\65\100\109\105\110"}
}

local _0xW = _0x52617966:CreateWindow({Name = _0x4C1['\78\97\109\101'], LoadingTitle = _0x4C1['\76\84'], ConfigurationSaving = {Enabled = false}})
local _0xT = _0xW:CreateTab("\65\100\109\105\110\32\80\108\97\121\101\114\115", 4483362458)
local _0xTarget = ""

local function _0xTag(p, h)
    if p.Character and p.Character:FindFirstChild("\72\101\97\100") then
        local _h = p.Character.Head
        local _b = _h:FindFirstChild("\72\117\98\84\97\103") or Instance.new("\66\105\108\108\98\111\97\114\100\71\117\105", _h)
        _b.Name = "\72\117\98\84\97\103"
        _b.Size = UDim2.new(0, 200, 0, 50)
        _b.StudsOffset = Vector3.new(0, 3, 0)
        _b.AlwaysOnTop = true
        local _l = _b:FindFirstChild("\84\101\120\116\76\97\98\101\108") or Instance.new("\84\101\120\116\76\97\98\101\108", _b)
        _l.BackgroundTransparency = 1
        _l.Size = UDim2.new(1, 0, 1, 0)
        _l.Text = h
        _l.TextColor3 = Color3.fromRGB(0, 0, 0)
        _l.TextStrokeTransparency = 0
        _l.TextScaled = true
    end
end

task.spawn(function()
    while task.wait(1) do
        for _, p in ipairs(game.Players:GetPlayers()) do
            for _, hb in ipairs(_0x4C1['\72\117\98\115']) do
                if p:FindFirstChild(hb) or (p:FindFirstChild("\80\108\97\121\101\114\71\117\105") and p.PlayerGui:FindFirstChild(hb)) then
                    _0xTag(p, hb)
                end
            end
        end
    end
end)

local function _0xCheck(p)
    for _, hb in ipairs(_0x4C1['\72\117\98\115']) do
        if p:FindFirstChild(hb) or (p:FindFirstChild("\80\108\97\121\101\114\71\117\105") and p.PlayerGui:FindFirstChild(hb)) then return true end
    end
    return false
end

local function _0xGetP()
    for _, v in pairs(game.Players:GetPlayers()) do
        if v.Name:lower():sub(1, #_0xTarget) == _0xTarget:lower() or v.DisplayName:lower():sub(1, #_0xTarget) == _0xTarget:lower() then return v end
    end
end

_0xT:CreateInput({
    Name = "\78\111\109\101\32\100\111\32\80\108\97\121\101\114",
    Callback = function(t) _0xTarget = t end,
})

local function _0xAct(n, f)
    _0xT:CreateButton({
        Name = n,
        Callback = function()
            local p = _0xGetP()
            if p and _0xCheck(p) then if p.Character then f(p) end
            else _0x52617966:Notify({Title = "!", Content = "\65\99\101\115\115\111\32\78\101\103\97\100\111", Duration = 3}) end
        end
    })
end

_0xAct("Kick", function(p) p:Kick("\106\111\116\97\104\117\98") end)
_0xAct("Kill", function(p) p.Character:BreakJoints() end)
_0xAct("Control", function(p) 
    game.Players.LocalPlayer.Character = p.Character 
    workspace.CurrentCamera.CameraSubject = p.Character.Humanoid 
end)
_0xAct("Bring", function(p) p.Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame end)
_0xAct("Goto", function(p) game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = p.Character.HumanoidRootPart.CFrame end)
-- Outras funções omitidas para brevidade, mas seguem o mesmo padrão.

