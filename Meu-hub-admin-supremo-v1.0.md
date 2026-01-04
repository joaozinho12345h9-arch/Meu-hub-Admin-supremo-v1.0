--[[ 
    Script Obfuscated for jotinha12hr2
    Proteção básica contra leitura direta.
]]

local _0x5F2 = loadstring(game:HttpGet(utf8.decode("\104\116\116\112\115\58\47\47\115\105\114\105\117\115\46\109\101\110\117\47\114\97\121\102\105\101\108\100")))()

local _0x1A = _0x5F2:CreateWindow({
   Name = "jotinha12hr2 hub's Admin",
   LoadingTitle = "carregando, by jotinha12hr2",
   LoadingSubtitle = "by jotinha12hr2",
   ConfigurationSaving = { Enabled = false }
})

local _0xTab1 = _0x1A:CreateTab("Admin Players", 4483362458)
local _0xTarget = ""

local _0xList = {
    "jotinha12hr2 hub's Admin",
    "coquette hub admin",
    "lyra hub Admin",
    "drip client admin",
    "Phantom cliente Admin"
}

local function _0xRenderTag(plr, txt)
    if plr.Character and plr.Character:FindFirstChild("Head") then
        local h = plr.Character.Head
        local b = h:FindFirstChild("HubTag") or Instance.new("BillboardGui", h)
        b.Name = "HubTag"
        b.Size = UDim2.new(0, 200, 0, 50)
        b.StudsOffset = Vector3.new(0, 3, 0)
        b.AlwaysOnTop = true

        local l = b:FindFirstChild("TextLabel") or Instance.new("TextLabel", b)
        l.BackgroundTransparency = 1
        l.Size = UDim2.new(1, 0, 1, 0)
        l.Text = txt
        l.TextColor3 = Color3.fromRGB(0, 0, 0)
        l.TextStrokeColor3 = Color3.fromRGB(255, 255, 255)
        l.TextStrokeTransparency = 0
        l.TextScaled = true
        l.Font = Enum.Font.SourceSansBold
    end
end

task.spawn(function()
    while task.wait(1) do
        for _, p in ipairs(game.Players:GetPlayers()) do
            for _, h in ipairs(_0xList) do
                if p:FindFirstChild(h) or (p:FindFirstChild("PlayerGui") and p.PlayerGui:FindFirstChild(h)) then
                    _0xRenderTag(p, h)
                end
            end
        end
    end
end)

local function _0xCheck(plr)
    for _, h in ipairs(_0xList) do
        if plr:FindFirstChild(h) or (plr:FindFirstChild("PlayerGui") and plr.PlayerGui:FindFirstChild(h)) then
            return true
        end
    end
    return false
end

local function _0xGetP()
    for _, v in pairs(game.Players:GetPlayers()) do
        if v.Name:lower():sub(1, #_0xTarget) == _0xTarget:lower() or v.DisplayName:lower():sub(1, #_0xTarget) == _0xTarget:lower() then
            return v
        end
    end
end

_0xTab1:CreateInput({
   Name = "Nome do Player", PlaceholderText = "Escreva o nome...",
   RemoveTextAfterFocusLost = false,
   Callback = function(t) _0xTarget = t end,
})

local function _0xAct(n, f)
    _0xTab1:CreateButton({
       Name = n,
       Callback = function()
          local p = _0xGetP()
          if p and _0xCheck(p) then
              if p.Character then f(p) end
          else
              _0x5F2:Notify({Title = "Aviso", Content = "Jogador não encontrado ou não usa os Hubs permitidos.", Duration = 3})
          end
       end,
    })
end

_0xAct("Kick Player Not Fe", function(p) p:Kick("Kicked by jotinha12hr2 hub") end)
_0xAct("Kill Player Not Fe", function(p) p.Character:BreakJoints() end)
_0xAct("Kill plus Player Not Fe", function(p) 
    p.Character.Humanoid.Health = 0
    for _, v in pairs(p.Character:GetChildren()) do if v:IsA("BasePart") then v:Destroy() end end
end)
_0xAct("Jumpscare 1 Player Not Fe", function(p) print("J1") end)
_0xAct("Jumpscare 2 Player Not Fe", function(p) print("J2") end)
_0xAct("Jumpscare 3 Player Not Fe", function(p) print("J3") end)

_0xAct("Jail 6 partes player fe not visual", function(p)
    local cf = p.Character.HumanoidRootPart.CFrame
    local m = Instance.new("Model", workspace)
    m.Name = "Jail_" .. p.Name
    local parts = {
        {s = Vector3.new(10, 1, 10), p = cf * CFrame.new(0, -5, 0)},
        {s = Vector3.new(10, 1, 10), p = cf * CFrame.new(0, 5, 0)},
        {s = Vector3.new(1, 10, 10), p = cf * CFrame.new(5, 0, 0)},
        {s = Vector3.new(1, 10, 10), p = cf * CFrame.new(-5, 0, 0)},
        {s = Vector3.new(10, 10, 1), p = cf * CFrame.new(0, 0, 5)},
        {s = Vector3.new(10, 10, 1), p = cf * CFrame.new(0, 0, -5)}
    }
    for _, v in pairs(parts) do
        local pt = Instance.new("Part", m)
        pt.Size = v.s; pt.CFrame = v.p; pt.Anchored = true; pt.Transparency = 0.5
    end
end)

_0xAct("UnJail Player Not Fe", function(p)
    if workspace:FindFirstChild("Jail_" .. p.Name) then workspace["Jail_" .. p.Name]:Destroy() end
end)

_0xAct("Controlar a pessoa not fe", function(p)
    game.Players.LocalPlayer.Character = p.Character
    workspace.CurrentCamera.CameraSubject = p.Character.Humanoid
end)

_0xAct("UnControl Player Not Fe", function(p)
    workspace.CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
end)

_0xAct("Backrooms Player Not Fe", function(p)
    p.Character.HumanoidRootPart.CFrame = CFrame.new(9999, -999, 9999)
end)

_0xAct("Goto Player Not Fe", function(p)
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = p.Character.HumanoidRootPart.CFrame
end)

_0xAct("Bring Player Not Fe", function(p)
    p.Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
end)

