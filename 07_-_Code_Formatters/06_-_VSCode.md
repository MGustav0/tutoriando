# Configuração do VSCode

Acessar as configurações do VSCode em `Files -> Preferences -> Settings -> Open Settings (JSON)` (ícone ao lado das abas) e colar este código:

```json
{
	"breadcrumbs.enabled": true,
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
		"!php",
		"!pug",
		"!python",
		"!restructuredtext",
		"!rust",
		"!scala",
		"!scss",
		"!twig"
	],
	"cSpell.language": "en,pt",
	"cSpell.userWords": [],
	"diffEditor.ignoreTrimWhitespace": true,
	"diffEditor.wordWrap": "on",
	"editor.acceptSuggestionOnCommitCharacter": false,
	"editor.accessibilitySupport": "off",
	"editor.bracketPairColorization.enabled": true,
	"editor.codeActionsOnSave": {
		"source.fixAll.eslint": true,
	},
	"editor.fontFamily": "Fira Code",
	"editor.fontLigatures": true,
	"editor.formatOnSave": true,
	"editor.inlineSuggest.enabled": true,
	"editor.parameterHints.enabled": false,
	"editor.quickSuggestions": {
		"strings": true
	},
	"editor.renderLineHighlight": "gutter",
	"editor.rulers": [
		90,
		120
	],
	"editor.semanticHighlighting.enabled": false,
	"editor.suggestSelection": "first",
	"editor.tabSize": 2,
	"emmet.includeLanguages": {
		"javascript": "javascriptreact"
	},
	"emmet.syntaxProfiles": {
		"javascript": "jsx"
	},
	"eslint.packageManager": "yarn",
	"explorer.compactFolders": false,
	"explorer.confirmDelete": false,
	"explorer.confirmDragAndDrop": false,
	"extensions.ignoreRecommendations": true,
	"files.associations": {
		".sequelizerc": "javascript",
		".stylelintrc": "json",
		".prettierrc": "json",
		"*.tsx": "typescriptreact",
		"*.css": "tailwindcss"
	},
	"files.exclude": {
		"**/.git": true,
		"**/.svn": true,
		"**/.hg": true,
		"**/CVS": true,
		"**/.DS_Store": true,
		"**/node_modules": true
	},
	"git.autofetch": true,
	"git.confirmSync": false,
	"git.enableSmartCommit": true,
	"git.inputValidation": "warn",
	"git-commit.subjectFormat.charactersRemainingTextColor": "rgba(153, 153, 153, 0.35)",
	"git-commit.subjectFormat.enableFormatter": true,
	"git-commit.subjectFormat.displayCharactersRemaining": true,
	"git-commit.subjectFormat.maxLength": 100,
	"github.copilot.enable": {
		"*": true,
		"yaml": true,
		"plaintext": true,
		"markdown": true
	},
	"gitlens.codeLens.recentChange.enabled": false,
	"javascript.suggest.autoImports": true,
	"javascript.updateImportsOnFileMove.enabled": "always",
	"markdown.extension.katex.macros": {},
	"markdown.extension.preview.autoShowPreviewToSide": true,
	"markdown.extension.print.imgToBase64": true,
	"markdown.extension.print.theme": "dark",
	"markdown.extension.tableFormatter.normalizeIndentation": true,
	"material-icon-theme.activeIconPack": "nest",
	"material-icon-theme.folders.associations": {
		"adapters": "contract",
		"grpc": "pipe",
		"kube": "kubernetes",
		"main": "lib",
		"websockets": "pipe",
		"implementations": "core",
		"protos": "pipe",
		"entities": "class",
		"kafka": "pipe",
		"use-cases": "functions",
		"migrations": "tools",
		"schemas": "class",
		"useCases": "functions",
		"eslint-config": "tools",
		"typeorm": "database",
		"_shared": "shared",
		"mappers": "meta",
		"fakes": "mock",
		"modules": "components",
		"subscribers": "messages",
		"domain": "class",
		"protocols": "contract",
		"infra": "app",
		"view-models": "views",
		"presentation": "template",
		"dtos": "typescript",
		"http": "container",
		"providers": "include",
		"factories": "class",
		"repositories": "mappings"
	},
	"material-icon-theme.languages.associations": {
		"dotenv": "tune"
	},
	"material-icon-theme.files.associations": {
		".sequelizerc": "javascript",
		".stylelintrc": "json",
		"*.tsx": "typescriptreact",
		".env.*": "dotenv",
		".prettierrc": "json",
		"tsconfig.json": "tune",
		"*.webpack.js": "webpack",
		"*.proto": "3d",
		"ormconfig.json": "database"
	},
	"npm.packageManager": "yarn",
	"security.workspace.trust.untrustedFiles": "newWindow",
	"screencastMode.onlyKeyboardShortcuts": true,
	"tailwindCSS.includeLanguages": {
		"plaintext": "html"
	},
	"telemetry.telemetryLevel": "off",
	"terminal.integrated.defaultProfile.linux": "zsh",
	"terminal.integrated.fontFamily": "FiraCode Nerd Font",
	"terminal.integrated.showExitAlert": false,
	"terminal.integrated.profiles.linux": {
		"zsh (login)": {
			"path": "zsh",
			"args": [
				"-l"
			]
		}
	},
	"typescript.suggest.autoImports": true,
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
	"typescript.tsserver.log": "off",
	"typescript.updateImportsOnFileMove.enabled": "never",
	"vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
	"window.titleBarStyle": "custom",
	"workbench.colorTheme": "Aura Dark (Soft Text)",
	"workbench.editor.labelFormat": "short",
	"workbench.editor.untitled.hint": "hidden",
	"workbench.editorAssociations": {
		"*.con": "default"
	},
	"workbench.iconTheme": "material-icon-theme",
	"workbench.productIconTheme": "fluent-icons",
	"workbench.startupEditor": "newUntitledFile",
	"[markdown]": {
		"editor.defaultFormatter": "vscode.markdown-language-features"
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
	"[json]": {
		"editor.defaultFormatter": "vscode.json-language-features"
	},
	"[prisma]": {
		"editor.defaultFormatter": "Prisma.prisma",
		"editor.formatOnSave": true
	},
	"[typescript]": {
		"editor.codeActionsOnSave": {
			"source.fixAll.eslint": true
		},
		"editor.defaultFormatter": "esbenp.prettier-vscode",
	},
	"[typescriptreact]": {
		"editor.codeActionsOnSave": {
			"source.fixAll.eslint": true
		}
	},
	"tabnine.experimentalAutoImports": true
}
```
