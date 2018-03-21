# PHP Style Guide

Este é o guia de desenvolvimento para classes de **PHP** do **SBS**. Em caso de dúvidas ou regra que não conste neste documento deve-se encontrar na [PSR-2](https://www.php-fig.org/psr/psr-2/), referência para este documento.

 1. **Visão Geral**
	 - **NÃO** deve existir um limite máximo do tamanho da linha, contudo é **RECOMENDÁVEL** utilizar no 			entre 80 a 120 caracteres.
	- É **OBRIGATÓRIO** o espaçamento de uma linha em branco depois no `namespace` e do `use` 
	 - Em todas as classes e métodos  é **OBRIGATÓRIO** que as chaves estejam em uma nova linha e a outra chave que fecha o escopo esteja na ultima linha da classe/método.
	 - A **VISIBILIDADE**  deve ser declarada em todos os métodos e propriedades; abstract e final precisam ser declaradas antes da visibilidade, somente static pode ser declarada depois.
	 - As [Palavras Chaves](http://php.net/manual/en/reserved.keywords.php) tem por **OBRIGAÇÃO** ter um espaço depois das mesmas. Métodos e Funções chamadas **NÃO**.
	 - A chave de abertura de estruturas **DEVEM** permanecer na mesma linha, e seu fechamento em uma nova linha.
	 - Os parênteses das estruturas de controle **NÂO DEVEM** possui um espaço depois dos mesmos.
```php
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
	 - **Arquivos**
		 - Em todos os arquivos **DEVEM** possui uma linha em vazia.
		- O fechamento `?>` **DEVE** ser omitido de arquivos que possuem somente PHP.
	 - **Linhas**
		- **PODEM** ser adicionadas linhas em branco para que com o objetivo de melhorar a legibilidade e 	para indicar bloco de códigos relacionados.
		- **NÃO DEVE** haver mais de uma declaração por linha.
	 - **Identação**
		 -  Utilize 4 espaços para que seja a identação.
	 - **Palavras Chaves**
		 - As constantes nativas do PHP `true`, `false`, `null` **DEVEM** 
	 - **Namespace e Use**
		 - Para cada declaração deve haver um `use`
 3. **Classes, Propriedades e Métodos**
	 - Os termo `extends` e `implements` **DEVEM** ser declarados na mesma linha do nome da classe, contudo no caso de muitos `implements` pode-se inserir uma declaraçao por linha.
	 - A chave de inicio da classe **DEVE**  possui linha própria e seu fechamento **DEVE** estar na última linha do arquivo.
	 - O nome da classe **DEVE** estar no singular.

    ```php
    <?php
    namespace Vendor\Package;
    
    use FooClass;
    use BarClass as Bar;
    use OtherVendor\OtherPackage\BazClass;
    
    class ClassName extends ParentClass implements
        \ArrayAccess,
        \Countable,
        \Serializable
    {
        // constants, properties, methods
    }
    ```
	- Propriedades
		- Não pode exisitir mais de uma declaração de propriedade por linha.
		- As propriedades **NÃO DEVEM** inicio com underline para indicar `protected` ou `private` visibilidade.
	- Métodos
		- Em todos os métodos a visibilidade **DEVE** ser informada.
		- Os métodos **NÃO DEVEM** possui *underline* para indicar `protected` ou `private` .
		- Os nomes dos métodos **NÃO DEVEM** possuir espaços em branco no final.
		- A chave de abertura **DEVE** ter linha própria, somente quando os argumentos estão na mesma linda. E sua chave de fechamento **DEVE** ter está na ultima linha da função.
		- O espaçamento so **DEVE** existir depois da virgula.
		- Todos os métodos **DEVEM** ter sua documentação na linha acima da declaração, seguibndo o padrão abaixo.
	```php
	<?php
	namespace Vendor\Package;

	class ClassName
	{
	    public function fooBarBaz($arg1, &$arg2, $arg3 = [])
	    {
	        // method body
	    }
	}
	```
	```php

	<?php
	namespace Vendor\Package;

	class ClassName
	{
	    public function aVeryLongMethodName(
	        ClassTypeHint $arg1,
	        &$arg2,
	        array $arg3 = []
	    ) {
	        // method body
	    }
	}

	```

	-	Abstract , final e static
		-	Quando presente, `abstract` e `final`  **DEVEM** estar antes da visibilidades, somente `static` **DEVE** ficar após.
		Devem ser parecidos com estes exemplos.
    ```php
	<?php
	bar();
	$foo->bar($arg1);
	Foo::bar($arg2, $arg3);
	```

    ```php
	<?php
	$foo->bar(
	    $longArgument,
	    $longerArgument,
	    $muchLongerArgument
	);
	```
- Estruturas de Controle
	- Em geral devem seguir as regras abaixo:
		- **DEVE** existir um espaço após a `palavra chave`
		- **NÃO DEVE** haver um espaço após o parentese de abertura e fechamento.
		- **DEVE** existir um espaço entre o parentese de fechamento e a chave de abertura.
		- A chave de fechamento **DEVE** ter linha própria.

	As estruturas de controle devem ser parecidas com os exemplos abaixo.

	

    ```php
	<?php
	if ($expr1) {
	    // if body
	} elseif ($expr2) {
	    // elseif body
	} else {
	    // else body;
	}
	```
	
	```php
	<?php
	switch ($expr) {
	    case 0:
	        echo 'First case, with a break';
	        break;
	    case 1:
	        echo 'Second case, which falls through';
	        // no break
	    case 2:
	    case 3:
	    case 4:
	        echo 'Third case, return instead of break';
	        return;
	    default:
	        echo 'Default case';
	        break;
	}
	```

	```php
	<?php
	while ($expr) {
	    // structure body
	}
	```
	
	```php
	<?php
	do {
	    // structure body;
	} while ($expr);
	```
	```php
	<?php
	for ($i = 0; $i < 10; $i++) {
	   // for body
	}
	```
	```php
	<?php
	foreach ($iterable as $key => $value) {
	  // foreach body
	}
	```
	
	```php
	<?php
	try {
	   // try body
	} catch (FirstExceptionType $e) {
	   // catch body
	} catch (OtherExceptionType $e) {
	   // catch body
	}
	```	
	
 5.  **Show Case**
		
-	**Classes**
		
```php
// Bad
<?php

namespace Vender\Package;
use foo\bar as Bar;
use foo\baz;
use FooInterface;

class FooBar extends Bar implements FooInterface{
	...
}

// Good
<?php
namespace Vender\Package;

use foo\bar as Bar;
use foo\baz;
use FooInterface;

/** [Descrição do arquivo]
* 
* [mais informações precisa ter 1 ENTER para definir novo parágrafo]
* 
* [pode usar quantas linhas forem necessárias]
* [linhas logo abaixo como esta, são consideradas mesmo parágrafo]
* 
* @package [Nome do pacote de Classes, ou do sistema] 
* @category [Categoria a que o arquivo pertence] 
* @name [Apelido para o arquivo] OBRIGATÓRIO
* @author [nome do autor] <[e-mail do autor]> OBRIGATÓRIO
* @copyright [Informações de Direitos de Cópia] OBRIGATÓRIO
* @license [link da licença] [Nome da licença] 
* @link [link de onde pode ser encontrado esse arquivo] 
* @version [Versão atual do arquivo] OBRIGATÓRIO
* @since [Arquivo existe desde: Data ou Versao] 
*/
class FooBar extends Bar implements FooInterface{
	...
}
```
- Classes
```php
// Good
class Upload
class User
class UploadFile

//Bad
class upload
class Uploads
class Upload_File
```

- Variáveis
```php
// Somentes as varíaveis que são atributos em bando de dados 
// devem ter syntaxe lowerse com underline

// Bad
$foo_bar; // Somente para atributos de banco de dados
$arrybarfoobaz;
$_foo_bar;

// Good
$fooBar;
$foo;
```
- Métodos
```php
//Bad
public function foo_bar_baz(){
	...
}

//Good
public function fooBar($arg, $arg2, $agr3){
	...
}

public function fooBarBazBar(
	$arg,
	$arg2,
	$agr3)
	{
	...
}
```







	  
 6. **Modelos**
 7. **Controladores**
 8. **Views**

