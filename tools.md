# 仮想環境
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)  
過去のバージョン, Extension Packもここにある
- [VMWare OVF Tool](https://my.vmware.com/web/vmware/details?productId=614&downloadGroup=OVFTOOL420)  
VMX -> OVFへの変換に使用

# OS
- [Kali Linux](https://www.offensive-security.com/kali-linux-vm-vmware-virtualbox-image-download/)  
仮想マシン用

# Torrent
- [µtorrent](https://www.utorrent.com/intl/ja/downloads)

# IP確認
- [確認くん](https://www.ugtop.com/spill.shtml)
- [WhatIsMyIPAddress](https://whatismyipaddress.com/)

# 検索
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
