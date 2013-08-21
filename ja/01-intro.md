<!-- # Introduction -->
# イントロダクション

<!-- ## Downtime Roulette -->
## ダウンタイム ルーレット

![Gambling With Uptime](../assets/decor/roulette.png)

<!-- Picture a roulette wheel in a casino, where any particular number has a 1 in 37 chance of being hit. Imagine you could place a single bet that a given number will *not* hit (about 97.3% in your favor), and winning would pay out 10 times your wager. Would you make that bet? I'd reach for my wallet so fast my thumb would start a fire on my pocket. -->
カジノのルーレットを想像してください。どんな数でも、37回に1回ヒットするチャンスがあります。どこか1点にそれがヒット*しない*ように賭けてください（当たる確率はおよそ97.3％です）。賞金は賭金の10倍です。賭けますか？　私だったらもうポケットから財布を取り出していますよ。

<!-- Now imagine you could bet again, but only win if the wheel made a sequential 100 spins in your favor, otherwise you lose. Would you still play? Winning a single bet might be easy, but over many trials the odds are not in your favor. -->
もう一度賭けてみましょう。でも、今度は賭けた目が100回続いたときだけ勝ち、そうでないと負けとします。やりますか？　1回くらいなら勝つことができるでしょうが、何度もやるには賭金に見合いません。

<!-- People make these sorts of bets with data all of the time. A single server has a good chance of remaining available. When you run a cluster with thousands of servers, or billions of requests, the odds of any one breaking down becomes the rule. -->
このような賭けをデータに対して常時行っているのです。サーバー1台だけでも十分に利用できます。何千ものサーバーにクラスタがあるとき、あるいは何十億ものリクエストがあるとき、賭けが破綻するのは目に見えています。

<!-- A once-in-a-million disaster is commonplace in light of a billion opportunities. -->
100万回に1回の災害でも、10億回の試せば珍しいものではありません。

<!-- ## What is Riak -->
## Riakって何

<!-- Riak is an open-source, distributed key/value database for high availability, fault-tolerance, and near-linear scalability. In short, Riak has remarkably high uptime and grows with you. -->
Riakはオープンソースの、高可用性分散型キー/バリューデータベースで、耐障害性、ほぼリニアなスケーラビリティを持っています。ひとことで言えば、Riakは極めて稼働時間の長い、成長するデータベースです。

<!-- image: phone with 1/0's flying from it to a disk array -->

<!-- As the modern world stitches itself together with increasingly intricate connections, major shifts are occurring in information management. The web and networked devices spur an explosion of data collection and access unseen in the history of the world. The magnitude of values stored and managed continues to grow at a staggering rate, and in parallel, more people than ever require fast and reliable access to this data. This trend is known as *Big Data*. -->
現代社会は相互に複雑関係で絡まり合っています。情報管理にも大きな転換が起きています。Webおよびネットワークデバイスは、未だかつて誰も見たことのない爆発的なデータを集め、アクセスしています。格納したり管理する値の増加率はますます大きくなり、同時により多くの人が、これまで以上にこのようなデータを、高速かつ確実にアクセスすることを要求しています。このトレンドが*ビッグデータ*と呼ばれています。

<aside id="big-data" class="sidebar"><h3><!-- So What is Big Data? -->それでビッグデータって？</h3>

<!-- There's a lot of discussion around what constitutes <em>Big Data</em>. -->
<em>ビッグデータ</em>が何かに付いては様々な議論があります。

<!-- I have a 6 Terabyte RAID in my house to store videos and other backups. Does that count? On the other hand, CERN grabbed about 200 Petabytes looking for the Higgs boson. -->
私の自宅には6テラバイトのRAIDがあり、ビデオやその他のバックアップを保管しています。これは数えるべきでしょうか？　一方でCERNはヒッグス粒子を探した200ペタバイトのデータを収集しています。

<!-- image: raid box -->

<!-- It's a hard number to pin down, because Big Data is a personal figure. What's big to one might be small to another. This is why many definitions don't refer to byte count at all, but instead about relative potentials. A reasonable, albeit wordy, definition of Big Data is provided by Gartner: -->
はっきりと決めるのは困難です。ビッグデータというのは見方によって変わるからです。ある人がビッグだと思っても、別な人はそう思いません。これが数で表せないさまざまな定義ができる理由です。相対的なものなのです。Gartnerによるビッグデータを次のように定義しています。少々回りくどいですが妥当なものです:

<!-- <blockquote><em>Big Data are high-volume, high-velocity, and/or high-variety information figures that require new forms of processing to enable enhanced decision making, insight discovery and process optimization.</em></blockquote> -->
<blockquote><em>ビッグデータとは大量の、高速で増える、そして/または、バラエティに富んだ情報で、意思決定の強化、真理の発見、処理の効率化を可能とし、そのために新しい処理方法を要するものである。</em></blockquote>
</aside>

<!-- <h3>Always Bet on Riak</h3> -->
<h3>常にRiakに賭ける</h3>

<!-- The sweet spot of Riak is high-volume (data that's available to read and write when you need it), high-velocity (easily responds to growth), and high-variety information figures (you can store any type of data as a value). -->
Riakのおいしいところは、大量の（必要なときに確実にリードおよびライト可能なデータ）、高速で増える（成長に容易に応える）、バラエティに富んだ情報（どのような種類のデータでも）を扱えることです。

<!-- Riak was built as a solution to real Big Data problems, based on the *Amazon Dynamo* design. Dynamo is a highly available design---meaning that it responds to requests quickly at very large scales, even if your application is storing and serving terabytes of data a day. Riak had been used in production prior to being open-sourced in 2009. It's currently used by Github, Comcast, Voxer, Disqus and others, with the larger systems storing hundreds of TBs of data, and handling several GBs per node daily. -->
Riakは*Amazon Dynamo*のデザインをベースに、現実のビッグデータを扱うために作られました。Dyanmoは高可用性デザイン---たとえ毎日テラバイトのデータを格納し、供給するという、非常に大きなスケールでもリクエストに素早く応えます。Riakは2009年にオープンソースとなる前に、プロダクションとして使われました。現在はGithub、Comcast、Voxer、Disqus、その他、何百テラバイトのデータを格納し、毎日ノードごとに数GBもを処理している巨大システムで使用されています。

<!-- Riak was written on the Erlang programming language. Erlang was chosen due to its strong support for concurrency, solid distributed communication, hot code loading, and fault-tolerance. It runs on a virtual machine, so running Riak requires an Erlang installation. -->
RiakはErlangというプログラム言語で書かれています。強力な同時処理能力、強力な分散コミュニケーション能力、ホットコードローディング、耐障害性がErlangを選択した理由です。仮想マシン上で動作するため、Riakを走らせるにはErlangがインストールされている必要があります。

<!- So should you use Riak? A good rule of thumb for potential users is to ask yourself if every moment of downtime will cost you in some way (money, users, etc). Not all systems require such extreme amounts of uptime, and if you don't, Riak may not be for you. -->
いかがですか、Riakを使いたくなりましたか？　ポテンシャルユーザーは、ダウンタイムがいくらくらいコスト（金銭的、ユーザーへの、その他）がかかるかを自問してください。すべてのシステムが稼働時間を絶対視するわけではありません。あなたのシステムがそうであれば、Riakでなくても構いません。

<!-- ## About This Book -->
## この本について

<!-- This is not an "install and follow along" guide. This is a "read and comprehend" guide. Don't feel compelled to have Riak, or even have a computer handy, when starting this book. You may feel like installing at some point, and if so, instructions can be found in the [Riak docs](http://docs.basho.com). -->
本書は「インストールして手順に従ってください」というガイドブックではありません。これは「読んで理解する」ガイドです。本書を始めるに当たって、Riakを持つことを強要するわけではなく、コンピュータを操作させることもありません。その気になったらインストールしてください。そのときは[Riak docs](http://docs.basho.com)に説明があります。

<!-- In my opinion, the most important section of this book is the [concepts chapter](#concepts). If you already have a little knowledge it may start slow, but it picks up in a hurry. After laying the theoretical groundwork, we'll move onto helping [developers](#developers) use Riak, by learning how to query it and tinker with some settings. Finally, we'll go over the basic details that [operators](#operators) should know, such as how to set up a Riak cluster, configure some values, use optional tools, and more. -->
私の意見ですが、本書のもっとも大切な章は[concepts chapter](#concepts)です。すでにいくらかの知識があるなら、はじめはゆっくりですが、急激に理解が進むことでしょう。基礎を学んでから、[開発者](#developpers)がRiakを使う手助けのために、クエリの仕方といくつかの細かい設定を学びます。最終的に、[オペレーター](#operators)が知っておくべき基本の全般、たとえばRiakクラスタのセットアップ方法、値の調整、オプションツールなどを学びます。
