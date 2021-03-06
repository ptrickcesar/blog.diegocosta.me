---
title: Atualizando todos seus casks via Homebrew no macOS
date: '2020-01-18T22:12:03.284Z'
description: Uma dica simples para forçar a atualização de todos seus casks via HomeBrew
tags: ['Terminal', 'MacOS', 'Homebrew', 'Caskroom']
lang: pt
---

Eu sou uma pessoa aficionada em manter meus programas atualizados e a melhor forma de se fazer isso no macOS é com a ajuda do gerenciador de dependências [Homebrew](https://brew.sh/index_pt-br), ao usa-lo para instalar seus programas podemos escrever scripts para automatizar esse processo.

No Homebrew o comando para atualizar todos os programas é `brew cask upgrade` mas ele nem sempre consegue encontrar atualizações para todos os programas, para solucionar esse problema devemos executar o upgrade para cada programa individualmente, exemplo: `brew cask upgrade google-chrome`.

Aqui entra a dica! Para não ter que rodar o `upgrade` para cada item manualmente, execute esse comando em seu terminal:

```shell
for cask in $(brew cask list); do brew cask upgrade $cask; done;
```

Nele usamos o `for` para percorrer por todos os itens retornados pelo comando `brew cask list` e forçar a atualização.
