# vim
## 検索
```
:%s/置換前の文字列/置換後の文字列/g
```

開いているファイル全てにおいて置換をします。置換をするかどうかを確認したい場合は以下のようにcをつけます。
```
:%s/置換前文字列/置換後文字列/gc
```

パス名などを変更する際には/を区切り文字に使うのではなく、;などを区切り文字に使うと便利
```
%s;/var/home;/home;gc
```

[例] - 63行目から79行目まででbeautyをhairnailに一括置換したい時
```
:63,79s /beauty/hairnail/g
```
文章全体でなく、特定範囲のみ置換したい場合は置換したい行の範囲を指定すればよい。

マッチングを利用した置換は正規表現を使います。

## Tios
- リロード
```
:e!
```

- 行番号を表示
```
:set number
```
