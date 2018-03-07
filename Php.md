# PHP Style Guide

Este é o guia de desenvolvimento para classes de **PHP** do **SBS**.

 1. **Visão Geral**
	 - **NÃO** deve existir um limite máximo do tamanho da linha, contudo é **RECOMENDÁVEL** utilizar no 			entre 80 a 120 caracteres.
	- É **OBRIGATÓRIO** o espaçamento de uma linha em branco depois no `namespace` e do `use` 
	 - Em todas as classes e métodos  é **OBRIGATÓRIO** que as chaves estejam em uma nova linha e a outra chave que fecha o escopo esteja na ultima linha da classe/método.
	 - A **VISIBILIDADE**  deve ser declarada em todos os métodos e propriedades; abstract e final precisam ser declaradas antes da visibilidade, somente static pode ser declarada depois.
	 - As [Palavras Chaves](http://php.net/manual/en/reserved.keywords.php) tem por **OBRIGAÇÃO** ter um espaço depois das mesmas. Métodos e Funções chamadas **NÃO**.
	 - A chave de abertura de estruturas **DEVEM** permanecer na mesma linha, e seu fechamento em uma nova linha.
	 - Os parênteses das estruturas de controle **NÂO DEVEM** possui um espaço depois dos mesmos.
```
<?php
namespace Vendor\Package;

use FooInterface;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class Foo extends Bar implements FooInterface
{
    public function sampleMethod($a, $b = null)
    {
        if ($a === $b) {
            bar();
        } elseif ($a > $b) {
            $foo->bar($arg1);
        } else {
            BazClass::bar($arg2, $arg3);
        }
    }

    final public static function bar()
    {
        // method body
    }
```
 2.  **Geral**
	 - Arquivos
		 - Em todos os arquivos **DEVEM** possui uma linha em vazia.
		- O fechamento `?>` **DEVE** ser omitido de arquivos que possuem somente PHP.
	 - Linhas
		- **PODEM** ser adicionadas linhas em branco para que com o objetivo de melhorar a legibilidade e 	para indicar bloco de códigos relacionados.
		- **NÃO DEVE** haver mais de uma declaração por linha.
	- adasasd
 4.  **Modelos**
 5. **Controladores**
 6. 

