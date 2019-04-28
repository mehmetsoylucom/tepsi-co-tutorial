# Eslint

```
yarn add eslint --dev
```

Ubuntu 18.04 icin Eslint'i projeye eklemek uzere terminale;

```
./node_modules/.bin/eslint --init
```

Bu asamada configurasyon formati olarak JSON seciliyor.

Sonucta `.eslintrc.json` isminde bir configurasyon dosyasi olusuyor. Dosya olustuktan sonra `vscode` otomatik olarak dahil ediyor.

Eslint icin ortam olarak `browser`, `node` ve `es6` aktif olarak sectim.

```package.json``` icinde eslint kodunu ekleyelim.

```json
"scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "lint:eslint": "eslint .", // eklenen bu satir 
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
```

Artik terminalde 

```bash
yarn run lint:eslint
``` 

yazinca `eslint` hatalari gosteriyor. 

`it` keyword icin cikan hata `Jest` ile ilgili. Hatayi duzeltmek icin `.eslinttrc.json` genisletiliyor.

```json
  "env": {
    "browser": true,
    "jest": true  
  },
```


```NOT : ```
tepsi.co icin video ders kapsaminda verilmis `create-react-app pek` cok `eslint` hatasina sahip. yeni versiyon ise bu hatalar giderilmis ve muhtemelen `eslint` versiyonu da degistigi icin videodaki duzeltmelerin bazilari sorunsuz olarak var.

Ayrica `eslint` kurulus sekli ve secilen standart icin farkli ayarlar sunuyor. `zsh` yuklu terminalde ise `./node_modules/.bin/eslint .` seklinde cagirmak ise yariyor.