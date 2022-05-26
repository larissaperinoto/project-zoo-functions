
# Projeto Zoo Functions

Projeto desenvolvido como encerramento do bloco 8 que abordou as Higher Order Functions do JavaScript ES6.

### Objetivos

Utilizar as Higher Order Functions para resolver problemas associados à dados do zoológico que estão contidos no arquivo `zoo_data.js` e também aplicar Testes Unitários usando Jest para validar as funções utilizadas.

### Requisitos

#### 1. Implemente a função `getSpeciesByIds`

Busque as espécies dos animais por meio de um <code>id</code> e retorne um array contendo todos os animais dessa espécie.

- Faça com que a função `getSpeciesByIds` possa receber vários parâmetros;

- Retorne um array vazio se a função não receber um `id`;

- Retorne as seguintes informações do arquivo `data`:

  - Se a função receber apenas um `id`, retorne a espécie do animal referente a este `id`;

  - Se a função receber vários `ids`, retorne todas as espécies referente a esses `ids`.

#### 2. Implemente a função `getAnimalsOlderThan`

Ao receber uma espécie e uma idade como parâmetro, retorne se todos os animais dessa espécie possuem essa idade ou são mais velhos.

- Verifique se todos os animais da espécie passada como parâmetro possuem a idade mínima:
  - Os animais devem ter essa idade ou serem mais velhos.

- Retorne um valor booleano.


#### 3. Implemente a função `getEmployeeByName`

Busque as pessoas colaboradoras pelo primeiro ou último nome delas

- Retorne um objeto vazio caso a função não receba parâmetros;

- Retorne as informações da pessoa colaboradora caso o parâmetro seja igual ao nome **ou** igual ao último nome no seguinte formato:

```javascript
  {
    id: 'c5b83cb3-a451-49e2-ac45-ff3f54fbe7e1',
    firstName: 'Nigel',
    lastName: 'Nelson',
    managers: ['0e7b460e-acf4-4e17-bcb3-ee472265db83', 'fdb2543b-5662-46a7-badc-93d960fdc0a8'],
    responsibleFor: ['0938aa23-f153-4937-9f88-4858b24d6bce', 'e8481c1d-42ea-4610-8e11-1752cfc05a46'],
  }
```

#### 4. Implemente a função `getRelatedEmployees`

Verifique se uma pessoa colaboradora é gerente e quais pessoas ela lidera

Considerando a boa prática de dividir o código em partes menores, o arquivo terá duas funções:

1. `isManager` que será responsável por verificar se uma pessoa colaboradora é gerente:
    - Retorne `true` se o `id` passado for de uma pessoa gerente;
    - Retorne `false` se o `id` passado não for de uma pessoa gerente.

2. `getRelatedEmployees` que retorna as pessoas lideradas pela gerência:
      - Utilize a função `isManager` para verificar se a pessoa é gerente ou não e faça as seguintes verificações:

        - Caso a pessoa seja gerente, retorne um array contendo nome e sobrenome das pessoas colaboradoras gerenciadas por essa pessoa.

        Exemplo de output:

        ```javascript

        [ 'Burl Bethea', 'Ola Orloff', 'Emery Elser' ];

        ```

        - Caso a pessoa não seja gerente, dispare um erro com a mensagem: **'O id inserido não é de uma pessoa colaboradora gerente!'**.

#### 5. Implemente a função `countAnimals`

Contabilize a quantidade de espécies de animais residentes no zoológico

A função `countAnimals` é responsável por contar a quantidade e animais que residem no zoológico.

- Retorne a quantidade de animais residentes por espécie, caso a função não receba parâmetro. O retorno deverá ser um objeto cujo o nome de cada espécie é a chave e o total de animais (residentes) dessa espécie é o valor. Por exemplo:

```javascript
  {
    lions: 4,
    // [...]
  }
```
- Retorne a quantidade de animais residentes no zoológico da espécie passada por parâmetro. Por exemplo:

  - ao receber o argumento `{ specie: 'penguins' }`, retorna apenas a quantidade (número) de pinguins que residem no zoológico;

  - ao passar o argumento `{ specie: 'giraffes', sex: 'female' }`, retorna apenas a quantidade (número) de girafas fêmeas que residem no zoológico.

#### 6. Obtenha ao menos 80% de cobertura de testes na função `handlerElephants`

Implemente os testes da função <code>handlerElephants</code> para obter ao menos 80% de cobertura

#### 7. Obtenha ao menos 90% de cobertura de testes na função `handlerElephants`

Implemente os testes da função <code>handlerElephants</code> para obter ao menos 90% de cobertura

#### 8. Implemente a função `calculateEntry`

Calcule o valor <strong>total</strong> da entrada dos visitantes do zoológico

O valor das entradas do zoológico é calculado a partir da faixa etária, onde:

  - `child`: são pessoas **menores** de 18 anos;

  - `adult`: são pessoas com idade **maior ou igual** a 18 anos **e menor** que 50 anos;

  - `senior`: são pessoas com idade **maior ou igual** a 50 anos.

Considerando a boa prática de dividir o código em partes menores, o arquivo terá duas funções, chamadas de `countEntrants` e `calculateEntry`.

As duas funções recebem um array no seguinte formato:

```javascript
const entrants = [
	{ name:  'Lara Carvalho', age:  5 },
	{ name:  'Frederico Moreira', age:  5 },
	{ name:  'Pedro Henrique Carvalho', age:  5 },
	{ name:  'Maria Costa', age:  18 },
	{ name:  'Núbia Souza', age:  18 },
	{ name:  'Carlos Nogueira', age:  50 },
];
```

1. `countEntrants` será responsável por calcular a quantidade de visitantes por faixa etária:

  Ela recebe um array e deve retornar um **objeto**. Para isso:

  - Realize a soma da quantidade de visitantes por faixa etária;

  - Retorne um objeto em um formato como esse: `{ child: 3, adult: 2, senior: 1 }`.

2. `calculateEntry` será responsável por somar o valor da entrada das pessoas no zoológico:

  Ela recebe um array e deve retornar a soma **total** dos valores do ingresso. Para isso:

  - Retorne `0` se nenhum parâmetro for passado ou seja um array vazio;

  - Utilize a função `countEntrants` para ter a quantidade total de pessoas por faixa etária;

  - Realize a soma dos valores dos ingressos por faixa etária. Seu retorno deve ser parecido com esse: `187.94`.

#### 9. Implemente a função `getSchedule`

Crie um cronograma com os horários de visita disponíveis para cada espécie de animal

As informações dos horários dos animais devem ser disponibilizadas em uma consulta para as pessoas que estão visitando o zoológico, que podem querer ter acesso ao cronograma da semana, de um dia ou de um animal específico.

- Retorne um array com os dias da semana em que um animal está disponível para visitação caso o parâmetro da função seja um animal. Por exemplo: `[ 'Tuesday', 'Thursday', 'Saturday', 'Sunday' ]`;

- Retorne todos os horários disponíveis para cada dia da semana caso a função:

  - não receba parâmetro;

  - o parâmetro passado para a função não seja um animal ou um dia;

  Para isso:

  - Crie um objeto e adicione todos os dias da semana como chave;

  - Os valores de cada dia da semana deve ser um objeto, possuindo as chaves `officeHour` e `exhibition`:

    - `officeHour` deve possuir o texto com o horário que o zoológico abre e fecha naquele dia da semana;

    - `exhibition` deve possuir um array com o nome de todos os animais disponíveis para visitação naquele dia da semana.

O retorno deve ser parecido com esse:

  ```javascript
  {
    Tuesday: { // Dia da semana
      officeHour: 'Open from 8am until 6pm', // n
      exhibition: [ 'lions', 'tigers', 'bears', 'penguins', 'elephants', 'giraffes' ],
    },
    Wednesday: {
      officeHour: 'Open from 8am until 6pm',
      exhibition: [ 'tigers', 'bears', 'penguins', 'otters', 'frogs', 'giraffes' ],
    },
    // [...]
  }
  ```

- Retorne os animais disponíveis no dia, caso o parâmetro da função seja apenas um dia da semana;

#### 10. Implemente a função `getOldestFromFirstSpecies`

Encontre o animal mais velho de uma espécie que é gerenciado por uma pessoa colaboradora

A função recebe um parâmetro `id` referente à pessoa colaboradora e a partir desse `id`:

- Encontre a pessoa colaboradora que possui o `id` passado por parâmetro;

- Encontre a **primeira** espécie de animal que a pessoa colaboradora é responsável;

- Encontre o animal mais velho daquela espécie;

- Retorne um array com as informações do animal mais velho daquela espécie.

#### 11. Implemente a função `getEmployeesCoverage`

Busque as informações sobre a pessoa colaboradora e por quais espécies ela é responsável.

A função vai receber um objeto como parâmetro que vai determinar o seu comportamento, sendo:

  - `name`: o nome **ou** sobrenome da pessoa a ser buscada;

  -  `id`: o id da pessoa a ser buscada.

E deve retornar um objeto no seguinte formato:

```javascript
{
	id: "4b40a139-d4dc-4f09-822d-ec25e819a5ad", // id da pessoa
	fullName: "Sharonda Spry", // nome completo: firstName + lastName
	species: [ "otters", "frogs" ], // espécies as quais a pessoa é responsável
	locations: [ "SE", "SW" ], // Um array contendo todas as localizações das espécies
}
```
Caso o parâmetro seja um objeto com nome e id, retorne as informações da pessoa colaboradora

```json
{
	"id": "4b40a139-d4dc-4f09-822d-ec25e819a5ad",
	"fullName": "Sharonda Spry",
	"species": [ "otters", "frogs" ],
	"locations": [ "SE", "SW" ]
}
```
Caso nenhuma pessoa seja encontrada com o nome, sobrenome ou id, lance um erro.

#### 12. Obtenha ao menos 85% de cobertura de testes na função `getOpeningHours`

Implemente os testes da função <code>getOpeningHours</code> para obter ao menos 85% de cobertura

Esta função recebe como argumentos um dia da semana e um horário, e retorna uma mensagem informando se o zoológico está aberto ou não naquela data e hora.

#### 13. Obtenha ao menos 95% de cobertura de testes na função `getOpeningHours`

Implemente os testes da função <code>getOpeningHours</code> para obter 95% de cobertura.

Esta função recebe como argumentos um dia da semana e um horário, e retorna uma mensagem informando se o zoológico está aberto ou não naquela data e hora.

#### 14. Implemente a função `getAnimalMap`

Faça o mapeamento geográfico dos animais de cada espécie e realize filtros de localização, nome em ordem alfabética e sexo.

A função `getAnimalMap` é responsável por categorizar os animais por localização, além de filtrá-los por região, nome e sexo a partir de um parâmetro. A estrutura do retorno da função é baseada na localização das espécies:

```javascript
  {
    NE: [ /* dados aqui */],
    NW: [/* dados aqui */],
    SE: [/* dados aqui */],
    SW: [/* dados aqui */],
  }
```

Os parâmetros da função podem ser:

<code>includeNames: true</code>, que retorna o nome dos animais no seguinte formato:


```javascript
  NE: [
    { lions: ['Zena', 'Maxwell', 'Faustino', 'Dee'] },
    { giraffes: ['Gracia', 'Antone', 'Vicky', 'Clay', 'Arron', 'Bernard'] },
  ],
  // [...]
```

 <code>sorted: true</code> que retorna o nome dos animais por ordem alfabética no seguinte formato:

  ```javascript
  NE: [
    { lions: ['Dee', 'Faustino', 'Maxwell', 'Zena'] },
    { giraffes: ['Antone', 'Arron', 'Bernard', 'Clay', 'Gracia', 'Vicky'] },
  ],
  // [...]
```

<code>sex: male</code> ou <code>sex: female</code> retorna o <strong>nome</strong> dos animais que são machos ou fêmeas no seguinte formato:


```javascript
  NE: [
    { lions: ['Zena', 'Dee'] },
    { giraffes: ['Gracia', 'Vicky'] },
  ],
  // [...]
```

Se o parâmetro for `{ sex: male }`, retorne apenas o nome dos animais machos e se o parâmetro for `{ sex: female }` retorne apenas o nome dos animais fêmeas.


  Caso a função não receba parâmetro, as espécies dos animais devem ser categorizadas por localização e deve retornar um objeto no seguinte formato:


  ```javascript
  {
    NE: ['lions', 'giraffes'],
    NW: ['tigers', 'bears', 'elephants'],
    SE: ['penguins', 'otters'],
    SW: ['frogs', 'snakes'],
  }
  ```

- Sem parâmetros, retorna animais categorizados por localização;

- Sem a opção `includeNames` especificada, retorna animais categorizados por localização;

- Com a opção `includeNames: true` especificada, retorna nomes de animais;

- Com a opção `sorted: true` especificada, retorna nomes de animais ordenados;

- Com a opção `sex: 'female'` ou `sex: 'male'` especificada, retorna somente nomes de animais macho/fêmea;

- Com a opção `sex: 'female'` ou `sex: 'male'` especificada e a opção `sorted: true` especificada, retorna somente nomes de animais macho/fêmea com os nomes dos animais ordenados;


#### 15. Obtenha 100% de cobertura de testes na função `handlerElephants`

Implemente os testes da função <code>handlerElephants</code> para obter 100% de cobertura.


#### 16. Obtenha ao menos 100% de cobertura de testes na função `getOpeningHours`

Implemente os testes da função <code>getOpeningHours</code> para obter 100% de cobertura.

---

### Projeto Aprovado!

![Captura de tela de 2022-05-24 09-30-54](https://user-images.githubusercontent.com/98956659/170396786-1eded97f-b26b-49e3-ae73-b650223e8d44.png)
