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


