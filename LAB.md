# 1.OSP10 ハンズオン

## 1-1.目的
  Red Hat が提供するOSP10のハンズオン実習を
   
### ***1-1-1. OpenShift のWebコンソールにログインし、"New Project" をクリックします。***  
 
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

