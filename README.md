# YngLabコーディング規約
本研究室が関わるWebサイト制作プロジェクトにて適用するコーディング規約をまとめます。

最終更新：16/7/27  
**Ver.0.5.0**

***
##この規約に関して
#### このドキュメントの目的
1. **コード品質の安定**
	- メンバー全員がある一定以上の品質でコーディングできる
1. **コミュニケーションコストの削減**
	- メンバー間の連絡や質問事項を減らす
1. **経験から得られる注意事項の共有**
	- 一度学んだことをメンバー間で共有する

#### 運営に関して
- メンバーは開発をするにあたり、この規約を守る必要がある
    - わからない点があれば規約製作者及びメンバーに問い合わせる
- この規約はプロジェクトの進行やメンバーのスキルにより変更することが出来る
    - ただし、変更を行う場合は全メンバーに変更点とその理由を通達し、また同じ内容を最下部パッチノートに追記する

#### 参考にしているWebページ

- [Markdown記法 チートシート - Qiita](http://qiita.com/Qiita/items/c686397e4a0f4f11683d)
- [ベストなコーディング規約の作り方](http://bonk.red/articles/project/coding_rule.html)
- [経験の浅いチームのためのHTML/CSSコーディング規約 - Qiita](http://qiita.com/WalkerEpps/items/9c9a1098404cd89c0068)
- [Googleが推奨しているHTML/CSSコーディングガイドラインをまとめてみました。 | NIWAKASOFT](http://niwakasoft.jp/column/coding_conventions/)
- [あなたのコーディング、大丈夫？ コーディング規約 HTML＋CSS編 | Web制作会社スタイル](http://www.hp-stylelink.com/news/2013/10/20131001.php)
- [HTML5 で省略できるタグ - Qiita](http://qiita.com/labocho/items/54fd70c73ced35c8ba49)

***

## 全体で共通の規約

#### エンコーディング
ソースコードのエンコードは**UTF-8(BOMなし)**を使用する

#### インデント
適切に挿入する  
スペースを2つ使う
> Tabを使いたいという意見はあったが、調べれば調べるほどこちらが一般的だった  
> 上記参考ページ参照

```html
<!-- 推奨 -->
<ul>
  <li>A
</ul>
```
```scss
/*推奨*/
.selector {
  color: black;
}
```
> [Sublime Text 3 - インデントの設定（スペース・タブ） - 開発メモ - Webkaru](http://webkaru.net/dev/sublime-text-3-indent/)

#### コメント
規約から外れた書き方をする場合・他メンバーが理解しづらいと考えられる部分にはコメントを残す

#### 1行1要素
可読性を保持するため1行に書く要素は1つに留める

```html
<!-- 非推奨 -->
<ul>
  <li>A<li>B
</ul>

<!-- 推奨 -->
<ul>
  <li>A
  <li>B
</ul>
```

#### 大文字/小文字
タグやID、色コードなどの記述はDOCTYPE,キャメルケース使用時を覗いて小文字で行う

```html
<!-- 非推奨 -->
<A HREF="#">ABC</A>

<!-- 推奨 -->
<a href="#">ABC</a>
```
```css
/*非推奨*/
.SELECTOR{
  COLOR: #0DAC1A;
}
.MYSELECTOR{
}

/*推奨*/
.selector{
  color: #0dac1a;
}
.mySelector{
}
```
#### 末尾の空白
動作の乱れが発生する場合があるため、末尾の空白は残さない

#### プロトコル
http/httpsは両方のプロトコル上で利用できない場合を除き、省略する

```html
<!-- 非推奨 -->
<script src="http://www.google.com/js/gweb/analytics/autotrack.js"></script>

<!-- 推奨 -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```

## HTMLコーディング規約

#### バージョン
**HTML5**を使用する

#### Doctype宣言
必ず宣言する
```html
<!DOCTYPE html>
```
#### 任意のタグの省略
Googleが推奨しているため導入
> [HTML5 で省略できるタグ - Qiita](http://qiita.com/labocho/items/54fd70c73ced35c8ba49)

```html
<!-- 非推奨 -->
<!DOCTYPE html>
<html>
  <head>
    <title>Spending money, spending bytes</title>
  </head>
  <body>
    <p>Sic.</p>
    <ul>
      <li>A</li>
      <li>B</li>
    </ul>
  </body>
</html>

<!-- 推奨 -->
<!DOCTYPE html>
<title>Saving money, saving bytes</title>
<p>Qed.
<ul>
  <li>A
  <li>B
</ul>

```
> li閉じタグは省略しないと予期しないマージンが入ることがある

#### スタイルシートとスクリプトの属性の省略
typeは自動認識されるため記述しない

```html
<!-- 非推奨 -->
<link rel="stylesheet" href="style.css"
  type="text/css">
<script src="smoothscroll.js"
  type="text/javascript"></script>

<!-- 推奨 -->
<link rel="stylesheet" href="style.css">
<script src="smoothscroll.js"></script>
```

#### スタイリング
外部CSSファイルを参照する

```html
<!-- 非推奨 -->
<style type="text/css">
  .helpButton{
    border: 1px solid #999;
  }
</style>

<p style="color: red">
<big>
<center>
<font>
<tt>

<!-- 推奨 -->
<link rel="stylesheet" href="style.css">
```

#### 引用符
ダブルクオーテーションを使用する

```html
<!-- 非推奨 -->
<a class='sns-button'>Sign in</a>

<!-- 推奨 -->
<a class="sns-button">Sign in</a>
```

#### 閉じないタグ
以下のタグは閉じてはいけない

> 文法が間違っているため予期しない問題が発生することがある

```html
<!-- 推奨 -->
<br>
<hr>
<img>
<link>
<meta>
<input>
```


***

#### パッチノート（更新履歴）
##### Ver.0.5.0
HTMLに関する規約を追記

##### Ver.0.3.2
プロトコルについて追記

##### Ver.0.3.1
一部GitHubの挙動に合わせ修正

##### Ver.0.3.0
共通の規約をまとめた

##### Ver.0.1.3
全体の規約を作成

##### Ver.0.1.2
一部MD記法の修正

##### Ver.0.1.1
運営に関して、パッチノートを追記

##### Ver.0.1.0
このドキュメントに関する情報をまとめた

***

#### このドキュメントの規約（ただのロマン）
#####文末
「。」はつけない  
たくさん並ぶと見づらいため

##### バージョン値について
###### Ver1.0.0以前（Ver1.0.0公開と同時に削除）
- 以下の変更を行った場合、該当する値だけVer.0.b.cのb+する
	- [x] このドキュメントに関する情報をまとめる: 1
	- [x] 共通の規約をまとめる: 2
	- [ ] HTMLに関する規約をまとめる: 2
	- [ ] CSS に関する規約をまとめる: 2
	- [ ] JS  に関する規約をまとめる: 2
	- [ ] PHP,その他に関する規約をまとめる: 1
- 一度コミットしたものに変更を加えた場合、Ver.0.b.cのcを+1する

###### Ver1.0.0以降
- 変更・追記は全て別ブランチ制作/Pull Requestによるマージを行う
− 変更を行った場合、Ver.a.b.cのbを+1する
- 追記を行った場合、Ver.a.b.cのcを+1する
- Ver.a.b.cのaはこのドキュメントの最終更新年度（西暦下二桁）-15とする
