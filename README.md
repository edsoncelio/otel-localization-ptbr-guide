Olá, aqui você vai encontrar todas (ou quase todas) as informações para começar 
a contribuir com a localização da documentação do OpenTelemetry para Português!

## Sobre a documentação do OpenTelemetry
* Toda a documentação é hospedada em https://opentelemetry.io/pt/docs/.
* As documentações são escritas em [Markdown](https://www.markdownguide.org/basic-syntax/).

## Sobre o time de localização (Português)
* Toda a comunicação acontece no canal `#otel-localization-ptbr` no workspace da CNCF no slack, então antes de tudo, entre no canal!!
  * Se você ainda não estiver entrado no workspace, pode solicitar um convite [aqui](https://communityinviter.com/apps/cloud-native/cncf)
* Temos encontros quinzenais via Zoom (quarta-feira, 19:17-19:45 BRT), detalhes da agenda e pauta, pode encontrar [aqui](https://docs.google.com/document/d/1W1jJ4OTm53sbOp7CrbNBMvR_2Z8TQRCkwejqD4f21SE/edit).

## Páginas prioritárias para tradução/localização
A princípio, estamos priorizando algumas páginas para tradução, sendo que:
* As páginas que estão [nessa issue](https://github.com/open-telemetry/opentelemetry.io/issues/4922) e ainda não tem uma pessoa atribuida são as prioritárias
* Após todas as páginas da issue acima estarem finalizadas, a prioridade são as páginas de linguagens (`https://opentelemetry.io/pt/docs/languages/`), focando em Go, Javascript e Java.


## Detalhes importantes
Alguns detalhes importantes que você deve conferir antes de abrir seu *Pull Request*.   
*  cada tradução é baseado em um commit das docs original, então obrigatóriamente deve ter um campo chamado `default_lang_commit` contendo a hash do commit da doc original, por exemplo:
```md
title: OpenTelemetry
description: >-
 Telemetria de alta qualidade, abrangente e portátil para permitir uma observabilidade eficaz
developer_note:
  O shortcode blocks/cover (usado abaixo) vai servir como imagem de background
  para qualquer arquivo de imagem que contenha "background" no nome.
show_banner: true
default_lang_commit: 08799298
```

Para uma página nova, você precisa executar o seguinte comando para buscar a hash do commit:
```bash
npm run fix:i18n:new
```
Mais detalhes você pode consultar [aqui](https://opentelemetry.io/docs/contributing/localization/#track-changes).

* Se atente a termos que já possuem um glossário, assim mantemos consistência entre as docs, pode checar [aqui](https://opentelemetry.io/docs/contributing/style-guide/#opentelemetryio-word-list) a lista
* Para garantir que a validação dos links na página funcione corretamente, precisamos manter as âncoras (_anchors_) sem tradução.   
Temos uma action do Github que verifica os links da página, caso esteja quebrado gera avisos de `Warnings` no build, exemplo de âncora:

```md
Título: ## O que é Observabilidade? {#what-is-observability}

Título: ## Trechos {#span}

Título: ## Rastros {#traces}
```

## Passo a Passo
Após estar familiarizado com o processo de contribuição, siga o passo a passo abaixo para fazer sua primeira contribuição.

1. Faça o fork do repositório da documentação: `https://github.com/open-telemetry/opentelemetry.io`

2. Faça o clone do seu fork para sua máquina local, exemplo:
```bash
git clone git@github.com:edsoncelio/opentelemetry.io.git
```

3. Crie uma branch a partir da branch `main` para fazer sua tradução, exemplo:
```bash
git checkout -b adiciona_traducao_traces
```
   
4. Com a branch criada, faça toda a sua tradução, sempre lembrando de fazer o push para o seu fork remoto, exemplo:
```bash
git add .
git commit -m "docs: adiciona traducao de traces"
git push origin adiciona_traducao_traces
```

5. Sempre antes de abrir um *Pull Request*, execute o *lint*, assim não vai quebrar nas checagens automáticas:
```bash
docker run -it  --rm -v$(pwd):/app -w /app  --entrypoint "" node:latest npx prettier --write .
``` 

6. Quando finalizar, ou apenas quiser solicitar uma revisão, abre o *Pull Request* para a branch main.   
Para essa etapa, sugerimos que use o prefixo `[pt]`no título, assim mantemos consistência, por exemplo:
```bash
[pt-br] Localize index page to Portuguese (Brazil)
```

7. Envie o PR no canal do slack `#otel-localization-ptbr`.
8. Aguarde as interações para revisão, é esperado que tenha bastante, não se assuste :) 


## Perguntas Frequentes
TBD
