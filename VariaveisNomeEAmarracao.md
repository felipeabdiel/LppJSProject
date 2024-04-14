# JavaScript (JS)
## Diário de Bordo - File 03 (Variáveis - Nome e amarração)
### Nomes de variável

Alguns pontos são importantes ao definir os nomes de variável dentro de uma linguagem. Dentro do campo de JavaScript alguns dos parâmetros estão descritos abaixo, juntamente com a definição.

• Tamanho máximo de nome: Não há um tamanho máximo estritamente definido para um nome em JavaScript. No entanto, é uma boa prática manter os nomes de variáveis, funções e identificadores em um tamanho razoável para melhor legibilidade e compreensão do código.

• Caracteres de coneção: Sim, em JavaScript, você pode usar caracteres de conexão como sublinhado (_) ou o sinal de cifrão ($) em nomes de variáveis, funções e identificadores. Exemplo segue abaixo.

~~~javascript

let minhaVariavel = "Exemplo";
let minha_funcao = function() {
    // Código aqui
};
let $elemento = document.getElementById("idElemento");

~~~

• Diferenciação entre caracteres minúsculos e maiúsculos: Sim, JavaScript é sensível a maiúsculas e minúsculas. Isso significa que minhaVariavel e minhavariavel são consideradas como identificadores diferentes em JavaScript. Em termos técnicos isso é chamado de case-sensitive.

~~~javascript

let minhaVariavel = "Olá";
let minhaVariavel = "Mundo"; 

~~~

• Palavras reservadas ou palavras chave: Em JavaScript, existem palavras reservadas que não podem ser usadas como nomes de variáveis, funções ou identificadores, pois são parte da linguagem e têm um significado específico.
Alguns exemplos dessas palavras é 'let', 'var', 'const' e 'function'.

#### Formas de nome

No que diz respeito às formas de nome de variáveis na linguagem JavaScript, não há símbolos que definam variáveis e funções. Isso significa que não classes, funções e variáveis são diferenciadas apenas no momento de sua declaração e/ou utilização em atribuições.
Além disso, é válido salientar que não há a possibilidade de utilizar espaços em branco na declaração do nome de variáveis, funcões e classes.


### Tipos de variável

Saindo do padrão geral do funcionamento da maioria esmagadora das linguagens de programação existentes, em JS as variáveis não possuem um tipo fixo associado à elas. Isto é, o tipo da variável é definido por meio da sua atribuição.
Em um resumo sucinto, a declaração não acompanha a definição do tipo antes da atribuição da variável, geralmente sendo utilizada a palavra 'let' ou 'var' dependendo do contexto.

Abaixo segue alguns exemplos visíveis do que foi citado para a linguagem

~~~javascript
let idade = 30;        // Inteiro
let preco = 19.99;     // Ponto flutuante
let nome = "Maria";
let mensagem = 'Olá, mundo!';
let ativo = true;
let verificado = false;
let valor;
let endereco = null;
const grandeNumero = 1234567890123456789012345678901234567890n;
const simbolo = Symbol('descricao');
~~~~

Conforme visualizado no exemplo, não há descrição clara do tipo da variável antes do seu valor atribuído, portanto, o tipo é definido a partir do seu valor. Entretanto, há uma função nativa que identifica o tipo da variável, conforme o exemplo que segue abaixo.
~~~javascript
typeof 10;          // "number"
typeof "Olá";       // "string"
typeof true;        // "boolean"
typeof undefined;   // "undefined"
typeof null;        // "object" (Nota: typeof null retorna "object", mas null é seu próprio tipo)
typeof {};          // "object"
typeof [];          // "object"
typeof function(){};// "function"
~~~~


### Endereços de variável

Quando citamos a ideia dos endereços de variável e seu funcionamento, se tratando de JavaScript, a linguagem funciona com base em algumas definições que podem ser realizadas por meio da resposta de duas perguntas. Sendo elas:

#### Posso ter uma variável associada a endereços diferentes, em momentos diferentes de execução do programa?
A resposta é que, em JavaScript, quando você reatribui uma variável de referência a um novo objeto, a variável passa a fazer referência ao novo objeto, mas isso não significa que ela tenha um "endereço de memória" diferente em termos de manipulação direta.
Abaixo segue um exemplo que ilustra o que foi citado:

~~~javascript
let obj1 = { nome: "João" };
let obj2 = obj1;  // obj2 faz referência ao mesmo objeto que obj1

obj1 = { nome: "Maria" };  // obj1 agora faz referência a um novo objeto

console.log(obj2.nome);  // Continua sendo "João", pois obj2 ainda faz referência ao objeto original
~~~

#### Posso ter variáveis diferentes com o mesmo endereço?
Como mencionado anteriormente, em JavaScript, quando você cria uma variável de referência e atribui-a a outra variável de referência, ambas as variáveis compartilham a mesma referência ao objeto no heap. No entanto, isso não é visível como um "endereço de memória" diretamente acessível ou manipulável.
Mais um exemplo segue abaixo, o qual ilustra a resposta citada.

~~~javascript
let obj1 = { nome: "João" };
let obj2 = obj1;  // obj2 faz referência ao mesmo objeto que obj1

console.log(obj1 === obj2);  // Retorna true, pois obj1 e obj2 têm a mesma referência

console.log(obj1 === { nome: "João" });  // Retorna false, pois este é um novo objeto com uma nova referência
~~~

### Amarração de tipo

Por conta de JavaScript se tratar de uma linguagem em que o tipo definido de variável não é estático, a amarração de tipo das variáveis se torna dinâmica, uma vez que uma mesma variável pode receber posteriormente na execução do programa um valor de um tipo diferente daquele que foi anteriormente declarado.
Para exemplificar melhor essa definição, segue abaixo o exemplo de amarração de tipo estático em Java e, após o exemplo de Java, imediatamente o exemplo de JavaScript.

•Exemplo de Java
~~~java
int idade = 30;       // Tipo é definido como int em tempo de compilação
idade = "trinta";     // Erro de compilação: tipo incompatível
~~~

•Exemplo de JavaScript
~~~javascript
let idade = 30;       // Tipo é determinado em tempo de execução (número)
idade = "trinta";     // Tipo é alterado para string em tempo de execução
~~~

### Conclusão

JavaScript abstrai o gerenciamento de memória e endereços de memória, simplificando o modelo de programação. Isso facilita a escrita de código eficiente, sem preocupações diretas sobre manipulação de memória, típicas de linguagens de baixo nível. Além disso, JavaScript oferece amarração dinâmica de tipo, determinando o tipo de uma variável em tempo de execução e permitindo alterações durante a execução do programa. Essa flexibilidade requer atenção ao manipular diferentes tipos de dados para evitar erros de tipo. Embora JavaScript não ofereça suporte nativo à amarração estática de tipo, ferramentas como TypeScript podem ser utilizadas para adicionar verificação de tipo estático ao código JavaScript.



