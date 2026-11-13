# Capítulo 2 — Variáveis e tipos de dados

## Variáveis

Uma variável guarda um valor com um nome.

~~~lua
local nome = "Kennedy"
local idade = 25
local ativo = true

print(nome, idade, ativo)
~~~

### `local` vs. global

Sempre use `local`. Sem ele, a variável vira **global**, fica visível em todo o script (e em alguns casos em outros arquivos do mesmo resource) e pode causar bugs difíceis de achar.

~~~lua
local certo = 10   -- visível só no bloco onde foi criada
errado = 20        -- global: evite!
~~~

## Tipos de dados

Lua tem 8 tipos. Os que você mais usará:

| Tipo | Exemplo | Observação |
| --- | --- | --- |
| `nil` | `nil` | Ausência de valor |
| `boolean` | `true`, `false` | Só `false` e `nil` são "falsos" |
| `number` | `42`, `3.14` | Inteiros e decimais |
| `string` | `"texto"` | Texto |
| `table` | `{1, 2, 3}` | Listas, dicionários, objetos |
| `function` | `function() end` | Funções são valores |

Use `type(valor)` para descobrir o tipo:

~~~lua
print(type(10))        --> number
print(type("oi"))      --> string
print(type(nil))       --> nil
print(type({}))        --> table
~~~

## Operadores

### Aritméticos

~~~lua
print(10 + 3)   --> 13
print(10 - 3)   --> 7
print(10 * 3)   --> 30
print(10 / 3)   --> 3.3333333333333
print(10 // 3)  --> 3   (divisão inteira)
print(10 % 3)   --> 1   (resto)
print(2 ^ 3)    --> 8.0 (potência)
~~~

### Comparação

~~~lua
print(5 == 5)   --> true
print(5 ~= 4)   --> true   (diferente usa ~=, não !=)
print(5 > 3, 5 <= 3)
~~~

### Lógicos

~~~lua
print(true and false)  --> false
print(true or false)   --> true
print(not true)        --> false
~~~

Truque comum para valor padrão:

~~~lua
local vida = jogador.vida or 100
~~~

## Strings

~~~lua
local nome = "Maria"
print("Olá, " .. nome)        -- concatenação com ..
print(#nome)                  -- tamanho: 5
print(string.upper(nome))     -- MARIA
print(nome:lower())           -- maria
print(("%s tem %d anos"):format(nome, 30))
~~~

- Concatenar usa `..` (dois pontos), não `+`.
- `#` retorna o tamanho de uma string ou lista.
- `string.format` é a forma mais limpa de montar mensagens.

## Convertendo tipos

~~~lua
print(tonumber("42") + 8)   --> 50
print(tostring(100) .. "%") --> 100%
print(tonumber("abc"))      --> nil
~~~

## Exercícios

1. Crie variáveis para nome, idade e cidade e imprima uma frase usando `string.format`.
2. Calcule a média de três notas e imprima o resultado.
3. O que imprime `print(0 and "sim")`? (Dica: em Lua, 0 é verdadeiro.)

---

⬅️ [Capítulo 1](01-introducao.md) · ➡️ [Capítulo 3 — Controle de fluxo](03-controle-de-fluxo.md)
