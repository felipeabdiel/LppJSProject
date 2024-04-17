# JavaScript (JS)
## Diário de Bordo - File 05 (Tipos de dados)
### Dados Primitivos

Quando são citados tipos de dados em uma determinada linguagem de programação, devemos entender que, de forma base, temos os tipos primitivos, as quais são parte inerente da linguagem codificada. Sâo formados, de modo geral, por dados únicos.
Nesse sentido, os dados primitivos em JavaScript são itemizados, de forma geral, conforme as descrições a seguir:

1. Number: Este tipo é usado para representar tanto inteiros quanto números de ponto flutuante. JavaScript usa um formato de ponto flutuante de dupla precisão para todos os seus números, conforme definido pela norma IEEE 754. Exemplos incluem 3, 3.14, e -200.

2. String: Representa uma sequência de caracteres e é usado para armazenar dados de texto. As strings em JavaScript são imutáveis, o que significa que uma vez criada, não é possível modificar o conteúdo da própria string (novas strings devem ser criadas). Exemplos de strings são "Olá mundo" e 'JavaScript'.

3. Boolean: Este tipo tem apenas dois valores possíveis: true (verdadeiro) e false (falso). É frequentemente usado em testes condicionais e lógica de controle de fluxo.

4. Undefined: Uma variável que não teve um valor atribuído a ela tem o tipo undefined. Este tipo é automaticamente atribuído a variáveis que são declaradas mas não inicializadas.

5. Null: Este tipo tem exatamente um valor: null. Ele é usado para indicar uma ausência deliberada de valor e é frequentemente utilizado em bases de código para representar o "nada" ou "nenhum valor".

6. Symbol: Introduzido no ECMAScript 2015 (ES6), o tipo Symbol é usado para criar identificadores únicos para propriedades de objetos. Cada valor Symbol é único e imutável.

7. BigInt: Também introduzido em versões mais recentes de JavaScript (ECMAScript 2020), o tipo BigInt é usado para representar números inteiros muito grandes que ultrapassam o limite seguro para o tipo Number. Um BigInt é criado ao anexar n ao final de um inteiro, como em 9007199254740991n.

Exemplo da definição de dados primitivos e aplicação em JavaScript

~~~javascript
let idade = 30;               // Number
let nome = "Maria";           // String
let usuarioAtivo = true;      // Boolean
let endereco;                 // Undefined
let salario = null;           // Null
let id = Symbol("id");        // Symbol
let grandeNumero = 123456789n;// BigInt
~~~


### Dados Estruturados
No que diz respeito aos dados estruturados, eles se tratam de um conjunto de outros dados primitivos ou ordinais estruturados, podendo abarcar também outras variáveis de tipo estruturado. Nesse sentido, seguem abaixo os tipos de dados estruturados possíveis de serem estabelecidos na linguagem de JavaScript.

1. Object: Este é o tipo de dado mais importante e mais versátil em JavaScript. Um objeto é uma coleção de propriedades, e uma propriedade é uma associação entre um nome (ou chave) e um valor. O valor de uma propriedade pode ser uma função, que é então considerada um método do objeto. Exemplos incluem objetos literais, arrays, funções, e muitos outros tipos de objetos embutidos.

~~~javascript
let pessoa = {
    nome: "João",
    idade: 28,
    falar: function() { console.log("Olá!"); }
};
~~~

2. Array: Arrays em JavaScript são objetos usados para armazenar listas ordenadas de valores. Eles podem conter qualquer tipo de dado, e os índices começam em 0. Arrays são objetos especiais com comportamentos e métodos adicionais para manipular listas ordenadas.
~~~javascript
let numeros = [1, 2, 3, 4, 5];
console.log(numeros[0]); // Acessa o primeiro elemento, 1
~~~

3. Date: Este é um tipo de objeto embutido que é usado para trabalhar com datas e horas. Ele permite a representação de momentos específicos no tempo e oferece métodos para operações de data e hora, como comparar datas, extrair partes de uma data (dia, mês, ano, etc.), e formatar datas.
~~~javascript
let agora = new Date();
console.log(agora); // Mostra a data e hora atual
~~~

4. RegExp (Expressões Regulares): Este é um objeto que descreve um padrão de caracteres. É usado principalmente para busca e substituição de texto em strings. É uma ferramenta poderosa para validar e manipular texto baseado em padrões definidos.
~~~javascript
let padrao = /ab+c/;
let resultado = padrao.test("abc"); // Retorna true
~~~

5. Map e Set: Introduzidos com ES6, esses são novos tipos de coleções de dados. Map é uma coleção de pares chave-valor que lembra a ordem original de inserção das chaves. Set, por outro lado, é uma coleção de valores que não permite duplicatas.
~~~javascript
let mapa = new Map();
mapa.set('chave', 'valor');
console.log(mapa.get('chave')); // 'valor'

let conjunto = new Set();
conjunto.add(1);
conjunto.add(2);
console.log(conjunto.has(1)); // true
~~~
