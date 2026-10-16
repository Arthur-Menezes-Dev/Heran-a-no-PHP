# Herança-no-PHP
Aula do dia 14/10/2026 Sobre o conceito de herança na Programação Orientada a Objetos usando a linguagem PHP 

São 6 arquivos

HelloWorld.php
Funcionario.php
Vendedor.php
VendedorNivel1.php
VendedorNivel2.php
VendedorNivel3.php
Gerente.php

## HelloWorld.php
```php
<?php
   
    include "Funcionario.php";
    include "Vendedor.php";
    include "VendedorNivel1.php";
    include "VendedorNivel2.php";
    include "VendedorNivel3.php";
    include "Gerente.php";


    $func = new Funcionario();
    $func->setMatricula(1010);
    $func->setNome("Pedro");
    $func->setSalarioBruto(3000);


    echo "*********** " . get_class($func) . " **************" .PHP_EOL;
    echo "Matricula: " . $func->getMatricula() .PHP_EOL;
    echo "Nome: " . $func->getNome() . PHP_EOL;
    echo "Salário: " . $func->getSalarioBruto() . PHP_EOL;
    echo "Bonificação (5%): " . $func->calcularBonificacao() . PHP_EOL;
    echo "Salário + Bonificação: " . ($func->getSalarioBruto() + $func->calcularBonificacao() . PHP_EOL);


    echo "\n";


    $vendedor1 = new VendedorNivel1();
    $vendedor1->setMatricula(2020);
    $vendedor1->setNome("Francisca");
    $vendedor1->setSalarioBruto(3000);


    echo "*********** " . get_class($vendedor1) . " **************" .PHP_EOL;
    echo "Matricula: " . $vendedor1->getMatricula() .PHP_EOL;
    echo "Nome: " . $vendedor1->getNome() . PHP_EOL;
    echo "Salário: " . $vendedor1->getSalarioBruto() . PHP_EOL;
    echo "Bonificação (5%): " . $vendedor1->calcularBonificacao() . PHP_EOL;
    echo "Comissão: " . $vendedor1->calcularComissao() .PHP_EOL;
    echo "Salário + Bonificação + Comissão: " . ($vendedor1->getSalarioBruto() + $vendedor1->calcularBonificacao()  + $vendedor1->calcularComissao() . PHP_EOL);


    echo "\n";


    $vendedor2 = new VendedorNivel2();
    $vendedor2->setMatricula(2021);
    $vendedor2->setNome("Roberto");
    $vendedor2->setSalarioBruto(3000);


    echo "*********** " . get_class($vendedor2) . " **************" .PHP_EOL;
    echo "Matricula: " . $vendedor2->getMatricula() .PHP_EOL;
    echo "Nome: " . $vendedor2->getNome() . PHP_EOL;
    echo "Salário: " . $vendedor2->getSalarioBruto() . PHP_EOL;
    echo "Bonificação (5%): " . $vendedor2->calcularBonificacao() . PHP_EOL;
    echo "Comissão: " . $vendedor2->calcularComissao() .PHP_EOL;
    echo "Salário + Bonificação + Comissão: "  . ($vendedor2->getSalarioBruto() + $vendedor2->calcularBonificacao()  + $vendedor2  ->calcularComissao() . PHP_EOL);


    echo "\n";


    $vendedor3 = new VendedorNivel3();
    $vendedor3->setMatricula(2022);
    $vendedor3->setNome("Paula");
    $vendedor3->setSalarioBruto(3000);


    echo "*********** " . get_class($vendedor3) . " **************" .PHP_EOL;
    echo "Matricula: " . $vendedor3->getMatricula() .PHP_EOL;
    echo "Nome: " . $vendedor3->getNome() . PHP_EOL;
    echo "Salário: " . $vendedor3->getSalarioBruto() . PHP_EOL;
    echo "Bonificação (5%): " . $vendedor3->calcularBonificacao() . PHP_EOL;
    echo "Comissão: " . $vendedor3->calcularComissao() .PHP_EOL;
    echo "Salário + Bonificação + Comissão: " . ($vendedor3->getSalarioBruto() + $vendedor3->calcularBonificacao()  + $vendedor3  ->calcularComissao() . PHP_EOL);


    echo "\n";


    $gerente = new Gerente();
    $gerente->setMatricula(2023);
    $gerente->setNome("Sandra");
    $gerente->setSalarioBruto(6500);


    echo "*********** " . get_class($gerente) . " **************" .PHP_EOL;
    echo "Matricula: " . $gerente->getMatricula() .PHP_EOL;
    echo "Nome: " . $gerente->getNome() . PHP_EOL;
    echo "Salário: " . $gerente->getSalarioBruto() . PHP_EOL;
    echo "Bonificação (5%): " . $gerente->calcularBonificacao() . PHP_EOL;
    echo "Comissão: " . $gerente->calcularComissao() .PHP_EOL;
    echo "Salário + Bonificação + Comissão: " . ($gerente->getSalarioBruto() + $gerente->calcularBonificacao()  + $gerente->calcularComissao() . PHP_EOL);

?>
```
## Funcionario.php

```php
<?php



class Funcionario{


    private $matricula;
    private $nome;
    private $salarioBruto;


    public function calcularBonificacao(){
        return $this->salarioBruto * 0.05;
    }


    public function getMatricula(){
        return $this->matricula;
    }


    public function getNome(){
        return $this->nome;
    }


    public function getSalarioBruto(){
        return $this->salarioBruto;
    }


    public function setMatricula($matricula){
        $this->matricula = $matricula;
    }


    public function setNome($nome){
        $this->nome = $nome;
    }


    public function setSalarioBruto($salarioBruto){
        $this->salarioBruto = $salarioBruto;
    }


}

?>
```

## Vendedor.php

```php
<?php


class Vendedor extends Funcionario{


    public function calcularComissao(){
        return 100000 * 0.006;
    }


}

?>
```

## VendedorNivel1.php

```php
<?php


class VendedorNivel1 extends Vendedor{
   
    public function calcularComissao(){
        return 100000 * 0.01;
    }


}

?>
```

## VendedorNivel2.php

```php
<?php


class VendedorNivel2 extends Vendedor{
   
    public function calcularComissao(){
        return 100000 * 0.006;
    }


}

?>
```

## VendedorNivel3.php

```php
<?php


class VendedorNivel3 extends Vendedor{


    public function calcularComissao(){
        return 100000 * 0.004;
    }


}

?>
```


## Gerente.php

```php
<?php


class Gerente extends Vendedor{


    public function calcularComissao(){
        return 300000 * 0.005;
    }

    	public function calcularBonificacao(){
		return parent::calcularBonificacao() + 500;
	}


}
?>
```
