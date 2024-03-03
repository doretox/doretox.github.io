---
layout: post
title:  "CI Workflow Utilizando Github Actions. Parte 1 - SAST com Bandit"
description:
date:   2024-03-03 00:00:00 +0530
tags: [InfoSec]
---

Neste post, explicarei o fluxo de trabalho para uma CI (Continuous Integration) que desenvolvi usando as GitHub Actions. Você pode acessar o repositório deste fluxo de trabalho através do seguinte [link](https://github.com/doretox/pygoat-devsecops-ex/actions/runs/8101766622/workflow).
Para este post, subentende-se que o leitor já tenha conhecimento prévio sobre os termos utilizados neste tipo de projeto. Esta é a demonstração de um exemplo prático.

Primeiramente foi feito um fork do projeto pygoat. O projeto [PyGoat](https://owasp.org/www-project-pygoat/) é uma aplicação de exemplo construída em Python, com o objetivo de fornecer um ambiente prático para aprender sobre práticas de segurança e testes de segurança de aplicações.
E o scan utilizado será o [Bandit](https://github.com/PyCQA/bandit), que é uma ferramenta de análise de segurança estática para código Python.

```
name: Fluxo de Trabalho de CI

on: workflow_dispatch
```

Iniciando com o título, este pode ser escolhido de acordo com sua preferência. A chave ```on:``` define quando seu fluxo de trabalho será acionado. Normalmente, é ```on: push```, para que o fluxo de trabalho seja executado automaticamente após um push. No entanto, no meu exemplo, optei por ```on: workflow_dispatch``` para permitir a execução manual, apenas para facilitar a execução e teste, já que estamos em ambiente simulado.

![Workflow Dispatch.](/images/ci-workflow-pt1/run_workflow.jpg)

O próximo passo será configurar os JOBS, que são todas os eventos que serão executados após realizar um push no repositório.

```
jobs:
 sast_scan:
   name: Run Bandit Scan
   runs-on: ubuntu-latest
```

Um nome é atribuído ao conjunto de tarefas que serão executadas, por exemplo, 'sast_scan'. Em primeiro lugar, é especificado ONDE este fluxo de trabalho será executado. No caso, optei por 'ubuntu-latest', mas poderia ser qualquer distribuição Linux de sua escolha.

```
steps:
   - name: Checkout code
     uses: actions/checkout@v4.1.1

   - name: Setup Python
     uses: actions/setup-python@v5.0.0
     with:
       python-version: 3.8

   - name: Install Bandit
     run: pip install bandit

   - name: Run Bandit Scan
     run: bandit -ll -ii -r . -f json -o bandit-report.json


   - name: Upload artifact
     uses: actions/upload-artifact@v4.3.1
     if: always() #executa independente dos outros falhar
     with:
       name: bandit-findings
       path: bandit-report.json
```

Os steps são conjuntos de atividades que serão executadas EM ORDEM.

1) Checkout
  Esta ação faz check-out do seu repositório em $GITHUB_WORKSPACE, para que seu workflow possa acessá-lo.
2) Setup Python
  O repositório em questão é uma aplicação em Python, portanto, é necessário configurar o ambiente Python.
3) Install Bandit
  Bandit é a ferramenta de análise de segurança que será utilizada neste contexto e precisa ser instalada.
4) Run Bandit Scan
  Realiza a execução da análise de segurança usando Bandit e salva o resultado em um formato JSON.
5) Upload Artifact
  Realiza o envio do arquivo JSON gerado como um artefato, tornando-o disponível para download no menu "Artifacts". Esse arquivo pode ser posteriormente enviado para o DefectDojo, por exemplo, para gerenciamento de vulnerabilidades.

![Resultado do Scan Bandit.](/images/ci-workflow-pt1/resultado_scan.jpg)

Em conclusão, este tutorial apresentou o processo de configuração de um fluxo de trabalho de integração contínua (CI) utilizando GitHub Actions para realizar uma análise de segurança em um projeto Python com o Bandit Scan. Através dos passos delineados, os desenvolvedores podem automatizar a detecção de potenciais vulnerabilidades em seus códigos, melhorando assim a segurança de suas aplicações.

Em breve farei a parte 2 deste tutorial, que abordará o scan de imagens Docker para fortalecer ainda mais a segurança em ambientes de desenvolvimento e produção.