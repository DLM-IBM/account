---

copyright:

  years: 2015, 2018
lastupdated: "2018-03-08"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 組織およびスペースの作成
{: #orgsspacesusers}

アカウント所有者は、{{site.data.keyword.Bluemix}} コンソールの「組織の管理」ページから、組織とスペースを管理できます。 組織管理者も、「組織の管理」ページを使用して、管理者として自分が設定されている任意の組織を管理できます。
{:shortdesc}

組織とスペースを管理するには、**「管理」** &gt; **「アカウント」** &gt; **「Cloud Foundry の組織」**をクリックします。 


## 組織の作成
{: #createorg}

組織は複数の地域にまたがることができ、以下の項目によって定義されます。

<dl>
<dt>ユーザー</dt>
<dd>組織とスペースの基本的なアクセス権限を付与された役割です。 組織内のスペースに対するその他のアクセス権を付与されるためには、
ユーザーは組織に割り当てられる必要があります。 詳しくは、『[ユーザーと役割 (Users
and roles)](/docs/iam/users_roles.html#userrolesinfo)』を参照してください。</dd>
<dt>ドメイン</dt>
<dd>組織に割り振られるインターネットへの経路を提供します。 経路にはサブドメインとドメインがあります。 サブドメインは通常アプリケーション名です。 ドメインは、システム・ドメイン、またはアプリケーション用に登録した
カスタム・ドメインの場合があります。 『[カスタム・ドメインの管理](/docs/account/manageorg.html#managedomains)』を参照してください。<br/>
<p>**注:** カスタム・ドメインを追加する場合、そのカスタム・ドメインが {{site.data.keyword.Bluemix_notm}} システム・ドメインを指すように解決されるよう、DNS サーバーを構成する必要があります。 この方法では、{{site.data.keyword.Bluemix_notm}}
はカスタム・ドメインの要求を受け取ると、ご使用のアプリケーションに適切に経路指定することができます。</p></dd>
<dt>割り当て量</dt>
<dd>組織による使用に割り振ることが可能なサービス数およびメモリー容量を含む、組織で使用可能なリソースを示します。 割り当て量は、組織の作成時に割り当てられます。 組織内のスペースにおけるアプリケーションまたはサービスはすべて、割り当て量の使用に算入されます。 従量課金 (PAYG) アカウントまたはサブスクリプション・アカウントの場合、組織変更による必要に応じて、Cloud Foundry のアプリケーションおよびコンテナーの割り当て量を調整できます。 『[割り当て量の管理](/docs/account/manageorg.html#managequota)』を参照してください。</dd>
</dl>

サブスクリプション・アカウントでは、割り当て量は、消費量の通知をトリガーするユーザー定義の制限です。
{: tip}

{{site.data.keyword.Bluemix_notm}} では、組織を使用してユーザー間のコラボレーションを可能にし、以下の方法でプロジェクト・リソースの論理的なグループ化を容易にすることができます。

   * スペース、アプリ、サービス、ドメイン、経路、およびユーザーのセットを一緒にして組織内でグループ化できます。 
   * スペースおよび組織へのアクセス権限を、ユーザー・ベースで管理することができます。 

組織を作成する際は、名前は {{site.data.keyword.Bluemix_notm}} で固有にする必要があります。 組織名が別の {{site.data.keyword.Bluemix_notm}} Public、Dedicated、または Local のユーザーによって既に使用されている場合は、新規名を指定する必要があります。 組織を作成したユーザーには、自動的に*組織管理者*許可が割り当てられ、組織名の編集、ユーザーの追加、および組織内のスペースの作成または削除が可能になります。有料アカウントがある場合は、必要な数だけ組織を作成できます。ただし、ライト・アカウントでは、1 つの組織しか持つことができません。 

組織を削除する必要がある場合は、サポートに連絡することができます。組織を削除すると、組織内のすべてのスペース、アプリケーション、およびサービスが削除されます。

以下の[ユーザー役割](/docs/iam/users_roles.html#userrolesinfo)を組織内のユーザーに割り当てることができます。 アカウントに招待されたすべてのユーザーに、監査員の役割がデフォルトで割り当てられます。

   * 組織管理者
   * 組織請求管理者
   * 組織監査員

以下のステップを実行して組織を作成できます。

1. **「管理」** &gt; **「アカウント」** &gt; **「Cloud Foundry の組織」**をクリックします。
2. **「新規 Cloud Foundry 組織の追加」**をクリックします。
3. 組織名を入力します。
4. **「追加」**をクリックします。


## スペースの作成
{: #spaceinfo}

組織内でスペースを使用して、
アプリケーション、サービス、およびユーザーのセットをグループ化することができます。 スペースは、{{site.data.keyword.Bluemix_notm}} 内の特定の地域に関連付けられます。

ユーザーを組織に追加した後、そのメンバーにスペースに対する許可を付与することができます。 組織と同様に、スペースにも、以下のように、チーム・メンバーに割り当てられる、特定の許可を備えた[ユーザー役割](/docs/iam/users_roles.html#userrolesinfo)セットがあります。

  * スペース管理者
  * スペース開発者
  * スペース監査員

ユーザーには、スペース内で少なくとも 1 つのアクセス権が割り当てられていなければなりません。
{: tip}

組織内にスペースを作成できます。例えば、開発環境として *dev* スペース、テスト環境として *test* スペース、実稼働環境として *production* スペースを作成できます。 その後、各スペースにアプリを関連付けることができます。 以下のステップを実行してスペースを作成します。

1. **「管理」** &gt; **「アカウント」** &gt; **「Cloud Foundry の組織」**をクリックします。
2. スペースを追加する組織を決定し、**「詳細を表示」**を選択します。
4. **「Cloud Foundry スペースの追加」**をクリックします。
5. スペース名を入力します。
6. **「追加」**をクリックします。