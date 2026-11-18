+++
draft = false
date = 2026-11-18
title = "Sincronize o Obsidian entre Computador e Celular com o Google Drive"
description = "Um jeito gratuito e sem complicação de manter um vault do Obsidian sincronizado entre o computador e o celular, usando o Google Drive e um app de sincronização."
slug = "sincronizar-obsidian-computador-celular-google-drive"
authors = ["paulohfm"]
tags = ["obsidian", "notas", "google-drive", "android", "macos", "produtividade"]
categories = ["Produtividade"]
series = []
+++

As boas ideias raramente aparecem quando você está sentado na mesa. Elas aparecem no ônibus, na cozinha, no meio de uma caminhada. Se as suas notas moram no [Obsidian](https://obsidian.md), você quer anotar a ideia no celular e continuar trabalhando nela depois, no computador.

Não precisa de serviço pago pra isso. Aqui vai uma configuração gratuita que usa só o **Google Drive** e um app de sincronização no celular. Vou usar macOS e Android nos exemplos.

<!--more-->

## A ideia

Um *vault* (cofre) do Obsidian é só uma pasta cheia de arquivos Markdown. Não tem banco de dados nem servidor especial, então qualquer ferramenta que mantenha uma pasta sincronizada entre dispositivos resolve.

O truque é colocar a pasta do vault **dentro do Google Drive** no computador, sincronizar essa mesma pasta do Drive com uma pasta local no celular e abrir ela com o Obsidian lá também:

```text
  Computador (Obsidian)  Google Drive        Celular (Obsidian)
  ┌───────────┐          ┌───────────┐       ┌───────────┐
  │  notes/   │  <────>  │  notes/   │ <───> │  notes/   │
  └───────────┘          └───────────┘       └───────────┘
        Google Drive para computador     app de sync (duas vias)
```

> **Uma regra:** isso serve pra *continuar* suas anotações em qualquer lugar, não pra editar a mesma nota nos dois dispositivos ao mesmo tempo. Mais sobre isso nos [cuidados](#cuidados-e-dicas) abaixo.

## Passo 1: Coloque uma pasta no Google Drive

1. Instale o [Google Drive para computador](https://www.google.com/drive/download/) e entre na sua conta.
2. No Mac, abra o **Finder**: você vai ver uma localização **Google Drive** na barra lateral. (No disco, ela fica em `~/Library/CloudStorage/GoogleDrive-<seu-email>/My Drive`.)
3. Crie uma pasta nova ali, por exemplo `notes`, e coloque um arquivo de teste dentro (um `hello.md` com uma linha de texto já basta).

O arquivo de teste ajuda depois: quando ele aparecer no celular, você sabe que a sincronização funciona.

## Passo 2: Abra essa pasta como vault no Obsidian

No Obsidian, no computador:

1. Abra o seletor de vaults e clique em **Manage vaults…** (Gerenciar cofres…)
2. Escolha **Open folder as vault** (Abrir pasta como cofre) e selecione a pasta `notes` dentro do Google Drive.

Escolha *Open folder as vault* e não *Create new vault*. A segunda opção cria mais uma pasta dentro do local escolhido, e o que você quer é que o Obsidian use a pasta do Drive exatamente como ela está. Se o seu Obsidian estiver em português, os nomes dos menus aparecem traduzidos.

## Passo 3: Sincronização nos dois sentidos no celular

O celular precisa de um app que sincronize uma pasta do Google Drive com uma pasta do aparelho. No Android, o **DriveSync (Sync for Google Drive)** resolve:

1. Instale o app e entre com a sua conta Google (provavelmente ela já está no celular, então geralmente é um toque só).
2. Escolha a **pasta no Drive** (`notes`) e uma **pasta local no celular** para sincronizar.
3. Configure a direção da sincronização para **os dois sentidos**.

Os dois sentidos são a parte importante. Com sincronização de uma via só, o que você escreve no celular nunca chega ao computador, ou o contrário.

## Passo 4: Abra a pasta sincronizada como vault no celular

Instale o Obsidian para celular e abra, como vault, a pasta local que o app de sincronização está usando. O seu arquivo de teste deve aparecer ali. Crie uma nota no celular, dê um tempinho pra sincronizar e confira se ela aparece no computador. Depois teste o caminho inverso.

Se funcionar nos dois sentidos, está pronto.

## Cuidados e dicas

- **Um dispositivo de cada vez.** A sincronização não é instantânea. Se você editar a mesma nota nos dois dispositivos antes de sincronizar, uma versão pode sobrescrever a outra ou você pode acabar com arquivos duplicados. Um bom hábito: terminar de escrever, deixar sincronizar e só então trocar de dispositivo.
- **Dê um tempinho.** O Google Drive para computador envia os arquivos em segundo plano, e o app do celular sincroniza no ritmo dele. Se uma nota não chegou, espere um pouco ou force uma sincronização manual no app antes de achar que algo quebrou.
- **Deixe o vault disponível offline.** Se o Google Drive para computador estiver configurado para transmitir (stream) os arquivos, a pasta de notas pode virar só um atalho para a nuvem. No Finder, clique com o botão direito na pasta e escolha **Acesso offline → Disponível offline** (o nome pode variar com o idioma) para o Obsidian sempre ter arquivos locais de verdade.
- **Atenção à pasta oculta `.obsidian`.** O Obsidian guarda as configurações de cada vault numa pasta oculta chamada `.obsidian`, dentro do vault. Se as suas configurações e plugins vão acompanhar você até o celular depende de como o app de sincronização trata pastas ocultas, então vale conferir depois da primeira sincronização. Alguns plugins da comunidade só funcionam no computador de qualquer forma.
- **iPhone?** Este guia é para Android. Eu não testei no iOS.

## Outras opções

Se essa configuração não for pra você, existem outros jeitos de chegar no mesmo resultado:

- **[Obsidian Sync](https://obsidian.md/sync)**, o serviço oficial e pago, com criptografia de ponta a ponta e histórico de versões.
- **iCloud**, se todos os seus dispositivos forem Apple.
- **Git** ou **Syncthing**, se você gosta de ter mais controle e não se importa de mexer um pouco.

## Resumindo

Um vault é só uma pasta, então sincronizar o vault é só sincronizar uma pasta. Google Drive no computador, um app de sincronização nos dois sentidos no celular, e você começa uma nota em qualquer lugar e termina em outro, de graça.
