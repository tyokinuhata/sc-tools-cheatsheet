# 仮想環境
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)  
過去のバージョン, Extension Packもここにある.
- [VMWare OVF Tool](https://my.vmware.com/web/vmware/details?productId=614&downloadGroup=OVFTOOL420)  
VMX -> OVFへの変換に使用した.

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
- [確認くん](https://www.ugtop.com/spill.shtml)  
IPアドレス, その他接続端末の情報表示.  
- [WhatIsMyIPAddress](https://whatismyipaddress.com/)  
IPアドレス, その他接続端末の情報表示.  
- netstat  
TCP/IPでの通信の状態を確認できるコマンド.  
`$ netstat -a` で状態が`LISTENING`であるコネクション一覧を表示可能.  
また, `-n`オプションを付けることで名前解決せずに表示できる(そのため時間がかからない).
- [Netcat](http://netcat.sourceforge.net/)  
ネットワークを介してデータを送受信できるコマンド.  
Kali Linuxではデフォルトでインストールされている.  
`$ nc -lvp <ポート番号>` で指定したポートでサーバを待ち受け状態にできる.  
`$ nc <IPアドレス> <ポート番号>` で指定したIPアドレスの指定したポート番号に接続できる.  
[Netcat for Windows](https://joncraton.org/blog/46/netcat-for-windows/)もある

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
`$ apt install shellter` でインストール.  
`$ shellter` で起動.  
実行形式のファイルにExploitコードを埋め込んだりできる.
- [MacroShop](https://github.com/khr0x40sh/MacroShop)  
MS Officeのマクロ機能でのExploitコードの実行を支援するスクリプト郡.

# マルウェア解析
- [VirusTotal](https://www.virustotal.com/ja/)  
実行ファイルを様々なアンチウイルスに通し, いくつのアンチウイルスに引っかかるかを調査できるWebサービス.
