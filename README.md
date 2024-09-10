# aula-05-artifact

# Hello Server - GitHub Actions Workflow

Este repositório contém um projeto simples em Go, que implementa um servidor HTTP. O repositório está configurado com um workflow do GitHub Actions para automatizar o build e o deploy do servidor.

## Estrutura do Projeto

- **hello-server.go**: Código-fonte do servidor HTTP escrito em Go.
- **run.sh**: Script que executa o binário gerado pelo workflow.
- **.github/workflows/main.yml**: Arquivo de configuração do GitHub Actions para o CI/CD.

## Funcionamento do Workflow

O workflow principal (`main.yml`) realiza as seguintes ações:

1. **Build do Projeto**:
    - O código Go é compilado tanto para Linux quanto para Windows.
    - Os binários são gerados e armazenados como artefatos.

2. **Jobs**:
    - `build-go`: Realiza o build do código Go e faz o upload dos artefatos.
    - `download-and-run-linux`: Faz o download do artefato Linux e executa o script `run.sh`.
    - `download-only-windows`: Faz o download do artefato Windows.

3. **Scheduler**:
    - O workflow é agendado para ser executado a cada 15 minutos de segunda a sábado.

