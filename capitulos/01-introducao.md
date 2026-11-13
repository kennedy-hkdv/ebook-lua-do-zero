# Capítulo 1 — Introdução e primeiro programa

## O que é Lua?

Lua é uma linguagem de programação **leve, rápida e fácil de aprender**. Ela é muito usada para criar scripts dentro de outros programas — jogos, por exemplo. No **FiveM**, praticamente toda a lógica dos seus recursos (resources) é escrita em Lua.

Características que importam para você:

- **Simples:** poucas palavras reservadas e sintaxe limpa.
- **Dinâmica:** você não declara o tipo das variáveis.
- **Poderosa:** uma única estrutura, a **tabela**, serve para listas, dicionários e objetos.
- **Contagem começa em 1:** diferente de muitas linguagens, o primeiro item de uma lista é o índice 1.

> No FiveM é usado o Lua 5.4. Para habilitar isso em um resource, adicione `lua54 'yes'` ao seu `fxmanifest.lua` (veremos no ebook de primeiros passos).

## Seu primeiro programa

~~~lua
print("Olá, mundo!")
~~~

Saída:

~~~
Olá, mundo!
~~~

`print` mostra valores no console. No FiveM, você verá essa saída no console do servidor (script server) ou do cliente (F8).

## Comentários

~~~lua
-- Comentário de uma linha

--[[
  Comentário
  de várias linhas
]]
~~~

Comentários são ignorados pelo programa. Use-os para explicar o **porquê** do código, não só o **quê**.

## Boas práticas desde o início

1. **Indente** o código (2 ou 4 espaços) para facilitar a leitura.
2. Use **nomes descritivos**: `vidaDoJogador` é melhor que `x`.
3. Prefira sempre variáveis `local` (capítulo 2).
4. Leia as mensagens de erro: elas dizem o arquivo e a linha do problema.

## Exercícios

1. Imprima seu nome e a sua cidade em duas linhas separadas.
2. Escreva um comentário de múltiplas linhas explicando o que o seu programa faz.
3. Imprima a mesma frase três vezes (por enquanto, copie e cole; no capítulo 3 você fará isso com um laço).

---

⬅️ [Voltar ao índice](../README.md) · ➡️ [Capítulo 2 — Variáveis e tipos](02-variaveis-e-tipos.md)
