# JavaScript (JS)
## Diário de Bordo - File 04 (Variáveis - Tempo de Vida e Escopo)
### Tempo de vida das variáveis

#### Variáveis estáticas (globais)
Se tratando do tempo de vida das variáveis dentro da linguagem JavaScript, as variáveis globais são aquelas que são acessíveis a qualquer parte do código e são declarados fora da função de execução. Nesse sentido, há 3 formas de declarar variáveis globais em JS, conforme visualizado nos exemplos a seguir.

• Declaração explícita no escopo global
Esse modo de declaração é o mais simples. Consiste em declarar explicitamente a variável no escopo global do código.
~~~javascript
var globalVar = "Sou global!";
~~~

• Omissão da palavra-chave de declaração
Embora não recomendado por dificultar a visualização de erros, esse modo de declaração é possível por meio de uma função de criação de variável, sem a utilização de palavras-chave para declarar.
~~~javascript
function criarGlobal() {
    globalSemVar = "Também sou global!";
}
criarGlobal();
~~~

• Propriedade do objeto global
Há nos navegadores e ambiente Node.js um objeto global, sendo window e global respectivamente. Ou seja, caso adicionado a variável aos objetos globais, é possível criar uma variável global.
~~~javascript
window.outraGlobal = "Acesso global via objeto window.";
~~~

Vale salientar que o uso de variáveis globais é desencorajado uma vez que torna o código muito estático e dificulta o dinamismo da aplicação, uma vez que modificações são mais difíceis de serem realizadas posteriormente.

#### Variáveis de pilha (stack)
No campo de variáveis de pilha em JS, a linguagem possui mecanismos para armazenamento de variáveis locais dentro da função participante da pilha. A cada função chamada, um novo stack frame é criado com as informações da função.
Ou seja, quando a função é executada ela faz a utilização das informações e, assim que finalizada, seus dados são desempilhados e as variáveis são descartadas. Abaixo segue um exemplo do funcionamento com citação de código.

~~~javascript
function exemploDePilha() {
    var local = "Estou na pilha";  // Variável local
    console.log(local);  // Acessa a variável da pilha
}

exemploDePilha();  // Chama a função, cria um novo quadro de pilha
// Após a execução, o quadro de pilha é removido e `local` não existe mais
~~~

#### Variáveis de heap implícito
JavaScript abstrai muitos detalhes de gerenciamento de memória para simplificar o desenvolvimento. Por exemplo, quando cria-se um objeto, um array, uma função ou um tipo de dado complexo, o JavaScript automaticamente aloca espaço para esses dados no heap. Essa é uma forma de "heap implícito", onde o desenvolvedor não precisa se preocupar com a alocação do heap.

1. Simplicidade: Os desenvolvedores podem se concentrar na lógica do programa sem se preocupar com detalhes de alocação e liberação de memória.
2. Segurança: Reduz o risco de bugs relacionados à memória, como vazamentos de memória e acessos a memória não inicializada, que são comuns em linguagens que requerem gerenciamento de memória manual.
3. Performance: Apesar de oferecer muitas vantagens, a gestão automática de memória pode levar a um consumo de recursos inconsistente, onde a execução do coletor de lixo pode afetar o desempenho do programa em momentos inoportunos.

Portanto, embora o termo "variáveis de heap implícito" não seja um termo técnico específico em JavaScript, o conceito subjacente está relacionado à forma como a linguagem gerencia automaticamente a memória para objetos e estruturas de dados complexas. Isso é feito de forma transparente para o desenvolvedor, o que simplifica a escrita de código mas também implica uma compreensão básica de como a gestão de memória funciona para otimizar o desempenho e gerenciar recursos eficientemente.

#### Variáveis de heap explícito
Em JavaScript, a distinção entre memória stack (pilha) e heap não é algo que os desenvolvedores geralmente manipulam diretamente, uma vez que a linguagem abstrai esses detalhes de gerenciamento de memória. No entanto, para entender como a memória é alocada e gerenciada em JavaScript, é útil discutir o conceito de variáveis armazenadas no heap, que são tipicamente objetos e outras estruturas de dados mais complexas.
O heap é uma área de memória usada para armazenar objetos e outras estruturas de dados que exigem um ciclo de vida mais flexível do que aquele permitido pela memória de pilha, que é limitada ao escopo de execução de funções. Diferente da pilha, a memória do heap não é gerenciada com base em uma estrutura LIFO (Last In, First Out - Último a Entrar, Primeiro a Sair).
Em JavaScript, quando cria-se um objeto, um array, ou qualquer outra estrutura complexa, essa estrutura é armazenada no heap. Por exemplo:

~~~javascript
let objeto = { nome: "ChatGPT", tipo: "Modelo de IA" };
let numeros = [1, 2, 3, 4, 5];
~~~

No que diz respeito ao gerenciamento de memória o JavaScript usa um coletor de lixo para gerenciar a memória no heap. O coletor de lixo monitora os objetos armazenados no heap e recupera automaticamente a memória ocupada por objetos que não são mais acessíveis ou necessários no programa. Isso é feito por meio de técnicas como contagem de referências ou algoritmos de rastreamento de alcance.
De forma direta, o uso do heap é aplicado quando é necessário utilizar de um maior dinamismo para manejo de variáveis e objetos. Isso é facilmente visualizado no exemplo a seguir.

~~~javascript
function manipulaDados() {
    let dadosComplexos = new Array(1000).fill({ mensagem: "Olá, mundo!" });
    return dadosComplexos;
}

let dados = manipulaDados();
~~~

### Escopo das variáveis
#### Escopo estático: Blocos

Sobre o escopo estático em blocos, a linguagem oferece um suporte à alocação de variáveis em escopo de blocos delimitados entre chaves [] declarados por meio das palavras-chave 'let' e 'const'. A diferença singular entre elas é que 'let' possibilita reatribuição durante a execução do código, enquanto 'const' trata a variável como uma constante imutável dentro da execução.
Segue abaixo alguns exemplos sobre os parâmetros citados.

• Escopo de bloco com 'let'
~~~javascript
if (true) {
    let escopoLet = "Escopo com let";
    console.log(escopoLet);  // "Escopo com let" - acessa a variável dentro do bloco
}

console.log(escopoLet);  // Erro: escopoLet is not defined
~~~

• Escopo de bloco com 'const'
~~~javascript
if (true) {
    const escopoConst = "Escopo com const";
    console.log(escopoConst);  // "Escopo com const" - acessa a variável dentro do bloco
}

console.log(escopoConst);  // Erro: escopoConst is not defined
~~~

• Reatribuição com 'let' 
~~~javascript
let reatribuicao = "Inicial";

if (true) {
    reatribuicao = "Reatribuído";
    console.log(reatribuicao);  // "Reatribuído" - reatribui valor à variável
}

console.log(reatribuicao);  // "Reatribuído" - variável foi reatribuída
~~~

Isso conclui que o escopo estático em blocos com let e const oferece uma maneira mais previsível e controlada de gerenciar escopo em JavaScript. Ele ajuda a evitar bugs e comportamentos inesperados, pois as variáveis são limitadas ao bloco em que foram declaradas, tornando o código mais legível e fácil de manter. Ao entender e aplicar corretamente o escopo de blocos, você cria um código mais robusto e menos propenso a erros.

#### Escopo estático: Subprogramas

No que diz respeito ao escopo estático baseado em subprogramas, é importante entender que refere-se à capacidade das funções do código acessarem variáveis de outras funções externas à ela. Parâmetros que dispõe dessa funcionalidade estão melhores descritos abaixo.

1. Escopo Léxico: As funções em JavaScript têm acesso ao escopo léxico em que foram definidas. Isso significa que elas podem acessar variáveis de funções "pai" mesmo após terem sido retornadas ou passadas como argumentos para outras funções.

2. Closure: O conceito de closure (fechamento) é central para entender o escopo léxico baseado em subprogramas. Uma closure ocorre quando uma função "captura" variáveis de seu escopo externo, permitindo que a função acesse essas variáveis mesmo depois de ter saído do escopo onde foram definidas.

Um exemplo claro dessa aplicação segue na citação de código abaixo:

~~~javascript
function externa() {
    let variavelExterna = "Eu sou externa";

    function interna() {
        console.log(variavelExterna);
    }

    return interna;
}

let minhaFuncao = externa();
minhaFuncao();  // "Eu sou externa" - acessa a variável da função externa
~~~

Em resumo, o escopo e tempo de vida de variáveis em JavaScript são regidos por regras bem definidas que determinam a visibilidade, acessibilidade e duração das variáveis no código. O conhecimento desses conceitos é essencial para aproveitar ao máximo as capacidades da linguagem e escrever código mais eficiente, modular e fácil de manter.


