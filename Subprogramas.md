# JavaScript (JS)

## Diário de Bordo - File 06 (Subprogramas)

### Subprogramas

Os subprogramas são, em suma, espécies de softwares que realizam, inseridos um contexto maior, uma função específica dentro de um programa maior. Isto é, os subprogramas estão sempre anexados a um outro software afim de simplilficar a sua execução. 
Em geral, os subprogramas são utilizados para facilitar a leitura tornando o código mais legível, além de o modularizar afim de facilitar a sua manutenção e chamadas dentro do software. Além disso, há uma diminuição de custos relativo ao tempo de codificação e a memória também é economizada na execução do código.

#### Padrões gerais de subprogramas utilizados em JavaScript

Em Javascript é possível utilizar de subprogramas de diversas formas. Entre elas podemos listar algumas mais gerais, como por exemplo

• Declaração de função:

~~~javascript

function HelloWorld(){
    return ("Hello World");
}

~~~

Essa função trata-se de um subprograma que faz a simplificação de um comando que seria mais longo. Ou seja, a chamada dessa função simplifica um procedimento que levaria mais tempo para ser executado.

• Modularização do código

~~~javascript

function soma(a, b) {
    return a + b;
}

function media(a, b) {
    return soma(a, b) / 2;
}

console.log(media(4, 6)); // 5

~~~

Nesse caso, a modularização permite uma legibilidade e manutenção muito melhor do código, de forma que qualquer necessidade de trabalho após a instalação do software se torna muito facilitada.

#### Cabeçalhos

Os tipos de cabeçalho em subprogramas de Javascript são formalmente definidos a partir de quatro estruturas básicas de declaração, conforme descritas abaixo:

• Declaração de Função

Na declaração de função, o cabeçalho tem como palavra-chave a expressão 'function', seguida do nome da função e, entre parênteses, a declaração de parâmetros.

~~~javascript
function nomeDaFuncao(param1, param2) {
    // corpo da função
}

~~~

• Expressão de função

Na expressão de função, há uma declaração da função por meio de um prefixo 'const' e o nome da função é opcional, embora seja obrigatório definir parâmetros para a função.

~~~javascript
const nomeDaFuncao = function(param1, param2) {
    // corpo da função
};

~~~

• Funções de seta

Nesse tipo de cabeçalho, a função é definida pelo prefixo 'const', seguida da lista de parâmetros seguida de uma seta que inicia o corpo da função.

~~~javascript
const nomeDaFuncao = (param1, param2) => {
    // corpo da função
};

~~~

• Funções anônimas

Há também o uso de funções anônimas (funções sem nome definido), as quais podem ser utilizadas como argumentos para outras funções do software.

~~~javascript
setTimeout(function() {
    console.log('Olá, mundo!');
}, 1000);

~~~

#### Declaração x Definição

Por se tratar de uma linguagem fracamente tipada, a declaração prévia de uma função sem a sua definição não é possível. Isto é, não há a possibilidade de declarar uma função sem definí-la de imediato. Isso será melhor traduzido nos exemplos a seguir:

~~~javascript

function Imprime(string); // declaração da função

function GoodbyeWorld(string){  //função qualquer definida que faz o uso da função declarada anteriormente
    if (string == "Goodbye"){
        console.log("Goodbye World);
    }
    else{
        Imprime(string);
    }
}

function Imprime(string){ 
    console.log(string); 
}

~~~

Nesse exemplo, a execução resultará em um erro por conta de não ter definido a função em sua declaração. Ou seja, em JS a declaração sem definição não é possível.

#### Função e procedimento

Em JavaScript não há a separação formal no que diz respeito entre procedimento e função, uma vez que são estruturalmente iguais. Entretanto, tal separação é possível de se realizar a nível conceitual. 

• Procedimento

É realizado com ou sem parâmetros, entretanto, ao contrário da função (que iremos ver no próximo item) não retorna valores específicos, sendo uma função que realiza uma atividade que modifica uma variável ou produz resultados de transferência de dados. 

~~~javascript

function imprimirSaudacao(nome) {
    console.log(`Olá, ${nome}!`);
}

imprimirSaudacao('Ana'); // Olá, Ana!

~~~

Esse exemplo mostra de forma clara de que forma um procedimento atua, uma vez que ele não é utilizado para retornar um valor ou um parâmetro específico, tendo como resultado da chamada a execução de uma atividade sem geração de valores dados como retorno da função.

• Função

A função, por outro lado, é caracterizada por se tratar de um subprograma com retorno de valores após a chamada da função. Isto é, sempre que a função for chamada em uma determinada parte do código, a ela será atribuída a geração de um valor que irá compor aquela parte do código afim de realizar uma determinada operação.

~~~javascript

function soma(a, b) {
    return a + b;
}

const resultado = soma(3, 4); // resultado será 7
console.log(resultado); // 7

~~~

Como pode se observar, a chamada da função resulta em um valor específico passado como parâmetro para a impressão.

#### Passagem de parâmetros

No que diz respeito a passagem de parâmetros nas funções, a linguagem de programação JavaScript oferece várias possibilidades. As definições e exemplos serão dados a seguir.

• Passagem por valor

Se tratando de tipos primitivos, JavaScript utiliza da passagem de parâmetros por valor para as funções. Isto é, para dados primitidos JS utiliza de forma nativa uma cópia da variável como valor para utilização do valor como parâmetro da função.

~~~javascript

function modificarValor(x) {
    x = 10;
}

let a = 5;
modificarValor(a);
console.log(a); // 5, 'a' não foi modificado

~~~

• Passagem por referência

Já a passagem por referência funciona de forma a alterar diretamente o valor do atributo por meio da passagem de referência do endereço de memória onde se localiza a variável/atributo, modificando-o diretamente, sem utilização de cópias. Em JavaScript, o uso de passagem por referência é utilizado, principalmente, com parâmetros objetos.

~~~javascript

function modificarObjeto(obj) {
    obj.propriedade = 'novo valor';
}

let meuObjeto = { propriedade: 'valor original' };
modificarObjeto(meuObjeto);
console.log(meuObjeto.propriedade); // 'novo valor'

~~~

#### Parâmetros posicionais e nomeados

JavaScript utiliza por natureza a passagem de parâmetros no modelo posicional, entretanto há maneiras de passar parâmetros para a função por meio de nomeação. Abaixo seguem dois exemplos, um com passagem posicional e outra com passagem por nomeação.

• Passagem posicional

A passagem posicional indica que os parâmetros devem ser passados e reconhecidos de acordo com a ordem em que a função é definida:

~~~javascript
function saudacao(nome, idade) {
    console.log(`Olá, ${nome}. Você tem ${idade} anos.`);
}

saudacao('Ana', 25); // Olá, Ana. Você tem 25 anos.
~~~

• Passagem nominal

A passagem por nome, ao contrário da passagem posicional, não depende da ordem em que é definido pois cada parâmetro é passado com acompanhamento do nome de seu atributo.

~~~javascript
function criarUsuario({ nome, idade, email }) {
    console.log(`Nome: ${nome}, Idade: ${idade}, Email: ${email}`);
}

criarUsuario({ nome: 'Ana', idade: 25, email: 'ana@example.com' });
// Nome: Ana, Idade: 25, Email: ana@example.com
~~~

#### Valores padrões de passagem

Algumas linguagens dispõe de uma necessidade de ter na passagem de parâmetros, uma mesma quantidade entre os parâmetros definidos na criação da função e os parâmetros declarados na chamada. Isto é, se uma função em sua definição tem quatro parâmetros definidos para passagem, a função deve ter obrigatoriamente quatro parâmetros passados na sua chamada em sua execução.
Nesse sentido JavaScript é uma linguagem que trata funções de forma flexível, o que significa que você pode passar qualquer número de argumentos para uma função, independentemente de quantos parâmetros formais a função tenha definido. Essa flexibilidade é permitida pela forma como a linguagem lida com os argumentos das funções. Esse funcionamento se dá pois cada função em JavaScript possui um objeto implícito chamado arguments. Esse objeto é uma coleção (semelhante a um array) de todos os argumentos passados para a função, independentemente de quantos parâmetros formais a função tenha declarado. Isso permite que você acesse todos os argumentos passados para a função, mesmo que eles não tenham correspondentes nos parâmetros formais.

~~~javascript
function exemplo() {
    console.log(arguments);
}

exemplo(1, 2, 3, 4); // [1, 2, 3, 4]
~~~

Além disso, mesmo que você passe mais argumentos do que os declarados formalmente, os argumentos adicionais podem ser acessados via o objeto arguments ou usando parâmetros rest. A função pode escolher ignorá-los, processá-los ou manipulá-los de acordo com a lógica implementada.

~~~javascript
function saudacao(nome) {
    console.log(`Olá, ${nome}`);
    console.log(`Argumentos adicionais:`);
    for (let i = 1; i < arguments.length; i++) {
        console.log(arguments[i]);
    }
}

saudacao('Ana', 'Como vai?', 'Tenha um bom dia!');
// Olá, Ana
// Argumentos adicionais:
// Como vai?
// Tenha um bom dia!
~~~

#### Subprogramas aninhados

Subprogramas aninhados, ou funções internas, são funções definidas dentro de outra função. Isto é, um subprograma que, definido dentro de um subprograma externo, é executado sempre que a função externa é chamada. Esse tipo de função pode ser uma alternativa viável em alguns casos, mas pode vir a ser problemática em desempenho e complexidade caso haja um uso absusivo, uma vez que a chamada da função externa cria novas instâncias internas. O maior benefício é o encapsulamento que algumas funções podem tomar, facilitando a legibilidade e funcionamento de alguns subprogramas.
Abaixo seguem alguns exemplos de funções aninhadas

• Exemplo 1
~~~javascript
function externa(nome) {
    // Variável no escopo da função externa
    let saudacao = 'Olá';

    // Função aninhada
    function interna() {
        // Acessa a variável 'saudacao' da função externa
        return `${saudacao}, ${nome}!`;
    }

    // Chama a função aninhada
    return interna();
}

console.log(externa('Ana')); // Olá, Ana!
~~~

• Exemplo 2
~~~javascript
function externa() {
    let x = 10;

    function interna() {
        console.log(x); // Acessa 'x' da função externa
    }

    interna();
}

externa(); // 10
~~~
