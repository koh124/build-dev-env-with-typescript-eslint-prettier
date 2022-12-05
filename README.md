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
