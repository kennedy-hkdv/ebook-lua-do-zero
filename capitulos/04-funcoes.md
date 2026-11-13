# Capítulo 4 — Funções

Funções agrupam código reutilizável. Em Lua, funções são **valores**: podem ser guardadas em variáveis, passadas como argumento e retornadas.

## Declarando e chamando

~~~lua
local function saudar(nome)
  print("Olá, " .. nome .. "!")
end

saudar("Carlos")   --> Olá, Carlos!
~~~

## Retornando valores

~~~lua
local function somar(a, b)
  return a + b
end

local resultado = somar(2, 3)
print(resultado)   --> 5
~~~

Uma função pode retornar **vários valores**:

~~~lua
local function minMax(a, b)
  if a < b then return a, b end
  return b, a
end

local menor, maior = minMax(9, 4)
print(menor, maior)   --> 4 9
~~~

## Parâmetros opcionais e valores padrão

Parâmetros não informados valem `nil`:

~~~lua
local function curar(jogador, quantidade)
  quantidade = quantidade or 25   -- padrão
  jogador.vida = math.min(100, jogador.vida + quantidade)
end
~~~

## Quantidade variável de argumentos

~~~lua
local function somarTudo(...)
  local total = 0
  for _, n in ipairs({ ... }) do
    total = total + n
  end
  return total
end

print(somarTudo(1, 2, 3, 4))   --> 10
~~~

## Funções anônimas e callbacks

~~~lua
local function executarDepois(acao)
  print("Preparando…")
  acao()
end

executarDepois(function()
  print("Executando!")
end)
~~~

Esse padrão (**callback**) é a base dos eventos no FiveM: você entrega uma função e o jogo a chama quando algo acontece.

## Escopo e closures

Uma função "lembra" das variáveis locais do lugar onde foi criada:

~~~lua
local function criarContador()
  local n = 0
  return function()
    n = n + 1
    return n
  end
end

local contar = criarContador()
print(contar())   --> 1
print(contar())   --> 2
~~~

## Tratando erros com `pcall`

~~~lua
local ok, erro = pcall(function()
  error("algo deu errado")
end)

if not ok then
  print("Falhou:", erro)
end
~~~

`pcall` executa uma função de forma protegida: se ela falhar, o script não quebra.

## Exercícios

1. Escreva `areaRetangulo(largura, altura)`.
2. Escreva `contarVogais(texto)` que retorna quantas vogais existem na string.
3. Crie uma função `criarSaldo(inicial)` que retorna duas funções: `depositar` e `consultar` (use closure).

---

⬅️ [Capítulo 3](03-controle-de-fluxo.md) · ➡️ [Capítulo 5 — Tabelas](05-tabelas.md)
