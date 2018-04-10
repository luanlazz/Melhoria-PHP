# Melhoria-PHP

## Desafio 1 

##### Ao conversarmos, percebemos que ao trabalhar com a linguagem PHP, algumas limitações de legibilidade ficam bem claras; já existem várias ideias novas sendo trabalhadas pelos próprios usuários de PHP. Algumas dessas ideias remetem à legibilidade e, consequentemente, à confiabilidade da linguagem, já que existem certos problemas ao programar com PHP que vemos que poderia ser melhorado, como a ideia do 'type hint' que foi recentemente implementado, até a imutabilidade de objetos e propriedades. Vamos assim explorar estas falhas e construir um projeto de otimização da linguagem.

## Desafio 2

### A) Domínio da linguagem:
##### PHP se define como uma linguagem imperativa baseada em execuções por scripting, ou seja, programas escritos para uma execução automatizada, que será interpretada por esse sistema. Diz-se imperativa por ser formada por comandos e instruções diretas, o que torna a linguagem bem pragmática.

### B) Aspectos importantes para a linguagem e possiveis Trade-Offs:
##### A linguagem, que hoje é uma das mais populares pra web, considera e muito seu código simples e sua geração de resultado dinâmico em HTML, o que traz uma facilidade maior ao ter noção do resultado de sua programação. Se é considerada também sua velocidade e portabilidade.

### C) Qual a influencia do projeto da linguaguem: 
##### PHP é uma linguagem que foi projetada inicialmente para ser um script do lado do servidor. Foi escrita majoritariamente em C. Mas suas influências são: Perl, C, C++, Java, Tcl  

### D) Metodo de implementacao da linguagem:
##### Em atualizacoes recentes o PHP passou de um linguagem interpretada, para uma execucao híbrido, ou seja ele compila o código para linguagem de maquina atravez de um interpretador.

### E) Ambiente de programacao:
##### O ambiente de programacao do php é composto de um servidor, interpretador da linguagem e um banco de dados (opcional). A instalacao desse ambiente pode ser feita manualmente, instalando componente por componente, ou atravez de um instalador que faz todo esse processo.

## Desafio 3

### A) 2 exemplos de código que reflitam facilidade de escrita e legibilidade:

```php
<?php
$var1 = 'var2';      //Estamos atribuindo o 'var2' a variavel $var1
${$var1} = 1234;     //ele atribui o valor 1234 a variavel $var2
echo $var2;          //mostra na tela o conteudo da variavel $var2
?>                   //Tambem refletimos a questao da facilidade de escrita, sendo
                     //que precisamos colocar "$" para declarar e chamar qualquer variavel
```

### B) Elaborar a representação em BNF ou EBFN de uma estrutura da linguagem:

```
class_declaration_statement = class_entry_type T_STRING
    [extends_from] [implements_list] "{" {class_statement} "}"
    | "interface" T_STRING [interface_extends_list] "{" {class_statement} "}" ;

class_entry_type = [ "abstract" | "final" ] "class" ;
``` 

### C) Identificar como é o gerenciamento de memoria da linguagem e descreva as vantagens e desvantagens:
##### Como o PHP é uma linguagem de script e é compilada em tempo de execução, pode acontecer de o compilador não identificar possiveis problemas de memória, portanto o PHP possui um Garbage Collector. O PHP gerencia as referências de todas as declarações, garantindo que só existam as necessárias e removendo o que não é usado. A vantagem ocorre em scripts de longa duração e uso excessivo de memória, onde o GC vai remover o 'lixo' da memória. A desvantagem ocorre em scripts pequenos ou de baixa duração, causando um overhead na execução, prejudicando um pouco. (mas conforme a documentação da linguagem, o overhead é bem baixo).

## Desafio 4

### A) Avaliem 5 regras semânticas da linguagem com base critérios de avaliação das linguagens:

### B) Avaliem os tipos de dados da linguagem:

### C) Avaliem como é a vinculação do tipos de dados da linguagem:

### D) Avaliem como é a compatibilidade e conversão dos tipos de dados da linguagem:
