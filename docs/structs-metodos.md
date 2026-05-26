# Structs e Metodos

Structs permitem agrupar dados relacionados em uma unica estrutura.

Elas sao muito usadas para representar entidades do mundo real, como usuarios, produtos, pedidos, alunos ou contas bancarias.

## O que e uma struct?

Uma struct e um tipo personalizado que possui campos.

Cada campo pode ter um nome e um tipo.

go
package main

import "fmt"

type Pessoa struct {
    Nome  string
    Idade int
}

func main() {
    pessoa := Pessoa{
        Nome:  "Ana",
        Idade: 25,
    }

    fmt.Println(pessoa.Nome)
    fmt.Println(pessoa.Idade)
}



Nesse exemplo, Pessoa possui os campos Nome e Idade.

## Criando uma struct

A estrutura basica de uma struct em Go e:


go
type Produto struct {
    Nome  string
    Preco float64
}



## Instanciando uma struct

Depois de criar a struct, podemos criar valores a partir dela.


go
produto := Produto{
    Nome:  "Notebook",
    Preco: 3500.00,
}



## Metodos

Metodos sao funcoes associadas a um tipo.

Em Go, um metodo e criado usando um receiver.


go
package main

import "fmt"

type Pessoa struct {
    Nome string
}

func (p Pessoa) Apresentar() string {
    return "Ola, meu nome e " + p.Nome
}

func main() {
    pessoa := Pessoa{Nome: "Carlos"}

    fmt.Println(pessoa.Apresentar())
}



## Receiver

O receiver indica a qual tipo o metodo pertence.

No exemplo abaixo, (p Pessoa) indica que o metodo pertence ao tipo Pessoa.


go
func (p Pessoa) Apresentar() string {
    return "Ola, meu nome e " + p.Nome
}



## Resumo

| Conceito | Descricao |
| --- | --- |
| struct | Tipo personalizado que agrupa campos |
| campo | Informacao armazenada dentro da struct |
| metodo | Funcao associada a um tipo |
| receiver | Indica o tipo ao qual o metodo pertence |

## Quando usar structs?

| Situacao | Exemplo |
| --- | --- |
| Representar entidades | Pessoa, Produto, Cliente |
| Agrupar dados relacionados | Nome, idade, email |
| Organizar regras de negocio | Calcular preco, validar dados |
| Criar metodos | Apresentar, CalcularTotal, Validar |

!!! tip "Dica"

    Use structs para deixar o codigo mais organizado e mais proximo do problema real que esta sendo resolvido.
