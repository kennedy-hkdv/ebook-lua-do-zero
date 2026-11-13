# Capítulo 6 — Lua na prática com FiveM

Agora que você viu a base da linguagem, veja onde cada conceito aparece em um script de FiveM.

## Eventos = callbacks

~~~lua
AddEventHandler('playerSpawned', function()
  print('Jogador nasceu!')
end)
~~~

A função anônima é um **callback** (capítulo 4): o jogo a executa quando o evento acontece.

## Tabelas como configuração

~~~lua
Config = {}

Config.Distancia = 3.0
Config.Locais = {
  { nome = "Loja Central", x = 25.7, y = -1347.3, z = 29.5 },
  { nome = "Loja Praia",   x = -1222.9, y = -907.2, z = 12.3 },
}
~~~

Um arquivo `config.lua` com uma tabela deixa o script fácil de ajustar sem mexer na lógica.

## Laços sobre dados

~~~lua
for _, loja in ipairs(Config.Locais) do
  print(("Loja: %s"):format(loja.nome))
end
~~~

## Loops contínuos com `Wait`

~~~lua
CreateThread(function()
  while true do
    -- verificações que precisam rodar sempre
    Wait(1000)   -- espera 1000 ms; NUNCA deixe um while true sem Wait
  end
end)
~~~

Sem `Wait`, o loop ocupa todo o processamento e trava o jogo. Quanto maior o intervalo, menos o seu script pesa.

## Funções locais e organização

~~~lua
local function distancia(a, b)
  return #(a - b)   -- operador de tamanho para vetores do FiveM
end
~~~

Funções `local` são mais rápidas e evitam conflitos de nome entre resources.

## Checklist antes de seguir

- [ ] Sei criar variáveis `local` e usar os tipos básicos
- [ ] Sei usar `if`, `for`, `while`
- [ ] Sei criar e chamar funções, inclusive anônimas
- [ ] Sei montar e percorrer tabelas

## ➡️ Próximo passo

Vá para o ebook **[FiveM: Primeiros Passos](https://github.com/kennedy-hkdv/ebook-fivem-primeiros-passos)** e crie seu primeiro resource.

---

⬅️ [Capítulo 5](05-tabelas.md) · 🏠 [Índice](../README.md)
