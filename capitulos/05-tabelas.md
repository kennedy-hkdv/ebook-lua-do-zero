# Capítulo 5 — Tabelas

A **tabela** (`table`) é a única estrutura de dados de Lua. Ela serve como lista, dicionário, objeto, pilha, fila… Dominar tabelas é dominar Lua.

## Tabela como lista

~~~lua
local itens = { "pistola", "colete", "água" }

print(itens[1])     --> pistola   (índice começa em 1!)
print(#itens)       --> 3

table.insert(itens, "lanterna")        -- adiciona no final
table.insert(itens, 1, "mochila")      -- adiciona na posição 1
table.remove(itens, 2)                 -- remove a posição 2
~~~

## Tabela como dicionário

~~~lua
local jogador = {
  nome = "Ana",
  vida = 100,
  coletes = 2,
}

print(jogador.nome)        --> Ana
print(jogador["vida"])     --> 100

jogador.vida = 80          -- altera
jogador.dinheiro = 500     -- cria nova chave
jogador.coletes = nil      -- remove a chave
~~~

`tabela.chave` e `tabela["chave"]` são equivalentes. Use colchetes quando a chave está em uma variável ou tem caracteres especiais.

## Tabelas aninhadas

~~~lua
local servidor = {
  nome = "Cidade Alta",
  jogadores = {
    { id = 1, nome = "Ana" },
    { id = 2, nome = "Bruno" },
  },
}

print(servidor.jogadores[2].nome)   --> Bruno
~~~

## Percorrendo

~~~lua
for i, jogador in ipairs(servidor.jogadores) do
  print(i, jogador.nome)
end
~~~

## Funções úteis de `table`

~~~lua
local nums = { 5, 2, 9, 1 }

table.sort(nums)                       -- {1, 2, 5, 9}
table.sort(nums, function(a, b)        -- decrescente
  return a > b
end)

print(table.concat(nums, ", "))        --> 9, 5, 2, 1
~~~

## Referência, não cópia

Tabelas são **referências**. Atribuir não copia:

~~~lua
local a = { 1, 2, 3 }
local b = a
b[1] = 99
print(a[1])   --> 99  (a e b são a MESMA tabela)
~~~

Para copiar, crie uma nova tabela:

~~~lua
local function copiar(t)
  local novo = {}
  for k, v in pairs(t) do novo[k] = v end
  return novo
end
~~~

## Métodos e o operador `:`

Funções dentro de tabelas formam "objetos":

~~~lua
local Contador = { valor = 0 }

function Contador:incrementar()
  self.valor = self.valor + 1
end

Contador:incrementar()
print(Contador.valor)   --> 1
~~~

`objeto:metodo()` é o mesmo que `objeto.metodo(objeto)`; o `self` recebe o próprio objeto.

## Exercícios

1. Crie uma lista de 5 números e some todos.
2. Crie uma tabela `veiculo` com marca, modelo e velocidade; imprima uma descrição.
3. Dada uma lista de jogadores (tabelas com `nome` e `pontos`), ordene por pontos, do maior para o menor.

---

⬅️ [Capítulo 4](04-funcoes.md) · ➡️ [Capítulo 6 — Lua na prática com FiveM](06-lua-no-fivem.md)
