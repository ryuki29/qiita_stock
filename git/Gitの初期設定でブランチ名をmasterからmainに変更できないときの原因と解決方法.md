# エラー内容

```git init```の実行後、```git branch -M main```を実行すると、以下のようなエラーが出る。

```
% git branch -M main
error: refname refs/heads/master not found
fatal: Branch rename failed
```

# 解決方法

```README.md```ファイルを新規作成し、```git add```実行後に```git commit```を実行するとエラーは解消され、mainブランチを作成することができる。

```
% touch README.md
% git add README.md
% git commit -m "initial commit"
% git branch -M main
```

上記コマンドを実行後に```git branch```コマンドでブランチ一覧を確認し、mainブランチが作成されていれば成功です！

```
% git branch
* main
```

# エラーの原因
ブランチはコミットへのポインタであるため、コミットが未作成の場合ブランチは存在しません。そのため、存在しないブランチの名前を変更することはできません。

なので、最初のコミットを行うことでブランチが作成され（デフォルトではmaster）、それから（ブランチが存在するので）名前を変更できるようになります。
