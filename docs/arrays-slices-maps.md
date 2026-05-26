# Arrays, Slices e Maps

Go possui estruturas para armazenar colecoes de dados.

As principais estruturas sao `arrays`, `slices` e `maps`.

## Arrays

Arrays possuem tamanho fixo. Isso significa que a quantidade de elementos e definida no momento da declaracao.

```go
package main

import "fmt"

func main() {
    var numeros [3]int = [3]int{1, 2, 3}

    fmt.Println(numeros)
}
```

Nesse exemplo, o array `numeros` possui exatamente 3 posicoes.

## Slices

Slices sao parecidos com arrays, mas possuem tamanho dinamico.

Eles sao mais usados na pratica porque permitem adicionar novos elementos com a funcao `append`.

```go
package main

import "fmt"

func main() {
    nomes := []string{"Ana", "Carlos", "Marina"}

    nomes = append(nomes, "Joao")

    fmt.Println(nomes)
}
```

## Maps

Maps armazenam dados em formato de chave e valor.

Eles sao uteis quando queremos buscar informacoes usando uma chave.

```go
package main

import "fmt"

func main() {
    idades := map[string]int{
        "Ana":    25,
        "Carlos": 30,
    }

    fmt.Println(idades["Ana"])
}
```

## Comparacao

| Estrutura | Tamanho | Uso comum |
| --- | --- | --- |
| Array | Fixo | Colecoes pequenas e previsiveis |
| Slice | Dinamico | Listas flexiveis |
| Map | Dinamico | Relacao entre chave e valor |

## Operacoes comuns

| Operacao | Exemplo | Estrutura |
| --- | --- | --- |
| Criar array | `var numeros [3]int` | Array |
| Criar slice | `nomes := []string{"Ana"}` | Slice |
| Adicionar item | `append(nomes, "Joao")` | Slice |
| Criar map | `map[string]int{}` | Map |
| Acessar valor | `idades["Ana"]` | Map |

## Quando usar cada um?

Use arrays quando o tamanho da colecao for fixo e conhecido.

Use slices quando precisar de uma lista flexivel.

Use maps quando precisar associar uma chave a um valor.

!!! warning "Cuidado"

    Slices sao mais comuns que arrays na maioria dos projetos em Go, pois oferecem mais flexibilidade.
