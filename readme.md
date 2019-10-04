# glassfishソースをwindows環境にgitする

1) ファイル文字列長さを無制限に変更
<pre>
 regedit
     →コンピューター\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem
        →LongPathsEnabledの値を1に変更
</pre>
![additional](https://i.ibb.co/h9dSyjG/my1.png "")　<p>

2) git for windowsをwindows10環境にインストール、git-bash.exeを管理者権限で実行

![additional](https://i.ibb.co/jDthjk7/my2.png "")　<p>

3)起動した管理コンソールでソースをgitする

     git config --system core.longpaths true #Filename too long in Git for Windows
     export http_proxy=zhang-liang%40.jp.fujitsu.com:password@kmt.proxy.nic.fujitsu.com:8080  #proxy設定
     export https_proxy=zhang-liang%40.jp.fujitsu.com:password@kmt.proxy.nic.fujitsu.com:8080 #proxy設定
     env | grep http  #proxy設定確認
     export GIT_SSL_NO_VERIFY=true　　#peer's certificate issuer is not recognized 回避
     git clone -b jdk11 http://sdt-gitlab.vpdc.sg.soft.fujitsu.com/paas-apmmrt/glassfish.git  
    
 
 ![additional](https://i.ibb.co/m0VQrcT/my3.png "")　<p>
 # eclipseでdom.javaの515行をリモートでdebugする。
 1) File→New→Java Project→名前入力(mydemo)→finish　<p>
 2)mydemo右クリック→New→Folder→Advanced→Linked Folde選択→先ほどgitしたglassfish指定→finish　<p>
 
 ![additional](https://i.ibb.co/3MBDyFT/my4.png "")　<p>
 
 3)/mydemo/glassfish/nucleus/hk2/hk2-config/src/main/javaフォルダを右クリック→BUild Path →Use as Source Folder　<p>
 
 ![additional](https://i.ibb.co/b3wfx8S/my5.png "")　<p>
 
 4)Run→Debug Configurations...→Remote Java Application右クリック→New Confiuration 　<p>
 5)naem,projicet, hostとport記入→Apply→Debug # サーバ側起動が前提　<p>
 　
