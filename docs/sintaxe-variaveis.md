# Sintaxe Basica e Variaveis

A sintaxe de Go e simples, organizada e pensada para facilitar a leitura do codigo.

Todo programa Go comeca com a declaracao de um pacote. Em programas executaveis, normalmente usamos o pacote main.

## Estrutura basica de um programa

go
package main

import "fmt"

func main() {
    fmt.Println("Programa em Go")
}



Nesse exemplo:

| Parte | Funcao |
| --- | --- |
| package main | Define que o arquivo pertence ao pacote principal |
| import "fmt" | Importa o pacote usado para imprimir mensagens |
| func main() | Funcao inicial de um programa executavel |
| fmt.Println | Exibe uma mensagem no terminal |

## Declaracao de variaveis

Go permite declarar variaveis de diferentes formas.


go
package main

import "fmt"

func main() {
    var nome string = "Ana"
    var idade int = 25
    cidade := "Sao Paulo"

    fmt.Println(nome, idade, cidade)
}



## Formas de declaracao

| Forma | Exemplo | Observacao |
| --- | --- | --- |
| Tipo explicito | var nome string = "Ana" | O tipo e informado manualmente |
| Inferencia de tipo | idade := 25 | Go identifica o tipo automaticamente |
| Constante | const pi = 3.14 | Valor nao pode ser alterado |

## Tipos basicos

| Tipo | Exemplo | Uso |
| --- | --- | --- |
| string | "texto" | Textos |
| int | 10 | Numeros inteiros |
| float64 | 10.5 | Numeros decimais |
| bool | true ou false | Valores logicos |

## Constantes

Constantes sao valores que nao podem ser alterados depois de definidos.


go
package main

import "fmt"

func main() {
    const linguagem = "Go"

    fmt.Println(linguagem)
}



!!! warning "Atencao"

    O operador := so pode ser usado dentro de funcoes. Fora de funcoes, use var ou const.
