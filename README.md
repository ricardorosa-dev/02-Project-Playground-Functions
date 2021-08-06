# 02 Playground Functions!


## Requisitos do projeto

## ⚠️ Leia-os atentamente e siga à risca o que for pedido. Não altere o nome de nenhuma função. ⚠️

O não cumprimento de um requisito, total ou parcialmente, impactará em sua avaliação.

---

**1 - Usando o operador &&**
-
JavaScript possui um operador lógico `&&`, o qual recebe dois valores e retorna `true` se ambos os valores são verdadeiros, e retorna `false` se algum dos valores não o for.

Considerando isso, crie uma função chamada `compareTrue` que, ao receber dois booleanos:

- Retorne `true` se ambos os valores são verdadeiros;
- Retorne `false` se um ou ambos os parâmetros forem falsos.

Faça a função utilizando o operador `&&`.

```JavaScript
// Desafio 1
function compareTrue(param1, param2) {
    // seu código aqui
    if (param1 == true && param2 == true) {
        console.log("Ambos os valores são verdadeiros!");
        return true;
    } else {
        console.log("Algum dos valores é falso!");
        return false;
    }
}
```

**2 - Área do triângulo** 
-
Escreva uma função com o nome `calcArea` que receba um valor de base (chamado `base`) e outro de altura (chamado `height`) de um triângulo e retorne o cálculo da sua área.

Lembre-se que a área de um triângulo é calculada através da seguinte fórmula: (base * altura) / 2.

```JavaScript
// Desafio 2
function calcArea(base, height) {
    // seu código aqui
    return (base * height) / 2;
}
```

**3 - Dividindo a frase**
-
Escreva uma função com o nome `splitSentence`, a qual receberá uma string e retornará uma array de strings separadas por cada espaço na string original.

Exemplo: se a função receber a string `"go Trybe"`, o retorno deverá ser `['go', 'Trybe']`.

```JavaScript
// Desafio 3
function splitSentence(string) {
    // seu código aqui
    array = string.split(" ");
    console.log(array);
    return array;
}
```

**4 - Concatenação de strings**
-
Escreva uma função com o nome `concatName` que, ao receber uma array de strings, retorne uma string com o formato `'ÚLTIMO ITEM, PRIMEIRO ITEM'`, independente do tamanho da array.

Isso quer dizer que, caso o parâmetro passado para `concatName` seja a Array ['Lucas', 'Cassiano', 'Ferraz', 'Paolillo'], a função deverá retornar `Paolillo, Lucas`.

```JavaScript
// Desafio 4
function concatName(array) {
    // seu código aqui
    resultado = array[array.length - 1] + ", " + array[0];
    console.log(resultado);
    return resultado;
}
```

**5 - Pontos no futebol**
-
Escreva uma função com o nome `footballPoints` que receba o número de vitórias (esse parâmetro deverá se chamar `wins`) e o número de empates (esse parâmetro deverá se chamar `ties`) e retorne a quantidade de pontos que o time marcou em um campeonato.

Para tanto, considere que cada vitória vale 3 pontos e cada empate vale 1 ponto.

```JavaScript
// Desafio 5
function footballPoints(wins, ties) {
    // seu código aqui
    //retornar os pontos, vitoria = 3, empate = 1
    resultado = wins * 3 + ties;
    console.log(resultado);
    return resultado;
}
```

**6 - Repetição do maior número**
-
Escreva uma função chamada `highestCount` que, ao receber uma array de números, retorne  a quantidade de vezes que o maior deles se repete.

Exemplo: caso o parâmetro de `highestCount` seja uma array com valores `[9, 1, 2, 3, 9, 5, 7]`, a função deverá retornar `2`, que é a quantidade de vezes que o número `9` (maior número do array) se repete.

```JavaScript
// Desafio 6
function highestCount(array) {
    // seu código aqui
    //saber qual é o maior
    let maiorNumero = array[0];
    let vezes = 1;
    for (let i = 1; i < array.length; i++) {
        if (array[i] > maiorNumero) {
            maiorNumero = array[i]
            vezes = 1;
        } else if (array[i] == maiorNumero) {
            vezes += 1;
        }
    }
    console.log("O número maior é " + maiorNumero + ", que se repete " + vezes + " vezes.");
    return vezes;
}
```

**7 - Caça ao rato**
-
Imagine que existem dois gatos, os quais chamaremos de `cat1` e `cat2`, e que ambos estão atrás de um rato chamado `mouse`. Imagine que cada um dos três animais está em uma posição representada por um número.

Sabendo disso, crie uma função chamada `catAndMouse` que, ao receber a posição de `mouse`, `cat1` e `cat2`, **nessa ordem**, calcule as distâncias entre o rato e os gatos e retorne qual dos felinos irá alcançar o rato primeiro (sendo aquele que estará mais perto).

Exemplo: caso o gato `cat2` esteja a 2 unidades de distância do rato, e `cat1` esteja a 3 unidades, sua função deverá retornar `cat2`.

Caso os gatos estejam na mesma distância do rato, a função deverá retornar a string `"os gatos trombam e o rato foge"`.

```JavaScript
// Desafio 7
function catAndMouse(mouse, cat1, cat2) {
    // seu código aqui
    let catpos1;
    let catpos2;

    // posição cat1
    if (cat1 > mouse) {
        catpos1 = cat1 - mouse;
    } else {
        catpos1 = mouse - cat1;
    }

    // posição cat2
    if (cat2 > mouse) {
        catpos2 = cat2 - mouse;
    } else {
        catpos2 = mouse - cat2;
    }

    if (catpos1 < catpos2) {
        // cat1 mais perto do rato
        console.log("Cat1 pegou o rato!");
        return "cat1";
    } else if (catpos2 < catpos1) {
        // cat2 mais perto
        console.log("Cat2 pegou o rato!");
        return "cat2";
    } else {
        // mesma distância
        console.log("os gatos trombam e o rato foge");
        return "os gatos trombam e o rato foge";
    }
}
```

**8 - FizzBuzz**
-
Crie uma função chamada `fizzBuzz` que receba uma array de números e retorne uma array da seguinte forma:

- Para cada número da Array que seja divisível por 3, apresente uma string `"fizz"`;
- Para cada número da Array que seja divisível por 5, apresente uma string `"buzz"`;
- Caso o número seja divisível por 3 ou 5, retorne a string `"fizzBuzz"`;
- Caso o número não possa ser dividido por 3 nem por 5, retorne a string `"bug!"`;

Exemplo: caso o parâmetro seja [2, 15, 7, 9, 45], sua função deverá retornar `["bug!", "fizzBuzz", "bug!", "fizz", "fizzBuzz"]`.

```JavaScript
// Desafio 8
function fizzBuzz(array) {
    // seu código aqui
    let resposta = [];
    for (let i = 0; i < array.length; i++) {
        if (array[i] % 3 === 0) {
            //é divisível ṕor 3
            if (array[i] % 5 === 0) {
                //é divisível pelos dois
                resposta[i] = "fizzBuzz";
            } else {
                resposta[i] = "fizz";
            }
        } else if (array[i] % 5 === 0) {
            //é divisível por 5
            resposta[i] = "buzz";
        } else {
            // não é divisível por nenhum deles
            resposta[i] = "bug!";
        }
    }
    return resposta;
}
```

**9 - Codifique e Decodifique**
-
Crie duas funções: a primeira deverá se chamar `encode` e, ao receber uma string como parâmetro, deverá trocar todas as vogais minúsculas por números, de acordo com o formato a seguir:

a -> 1 \
e -> 2 \
i -> 3 \
o -> 4 \
u -> 5

Ou seja, caso o parâmetro de `encode` seja `"hi there!"`, o retorno deverá ser `"h3 th2r2!"`.

A segunda função deverá se chamar `decode` e faz o contrário de `encode` - ou seja, recebe uma string contendo números no lugar de letras minúsculas e retornará uma string com vogais minúsculas no lugar dos números (então, caso o parâmetro de `decode` seja `"h3 th2r2!"`, o retorno deverá ser `"hi there!"`).

```JavaScript
// Desafio 9
function encode(string) {
    // seu código aqui
    // transforma a string em array. Vira 'frase'
    let frase = string.split("");

    // troca as letras
    for (let i = 0; i < frase.length; i++) {
        switch (frase[i]) {
            case "a":
                frase[i] = "1";
                break;
            case "e":
                frase[i] = "2";
                break;
            case "i":
                frase[i] = "3";
                break;
            case "o":
                frase[i] = "4";
                break;
            case "u":
                frase[i] = "5";
                break;
            default:
        }
    }
    //junta de novo (o contrario de split)
    frase = frase.join("");
    console.log(frase)
    return frase;
}

function decode(string) {
    // seu código aqui
    // transforma a string em array. Vira 'frase'
    let frase = string.split("");

    // troca as letras
    for (let i = 0; i < frase.length; i++) {
        switch (frase[i]) {
            case "1":
                frase[i] = "a";
                break;
            case "2":
                frase[i] = "e";
                break;
            case "3":
                frase[i] = "i";
                break;
            case "4":
                frase[i] = "o";
                break;
            case "5":
                frase[i] = "u";
                break;
            default:
        }
    }
    //junta de novo (o contrario de split)
    frase = frase.join("");
    console.log(frase)
    return frase;
}
```

**10 - Lista de tecnologias**
-
Crie uma função que recebe um array de nomes de tecnologias que você quer aprender. Essa função deve receber também um segundo parâmetro chamado `name` com um nome.

Para cada tecnologia no array, crie um objeto com a seguinte estrutura:

```
{
  tech: "NomeTech",
  name: name
}
```

Estes objetos devem ser inseridos em uma nova lista em ordem crescente a partir do campo `tech` no objeto.

A saída da sua função deve ser uma lista de objetos ordenada pelo campo `tech` dos objetos com o formato acima.

Exemplo:
```
Entradas da função:

["React", "Jest", "HTML", "CSS", "JavaScript"]
"Lucas"

// Saída:

[
  {
    tech: "CSS",
    name: "Lucas"
  },
  {
    tech: "HTML",
    name: "Lucas"
  },
  {
    tech: "JavaScript",
    name: "Lucas"
  },
  {
    tech: "Jest",
    name: "Lucas"
  },
  {
    tech: "React",
    name: "Lucas"
  }
]
```

Caso o array venha vazio sua função deve retornar 'Vazio!'

```JavaScript
// Desafio 10
function techList(array, name) {
    if (array.length < 1) {
        console.log("Vazio!");
        return "Vazio!";
    } else {
        //sorting
        let sortedArray = array.sort();

        // seu código aqui.
        let objects = [];
        for (let i = 0; i < sortedArray.length; i++) {
            objects[i] = {
                tech: sortedArray[i],
                name: name,
            }
        }
        console.log(objects);
        return objects;
    }
}
```

**Bônus**
=
**11 - Número de telefone**
-
Crie uma função chamada `generatePhoneNumber` que receba uma array com 11 números e retorne um número de telefone, respeitando parênteses, traços e espaços.

Exemplo: caso o parâmetro da função seja [1, 2, 3, 4, 5, 6, 7, 8, 9, 0, 1], `generatePhoneNumber` deverá retornar `(12) 34567-8901`.

- Se a função receber um array com tamanho diferente de 11, a mesma deve retornar `"Array com tamanho incorreto."`.

- Caso algum dos números da array seja menor que 0, maior que 9 ou se repita 3 vezes ou mais, `generatePhoneNumber` deverá retornar a string `"não é possível gerar um número de telefone com esses valores"`.

```JavaScript
// Desafio 11
function generatePhoneNumber(param) {
    // seu código aqui
    if (param.length !== 11) {
        return "Array com tamanho incorreto.";
    } else {

        for (let i = 0; i < param.length; i++) {

            if (param[i] < 0 || param[i] > 9) {
                return "não é possível gerar um número de telefone com esses valores";
            }

            let numTimes = 1;
            for (let j = 0; j < param.length; j++) {

                if (i === j) {

                } else {

                    if (param[j] == param[i]) {
                        numTimes += 1;
                    }

                }

            } // for interno

            if (numTimes >= 3) {
                return "não é possível gerar um número de telefone com esses valores";
            }


        } // for externo 

        let fullNumber = "(" + param[0] + param[1] + ") " + param[2] + param[3] + param[4] + param[5] + param[6] + "-" + param[7] + param[8] + param[9] + param[10];
        console.log(fullNumber);
        return fullNumber;
    } //else
} //function
```

**12 - Condição de existência de um triângulo**
-
Um triângulo é composto de três linhas: `lineA`, `lineB` e `lineC`. Crie uma função chamada `triangleCheck` que deverá receber as três linhas como parâmetro e retornar se é possível formar um triângulo com os valores apresentados de cada linha

Para tanto, tenha em mente algumas considerações:

- Para que seja possível formar um triângulo, é necessário que a medida de qualquer um dos lados seja menor que a soma das medidas dos outros dois e maior que o valor absoluto da diferença entre essas medidas.

- Para obter o valor absoluto de um número em JavaScript, pesquise pela função `Math.abs`.

- O retorno da sua função deverá ser um booleano.

Exemplo: o retorno de `triangleCheck(10, 14, 8)` deverá ser `true`.

```JavaScript
// Desafio 12
function triangleCheck(lineA, lineB, lineC) {
    // seu código aqui
    //Pasou, agora vou escrever mais limpo
    let lado1 = false;
    if (lineA < lineB + lineC && lineA > Math.abs(lineB - lineC)) {
        lado1 = true;
    }

    let lado2 = false;
    if (lineB < lineC + lineA && lineB > Math.abs(lineC - lineA)) {
        lado2 = true;
    }

    let lado3 = false;
    if (lineC < lineA + lineB && lineC > Math.abs(lineA - lineB)) {
        lado3 = true;
    }

    // Retorna o resultado
    if (lado1 === true && lado2 === true && lado3 === true) {
        return true;
    } else {
        return false;
    }
}
```

**13 - Bem vindo ao Bar da Trybe!**
-
Segundo as regras desse bar, a cada bebida deve-se beber um copo de água para que não se tenha ressaca.

Crie a função `hydrate` que recebe uma string, e retorne a sugestão de quantos copos de água você deve beber. Exemplos:
```
String recebida:
  "1 cerveja"
String retornada:
  "1 copo de água"
```

```
String recebida:
  "1 cachaça, 5 cervejas e 1 copo de vinho"
String retornada:
  "7 copos de água"
```

```
String recebida:
  "1 cachaça, 5 cervejas e 1 copo de vinho"
String retornada:
  "7 copos de água"
```

**Notas**

- Para simplificar, consideraremos que qualquer coisa com um número à frente é uma bebida **e que a sua string sempre virá com o formato quantidade (em número) + tipo da bebida**.

- O número na frente de cada bebida está no intervalo entre 1 e 9.

**Dica:** pesquise por algo similar a `get all integers inside a string js`.

```JavaScript
// Desafio 13
function hydrate(param) {
    // seu código aqui 
    //console.log(param.split(" "));
    paramArray = param.split(" ");
    let sum = 0;
    for (let i = 0; i < paramArray.length; i += 1) {
        if (isNaN(paramArray[i])) {
            // console.log(paramArray[i]);
            // console.log("Não é um número");
        } else {
            // console.log(paramArray[i]);
            // console.log("É um número");
            sum += Number(paramArray[i]);
        }
    }
    //Pra fazer a diferença de 'copo' e 'copos'. Não ficou claro se é necessário isso.
    if (sum > 1) {
        console.log(sum + " copos de água");
        return sum + " copos de água";
    } else {
        console.log(sum + " copo de água");
        return "1 copo de água";
    }
}
```

---
