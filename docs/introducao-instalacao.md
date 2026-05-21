# Introducao e Instalacao

Go, tambem conhecida como Golang, e uma linguagem de programacao criada pelo Google com foco em simplicidade, desempenho e produtividade.

Ela e muito usada no desenvolvimento de APIs, ferramentas de linha de comando, sistemas distribuidos, microsservicos e aplicacoes de alta performance.

## Principais caracteristicas

| Caracteristica | Descricao |
| --- | --- |
| Simplicidade | Possui sintaxe direta e facil de entender |
| Performance | E uma linguagem compilada |
| Concorrencia | Possui goroutines e channels |
| Portabilidade | Permite compilar para diferentes sistemas operacionais |
| Tipagem estatica | Os tipos sao verificados em tempo de compilacao |

## Instalacao

Para instalar Go, acesse o site oficial da linguagem e baixe o instalador para o seu sistema operacional.

Depois da instalacao, verifique se o Go foi instalado corretamente:

```bash
go version
```

## Primeiro programa em Go

```go
package main

import "fmt"

func main() {
    fmt.Println("Ola, Go!")
}
```

Para executar o programa:

```bash
go run main.go
```

!!! tip "Dica"

    Sempre confira se o Go foi adicionado corretamente ao PATH do sistema.
