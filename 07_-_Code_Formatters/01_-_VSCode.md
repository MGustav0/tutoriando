# Configuração do VSCode

Acessar as configurações do VSCode em `Files -> Preferences -> Settings -> Open Settings (JSON)` (ícone ao lado das abas) e colar este código:

```json
{
	// Configurações do Git
	"git.autofetch": true,
	"git.enableSmartCommit": true,
	// Configurações de Aparência
	"workbench.startupEditor": "newUntitledFile",
	"workbench.iconTheme": "material-icon-theme",
	"workbench.editor.labelFormat": "short",
	"explorer.confirmDragAndDrop": false,
	"explorer.compactFolders": false,
	"explorer.confirmDelete": false,
	"extensions.ignoreRecommendations": true,
	// Configura a fonte do VSCode
	"editor.fontFamily": "Fira Code",
	"editor.fontLigatures": true,
	"editor.suggestSelection": "first",
	"javascript.suggest.autoImports": true,
	"typescript.suggest.autoImports": true,
	/* Aplica linhas verticais para lembrar de quebrar linha em codigo muito grande
		*"92" é a medida exata para o monitor Ultra-Wide FHD, meia janela
	*/
	"editor.rulers": [
		80,
		92
	],
	"editor.renderLineHighlight": "all",
	"editor.tabSize": 2,
	// Desabilita dica dos parâmetros
	"editor.parameterHints.enabled": false,
	// Configurar autocomplete para javascript e react
	"emmet.includeLanguages": {
		"javascript": "javascriptreact"
	},
	"emmet.syntaxProfiles": {
		"javascript": "jsx"
	},
	// Desabilita importações erradas do VSCode
	"javascript.updateImportsOnFileMove.enabled": "never",
	"breadcrumbs.enabled": true,
	"terminal.integrated.shell.linux": "/usr/bin/zsh",
	// Retirar a barra de títulos da janela
	"window.titleBarStyle": "custom",
	// Configurações do eslint
	"editor.formatOnSave": false,
	"editor.codeActionsOnSave": {
		"source.fixAll.eslint": true
	},
	"[javascript]": {
		"editor.codeActionsOnSave": {
			"source.fixAll.eslint": true
		},
	},
	"[javascriptreact]": {
		"editor.codeActionsOnSave": {
			"source.fixAll.eslint": true
		},
	},
  "[typescript]": {
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
    },
	},
  "[typescriptreact]": {
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
    }
  },
	"files.associations": {
		".sequelizerc": "javascript",
		".stylelintrc": "json",
		"prettierrc": "javascript"
	},
	"diffEditor.ignoreTrimWhitespace": true,
	"vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
	"[markdown]": {
		"editor.defaultFormatter": "vscode.markdown-language-features"
	},
	"cSpell.language": "en,pt-BR",
	"sync.autoDownload": true,
	"sync.autoUpload": true,
	"sync.quietSync": true,
	"sync.gist": "ea86f0176b244a2f2ecff2f0a9bd86d7",
	"cSpell.userWords": [
		"esnext",
		"unform"
	],

	"material-icon-theme.folders.associations": {
		"infra": "app",
		"entities": "class",
		"schemas": "class",
		"typeorm": "database",
		"orm": "database",
		"repositories": "mappings",
		"http": "container",
		"migrations": "tools",
		"modules": "components",
		"implementations": "core",
		"dtos": "typescript",
		"fakes": "mock"
	},

	"material-icon-theme.files.associations": {
		"ormconfig.json": "database",
		"tsconfig.json": "tune"
	},
	"workbench.colorTheme": "Omni"
}
```
