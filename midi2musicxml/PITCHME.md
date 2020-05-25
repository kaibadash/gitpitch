## MIDI と 歌詞から MusicXML を生成して NEUTRINO に渡して幸せになりたかった


---

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/elasticsearch.png?raw=true)

---

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/slippr.png?raw=true)

---

## 今日のお話

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/midi2musicxml.png?raw=true)

とりあえず歌わせるなら

多分これが一番早いと思います。

---

## NEUTRINO

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/neutrino.png?raw=true)

- 初音ミクみたいなやつ(雑)
- 機械学習を元にリアルに歌ってくれる
- 無料

---

## 現状の問題(1)

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/flow.png?raw=true)

---

## 現状の問題(2)

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/flow2.png?raw=true)

---

## MuseScore辛すぎ

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/musescore.png?raw=true)

音符を選択し… 祈り…
歌詞を1文字入力する…

---

## 歌詞の入力は意外と難しくトライアンドエラーが必要

---

## NG例: チューリップ

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/ng.png?raw=true)

[聞く](https://soundcloud.com/kaibadash/ng-1)

え、MIDI出力からやりなおし…?

その代わり祈る時間が増えた。

---

## OK例: チューリップ

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/ok.png?raw=true)

[聞く](https://soundcloud.com/kaibadash/ok-1)

打ち込む歌詞は「ちゅりぷのはなが」になる。

---

## つらすぎるのでこうしたい

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/midi2musicxml.png?raw=true)

---

## 技術選定

- DTMerはCUIはいじれない人も多い。mac/WindowsでGUIをサポートしたい => あなたとJAVA!
- midiを自前でパースしたくない => あなたとJAVA!
- 形態素解析使いたい => あなたとKuromoji!
- 仕事にも役立つ => あなたとJAVA!
- 音楽ソフトのプラグイン VSTi…? C++…? => あなたとJAVA!

今すぐダウンロー

ド

---

## 技術選定

- あなたとKotlin!
- JavaFX
- Thymeleaf
- Kuromoji
- JUnit
- Gradle
- GitHub Actions

---

## できました!

めでたしめでたし

![](https://github.com/kaibadash/gitpitch/blob/master/midi2musicxml/gui.png?raw=true)

---

## 苦労したところ

---

## MIDI

- MIDIには休符がないが楽譜には休符がある
- Tickという長さ => 音符の変換。

---

## GUI

- JavaFXのCSSはあんまりCSSじゃなかった
- Java11で作ったらJREの配布がJava8までだった
- そこでjpackageでJREを同梱ですよ
- WindowsではWIXが必要。GitHub Actionsではつらそう
- Electronで作るべきだったかも…

---

## その他

- Kuromojiで発音が取れた! 歌詞には最適!
  - こんにちは => こんにちわ
- GitHub Actionsは CircleCIやDroneを使っていれば迷うことはあまりない。Windows、Macもサポート!
- TDDっぽく開発してスムーズにできた

---

## 今後の課題

- いろんなmidiがあるようでうまく動かない場合がある
- 連符のサポート
- NEUTRINOの標準出力をGUIに表示する
- SJIS…まだ生きていたのか…

---

## ありがとうございました！

俺たちの開発はまだこれからだ!

是非使ってみてください。
