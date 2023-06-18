# Lint-утилиты для современного Next приложения 

## Корректно работает на Next 13.4

1. Установка  **Prettier**
    - Создаем файл `.prettierrc` в корне проекта
    - Добавляем в файл следующую конфигурацию 
    
      ```
      {
        "trailingComma": "es5",
        "useTabs": true,
        "tabWidth": 2,
        "semi": true,
        "singleQuote": true,
        "jsxSingleQuote": true
      }
      ```
      
    - Устанавливаем следующие пакеты `npm install eslint-config-prettier@8.5.0 eslint-plugin-prettier@4.2.1 prettier@2.7.1 stylelint-config-prettier@9.0.3 -D`
    - В IDE устанавливаем плагин **Prettier** и проверяем чтоб он считывался с node_modules/prettier вашего проекта
2. Установка  **Eslint** 
    - Создаем файл `.eslintrc.json` в корне проекта
    - Добавляем в файл следующую конфигурацию 
    
      ```
      {
        "root": true,
        "parser": "@typescript-eslint/parser",
        "plugins": [
          "@typescript-eslint",
          "prettier"
        ],
        "rules": {
          "semi": "off",
          "@typescript-eslint/semi": [
            "warn"
          ],
          "@typescript-eslint/no-empty-interface": [
            "error",
            {
              "allowSingleExtends": true
            }
          ],
          "@typescript-eslint/no-explicit-any": "off",
          "no-console": "error",
          "no-debugger": "error"
        },
        "extends": [
          "eslint:recommended",
          "plugin:@typescript-eslint/eslint-recommended",
          "plugin:@typescript-eslint/recommended",
          "next/core-web-vitals",
          "prettier"
        ]
      }
      ```
      
     - Устанавливаем следующие пакеты `npm install eslint@7.32.0 @typescript-eslint/parser@5.30.6 @typescript-eslint/eslint-plugin@5.30.6 -D`
     - В IDE устанавливаем плагин **Eslint** и проверяем чтоб он считывался с node_modules/eslint вашего проекта
2. Подключение  **EditorConfig**
     - Создаем файл `.editorconfig` в корне проекта
     - Добавляем в файл следующую конфигурацию 

        ```
       # EditorConfig is awesome: https://EditorConfig.org
        root = true

        # Matches multiple files with brace expansion notation
        # Set default charset [*.{js,py}]
        [*]
        charset = utf-8
        trim_trailing_whitespace = true
        insert_final_newline = true
        # Tab indentation (no size specified)
        indent_style = tab
        # 2 tab indentation
        tab_width = 2

        max_line_length = 120
        ```
      
3. Установка  **TypeScript**
    - Уставнавливаем TypeScript `npm insall typescript -D`
    - Создаем файл `.tsconfig.json` в корне проекта
    - Добавляем в файл следующую конфигурацию
       
      ```
      {
        "compilerOptions": {
          "target": "es2015",
          "lib": [
            "dom",
            "dom.iterable",
            "esnext"
          ],
          "allowJs": false,
          "skipLibCheck": true,
          "strict": true,
          "strictPropertyInitialization": false,
          "forceConsistentCasingInFileNames": true,
          "noEmit": true,
          "incremental": true,
          "esModuleInterop": true,
          "module": "esnext",
          "moduleResolution": "node",
          "resolveJsonModule": true,
          "isolatedModules": true,
          "jsx": "preserve",
          "plugins": [
            {
              "name": "next"
            }
          ]
        },
        "include": [
          "next-env.d.ts",
          "**/*.ts",
          "**/*.tsx",
          ".next/types/**/*.ts"
        ],
        "exclude": [
          "node_modules"
        ]
      }
      ```
    - Создаем файл `.tsconfig.json` в корне проекта   
    - В IDE устанавливаем плагин **TypeScript** и проверяем чтоб он считывался с node_modules/typescript вашего проекта
   
4. Подключаем **.gitignore** файл
    - Создаем файл `.gitignore` в корне проекта
    - Добавляем в файл следующую конфигурацию 
    
      ```
      # See https://help.github.com/articles/ignoring-files/ for more about ignoring files.

      # dependencies
      /node_modules
      /.pnp
      .pnp.js

      # testing
      /coverage

      # next.js
      /.next/
      /out/

      # production
      /build

      # misc
      .DS_Store
      *.pem

      # debug
      npm-debug.log*
      yarn-debug.log*
      yarn-error.log*
      .pnpm-debug.log*

      # local env files
      .env*.local
      .env

      # vercel
      .vercel

      # IDE or OS
      .idea
      .vscode
      Thumbs.db
      ```
      
 5. Установка  **StyleLint**
    - Создаем файл c в корне проекта
    - Добавляем в файл следующую конфигурацию
        
      ```
      {
        "extends": ["stylelint-config-standard", "stylelint-order-config-standard", "stylelint-config-prettier"],
        "plugins": ["stylelint-order", "stylelint-scss"],
        "rules": {
          "indentation": "tab",
          "color-hex-case": "upper",
          "color-hex-length": "long",
          "color-named": "never",
          "string-quotes": "double",
          "declaration-no-important": true,
          "at-rule-no-unknown": null,
          "scss/dollar-variable-pattern": [
            "^([a-z][a-z0-9]*)(-[a-z0-9]+)*$",
            {
              "message": "Expected variable name in kebab-case"
            }
          ]
        }
      }
      ```
    - Устанавливаем следующие пакеты **поочередно в этой последовательности:**  
    - `npm install stylelint@13.13.1 -D`
    - `npm install stylelint-scss@3.21.0 -D`
    - `npm install stylelint-config-standard@21.0.0 -D`
    - `npm install stylelint-order@4.1.0 -D`
    - `npm install stylelint-order-config-standard@0.1.3 -D`
     
