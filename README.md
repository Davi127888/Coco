local Players = game:GetService("Players")
local localPlayer = Players.LocalPlayer
local mouse = localPlayer:GetMouse()

-- function to find the nearest enemy
function getClosestTarget()
    local closest = nil
    local shortestDistance = math.huge

    for _, player in pairs(Players:GetPlayers()) do
        if player ~= localPlayer and player.Character and player.Character:FindFirstChild("Head") then
            local head = player.Character.Head
            local screenPos, onScreen = workspace.CurrentCamera:WorldToViewportPoint(head.Position)

            if onScreen then
                local dist = (Vector2.new(mouse.X, mouse.Y) - Vector2.new(screenPos.X, screenPos.Y)).Magnitude
                if dist < shortestDistance then
                    shortestDistance = dist
                    closest = head
                end
            end
        end
    end

    return closest
end

-- Assisted aim (chamar quando necessário, tipo ao clicar)
local target = getClosestTarget()
if target then
    mouse.TargetFilter = target.Parent
    mouse.Icon = "rbxassetid://12345678" -- ícone opcional para indicar lock
    print("target locked:", target.Parent.Name)
end)
