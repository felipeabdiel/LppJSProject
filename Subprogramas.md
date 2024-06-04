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

Se tratando de tipos primitivos, JavaScript utiliza da passagem de parâmetros por valor para as funções.