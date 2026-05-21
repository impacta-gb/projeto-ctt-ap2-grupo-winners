# Gerenciamento de Pacotes: Go Modules

Go Modules e o sistema oficial de gerenciamento de dependencias da linguagem Go.

Ele permite organizar projetos, controlar versoes de bibliotecas externas e facilitar o compartilhamento de codigo entre diferentes ambientes.

## O que e um modulo?

Um modulo em Go representa um projeto ou conjunto de pacotes versionados.

Normalmente, um projeto Go possui um arquivo chamado `go.mod`, que guarda o nome do modulo e as dependencias utilizadas.

## Criando um modulo

Para criar um novo modulo, use o comando:

```bash
go mod init exemplo.com/meu-projeto
```

Esse comando cria o arquivo `go.mod` na raiz do projeto.

## Instalando dependencias

Para adicionar uma biblioteca externa ao projeto, use:

```bash
go get github.com/gin-gonic/gin
```

Depois disso, o Go atualiza automaticamente os arquivos `go.mod` e `go.sum`.

## Arquivos importantes

| Arquivo | Funcao |
| --- | --- |
| go.mod | Define o modulo e lista as dependencias principais |
| go.sum | Registra verificacoes de integridade das dependencias |
| main.go | Arquivo principal da aplicacao, quando existir |
| packages | Pacotes usados para organizar o codigo |

## Exemplo de arquivo go.mod

```go
module exemplo.com/meu-projeto

go 1.22

require github.com/gin-gonic/gin v1.10.0
```

## Comandos comuns

| Comando | Descricao |
| --- | --- |
| go mod init | Cria um novo modulo |
| go get | Adiciona uma dependencia |
| go mod tidy | Remove dependencias nao usadas e organiza o modulo |
| go list -m all | Lista os modulos utilizados |

!!! note "Observacao"

    Os arquivos `go.mod` e `go.sum` devem ser versionados no Git, pois eles ajudam a manter o mesmo ambiente de dependencias para todos os desenvolvedores.
