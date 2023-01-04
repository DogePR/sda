local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()

OrionLib:MakeNotification({
	Name = "Delux#6666 Menu",
	Content = "Welcome Skids! Have Fun!",
	Image = "rbxassetid://4483345998",
	Time = 5
})

_G.Key = "Hello"
_G.KeyString = "String"

function makescripto()
	if syn then
		if isfolder("AA") then    -- Checks if the folder already exists
			print("The folder, MyFolder is already created on the User's PC therefore we wont make another one.")    -- If yes we will just print that it exists
		else
			makefolder("AA")   -- If the folder doesnt exist, make a new one
		end
	 end
	 
	 if syn then -- Check if script is being executed with synapse
		if isfile('AA/BlurSave.txt') then -- Check if the blur file exists
			print("File already exists therefore I will not make another one.") -- If yes, we wont make another one
		else	
			writefile("AA/BlurSave.txt", "true")  -- If not, we will create a file with the value: true meaning that the player will load up with a blur effect as their default
		end
	 end
	 end

local Window = OrionLib:MakeWindow({Name = "Delux#6666 Hub", HidePremium = false, SaveConfig = true, ConfigFolder = "Delux#6666"})


local PlayerTab = Window:MakeTab({
	Name = "Key System",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})





PlayerTab:AddTextbox({
	Name = "Enter Key",
	Default = "Enter Key",
	TextDisappear = true,
	Callback = function(value)
		_G.KeyString = value
  	end   
})

PlayerTab:AddButton({
	Name = "Check key",
	Callback = function()
if _G.KeyString == _G.Key then
	makescripto()
	OrionLib:MakeNotification({
		Name = "Delux#6666 Menu",
		Content = "Key, Correct {Saving keys}.",
		Image = "rbxassetid://4483345998",
		Time = 5
	})
	end    
end
})



PlayerTab:AddButton({
	Name = "Destroy UI",
	Callback = function()
        OrionLib:Destroy()
  	end    
})
