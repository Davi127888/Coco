local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()

local Window = Fluent:CreateWindow({
    Title = "Aimlock Script" .. Fluent.Version,
    TabWidth = 160, Size = UDim2.fromOffset(580, 460), Theme = "Dark"
})

local Tabs = {
    Main = Window:AddTab({ Title = "Aimlock" }),
    Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
}
-- parágrafo
Tabs.Main:AddParagraph({ Title = "Davi Te Ajudou", Content = "Obrigado por usar Meu Aimbot" })
-- botões
Tabs.Main:AddButton({ Title = "Button", Callback = function() getgenv().serial = {
    Settings = {
        Prediction = 0.0440, 
        AutoClick = false, -- Dont work atm
    },
    TargetLock = {
        LockedTarget = nil, -- dont change
        AimPart = "Head", 
        Enabled = true, 
    },
    TargetStrafe = {
        Enabled = true,
        UseButton = true,  
        Distance = 5,  
        Height = 5,    
        Speed = 20,     
  end
         end
               end)
