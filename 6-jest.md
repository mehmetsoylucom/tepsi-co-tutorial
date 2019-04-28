# Prettier

Vscode plugini olarak `Prettier` kurulur.

```bash
yarn add --dev prettier-eslint prettier-eslint-cli prettier-stylelint
```

Projeyi actiginiz en ust dizinde `.vscode` dizini acilir ve icinde `settings.json` asagidaki icerikle olusturulur.

```json
// .vscode/settings.json
{
  "prettier.eslintIntegration": true,
  "prettier.stylelintIntegration": true,
  "eslint.autoFixOnSave": false,
  "editor.formatOnSave": true
}

```

.eslintrc.json dosyasına prettierın ruleslarını kullanacağımızı belirtiyoruz.

```json
// .eslintrc.json
{
  "parser": "babel-eslint",
  "extends": ["prettier", "react-app", "plugin:prettier/recommended"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": ["error"],
    "jsx-a11y/href-no-hash": [0],
    "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx"] }]
  }
}
```

package.json içersine bu scriptleri ekledikten sonra işlem tamamdır.

```json
// package.json
{
  "scripts": {
    "fix-code": "prettier-eslint --write 'source/**/*.{js,jsx}' ",
    "fix-styles": "prettier-stylelint --write 'source/**/*.{css,scss}' "
  }
}
```