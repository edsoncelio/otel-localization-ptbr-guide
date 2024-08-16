## Informações Gerais
* Toda a comunicação acontece no canal (aberto) `#otel-localization-ptbr` no slack da CNCF.
* As documentações (docs) são escritas em Markdown,
* Para ver o preview da sua tradução, pode abrir o PR como rascunho (draft) que vai ser gerado um preview via Netlify,

## Passo a Passo
#### 1. Faça o fork do repositório da documentação
O repositório da documentação do projeto é o [open-telemetry/opentelemetry.io](https://github.com/open-telemetry/opentelemetry.io)
#### 2. Faça o pull para sua máquina local do seu fork
#### 3. Crie uma branch a partir da branch `main`
#### 4. Faça a localização na branch que criou 

Alguns pontos importantes:
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

#### 5. Faça o lint da sua tradução
Para garantir que o seu PR vai passar nos checks do repositório, faça o lint do arquivo com o comando abaixo (usando docker):
```bash
docker run -it  --rm -v$(pwd):/app -w /app  --entrypoint "" node:latest npx prettier --write .
``` 
#### 6. Abra o PR para a branch `main`
Sugerimos que use um título começando com [pt], assim mantemos consistência, por exemplo:
```bash
[pt-br] Localize index page to Portuguese (Brazil)
```
#### 7. Envie o PR no canal `#otel-localization-ptbr` no slack da CNCF.
#### 8. Aguarde as interações para revisão, é esperado que tenha bastante, não se assuste :) 
