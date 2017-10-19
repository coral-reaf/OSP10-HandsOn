# 1.OSP10 ハンズオン

## 1-1.目的
  Red Hat が提供するOSP10をハンズオンにより実習体験することを目的としたドキュメントです。
  ハンズオンは、Packstackを使ったインストールを実施します。

## 1-2.環境
　環境は以下を前提としています。
　・Workstation：SSHの踏み台ホスト
　　外部 : workstation-<guid>.rhpds.opentlc.com ---> SSH 接続用
　　内部 : workstation.example.com　192.168.0.5
　・Controller：
　　外部 : https://ctrl-<guid>.rhpds.opentlc.com ---> Horizon 接続用
　　内部 : 192.168.0.20
　・Compute Node 01 : 192.168.0.30
　・Compute Node 02 : 192.168.0.31
　・Storage : 192.168.0.40
　・LDAP : 192.168.0.50
 
すべての操作は、お手元の端末から、踏み台のWorkstationに接続し、そこから各OSPを構成する
端末にSSHログオンして実施します。どの端末に対する操作であるかは、[] で示しています。
[Controller]



### ***2-1. OpenShift のWebコンソールにログインし、"New Project" をクリックします。***  
 
   <img src="2-1-1.jpg" alt="attach:cat" title="attach:cat" width="700">  
   　　   　※Webコンソールのアドレスについては別途ご確認ください。  
### ***1-1-2. Name欄に、"nexus-your-name"を入力し、Createをクリックします。***  
 ※your-name にはご自身のお名前をローマ字で入力ください。今回利用する環境はDemo環境で、利用者共有のシステムとなっています。OpenShiftでは、プロジェクト名は一意でなければなりません。プロジェクト名にご自身の名前を入れるのは、プロジェクト名の重複を避けるためです。
<img src="2-1-2.jpg" alt="attach:cat" title="attach:cat" width="700">  
   
  
## 1-2.コンテナのデプロイメント
プロジェクト内にアプリケーションを作成してみます。  

### ***1-2-1. Deploy Imageをクリック。Image Name 欄に、”sonatype/nexus3”を入力の上、右端の*** 🔍 ***アイコンをクリックします。下方に画面をスクロールし、Createをクリックします。***
　![project-Deploy1](./2-2-1-2.jpg)
※Sonatype が提供するDockerレポジトリからのコンテナ取得を行っています。また、詳細パラメータでは、コンテナに独自の構成情報を付加する「環境変数」と、リソースをグループ化し、アクセス制限など細かな制御を実現する「ラベル」の設定が可能であることを確認します（今回は設定しません）。
  　
  　
  　
### ***1-2-2. Continue to overviewをクリックします。***
　![project-Deploy1](./2-2-3.jpg)

Before starting the remaining labs, make sure that your packages are up to date.

Update the packages on all of the nodes:
[Controller node] [Compute nodes] [Storage node]
# yum -y update
If the update contains a new kernel, reboot the nodes:
# reboot
