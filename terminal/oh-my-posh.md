# Oh My Posh

Oh My Posh é uma engine de prompt personalizada para qualquer shell que tenha a capacidade de ajustar a string do prompt com uma função ou variável.

No linux costumo utilizar o Oh My Zsh, mas no windows a melhor alternativa foi o Oh My Posh.

## Instalação

Há vários modos de [instalação do Oh My Posh](https://ohmyposh.dev/docs/installation/windows), eu gosto de seguir a do winget, via Power Shell siga os comando da documentação.

Gosto de instalar a `Nerd Fonts Fira Code`, mas fique à vontade para escolher qualquer uma [dessa lista](https://www.nerdfonts.com/font-downloads). Instale no seu sistema operacional, no windows basta descompactar, selecionar tudo, clicar com o botão direito do mouse e instalar todas.

Siga [esta documentação](https://ohmyposh.dev/docs/installation/prompt):

1. `notepad $PROFILE`, caso dê problema, insira essa linha `New-Item -Path $PROFILE -Type File -Force` no power shell e dê enter, ela criará um novo perfil para o seu power shell.
2. Digite novemente `notepad $PROFILE`, abrirá o Bloco de Notas no seu perfil, adicione essas linhas:

```ps1
oh-my-posh init pwsh | Invoke-Expression

oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH/jandedobbeleer.omp.json" | Invoke-Expression

Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
```

A primeira linha iniciará o Oh My Posh, a segunda seleciona o tema, com base [nestes temas](https://ohmyposh.dev/docs/themes), a terceira fará com que haja predição de comandos e a quarta gerá uma lista de comandos baseado em seu histórico.

## Configuração

Execute esta linha `Set-PSReadLineOption -PredictionSource History`, reinicie o terminal e execute esta linha: `Set-PSReadLineOption -PredictionViewStyle ListView`.

## Conclusão

Agora o power shell esá customizado, basta altera a linha 2 no profile `notepad $PROFILE` e colocar o tema da sua escolha, sempre respeitando a extensão `*.omp.json`
