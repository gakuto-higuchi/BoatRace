これは大学2回生時の8月から作り始めた競艇の予測AIです。

8/24
	今までやってきたcsvfileではlightgbmのランキング学習に適応できないとのことなので、
	もう一度、1からcsvfileを作らなければならないことになりました。

8/25
	もう一度、csvfileを作っているのですが、予想以上に難しい。地道にやっていくほかなさそうですね。csvfileのencodingをshift_jisからutf-8に変更
	心が折れそうなので、、一旦競走成績の方の前処理ができたらlightgbmにぶちこむ
	(後に番組表の方もやっていく)

8/27
	やっと試行錯誤してランキング学習用のcsvfileができました。
	正規表現の使い方が上達しました。感謝感謝
	とりあえず競走成績の方のcsvfileが完成したので学習させてみたい
	(results_csvがランキング学習用のcsvfileでodds_results.csvが元のcsvfileです。)
	raceタイムの　.. という欠損値をどう対処しようか考え中...
	大雑把に正規表現でデータを取得していたのですが、いらないデータがcsvfileに入っていたことが発覚しました。なえました。修正します。

8/28
	wind以降のデータが正規表現でうまく取得できなくて苦戦中
	どうやったらええんや
	できない可能性として挙げられるのは、データを年単位で取得しているので、どこかでデータの形式が変更された可能性がある。対策としてはlist以外の方法で取得する？？
	柔軟な対応が思いつかない今日この頃

8/30
	8/28のwind以降のデータですが、listをcontents[-3]というふうにすれば、綺麗に取得できたので、問題解決できました。
	まだraceタイムの欠損値をどう対処するかは考え中
	これから前処理をしていく。特徴量をどうするかやなぁ。本を参考にしながらいい感じにしていこうと思う。

8/31
	焼肉を人のお金で食す。元気が出た。

9/1
	1 race_code,name,dateの二つをdropして、place,round,type,weather,windをlabel encoding。race_dateをdatetime形式に変更したい

9/6
	東京大学の自然言語処理サマースクールの講義を受けているので、deeplearningとnlpを復習中。
	落ち着いたら競艇AIに戻ろうと考えています。

10/6
	やっと戻ってきました。夏休みを忙しくて、こちらの趣味に手が回りませんでした。ちょうど１ヶ月ですね。
	お金が金欠中なのでできるだけ早く開発して一発当てていきたいモノですね。
	とりあえずデータの前処理をやっていきます。