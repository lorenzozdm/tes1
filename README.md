local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Player = game.Players.LocalPlayer
local Window = OrionLib:MakeWindow({Name = "LOL Hub", HidePremium = false, SaveConfig = true, IntroEnebled = false})

OrionLib:MakeNotification({
	Name = "LOL Hub Loaded!",
	Content = "Hi! " .. Player.Name,
	Image = "rbxassetid://4483345998",
	Time = 3
})



function MakeScriptHub()
    
end


function Correctmensage()
 OrionLib:MakeNotification({
	 Name = "Correct Key!",
	 Content = "Thx" .. Player.Name .. "to active the Key!",
	 Image = "rbxassetid://4483345998",
	 Time = 3
 })
end


function Incorrectmensage()
 OrionLib:MakeNotification({
	 Name = "Incorrect Key!",
	 Content = "Pls " .. Player.Name .. "Verify your Key!",
	 Image = "rbxassetid://4483345998",
	 Time = 3
 })
end



OrionLib:MakeNotification({
	Name = "Key!",
	Content = "Pls " .. Player.Name .. " Active Key",
	Image = "rbxassetid://4483345998",
	Time = 3
})

local Tab = Window:MakeTab({
	Name = "Key",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

Tab:AddLabel("LOL Hub Key")

_G.Key = "H22"
_G.KeyInput = "string"


Tab:AddTextbox({
	Name = "Enter Key",
	Default = "Key Here!",
	TextDisappear = false,
	Callback = function(Value)
		_G.KeyInput = Value
	end	  
})

Tab:AddButton({
	Name = "Check",
	Callback = function()
      		print("button pressed")
                if _G.KeyInput == _G.Key then
                     MakeScriptHub()
                     Correctmensage()                  
                else
                    Incorrectmensage()
                end 
  	end    
})

Tab:AddLabel("Close the Window After Correct Key or it Lags!")
