-- infinitejump.lua
local Players = game:GetService("Players")
local ContextActionService = game:GetService("ContextActionService")

local player = Players.LocalPlayer

local function infiniteJump(actionName, inputState, inputObject)
    if inputState == Enum.UserInputState.Begin then
        local character = player.Character
        if character then
            local humanoid = character:FindFirstChild("Humanoid")
            if humanoid and humanoid.Health > 0 then
                humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
            end
        end
    end
end

ContextActionService:BindAction("InfiniteJump", infiniteJump, true, Enum.KeyCode.Space)
