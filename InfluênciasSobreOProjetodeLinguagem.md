# JavaScript (JS)
## Diário de Bordo - File 02 (Influências sobre o projeto da linguagem)
### Tipo da linguagem

No que diz respeito aos tipos de linguagem, JavaScript é uma linguagem imperativa com foco em script. Para comprovação dos fatos citados, vamos estabelecer alguns pontos importantes sobre o paradigma imperativo e paradigma de script da linguagem:

#### Paradigma Imperativo
No campo do paradigma imperativo JS desempenha algumas características que é melhor descrita abaixo.

1. Estado e Mutabilidade: No paradigma imperativo, o foco está na mudança de estado do programa ao longo do tempo. Em JavaScript, isso é frequentemente realizado por meio da manipulação direta de variáveis.

2. Instruções e Estruturas de Controle: Utiliza instruções como if, else, for, while para controlar o fluxo de execução do programa.

3. Procedimentos e Funções: A linguagem permite a definição de procedimentos (bloco de código que realiza uma tarefa específica) e funções (procedimentos que podem retornar um valor).

Abaixo segue um exemplo de código de JS que utiliza do paradigma imperativo.

~~~javascript

let saldo = 1000;

if (saldo > 0) {
    saldo -= 100;  // Reduz o saldo em 100
} else {
    console.log("Saldo insuficiente");
}

function depositar(valor) {
    saldo += valor;  // Adiciona o valor ao saldo
}

~~~

#### Paradigma de script

No que diz respeito ao paradigma de script, seguem abaixo as descrições de alguns parâmetros importantes do paradigma no campo da linguagem supracitada, seguido de um exemplo de código utilizando do paradigma de script que a linguagem oferece.

1. Interpretação e Execução Direta: No paradigma de script, o código é frequentemente interpretado e executado diretamente, sem a necessidade de compilação.

2. Automatização e Automação: Focado em automatizar tarefas, manipular dados e interagir com sistemas externos (como navegadores, APIs, sistemas de arquivos).

3. Flexibilidade e Dinamismo: Linguagens de script são geralmente mais flexíveis e dinâmicas, permitindo alterações em tempo de execução e uma abordagem mais interativa.

~~~javascript

// Script para validar um formulário e enviar dados via AJAX

document.getElementById("formulario").addEventListener("submit", function(event) {
    event.preventDefault();  // Impede o envio padrão do formulário

    let nome = document.getElementById("nome").value;
    let email = document.getElementById("email").value;

    if (nome && email) {
        // Simula envio dos dados para um servidor via AJAX
        fetch("https://api.exemplo.com/enviar", {
            method: "POST",
            body: JSON.stringify({ nome, email }),
            headers: {
                "Content-Type": "application/json"
            }
        })
        .then(response => response.json())
        .then(data => {
            if (data.sucesso) {
                alert("Dados enviados com sucesso!");
            } else {
                alert("Erro ao enviar dados.");
            }
        })
        .catch(error => {
            console.error("Erro:", error);
        });
    } else {
        alert("Por favor, preencha todos os campos.");
    }
});

~~~

### Métodos de implementação da linguagem

Sobre o método de implementação da linguagem, JS é baseada em execução por interpretador. Isso significa que, no momento em que o código é executado, um segundo software realiza a leitura do código linha por linha enquanto o executa.
Nesse sentido, a interpretação fornece alguns pontos fortes e fracos.

• Vantagens da Interpretação
1. Portabilidade: Código interpretado é geralmente mais portátil, pois depende do interpretador em vez do sistema operacional ou arquitetura de hardware específica.

2. Desenvolvimento Rápido: A interpretação permite um ciclo de desenvolvimento mais rápido, pois não é necessário esperar pelo processo de compilação antes de testar as mudanças.

3. Flexibilidade: Linguagens interpretadas são geralmente mais flexíveis e dinâmicas, permitindo a execução de código em tempo real e a introspecção de objetos em tempo de execução.

• Desvantagens da Interpretação
1. Desempenho: Em geral, código interpretado tende a ser mais lento que código compilado, especialmente para operações intensivas em CPU, devido à necessidade de interpretar o código em tempo real.

2. Segurança: A natureza dinâmica e flexível da interpretação pode introduzir potenciais vulnerabilidades de segurança se não forem tomadas precauções adequadas.

#### Interpretadores de JS

Sobre os interpretadores de JavaScript, por ser uma linguagem com uso muito extenso, muitos softwares fornecem interpretadores nativos, como é o caso de navegadores como o Google Chrome, que possui o interpretador V8 e o SpiderMonkey no Mozilla Firefox.
Outro ponto importante é que a linguagem oferece suporte facilitado para a interpretação *Just-In-Time* (JIT), que é basicamente uma funcionalidade que compila partes do código em código de máquina para melhora do desempenho de execução, uma vez que códigos de máquina são lidos com uma velocidade muito maior.
Além disso, como no caso do ByteCode muito comum na linguagem Java, a linguagem JS pode ser executada por meio de um Bytecode utilizando o real time do Node.js.

### Conclusão

JavaScript é uma linguagem de programação interpretada, o que significa que o código JavaScript é executado diretamente pelo interpretador, linha por linha, sem uma etapa separada de compilação. Embora seja interpretada, a execução do JavaScript é otimizada através de técnicas como JIT compilation, proporcionando um equilíbrio entre flexibilidade de desenvolvimento e desempenho de execução.
