TypescriptでESLint+Prettierを導入するチュートリアル

1.npmでプロジェクトを初期化（package.jsonの生成）
```
$npm init -y
```

2.Typescriptをインストール
```
npm install -D typescript
```

3.Typescriptのコンパイル設定ファイルであるtsconfig.jsonの生成
```
npx tsc --init
```

4.tsファイルを作ってみる
```index.ts
function Hello(text: string): void {
  console.log('Hello, ' + text + '!');
}
const text: string = 'World';
Hello(text);
```

5.コンパイル実行
```
npx tsc index.ts
```

6.node.jsでコンパイルされたjsファイルを実行
```js
node index.js
```

正常に動作したら、コンパイル成功

7.npx eslint --initで対話的にESLint構成を作成する

***中略***

8.ESLintの実行
```
$ npx eslint index.ts
```

9.prettierの実行
```
$ npx prettier --write index.ts
```

----------メモ----------

・npx eslint index.tsでESLintを実行できるが、こんな感じのエラーが出る

Error: Error while loading rule '@typescript-eslint/dot-notation': You have used a rule which requires parserServices to be generated. You must therefore provide a value for the "parserOptions.project" property for @typescript-eslint/parser.

★解決

eslintrc.jsに記述
```
parserOptions: {
  project: ['./tsconfig.json']
}

//tsconfig.eslint.jsonに追記する場合
parserOptions: {
  project: ['./tsconfig.eslint.json']
}

tsconfig.eslint.json
{
  "extends": "./tsconfig.json", //tsconfig.eslint.jsonでtsconfig.jsonを読み込む
}
```
