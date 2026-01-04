-- Obfuscated by jotinha12hr2 Tool
local _0x5261796669656C64 = loadstring(game:HttpGet(string.char(104,116,116,112,115,58,47,47,115,105,114,105,117,115,46,109,101,110,117,47,114,97,121,102,105,101,108,100)))()
local _0xW = _0x5261796669656C64:CreateWindow({Name = "jotinha12hr2 hub's Admin", LoadingTitle = "carregando...", ConfigurationSaving = {Enabled = false}})
local _0xT = _0xW:CreateTab("Admin Players", 4483362458)
local _0xTarget = ""
local _0xHubs = {"jotinha12hr2 hub's Admin", "coquette hub admin", "lyra hub Admin", "drip client admin", "Phantom cliente Admin"}

local function _0xTag(_0xP, _0xH)
    if _0xP.Character and _0xP.Character:FindFirstChild("Head") then
        local _0xB = _0xP.Character.Head:FindFirstChild("HubTag") or Instance.new("BillboardGui", _0xP.Character.Head)
        _0xB.Name = "HubTag"; _0xB.Size = UDim2.new(0, 200, 0, 50); _0xB.StudsOffset = Vector3.new(0, 3, 0); _0xB.AlwaysOnTop = true
        local _0xL = _0xB:FindFirstChild("TextLabel") or Instance.new("TextLabel", _0xB)
        _0xL.BackgroundTransparency = 1; _0xL.Size = UDim2.new(1, 0, 1, 0); _0xL.Text = _0xH; _0xL.TextColor3 = Color3.fromRGB(255, 255, 0); _0xL.TextScaled = true; _0xL.Font = Enum.Font.SourceSansBold
    end
end

task.spawn(function()
    while task.wait(2) do
        for _, v in ipairs(game.Players:GetPlayers()) do
            for _, h in ipairs(_0xHubs) do
                if v:FindFirstChild(h) or (v:FindFirstChild("PlayerGui") and v.PlayerGui:FindFirstChild(h)) then _0xTag(v, h) end
            end
        end
    end
end)

local function _0xCheck(_0xP)
    for _, h in ipairs(_0xHubs) do
        if _0xP:FindFirstChild(h) or (_0xP:FindFirstChild("PlayerGui") and _0xP.PlayerGui:FindFirstChild(h)) then return true end
    end
    return false
end

local function _0xGet()
    for _, v in pairs(game.Players:GetPlayers()) do
        if v.Name:lower():sub(1, #_0xTarget) == _0xTarget:lower() or v.DisplayName:lower():sub(1, #_0xTarget) == _0xTarget:lower() then return v end
    end
end

_0xT:CreateInput({Name = "Nome do Player", PlaceholderText = "...", Callback = function(t) _0xTarget = t end})

local function _0xAct(_0xN, _0xF)
    _0xT:CreateButton({Name = _0xN, Callback = function()
        local p = _0xGet()
        if p and _0xCheck(p) and p.Character then _0xF(p) else
            _0x5261796669656C64:Notify({Title = "Erro", Content = "Alvo invalido ou sem Hub", Duration = 3})
        end
    end})
end

_0xAct("Kick", function(p) p:Kick("jotinha12hr2") end)
_0xAct("Kill", function(p) p.Character:BreakJoints() end)
_0xAct("Backrooms", function(p) p.Character.HumanoidRootPart.CFrame = CFrame.new(9999, -999, 9999) end)
_0xAct("Bring", function(p) p.Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame end)

