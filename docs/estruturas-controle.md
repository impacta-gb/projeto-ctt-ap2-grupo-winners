# Estruturas de Controle

As estruturas de controle permitem controlar o fluxo de execucao de um programa.

Em Go, as principais estruturas de controle sao `if`, `for` e `switch`.

## If e Else

O `if` executa um bloco de codigo quando uma condicao e verdadeira.  
O `else` pode ser usado para definir o que acontece quando a condicao e falsa.

```go
package main

import "fmt"

func main() {
    idade := 18

    if idade >= 18 {
        fmt.Println("Maior de idade")
    } else {
        fmt.Println("Menor de idade")
    }
}
```

## If com declaracao curta

Go permite criar uma variavel diretamente dentro do `if`.

```go
package main

import "fmt"

func main() {
    if nota := 8; nota >= 6 {
        fmt.Println("Aprovado")
    } else {
        fmt.Println("Reprovado")
    }
}
```

## For

Em Go, o `for` e a principal estrutura de repeticao.  
A linguagem Go nao possui `while`, entao o `for` tambem pode ser usado para repetir enquanto uma condicao for verdadeira.

```go
package main

import "fmt"

func main() {
    for i := 0; i < 5; i++ {
        fmt.Println(i)
    }
}
```

## For como while

```go
package main

import "fmt"

func main() {
    contador := 0

    for contador < 3 {
        fmt.Println(contador)
        contador++
    }
}
```

## Switch

O `switch` e usado quando existem varias possibilidades de decisao.

```go
package main

import "fmt"

func main() {
    dia := "segunda"

    switch dia {
    case "segunda":
        fmt.Println("Inicio da semana")
    case "sexta":
        fmt.Println("Quase fim de semana")
    default:
        fmt.Println("Outro dia")
    }
}
```

## Resumo das estruturas

| Estrutura | Funcao |
| --- | --- |
| if | Executa codigo com base em uma condicao |
| else | Define uma alternativa quando o if e falso |
| for | Realiza repeticoes |
| switch | Escolhe entre varios casos |
| default | Caso padrao do switch |

## Boas praticas

| Boa pratica | Descricao |
| --- | --- |
| Evitar condicoes muito grandes | Melhora a leitura do codigo |
| Usar switch quando houver muitos casos | Deixa o codigo mais organizado |
| Manter blocos pequenos | Facilita manutencao |
| Usar nomes claros | Ajuda a entender a regra aplicada |

!!! note "Observacao"

    Em Go nao existe a estrutura `while`. Para esse comportamento, utilize `for` com uma condicao.
