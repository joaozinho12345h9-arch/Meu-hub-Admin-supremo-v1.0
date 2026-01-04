--[[ Obfuscated by jotinha12hr2 ]]--
local _0x526179 = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
local _0x57696E = _0x526179:CreateWindow({Name = "\106\111\116\105\110\104\97\49\50\104\114\50\32\104\117\98\39\115\32\65\100\109\105\110", LoadingTitle = "\99\97\114\114\101\103\97\110\100\111\46\46\46", LoadingSubtitle = "\98\121\32\106\111\116\105\110\104\97\49\50\104\114\50", ConfigurationSaving = {Enabled = false}})
local _0x546162 = _0x57696E:CreateTab("\65\100\109\105\110\32\80\108\97\121\101\114\115", 4483362458)
local _0x54617267 = ""
local _0x416C6C6F77 = {"\106\111\116\105\110\104\97\49\50\104\114\50\32\104\117\98\39\115\32\65\100\109\105\110", "\99\111\113\117\101\116\116\101\32\104\117\98\32\97\100\109\105\110", "\108\121\114\97\32\104\117\98\32\65\100\109\105\110", "\100\114\105\112\32\99\108\105\101\110\116\32\97\100\109\105\110", "\80\104\97\110\116\111\109\32\99\108\105\101\110\116\101\32\65\100\109\105\110"}

local function _0x5665726966(plr)
    if not plr then return false end
    for _, h in ipairs(_0x416C6C6F77) do
        if plr:FindFirstChild(h) or (plr:FindFirstChild("PlayerGui") and plr.PlayerGui:FindFirstChild(h)) then return true end
    end
    return false
end

local function _0x47657450()
    for _, v in pairs(game.Players:GetPlayers()) do
        if v.Name:lower():sub(1, #_0x54617267) == _0x54617267:lower() or v.DisplayName:lower():sub(1, #_0x54617267) == _0x54617267:lower() then return v end
    end
end

_0x546162:CreateInput({Name = "Nome do Player", PlaceholderText = "...", RemoveTextAfterFocusLost = false, Callback = function(t) _0x54617267 = t end})

local function _0x45786563(n, f)
    _0x546162:CreateButton({Name = n, Callback = function()
        local p = _0x47657450()
        if p then
            if _0x5665726966(p) then if p.Character then f(p) end
            else _0x526179:Notify({Title = "Erro", Content = "Hub nao detectado", Duration = 3}) end
        end
    end})
end

_0x45786563("Kick (Not FE)", function(p) p:Kick("jotinha12hr2") end)
_0x45786563("Kill (Not FE)", function(p) p.Character:BreakJoints() end)
_0x45786563("Jail (Not FE)", function(p)
    local cf = p.Character.HumanoidRootPart.CFrame
    local m = Instance.new("Model", workspace)
    m.Name = "Jail_" .. p.Name
    local ps = {{s = Vector3.new(10, 1, 10), p = cf * CFrame.new(0, -3.5, 0)}, {s = Vector3.new(10, 1, 10), p = cf * CFrame.new(0, 3.5, 0)}, {s = Vector3.new(1, 10, 10), p = cf * CFrame.new(5, 0, 0)}, {s = Vector3.new(1, 10, 10), p = cf * CFrame.new(-5, 0, 0)}, {s = Vector3.new(10, 10, 1), p = cf * CFrame.new(0, 0, 5)}, {s = Vector3.new(10, 10, 1), p = cf * CFrame.new(0, 0, -5)}}
    for _, v in pairs(ps) do
        local part = Instance.new("Part", m)
        part.Size = v.s part.CFrame = v.p part.Anchored = true part.Transparency = 0.5
    end
end)
_0x45786563("Bring (Not FE)", function(p) p.Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame end)
_0x45786563("Goto (Not FE)", function(p) game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = p.Character.HumanoidRootPart.CFrame end)
_0x45786563("Control (Not FE)", function(p) game.Players.LocalPlayer.Character = p.Character workspace.CurrentCamera.CameraSubject = p.Character.Humanoid end)
