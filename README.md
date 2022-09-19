<h1>TwitterAPI v2_reserach_and_ranking</h1>
 APIv2で特定のワードを100抽出した後、比べたいワードを複数指定しランキング形式で出力します<br>
<br>
<h2>手順(内容はソースコードTwitterAPIv2_reseach_ranking参照）</h2>
TwitterAPIv2 tweepyを用いて、<br>
特定のワードを含む間近100件のツイートを取得後※1<br>

その母集団100件に任意のワード※2 <br>
を含むツイートがどのくらいの比率で返ってきているかを断続的に可視化します。

使用例)
※1 #〇〇人気投票　#〇〇選手権<br>
※2 〇〇人気投票のキャラ名　〇〇選手権の出場者名　（複数選択）

例の様に、ハッシュタグ〇〇人気投票などの中でどのキャラクター（人物）
が実際にどれくらいの割合でツイートされているのかを可視化することができます。

プログラムを出力するファイル（csvとpng)はカレントディレクトリに置いておいてください。
今回はファイル名（mons.csvとimage.png)で最初からGithub上に設置しています。
（作成していなくてもコード内のcsv,png両ファイルとも指定した名前のファイルが実行時にできます。）

今回のソースコードではscheduleを1分毎にスリープ1秒としていますが、
任意の時間ごとに取得することで検索したツイートの重複をさけることもできます。

<h2>今回のプログラムでの検索内容</h2>
今回のコード内では例として、ゲームの【モンスターハンター】で使用されるタグ【#MHRise】ツイート100件を取得し、
その中に特定のモンスター名がどの程度の割合で出現するかをランキングとして見れるようなソースコードとして書いています。

<h2>今後の展望</h2>
最初に抽出する100ツイートのうちの「特定のキーワード」をある程度の数量含むという条件部分は、
ソースコードを変更、もしくは検索条件の検討の余地あり。
今回のMHRiseでは数回の取得で十分な比較対象数が抽出できたとはいいがたかった為。
一回のツイート取得（100件）で、それぞれの出現ワードの数値が十分取得できるようにAPIからのデータ取得を改善する余地がある。

また、十分な数値がある程度の期間で母数として集まる検索条件、もしくはソースコードの変更ができれば、
取得したデータをもとに次のプログラム実行時にどのような比率で返ってくるかなどを予測するAIプログラムなどの作成にも
今回作ったTwitterv2_reseach_and_rankingを発展させていく予定あり。
