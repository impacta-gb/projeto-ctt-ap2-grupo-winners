# Tratamento de Erros

Em Go, erros sao tratados de forma explicita.

Diferente de algumas linguagens que usam excecoes para muitos casos, Go normalmente trabalha com valores de erro retornados pelas funcoes.

## O tipo error

O tipo error e usado para representar uma situacao de erro.

Uma funcao pode retornar um valor normal e tambem um erro.

go
func dividir(a float64, b float64) (float64, error) {
    if b == 0 {
        return 0, errors.New("divisao por zero")
    }

    return a / b, nil
}



## Exemplo completo


go
package main

import (
    "errors"
    "fmt"
)

func dividir(a float64, b float64) (float64, error) {
    if b == 0 {
        return 0, errors.New("divisao por zero")
    }

    return a / b, nil
}

func main() {
    resultado, err := dividir(10, 0)

    if err != nil {
        fmt.Println("Erro:", err)
        return
    }

    fmt.Println("Resultado:", resultado)
}



## Verificando erros

O padrao mais comum em Go e verificar se o erro e diferente de nil.


go
resultado, err := algumaFuncao()

if err != nil {
    return err
}



Quando err e nil, significa que nao ocorreu erro.

## Criando mensagens de erro

Uma forma simples de criar erros e usando errors.New.


go
errors.New("mensagem de erro")



Tambem e possivel criar erros formatados com fmt.Errorf.


go
fmt.Errorf("usuario %s nao encontrado", nome)



## Resumo

| Elemento | Funcao |
| --- | --- |
| error | Tipo usado para representar erros |
| nil | Indica ausencia de erro |
| err != nil | Verifica se ocorreu erro |
| errors.New | Cria uma mensagem de erro simples |
| fmt.Errorf | Cria uma mensagem de erro formatada |

## Boas praticas

| Boa pratica | Descricao |
| --- | --- |
| Verificar erros | Sempre confira se err != nil |
| Retornar cedo | Use return quando encontrar um erro |
| Criar mensagens claras | Facilita a identificacao do problema |
| Nao ignorar erros | Evita falhas escondidas no sistema |

!!! warning "Atencao"

    Nao ignore erros retornados por funcoes. Em Go, tratar erros corretamente faz parte da logica principal do programa.
