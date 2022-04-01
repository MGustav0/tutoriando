# Configuração do VSCode

Acessar as configurações do VSCode em `Files -> Preferences -> Settings -> Open Settings (JSON)` (ícone ao lado das abas) e colar este código:

```json
{
	// Configurações do Git
	"git.autofetch": true,
	"git.enableSmartCommit": true,
	"git.inputValidation": "warn",
	// Configurações do Git-Commit
	// https://marketplace.visualstudio.com/items?itemName=trentrand.git-commit-helper-vscode
	"git-commit.subjectFormat.enableFormatter": true,
	"git-commit.subjectFormat.displayCharactersRemaining": true,
	"git-commit.subjectFormat.maxLength": 100,
	"git-commit.subjectFormat.charactersRemainingTextColor": "rgba(153, 153, 153, 0.35)",
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
	// "editor.fontSize": 14,
	// "editor.lineHeight": 26,
	"editor.fontLigatures": true,
	"editor.suggestSelection": "first",
	"editor.bracketPairColorization.enabled": true,
	"javascript.suggest.autoImports": true,
	"typescript.suggest.autoImports": true,
	/* Aplica linhas verticais para lembrar de quebrar linha em codigo muito grande
		*"92" é a medida exata para o monitor Ultra-Wide FHD, meia janela
	*/
	"editor.rulers": [
		90,
		120
	],
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
	"javascript.updateImportsOnFileMove.enabled": "always",
	"typescript.updateImportsOnFileMove.enabled": "never",
	"breadcrumbs.enabled": true,
	"terminal.integrated.profiles.linux": {
		"zsh (login)": {
			"path": "zsh",
			"args": [
				"-l"
			]
		}
	},
	"terminal.integrated.defaultProfile.linux": "zsh",
	// Retirar a barra de títulos da janela
	"window.titleBarStyle": "custom",
	"editor.codeActionsOnSave": {
		"source.fixAll.eslint": true,
	},
	"editor.semanticHighlighting.enabled": false,
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
	"files.exclude": {
		"**/.git": true,
		"**/.svn": true,
		"**/.hg": true,
		"**/CVS": true,
		"**/.DS_Store": true,
		// "**/node_modules": true
	},
	"files.associations": {
		".sequelizerc": "javascript",
		".stylelintrc": "json",
		".prettierrc": "json",
		"*.tsx": "typescriptreact"
	},
	"diffEditor.ignoreTrimWhitespace": true,
	"vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
	"[markdown]": {
		"editor.defaultFormatter": "vscode.markdown-language-features"
	},
	"git.confirmSync": false,
	"typescript.tsserver.log": "off",
	"material-icon-theme.activeIconPack": "nest",
	"material-icon-theme.folders.associations": {
		"infra": "app",
		"entities": "class",
		"domain": "class",
		"schemas": "class",
		"typeorm": "database",
		"repositories": "mappings",
		"http": "container",
		"migrations": "tools",
		"modules": "components",
		"implementations": "core",
		"dtos": "typescript",
		"dto": "typescript",
		"fakes": "mock",
		"websockets": "pipe",
		"protos": "pipe",
		"grpc": "pipe",
		"providers": "include",
		"subscribers": "messages",
		"useCases": "controller",
		"kafka": "scripts",
		"mappers": "meta",
		"_shared": "shared",
		"eslint-config": "tools",
		"kube": "kubernetes"
	},
	"material-icon-theme.files.associations": {
		"ormconfig.json": "database",
		"tsconfig.json": "tune",
		"*.proto": "3d",
		"*.webpack.js": "webpack"
	},
	"cSpell.enableFiletypes": [
		"!asciidoc",
		"!c",
		"!cpp",
		"!csharp",
		"!go",
		"!handlebars",
		"!haskell",
		"!jade",
		"!java",
		"!latex",
		"!pug",
		"!python",
		"!restructuredtext",
		"!rust",
		"!scala",
		"twig"
	],
	"cSpell.language": "en,pt",
	"cSpell.userWords": [
		"androidpublisher",
		"appstoreconnect",
		"azurecr",
		"bccorreios",
		"chakra",
		"cloudwatchlogs",
		"cnpj",
		"CODECOV",
		"coderockr",
		"commitlint",
		"dtos",
		"ellipsize",
		"esnext",
		"inappproducts",
		"jose",
		"keycloak",
		"kitabisa",
		"middlewares",
		"nestjs",
		"postgres",
		"postgresql",
		"prefetch",
		"prismaio",
		"Qube",
		"rocketseat",
		"sendgrid",
		"smtps",
		"SONARQUBE",
		"thekey",
		"tsyringe",
		"typeorm",
		"uncolorize",
		"unform",
		"UNPROCESSABLE",
		"uuidv",
		"varchar",
		"Youtube"
	],
	"terminal.integrated.showExitAlert": false,
	// Demais configurações
	"editor.renderLineHighlight": "gutter",
	"todo-tree.general.tags": [
		"BUG",
		"HACK",
		"FIXME",
		"TODO",
		"XXX",
		"[ ]",
		"[x]"
	],
	"todo-tree.regex.regex": "(//|#|<!--|;|/\\*|^|^\\s*(-|\\d+.))\\s*($TAGS)",
	"workbench.editor.untitled.hint": "hidden",
	"workbench.colorTheme": "Dracula",
	"diffEditor.wordWrap": "on",
	"editor.inlineSuggest.enabled": true,
	"security.workspace.trust.untrustedFiles": "open",
	"workbench.editorAssociations": {
		"*.con": "default"
	},
	"github.copilot.enable": {
		"*": true,
		"yaml": false,
		"plaintext": false,
		"markdown": true
	},
	"editor.formatOnSave": true,
	"[prisma]": {
		"editor.defaultFormatter": "Prisma.prisma"
	}
}
```
