# Adding-prettier-to-projects
### Integrating Prettier + ESLint + Airbnb Style Guide in VSCode

Before we begin, you will have to install npm and then npx.

1. Download the [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) and [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) extensions for VSCode.

2. Install the ESLint and Prettier libraries into our project. In your project’s root directory, you will want to run: 
    ```bash 
    npm install -D eslint prettier
    ```
3. Install the [Airbnb](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb) config. If you’re using npm 5+, you can run this shortcut to install the config and all of its dependencies: 
    ```bash
    npx install-peerdeps --dev eslint-config-airbnb
    ```
4. Install [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier) (disables formatting for ESLint) and [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier) (allows ESLint to show formatting errors as we type) 

    ```bash
    npm install -D eslint-config-prettier eslint-plugin-prettier
    ```    
5. Create ``` .eslintrc.json ```  file in your project’s root directory:

    ```js
    { 
        "extends": ["airbnb", "prettier"],
        "plugins": ["prettier"],
        "rules": {
            "prettier/prettier": ["error"]
        },
    }
    ```

6. Create ``` .prettierrc ``` file in your project’s root directory. This will be where you configure your formatting settings. Example:
    ```js
    {
        "arrowParens": "always",
        "trailingComma": "all",
        "tabWidth": 2,
        "semi": true,
        "singleQuote": true
    }
    ```
    Refer to [Prettier config file](https://github.com/prettier/prettier#configuration-file) for more configurations