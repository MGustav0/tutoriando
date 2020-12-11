# Estrutura lógica

Essa é a estrutura lógica de uma aplicação com ReactJS que eu sigo (06/2020).

## Estrutura de Pastas e Arquivos

### Raíz

`src/` - Pasta que contém todos os arquivos da aplicação.

_Arquivos de configuração_ - Conterá outros arquivos de configuração.

### Pasta SRC

#### Pastas

* `assets/` - Contém arquivos de imagem e fontes.

* `components/` - Contém os componentes globais da aplicação, que serão reutilizados nos componentes de `pages`.

  * `SeuComponenteGlobal`- Página contendo o `index.tsx/jsx` e o `styles.ts/js`, nela estão os componentes que serão usados globalmente, como um _header_.

* `hooks/` - Conterá os hooks da aplicação.

* `pages/` - Conterá os componentes individuais em forma das telas/páginas da aplicação.

  * `SuaPagina` - Página contendo o `index.tsx/jsx` e o `styles.ts/js`, nela estão as regras de negócio da aplicação separadas por páginas/layouts/telas.

* `routes/` - Conterá as rotas e o arquivo de configuração das rotas `Route.tsx/jsx`.

* `services/` - Conterá os arquivos que servem à aplicação, como a API servidor e API de imagens, etc.

* `styles/` - Conterá os estilos globais da aplicação.

* `utils/` - Conterá os arquivos com funções que serão reaproveitadas em toda a aplicação, como o arquivo de erros.
