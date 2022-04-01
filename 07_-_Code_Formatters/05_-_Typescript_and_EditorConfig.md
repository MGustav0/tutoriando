# Configuração

Configuração básica para qualquer projeto.

## TypeScript

Caso não tenha o Typescript instalado de forma global: `yarn add typescript -g` e depois `tsc --init`.

## EditorConfig

Padroniza várias IDEs com uma configuração. Assim ajusta-se as configurações de identação, estilos, etc para vários desenvolvedores independente da IDE.

Instale a extensão [EditorConfig for VS Code](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) e na pasta raiz dos nossos projetos podemos clicar com o botão direito do mouse e escolher a opção `Generate .editorconfig`.

1. Instalar a extensão EditorConfig
2. Clicar com o botão direito do mouse na raiz do projeto e na opção: `.editorconfig`
3. No arquivo gerado ajuste a configuração para:

```properties
root = true

[*]
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
end_of_line = lf
```
