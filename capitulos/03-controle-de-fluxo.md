# Capítulo 3 — Controle de fluxo e laços

## Condicionais: `if`

~~~lua
local vida = 30

if vida <= 0 then
  print("Morto")
elseif vida < 50 then
  print("Ferido")
else
  print("Saudável")
end
~~~

Regras:

- Toda condição termina com `then` e o bloco com `end`.
- Use `elseif` (uma palavra) para condições extras.
- Apenas `false` e `nil` são falsos. `0` e `""` são **verdadeiros**.

### Combinando condições

~~~lua
if idade >= 18 and temCarteira then
  print("Pode dirigir")
end

if not ativo then
  print("Inativo")
end
~~~

## Laço `for` numérico

~~~lua
for i = 1, 5 do
  print(i)          -- 1 2 3 4 5
end

for i = 10, 0, -2 do
  print(i)          -- 10 8 6 4 2 0 (passo -2)
end
~~~

## Percorrendo tabelas

~~~lua
local frutas = { "maçã", "banana", "uva" }

-- Listas (ordenadas): ipairs
for indice, fruta in ipairs(frutas) do
  print(indice, fruta)
end

-- Dicionários: pairs
local jogador = { nome = "Ana", vida = 100 }
for chave, valor in pairs(jogador) do
  print(chave, valor)
end
~~~

- `ipairs` percorre índices 1, 2, 3… em ordem e para no primeiro `nil`.
- `pairs` percorre todas as chaves, **sem ordem garantida**.

## `while` e `repeat`

~~~lua
local contador = 0
while contador < 3 do
  contador = contador + 1
  print("Volta", contador)
end

repeat
  contador = contador - 1
until contador == 0
~~~

## `break` e `goto continue`

~~~lua
for i = 1, 10 do
  if i == 5 then break end   -- sai do laço
  print(i)
end

for i = 1, 5 do
  if i % 2 == 0 then goto continue end
  print(i)                    -- só ímpares
  ::continue::
end
~~~

## Cuidado em jogos

Laços infinitos **travam** o script. Em FiveM, loops contínuos precisam de `Wait(...)` dentro (veja o ebook de primeiros passos), caso contrário o servidor/cliente congela.

## Exercícios

1. Imprima os números de 1 a 20 que são múltiplos de 3.
2. Dada `{ 5, 12, 8, 21 }`, encontre o maior valor.
3. Faça um contador regressivo de 10 a 1 usando `while`.

---

⬅️ [Capítulo 2](02-variaveis-e-tipos.md) · ➡️ [Capítulo 4 — Funções](04-funcoes.md)
