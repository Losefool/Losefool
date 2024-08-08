local AnimationId = "YOUR_ANIMATION_ID" -- Replace with your twerking animation ID

-- Function to load and play animation
local function playTwerkingAnimation(character)
    -- Create a new Animator if it doesn't exist
    local humanoid = character:FindFirstChildOfClass("Humanoid")
    if humanoid then
        local animator = humanoid:FindFirstChildOfClass("Animator")
        if not animator then
            animator = Instance.new("Animator")
            animator.Name = "Animator"
            animator.Parent = humanoid
        end
        
        -- Create the animation
        local animation = Instance.new("Animation")
        animation.AnimationId = "rbxassetid://" .. AnimationId
        
        -- Create and load the animation track
        local animationTrack = animator:LoadAnimation(animation)
        animationTrack:Play()
    end
end

-- Example usage
game.Players.PlayerAdded:Connect(function(player)
    player.CharacterAdded:Connect(function(character)
        playTwerkingAnimation(character)
    end)
end)
