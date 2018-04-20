# Melhoria-PHP

## Desafio 1 

Ao conversarmos, percebemos que ao trabalhar com a linguagem PHP, algumas limitações de legibilidade ficam bem claras; já existem várias ideias novas sendo trabalhadas pelos próprios usuários de PHP. Algumas dessas ideias remetem à legibilidade e, consequentemente, à confiabilidade da linguagem, já que existem certos problemas ao programar com PHP que vemos que poderia ser melhorado, como a ideia do 'type hint' que foi recentemente implementado, até a imutabilidade de objetos e propriedades. Vamos assim explorar estas falhas e construir um projeto de otimização da linguagem.

## Desafio 2

1. **Domínio da linguagem:**

	PHP se define como uma linguagem imperativa baseada em execuções por scripting, ou seja, programas escritos para uma execução automatizada, que será interpretada por esse sistema. Diz-se imperativa por ser formada por comandos e instruções diretas, o que torna a linguagem bem pragmática.

2. **Aspectos importantes para a linguagem e possiveis Trade-Offs:**

	A linguagem, que hoje é uma das mais populares pra web, considera e muito seu código simples e sua geração de resultado dinâmico em HTML, o que traz uma facilidade maior ao ter noção do resultado de sua programação. Se é considerada também sua velocidade e portabilidade.

3. **Qual a influencia do projeto da linguaguem:**

	PHP é uma linguagem que foi projetada inicialmente para ser um script do lado do servidor. Foi escrita majoritariamente em C. Mas suas influências são: Perl, C, C++, Java, Tcl  

4. **Metodo de implementacao da linguagem:**

	Em atualizacoes recentes o PHP passou de um linguagem interpretada, para uma execucao híbrido, ou seja ele compila o código para linguagem de maquina atravez de um interpretador.

5. **Ambiente de programacao:**

	O ambiente de programacao do php é composto de um servidor, interpretador da linguagem e um banco de dados (opcional). A instalacao desse ambiente pode ser feita manualmente, instalando componente por componente, ou atravez de um instalador que faz todo esse processo.

## Desafio 3

1. **2 exemplos de código que reflitam facilidade de escrita e legibilidade:**

```php
<?php
$var1 = 'var2';      //Estamos atribuindo o 'var2' a variavel $var1
${$var1} = 1234;     //ele atribui o valor 1234 a variavel $var2
echo $var2;          //mostra na tela o conteudo da variavel $var2
                     //Tambem refletimos a questao da facilidade de escrita, sendo
                     //que precisamos colocar "$" para declarar e chamar qualquer variavel
?>
```

2. **Elaborar a representação em BNF ou EBFN de uma estrutura da linguagem:**

```
class_declaration_statement = class_entry_type T_STRING
    [extends_from] [implements_list] "{" {class_statement} "}"
    | "interface" T_STRING [interface_extends_list] "{" {class_statement} "}" ;

class_entry_type = [ "abstract" | "final" ] "class" ;
``` 

3. **Identificar como é o gerenciamento de memoria da linguagem e descreva as vantagens e desvantagens:**

	Como o PHP é uma linguagem de script e é compilada em tempo de execução, pode acontecer de o compilador não identificar possiveis problemas de memória, portanto o PHP possui um Garbage Collector. O PHP gerencia as referências de todas as declarações, garantindo que só existam as necessárias e removendo o que não é usado. A vantagem ocorre em scripts de longa duração e uso excessivo de memória, onde o GC vai remover o 'lixo' da memória. A desvantagem ocorre em scripts pequenos ou de baixa duração, causando um overhead na execução, prejudicando um pouco. (mas conforme a documentação da linguagem, o overhead é bem baixo).

## Desafio 4

1. Avaliem 5 regras semânticas da linguagem com base critérios de avaliação das linguagens:

```php
$a = 1               //Variavel a recebe valor declarado
```

```php
$c = $a * $b;        //Variavel c recebe multiplicação entre a variavel a e b
```

```php
if($idade < 18) {                        //Se a condição entre parenteses for verdadeira 
    echo 'Você não pode entrar aqui!';   //executa o trecho de código entre as chaves
} else {                                 //Se a condição não for verdadeira então
    echo 'Seja bem – vindo';             //executa este trecho de código entre as chaves
} 
```

```php                         
while($num < 10 ) {               //Enquanto a condição for verdadeira
    echo $num++;                  //executa o trecho de código entre as chaves
  }
```

```php 
for($a = 1; $a <= 10; $a++){         //Inicializa a variavel de controle, executa o laço de repetição enquanto a condição for 
  $cubo = $a * $a * $a;              //verdadeira, manipula a variavel de controle e executa o trecho de código entre chaves
  echo "O cubo de $a é $cubo<br />";
}
```

2. **Avaliem os tipos de dados da linguagem:**

	O PHP é muito parecido com as outras linguagens neste aspecto. Temos os seguintes tipos de dados: numerico, booleano, string, array, objeto, recurso, misto, callback e null. A maioria das linguagens tem esses tipos de dados, porém um ponto em que o PHP é diferente, é a questão de que não precisa declara qual o tipo da variavel, você simplesmente declara uma variavel e atribui a ela o valor que desejar.

3. **Avaliem como é a vinculação do tipos de dados da linguagem:**

	A vinculação dos tipos de dados no PHP é dinâmica, ou seja, ela é somente verificada em tempo de execução, o que torna a execução mais lenta, mas também promove uma flexibilidade maior ao programar. Assim, na linguagem PHP não se é necessário definir o tipo a ser declarado, mas sim somente atribuí-lo um nome e um valor.
	Os tipos de dados dinâmicos são um dos motivos pelos quais o PHP tem sua execução mais lenta, porém é  compensado com a simplicidade de código e fácil visualização do resultado do mesmo por uma aba de um browser qualquer.


4. **Avaliem como é a compatibilidade e conversão dos tipos de dados da linguagem:**

	No PHP é possivel converter os dados de um tipo para outro. Porém existem algumas regras e restricões, por exemplo conversão de string para inteiro, só será convertido caso o número esteja na primeira possicão da string, caso contrario ele converte para 0. Na maioria dos casos, ocorre a conversão automatica de tipos de dados, como por exemplo, caso você tenha uma variavel do tipo int e outra float, quando for feita uma adicão entre elas o resultado será do tipo float.

## Desafio 5

1. **Identifique as categorias de controle de fluxo utilizados na linguagem e apresente exemplos.**

Segundo a documentação oficial do [PHP](https://secure.php.net/manual/en/language.control-structures.php), existem estas estruturas de controle na linguagem:

#### Seleção

* if
* else
* elseif/else if
* goto
* switch

```php
<?php
// if/else
if ($a > $b) {
  echo "a is greater than b";
} else {
  echo "a is NOT greater than b";
}

// goto
goto a;
echo 'Foo';
 
a:
echo 'Bar';
```

#### Iteração

* while
* do-while
* for
* foreach
* break
* continue

```php
<?php
// while
while ($i <= 10) {
    echo $i++;  
}
```

#### Abstração procedural

* require
* include
* require_once
* include_once
* return

```php
<?php
require('somefile.php');
?>
```

#### Manipulação/tratamento de exceção e especulação, 

* try/catch (não está na documentação, mas possui na linguagem).

Exemplos:

```php
<?php
try {
    echo inverse(5) . "\n";
    echo inverse(0) . "\n";
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
}
```

2. **Identifique quais as formas de abstração de controle e abstração de dados utilizados na linguagem e apresente exemplos.**

Funções, Classes, Herança, Polimorfismo, Encapsulamento (público, privado, protegido e namespaces), Classes Abstratas.

Exemplos:

*Utilização de namespaces (encapsulamento)*

arquivo1:
```php
<?php
namespace foo;
  class Cat {
    static function says() {echo 'meoow';}
  }
 ?>
```

arquivo2:
```php
<?php
namespace bar;
  class Dog {
    static function says() {echo 'ruff';}
  }
?>
```

arquivo3:
```php
<?php
namespace animate;
  class Animal {
    static function breathes() {echo 'air';}
}
?>
```

arquivo4:
```php
<?php
namespace fub;
  include 'file1.php';
  include 'file2.php';
  include 'file3.php';
  use foo as feline;
  use bar as canine;
  use animate;
  echo \feline\Cat::says(), "<br />\n";
  echo \canine\Dog::says(), "<br />\n";
  echo \animate\Animal::breathes(), "<br />\n";
?>
```

*Utilização de array_map (função que abstrai uma iteração)*
```php
<?php
function cube($n)
{
    return($n * $n * $n);
}

$a = array(1, 2, 3, 4, 5);
$b = array_map("cube", $a);
print_r($b);
?>
```

3. **Identifique qual o paradigma da linguagem.**

O PHP é considerado como procedural, funcional e orientado a objetos. O início do suporte à orientação a objetos foi na versão 5.0, em 2004, e desde então vem evoluindo.
