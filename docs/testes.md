# Testes Automatizados em Go

Go possui suporte nativo para testes automatizados por meio do pacote testing.

Os testes ajudam a garantir que o codigo continue funcionando corretamente mesmo depois de alteracoes, correcoes ou novas funcionalidades.

## Como funcionam os testes em Go?

Em Go, os arquivos de teste devem terminar com o sufixo _test.go.

Exemplo:

text
calculadora_test.go



As funcoes de teste normalmente comecam com Test e recebem um parametro do tipo *testing.T.

## Funcao que sera testada


go
package calculadora

func Soma(a int, b int) int {
    return a + b
}



## Criando um teste


go
package calculadora

import "testing"

func TestSoma(t *testing.T) {
    resultado := Soma(2, 3)

    if resultado != 5 {
        t.Errorf("esperado 5, recebeu %d", resultado)
    }
}



## Executando os testes

Para executar os testes do pacote atual:


bash
go test



Para executar os testes mostrando mais detalhes:


bash
go test -v



Para executar testes em todos os pacotes do projeto:


bash
go test ./...



## Comandos comuns

| Comando | Funcao |
| --- | --- |
| go test | Executa os testes do pacote atual |
| go test -v | Executa os testes com detalhes |
| go test ./... | Executa testes em todos os pacotes |
| go test -cover | Mostra a cobertura dos testes |

## Boas praticas

| Boa pratica | Descricao |
| --- | --- |
| Testar regras importantes | Garante que partes criticas funcionem |
| Usar nomes claros | Facilita entender o objetivo do teste |
| Manter testes simples | Evita testes dificeis de manter |
| Rodar testes antes do commit | Ajuda a evitar erros no repositorio |

!!! tip "Boa pratica"

    Sempre rode os testes antes de enviar alteracoes para o repositorio.
