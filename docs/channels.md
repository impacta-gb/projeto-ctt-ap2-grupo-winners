# Concorrencia II: Channels

Channels permitem a comunicacao entre goroutines.

Eles sao usados para enviar e receber valores de forma segura entre execucoes concorrentes, ajudando a sincronizar tarefas dentro de um programa Go.

## O que e um Channel?

Um channel e um canal de comunicacao entre goroutines.

Ele permite que uma goroutine envie dados e outra goroutine receba esses dados.

## Criando um Channel

Para criar um channel em Go, usamos a funcao make.

go
canal := make(chan string)



Nesse exemplo, o channel transporta valores do tipo string.

## Enviando dados para um Channel

Para enviar um valor para um channel, usamos o operador <-.


go
canal <- "Mensagem enviada"



## Recebendo dados de um Channel

Para receber um valor de um channel, tambem usamos o operador <-.


go
mensagem := <-canal



## Exemplo completo


go
package main

import "fmt"

func enviarMensagem(canal chan string) {
    canal <- "Mensagem enviada pelo channel"
}

func main() {
    canal := make(chan string)

    go enviarMensagem(canal)

    mensagem := <-canal

    fmt.Println(mensagem)
}



Nesse exemplo, a goroutine envia uma mensagem pelo channel, e a funcao main recebe essa mensagem.

## Operacoes com Channels

| Operacao | Exemplo |
| --- | --- |
| Criar channel | make(chan string) |
| Enviar valor | canal <- "texto" |
| Receber valor | mensagem := <-canal |
| Passar channel para funcao | func exemplo(canal chan string) |

## Channels com buffer

Tambem e possivel criar channels com buffer.


go
canal := make(chan string, 2)

canal <- "Primeira mensagem"
canal <- "Segunda mensagem"

fmt.Println(<-canal)
fmt.Println(<-canal)



Um channel com buffer permite armazenar uma quantidade limitada de valores antes que eles sejam recebidos.

## Quando usar Channels?

| Situacao | Uso recomendado |
| --- | --- |
| Comunicar goroutines | Sim |
| Sincronizar tarefas concorrentes | Sim |
| Enviar resultados entre processos | Sim |
| Compartilhar dados sem controle | Evitar |
| Substituir toda logica do programa | Nao recomendado |

!!! tip "Boa pratica"

    Use channels quando goroutines precisarem trocar dados ou sincronizar a execucao de tarefas.
