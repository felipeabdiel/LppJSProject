# JavaScript (JS)

## Diário de Bordo - File 06 (Subprogramas)

### Subprogramas

Os subprogramas são, em suma, espécies de softwares que realizam, inseridos um contexto maior, uma função específica dentro de um programa maior. Isto é, os subprogramas estão sempre anexados a um outro software afim de simplilficar a sua execução. 
Em geral, os subprogramas são utilizados para facilitar a leitura tornando o código mais legível, além de o modularizar afim de facilitar a sua manutenção e chamadas dentro do software. Além disso, há uma diminuição de custos relativo ao tempo de codificação e a memória também é economizada na execução do código.

#### Padrões gerais de subprogramas utilizados em JavaScript

Em Javascript é possível utilizar de subprogramas de diversas formas. Entre elas podemos listar algumas mais gerais, como por exemplo

• Declaração de função:

´´´(javascript)

function HelloWorld(){
    return ("Hello World");
}

´´´
Essa função trata-se de um subprograma que faz a simplificação de um comando que seria mais longo. Ou seja, a chamada dessa função simplifica um procedimento que levaria mais tempo para ser executado.

• Modularização do código

´´´(javascript)

function soma(a, b) {
    return a + b;
}

function media(a, b) {
    return soma(a, b) / 2;
}

console.log(media(4, 6)); // 5

´´´
Nesse caso, a modularização permite uma legibilidade e manutenção muito melhor do código, de forma que qualquer necessidade de trabalho após a instalação do software se torna muito facilitada.

#### Cabeçalhos

Os tipos de cabeçalho em subprogramas de Javascript são formalmente definidos a partir de quatro estruturas básicas de declaração, conforme descritas abaixo:

• Declaração de Função

Na declaração de função, o cabeçalho tem como palavra-chave a expressão 'function', seguida do nome da função e, entre parênteses, a declaração de parâmetros.

´´´(javascript)
function nomeDaFuncao(param1, param2) {
    // corpo da função
}

´´´

• Expressão de função

Na expressão de função, há uma declaração da função por meio de um prefixo 'const' e o nome da função é opcional, embora seja obrigatório definir parâmetros para a função.

´´´(javascript)
const nomeDaFuncao = function(param1, param2) {
    // corpo da função
};

´´´

• Funções de seta 

Nesse tipo de cabeçalho, a função é definida pelo prefixo 'const', seguida da lista de parâmetros seguida de uma seta que inicia o corpo da função.

´´´(javascript)
const nomeDaFuncao = (param1, param2) => {
    // corpo da função
};

´´´

• Funções anônimas

Há também o uso de funções anônimas (funções sem nome definido), as quais podem ser utilizadas como argumentos para outras funções do software.

´´´(javascript)
setTimeout(function() {
    console.log('Olá, mundo!');
}, 1000);

´´´

#### Declaração x Definição

Por se tratar de uma linguagem fracamente tipada