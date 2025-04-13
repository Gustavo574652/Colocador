
-- Script de Giros da Sorte BLUE Lock

-- Configurações
local giros = 100
local premios = {
    {nome = "Treinamento com o técnico Bachira", chance = 10},
    {nome = "Seleção para o time nacional", chance = 5},
    {nome = "Acesso ao campo de treinamento secreto", chance = 15},
    {nome = "Duelo contra Isagi", chance = 20},
    {nome = "Análise de jogo com o técnico", chance = 50}
}

-- Função para realizar um giro
local function realizarGiro()
    local sorteio = math.random(1, 100)
    local premioSorteado = nil
    
    for _, premio in pairs(premios) do
        if sorteio <= premio.chance then
            premioSorteado = premio.nome
            break
        else
            sorteio = sorteio - premio.chance
        end
    end
    
    return premioSorteado
end

-- Realizar giros
for i = 1, giros do
    local premio = realizarGiro()
    print("Giro #" .. i .. ": " .. premio)
end
