# Batalha Naval

## Introdução

Esta entrega tem como objetivo desenvolver um jogo de batalha naval simples utilizando o JavaScript e as funções fornecidas. A ideia é que se possa alocar navios em um tabuleiro, fazer suposições sobre a localização dos navios e verificar se conseguiu afundar todos.

O desafio consiste em interpretar o problema e desenvolver uma solução adequada. Para iniciar seu projeto, utilize o seguinte template.

Todo o seu código deve ficar no arquivo script.js. Não altere nenhum dos outros arquivos.

## Instruções
Você terá que desenvolver três funções seguindo os procedimentos adequados. Cada uma das três funções deve ser independente da outra, ou seja, elas devem funcionar por conta própria somente com os parâmetros passados.

O nome das funções deve ser exatamente como descrito pelo enunciado. Se atente para as instruções e procedimentos, todas as funções possuem retorno e é necessário seguir as instruções para que os testes funcionem da melhor forma.

### allocateShips

- Parâmetro(s):

shipPositions: Um array de arrays contendo as posições para alocar os navios.

initialBoard: Um array de arrays 5x5 simbolizando o tabuleiro vazio em que serão alocados os navios.

- Procedimento(s):

Criar uma função chamada allocateShips que aloque os navios em posições específicas no tabuleiro. A função deve receber como argumentos um array de posições de navios (shipPositions) e o tabuleiro com a formação inicialmente sem nenhum navio (initialBoard), apenas com valores ".". Cada posição de navio é um array de 2 elementos, representando a linha e a coluna onde o navio deve ser alocado. A função deve percorrer todas as posições de navio e alterar o valor correspondente no tabuleiro para "S".

- Retorno:

A função deve retornar o tabuleiro (array de arrays) modificado após a inserção dos navios.

### checkGuesses

- Parâmetro(s):

guesses: Um array de arrays contendo as suposições de onde estão os navios.

mountedBoard: Um array de arrays 5x5 simbolizando o tabuleiro já com os navios alocados.

- Procedimento(s):

Criar uma função chamada checkGuesses que verifique as suposições do jogador em relação à posição dos navios do adversário. A função deve receber como argumentos um array de suposições e o tabuleiro já montado com os navios. Cada suposição é um array de 2 elementos, representando a linha e a coluna onde o jogador supõe que um navio esteja. A função deve percorrer todas as suposições e, se uma suposição acertar a posição de um navio, deve alterar o valor correspondente no tabuleiro do adversário para "X".

- Retorno:

A função deve retornar o tabuleiro (array de arrays) modificado após as suposições de onde estão os navios.

### checkWinCondition

- Parâmetro(s):

guessedBoard: Um array de arrays 5x5 simbolizando o tabuleiro já com os navios alocados e com os palpites executados.

- Procedimento(s):

Criar uma função chamada checkWinCondition que verifique se o jogador venceu a partida. A função deve receber como argumento o tabuleiro de suposições do jogador. A função deve percorrer todo o tabuleiro de suposições e verificar se ainda há navios presentes no tabuleiro.

- Retorno:

Se todos os navios foram atingidos, a função deve retornar true, caso contrário, deve retornar false.

## Testagem

O repositório conta com uma página index.html de testes para te ajudar a debugar seu código. Para acessá-la, utilize a extensão LiveServer do VSCode. Com seu VSCode aberto no projeto, no arquivo index.html, clique no botão "Go Live" localizado na parte inferior direita do VSCode. Uma página deve ser aberta em seu navegador (caso não abra, você pode acessar manualmente em http://localhost:5500/).

Você precisará desenvolver as funções para que os testes comecem a funcionar. Criada as funções, você pode clicar no botão "Rodar Testes" para observar os resultados. A página contém três baterias de testes, uma bateria para cada função, e cada uma das três baterias pode ser executada individualmente.

## Debugando com eficiência

Com os dados esperados em mãos, podemos fazer nossos testes manuais no arquivo script.js para ajustar algum teste que não tenha passado. Cada uma das três funções deve ser independente, e os exemplos são de argumentos a serem passados ao chamar as funções. Observe com atenção o fluxo (são apenas alguns dos possíveis exemplos):

### allocateShips

```javascript
// Exemplo de tabuleiro vazio
const seaBoard = [
  [".", ".", ".", ".", "."],
  [".", ".", ".", ".", "."],
  [".", ".", ".", ".", "."],
  [".", ".", ".", ".", "."],
  [".", ".", ".", ".", "."],
];

// Exemplo de posições de navio
const shipPositions = [
  [0, 0],
  [1, 1],
  [2, 3],
  [4, 0],
  [4, 4],
  [2, 2],
];

// Exemplo de um retorno correto
[
  ["S", ".", ".", ".", "."],
  [".", "S", ".", ".", "."],
  [".", ".", "S", "S", "."],
  [".", ".", ".", ".", "."],
  ["S", ".", ".", ".", "S"],
];
```

### checkGuesses

```javascript
// Exemplo de tabuleiro montado
const mountedSeaBoard = [
  ["S", ".", ".", ".", "."],
  [".", "S", ".", ".", "."],
  [".", ".", "S", "S", "."],
  [".", ".", ".", ".", "."],
  ["S", ".", ".", ".", "S"],
];

// Exemplo de palpites
const guesses = [
  [0, 0],
  [1, 1],
  [2, 2],
  [2, 3],
  [4, 0],
  [4, 4],
];

// Exemplo de um retorno correto
[
  ["X", ".", ".", ".", "."],
  [".", "X", ".", ".", "."],
  [".", ".", "X", "X", "."],
  [".", ".", ".", ".", "."],
  ["X", ".", ".", ".", "X"],
];
```

### checkWinCondition

```javascript
// Exemplo de tabuleiro após palpites
const guessedSeaBoard = [
  ["X", ".", ".", ".", "."],
  [".", "X", "X", ".", "."],
  [".", ".", ".", ".", "."],
  [".", ".", ".", "X", "."],
  [".", ".", ".", ".", "X"],
];


// Exemplo de um retorno correto (a depender do que se espera)
true
``
