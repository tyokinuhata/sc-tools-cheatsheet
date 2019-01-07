# 仮想環境
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)  
過去のバージョン, Extension Packもここにある.
- [VMWare OVF Tool](https://my.vmware.com/web/vmware/details?productId=614&downloadGroup=OVFTOOL420)  
VMX形式からOVF形式への変換に使用した.

# OS
- [Kali Linux](https://www.offensive-security.com/kali-linux-vm-vmware-virtualbox-image-download/)  
仮想マシン用のイメージファイル.
- [Windows 7](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/)  
仮想マシン用のイメージファイル.  
あくまでIEの検証用ということに注意する.  
無償で60日間使用できる.
- [Windows10](https://www.microsoft.com/ja-jp/software-download/windows10ISO)  
ISO形式で配布されている.  
エディションはS/Home/Education/Proの中から選択可能.  
この中ではProが一番強い.  
ライセンスの猶予期間はあるが, 猶予期間30日で猶予期限リセット可能回数が1000回以上あるので実質無制限.
- [Windows 10 Enterprise](https://www.microsoft.com/ja-jp/evalcenter/evaluate-windows-10-enterprise)  
Windows 10のEnterpriseエディションの試用版が配布されている.  
ISO形式.

# 脆弱性体験ツール
- [Metasploitable 2](https://sourceforge.net/projects/metasploitable/files/MetaSploitable2/)  
あえて脆弱性が存在する状態で構成されたLinuxディストリビューション.  
現在はMetasploitable 3も出ているのでそっちを触るのも良い.
- [DVWA](http://dvwa.co.uk/)  
DVWA(Damn Vulnerable Web App)はあえて脆弱性が存在する状態で構成されたWebアプリケーション.  
上述したMetasploitable 2にもDVWAが組み込まれているが, Metasploitable 2自体がそもそもメンテナンスされていないので別途入れることをオススメする.
- [bWAPP bee-box](https://sourceforge.net/projects/bwapp/files/bee-box/)  
Webセキュリティを学習するためのWebアプリケーション.

# Torrent
- [µtorrent](https://www.utorrent.com/intl/ja/downloads)

# ファイル検索
- locate  
ファイルやコマンドのパスを検索できるコマンド.  
`$ locate <検索キーワード>` で検索できる.
`$ updatedb` で検索に使用されるDBを更新できるが, １日１回ぐらいは自動更新されているっぽい.
- find  
指定したディレクトリ配下のファイルやコマンドを検索できるコマンド.  
`$ find <ディレクトリ名> -name <検索キーワード>` で検索できる.  
正規表現やファイルのみ/ディレクトリのみ, のような指定ができるので柔軟性が高い.
- apt-file  
ソースコードを読みたいコマンドがどのパッケージに含まれているかを確認できる.  
`$ apt install apt-file` でインストール.  
`$ apt-file search <コマンドのパス>` で検索.
- grep  
ファイル内の文字列を検索できるコマンド.  
`$ grep <正規表現> <ファイル名>` で検索できる.

# ネットワーク調査
- ifconfig  
`$ ifconfig` で端末のインタフェース情報表示, `$ ifconfig <インタフェース名> <up/down>` でインタフェースをup/downできる.
- iwconfig  
`$ iwconfig` で無線LANアダプタの情報表示, `$ iwconfig <無線LANインタフェース名> mode <managed/monitor>` でモードの変更を行える.
- route  
ルーティングテーブルを確認できるコマンド.
- arp  
ARPテーブルを表示するコマンド.
- ip  
`ip addr`/`ip a`/`ip address`で端末のインタフェース情報を確認できる.  
`ifconfig`の後継.  
`ip route`/`ip r`で端末のルーティングテーブルを確認できる.  
`route`の後継.  
`ip neigh`/`ip n`/`ip neighbor`でARPテーブルを確認できる.  
`arp`の後継.
- [確認くん](https://www.ugtop.com/spill.shtml)  
IPアドレス, その他接続端末の情報表示.  
- [WhatIsMyIPAddress](https://whatismyipaddress.com/)  
IPアドレス, その他接続端末の情報表示.  
- iw  
`$ iw <無線LANインタフェース名> link` で指定した無線LANインタフェースの接続状況を確認できる.
- netstat  
TCP/IPでの通信の状態を確認できるコマンド.  
ちなみに`netstat`の後継コマンドには`ss`がある.
`$ netstat -a` で状態が`LISTENING`であるコネクション一覧を表示可能.  
また, `-n`オプションを付けることで名前解決せずに表示できる(そのため時間がかからない).
- [Netcat](http://netcat.sourceforge.net/)  
ネットワークを介してデータを送受信できるコマンド.  
`$ nc -lvp <ポート番号>` で指定したポートでサーバを待ち受け状態にできる.  
`-l`オプションで待受け状態, `-v`オプションで冗長モード(表示内容が増える), `-p`オプションでポート番号を指定する.  
`$ nc <IPアドレス> <ポート番号>` で指定したIPアドレスの指定したポート番号に接続できる.  
[Netcat for Windows](https://joncraton.org/blog/46/netcat-for-windows/)もある.
- [nmap](https://nmap.org/)  
高機能なポートスキャナー.  
`$ nmap <IPアドレス>` でポートスキャンできる.  
`-sV`オプションで各ポートのサービスのバージョンまで検出, `-O`オプションでターゲットのOSの特定, `-p-`オプションでポート番号1番 ~ 65535番までを対象とする.
- Wash
WPS(WiFi Protected Setup)という簡単に端末を無線LANに接続できる仕組みの状態をスキャンするツール.  
`$ wash -i <無線LANインタフェース名>` でスキャン可能.
- iwlist  
APをスキャンし各種情報を取得できるコマンド.  
`$ iwlist <無線LANのインタフェース名> scan` でスキャンできる.
- wifite
周辺にあるAPをスキャンできるツール.  
`$ wifite` で起動すると自動でスキャンがかかる.
- [Wifi Analyzer](https://play.google.com/store/apps/details?id=com.farproc.wifi.analyzer)  
無線LANの状況をグラフィカルに表示できるAndroidアプリ.
- [Fing](https://play.google.com/store/apps/details?id=com.overlook.android.fing)  
各種ネットワークユーティリティを備えたAndroidアプリ.

# パケット解析
- [Wireshark](https://www.wireshark.org/)  
LANに流れるデータをキャプチャできるアプリケーション.  
様々なOSで動作し, GUIで操作できる.  
`$ wireshark` で起動する.
- tshark  
WiresharkのCUI版アプリケーション.  
パケットキャプチャは重い処理であり, GUIとなるとより重くなるため, tsharkが使用されることがある.  
`$ tshark -i <インタフェース名> -c <パケット数>` で指定したインタフェースの指定した個数のパケットをキャプチャできる.  
また, `-f`オプションでTCP or UDPやポート番号の指定(`-f "udp port 53"`のようにする)や, `-w`オプションでキャプチャファイルの読み込みができる.
- [NetworkMiner](https://www.netresec.com/?page=networkminer)  
キャプチャファイルを読み込むと自動的に中に含まれるファイルを識別してくれるため便利.  
ただし, `pcapng`形式は読み込めない.
- [Xplico](https://www.xplico.org/)  
キャプチャファイルを読み込んで解析したり, リアルタイムにパケットを解析することができるアプリケーション.  
画像やメールの解析が得意.  
`apt install xplico` でインストールできる.
- xxd  
ファイルを16進数または2進数でダンプできるコマンド.  
`$ xxd <ファイル名>` でダンプできる.

# ネットワーク攻撃
- macchanger  
無線LANアダプタのMACアドレスを偽装する.  
`$ macchanger -s <インタフェース名>` で指定したインタフェースのMACアドレスを確認, `$ macchanger --mac=<MACアドレス> <インタフェース名>` で指定したインタフェースを指定したMACアドレスに偽装できる.
- arpspoof  
偽装したARPパケットを送信するコマンド.  
`$ arpspoof -i <インタフェース名> -t <ターゲットのIPアドレス> <書き換えたいIPアドレス>` でターゲットのIPアドレスに対して偽装したARPパケットを送信し, ARPテーブルを汚染できる.
- [MITMf](https://github.com/byt3bl33d3r/MITMf)  
中間者攻撃(Man-in-the-middle attack)を支援するアプリケーション.  
SSLstrip攻撃を利用し, ARPスプーフィングやDNSスプーフィングなど様々な攻撃を行える.  
`$ apt install mitmf` でインストール.  
ARPスプーフィングの場合, `$ mitmf -i <インタフェース名> --arp --spoof --gateway <ルーターのIPアドレス> --target <ターゲットのIPアドレス>` を実行すれば良い.
- [BeEF](https://beefproject.com/)  
ブラウザに焦点を当てたペネトレーションツール.  
MITMfの`--js-url`オプションにBeEFに用意されているスクリプトを指定し, Webページにスクリプトを埋め込む, といった使い方ができる.
- [Aircrack-ng](https://www.aircrack-ng.org/)  
無線LANに対する各種攻撃を行えるツール.  
`$ airmon-ng` コマンドでは認識している無線LANアダプタのドライバ名やチップセット名を表示できる.  
また, インタフェースのup/downも行える.  
`$ airodump-ng <無線LANインタフェース名>` では指定した無線LANインタフェースに対応するAPをスキャンする.  
また, 簡単なパケットキャプチャなども行える.  
`$ aircrack-ng <キャプチャファイル名>` でキャプチャファイルを読み込み, パスワード解析を行える.  
WEPキーぐらいなら割と簡単に特定できる.  
`$ aireplay-ng` ではAPに対して偽の認証を行ったり, KoreK chopchop attack, ARP要求リプレイ攻撃といったWEPに対する攻撃を行える.  
`$ packetforge-ng` では自作のパケットを作成し, 送信することができる.
- [WiFi Pumpkin](https://github.com/P0cL4bs/WiFi-Pumpkin/issues?q=is%3Aissue+is%3Aclosed)  
おとりAPを立ち上げられるアプリケーション.
- [Burp](https://portswigger.net/burp/)  
ローカルProxyの一種で, HTTPリクエストを確認したり, 様々な情報を補足することができる.

# 脆弱性検査
- [Metasploit Framework](https://www.metasploit.com/)  
調査, 侵入, 攻撃, バックドアの設置, 接続など, サーバ侵入における一連の攻撃をサポートするアプリケーション.  
`$ msfconsole` で起動できる.  
また, `msfvenom -p <ペイロード名>` でペイロードの作成ができる.
- [LaZagne](https://github.com/AlessandroZ/LaZagne)  
ローカルPC内のパスワードを収集できるアプリケーション.  
Windows/Mac/Linux用が用意されている.
- [Veil Framework](https://www.veil-framework.com/)  
アンチウイルスをバイパスするExploitコードを生成するアプリケーション.  
`$ apt install veil-evasion` でインストール.  
`$ veil` で起動.  
- [Shellter](https://www.shellterproject.com/)  
実行形式のファイルにExploitコードを埋め込んだりできる.  
`$ apt install shellter` でインストール.  
`$ shellter` で起動.
- [MacroShop](https://github.com/khr0x40sh/MacroShop)  
MS Officeのマクロ機能でのExploitコードの実行を支援するスクリプト郡.
- [CVE Details](https://www.cvedetails.com/)  
様々なアプリケーションの脆弱性情報の検索サービス.
- [EXPLOIT DATABASE](https://www.exploit-db.com/)  
様々なアプリケーションの脆弱性情報の検索サービス.
- [Sqlmap](http://sqlmap.org/)  
ブラインドSQLインジェクションの脆弱性を持つWebサイトのDBやテーブルの情報の洗い出し, パスワード解析などを行う.

# マルウェア解析
- [VirusTotal](https://www.virustotal.com/ja/)  
実行ファイルを様々なアンチウイルスに通し, いくつのアンチウイルスに引っかかるかを調査できるWebサービス.

# パスワード解析
- [Hydra](https://github.com/vanhauser-thc/thc-hydra)  
オンラインパスワードクラッカー.  
辞書攻撃の場合, `hydra -L <ユーザリスト> -P <パスワードリスト> <IPアドレス> <サービスプロトコル名>` で解析可能.  
また`-t <数値>`オプションでターゲットに対する並列処理のタスク数を指定可能(デフォルトは16).  
xHydraというHydraのGUI版も提供されている.
- [Patator](https://github.com/lanjelot/patator)  
オンラインパスワードクラッカー.  
辞書攻撃の場合, `patator <モジュール名> host=<IPアドレス> user=FILE0 password=FILE1 0=<ユーザリスト> 1=<パスワードリスト>` で解析可能.  
Patatorでは認証毎にモジュールが用意されており, SSHの場合はモジュール名に`ssh_login`を指定する.
- crunch  
辞書ファイルの生成を行える.  
`$ crunch <最小桁数> <最大桁数> -t <対象とする文字列> <候補文字>` または `$ crunch <最小桁数> <最大桁数> -t <対象とする文字列> -f <セットファイル> <パターン>` のように指定する.  
crunchにはセットファイルとして`/usr/share/crunch/charset.lst`が用意されている.  
具体的な使用方法だが, 前半７桁が既知である１３桁のWEPキーの辞書ファイルを生成する場合, `$ crunch 13 13 -t 1234567%%%%%% 1234567890` または `$ crunch 13 13 -t 1234567%%%%%% -f /usr/share/crunch/charset.lst numeric` とする.  
すると1234567000000 ~ 1234567999999の辞書ファイルが生成される.
- [wpa2-wordlists](https://github.com/kennyn510/wpa2-wordlists)  
WPA2キーの辞書ファイル.
- [CrackStation](https://crackstation.net/)  
ハッシュ値を解析するWebサービス.
- [MD5 Online](https://www.md5online.org/)  
MD5のハッシュ値を解析できるWebサービス.
- [findmyhash](https://github.com/frdmn/findmyhash)  
様々なハッシュ値の解析サービスを自動で巡回して解析を試みるツール.  
例えばMD5のハッシュ値を解析したい場合, `$ findmyhash MD5 -h <ハッシュ値>` のように指定する.

# ログ改竄
- shred  
rmコマンドではファイルの内容が完全に削除されないため, このコマンドを使用することがある.  
`$ shred -n <書き込み回数> -zu <ログのパス>` で該当するログを`-n`オプションで指定した回数だけランダムに書き込み, `-z`オプションを付けた場合は最後に０を書き込む.

# 匿名化
- Tor  
`apt install tor` でインストールできる.
