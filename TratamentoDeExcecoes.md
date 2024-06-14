# JavaScript (JS)

## Diário de Bordo - File 07 (Tratamento de Exceções)

### Tratamento de exceções

O tratamento de exceções é um modo de prevenir e tratar eventos inesperados no software, de forma que haja menores chances do programa parar ou fechar enquanto é executado. Em linguagens mais antigas o tratamento de exceção era feito, em muitas situações, de forma completamente manual, entretanto, linguagens mais atuais dispõe de ferramentas específicas para o tratamento de exceções em sua codificação.

#### Estrutura básica

A estrutura básica utilizada na maioria dos códigos atuais, bem como em JavaScript é o funcionamento dos blocos 'try', 'catch' e 'finally'. O bloco try é aquele responsável por executar uma rotina no software potencialmente passível de eventos inesperados. Dessa forma, ao ser executado, caso um evento inesperado aconteça, ele passa pelo bloco catch, de forma que esse bloco realiza a execução do chamado tratamento de exceção, realizando alguma função que possibilita a continuação de execução do código de acordo com a exceção verificada no mesmo bloco. Por fim, o bloco finally se trata de uma rotina que deve ser executada ao fim do código sob qualquer situação, isto é, independente de ser ou não encontrada uma exceção na execução do software.

~~~javascript
try {
    // Tentando dividir dois números
    let resultado = 10 / 0;
    if (!isFinite(resultado)) {
        throw new Error('Divisão por zero não é permitida.');
    }
    console.log('Resultado:', resultado);
} catch (erro) {
    // Lidando com o erro
    console.error('Ocorreu um erro:', erro.message);
} finally {
    // Limpando depois
    console.log('Tentativa de divisão concluída.');
}
~~~

O exemplo acima mostra, de forma prática o funcionamento simples de um código com tratamento de exceção implantado.

#### Tratadores de exceção

O tratamento de exceções em JavaScript é essencial para garantir que seu código lide com erros de maneira controlada e elegante. As exceções são situações inesperadas que ocorrem durante a execução do código, como a falta de uma variável necessária ou a tentativa de dividir por zero. A estrutura básica do tratamento de exceções envolve o uso das palavras-chave try, catch, finally e throw.

O bloco try contém o código que pode gerar uma exceção. Se o código no bloco try executa sem erros, o fluxo do programa continua normalmente, ignorando o bloco catch. Se uma exceção ocorre dentro do bloco try, o controle é transferido para o bloco catch, onde a exceção é tratada. O bloco catch captura o erro e permite que você tome uma ação apropriada, como registrar o erro ou mostrar uma mensagem ao usuário. O bloco catch recebe um parâmetro que é a exceção lançada.

O bloco finally é opcional e contém o código que será executado independentemente de uma exceção ter sido lançada ou não. Ele é usado para executar ações de limpeza, como fechar arquivos ou liberar recursos. O bloco finally garante que o código seja executado após o bloco try e/ou catch.

A palavra-chave throw permite que você lance suas próprias exceções. Você pode lançar qualquer objeto, mas é comum lançar instâncias de Error. A utilização de throw interrompe o fluxo normal do código e transfere o controle para o bloco catch associado, permitindo criar e lançar exceções personalizadas quando detecta situações específicas no seu código que devem ser tratadas como erros.

JavaScript possui vários tipos de objetos de erro, cada um representando uma categoria específica de problemas. Os tipos mais comuns são Error, que é o tipo genérico de erro; SyntaxError, que ocorre quando há um erro de sintaxe no código; ReferenceError, que é lançado quando se tenta acessar uma variável que não está definida; TypeError, que ocorre quando um valor não é do tipo esperado; RangeError, que é lançado quando um valor não está dentro do intervalo ou conjunto de valores permitidos; URIError, que ocorre quando há um erro nas funções de URI, como decodeURIComponent; EvalError, que é lançado quando há um erro no uso da função eval (embora seja raro em versões modernas de JavaScript); e AggregateError, que representa múltiplos erros agrupados e é geralmente usado com Promise.any().

Compreender e utilizar essas ferramentas eficazmente ajuda a criar código mais confiável e fácil de manter. O tratamento de exceções em JavaScript permite que você lide com erros de forma controlada, fornecendo feedback útil para depuração e garantindo que recursos sejam liberados adequadamente. Essa prática é vital para construir aplicativos robustos e resilientes, que podem continuar funcionando mesmo quando ocorrem problemas inesperados.

#### Tipo de exceção

Em JavaScript, exceções são representadas como objetos. Cada tipo de exceção é uma instância de uma classe específica que herda da classe básica Error. Essas classes incluem Error, SyntaxError, ReferenceError, TypeError, RangeError, URIError, EvalError, e AggregateError.

Quando uma exceção é lançada, um objeto é criado a partir de uma dessas classes e contém propriedades que descrevem o erro, como name (nome do tipo de erro) e message (mensagem descritiva do erro). Você também pode adicionar suas próprias propriedades personalizadas a esses objetos de erro.

• Criação e uso de erros

~~~javascript
try {
    throw new TypeError('Este é um erro de tipo');
} catch (erro) {
    console.log(erro.name); // Saída: TypeError
    console.log(erro.message); // Saída: Este é um erro de tipo
    console.log(erro.stack); // Saída: stack trace detalhando onde o erro ocorreu
}
~~~

• Herança de erros

~~~javascript
class MeuErroPersonalizado extends Error {
    constructor(mensagem) {
        super(mensagem);
        this.name = 'MeuErroPersonalizado';
    }
}

try {
    throw new MeuErroPersonalizado('Algo deu muito errado!');
} catch (erro) {
    console.log(erro.name); // Saída: MeuErroPersonalizado
    console.log(erro.message); // Saída: Algo deu muito errado!
}
~~~