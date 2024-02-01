-- Hub Preto e Branco
-- Criado por Copilot

-- Variáveis para controle
local isPlaying = false
local currentIndex = 1
local typingSpeed = 10 -- Velocidade de digitação (ajuste conforme desejado)
local keyPressTime = 0.1 -- Tempo de pressionamento da tecla (ajuste conforme desejado)

-- Função para digitar o texto
function TypeText(text)
    for i = 1, #text do
        if isPlaying then
            local char = text:sub(i, i)
            game:GetService("UserInputService").InputBegan:Fire(char)
            wait(keyPressTime)
            game:GetService("UserInputService").InputEnded:Fire(char)
            wait(typingSpeed)
        else
            break
        end
    end
end

-- Botões
local playButton = script.Parent:FindFirstChild("PlayButton")
local stopButton = script.Parent:FindFirstChild("StopButton")
local pauseButton = script.Parent:FindFirstChild("PauseButton")

-- Evento para o botão Play
playButton.MouseButton1Click:Connect(function()
    isPlaying = true
    local textToType = script.Parent:FindFirstChild("TextInput").Text
    TypeText(textToType)
    isPlaying = false
end)

-- Evento para o botão Stop
stopButton.MouseButton1Click:Connect(function()
    isPlaying = false
    currentIndex = 1
end)

-- Evento para o botão Pause
pauseButton.MouseButton1Click:Connect(function()
    isPlaying = not isPlaying
end)

-- Função para adicionar música
function AddMusic(AddMusic("/storage/emulated/0/Arceus X/workspace/sheets/sheets1.txt)
    -- Implemente a lógica para adicionar músicas ao diretório especificado
end

-- Função para remover música
function RemoveMusic(AddMusic("/storage/emulated/0/Arceus X/workspace/sheets/sheets1.txt)
    -- Implemente a lógica para remover músicas do diretório especificado
end

-- Exemplo de uso:
AddMusic("/storage/emulated/0/Arceus X/workspace/sheets/sheets1.txt")
