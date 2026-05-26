# Concorrencia I: Goroutines

Goroutines sao funcoes executadas de forma concorrente em Go.

Elas permitem que diferentes partes de um programa sejam executadas ao mesmo tempo ou de forma sobreposta, tornando a linguagem muito eficiente para tarefas como servidores, APIs, processamento paralelo e sistemas distribuidos.

## O que e uma Goroutine?

Uma goroutine e criada usando a palavra-chave go antes da chamada de uma funcao.

go
go minhaFuncao()



Quando isso acontece, a funcao passa a executar de forma concorrente com o restante do programa.

## Exemplo basico


go
package main

import (
    "fmt"
    "time"
)

func mensagem() {
    fmt.Println("Executando em uma goroutine")
}

func main() {
    go mensagem()

    time.Sleep(time.Second)

    fmt.Println("Fim do programa")
}



Nesse exemplo, a funcao mensagem e executada como uma goroutine.

## Por que usar Goroutines?

Goroutines sao leves e simples de criar. Elas ajudam quando o programa precisa realizar varias tarefas ao mesmo tempo.

## Comparacao

| Conceito | Descricao |
| --- | --- |
| Goroutine | Funcao executada de forma concorrente |
| Palavra-chave go | Inicia uma goroutine |
| Concorrencia | Execucao de tarefas de forma sobreposta |
| main | Funcao principal do programa |
| time.Sleep | Usado no exemplo para aguardar a goroutine |

## Exemplo com varias Goroutines


go
package main

import (
    "fmt"
    "time"
)

func tarefa(nome string) {
    for i := 1; i <= 3; i++ {
        fmt.Println(nome, i)
        time.Sleep(time.Millisecond * 500)
    }
}

func main() {
    go tarefa("Tarefa A")
    go tarefa("Tarefa B")

    time.Sleep(time.Second * 3)

    fmt.Println("Programa finalizado")
}



## Quando usar Goroutines?

| Situacao | Uso recomendado |
| --- | --- |
| Processar tarefas independentes | Sim |
| Fazer chamadas de rede | Sim |
| Executar operacoes em paralelo | Sim |
| Controlar ordem exata de execucao | Exige cuidado |
| Compartilhar dados entre tarefas | Usar sincronizacao |

!!! warning "Cuidado"

    Se a funcao main terminar antes da goroutine, a goroutine tambem sera encerrada. Por isso, em programas reais, e comum usar mecanismos de sincronizacao.
