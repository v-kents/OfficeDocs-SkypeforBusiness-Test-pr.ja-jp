﻿---
title: 'Lync Server 2013: 対話ワークフローの作成または変更'
TOCTitle: 対話ワークフローの作成または変更
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48273405
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での対話ワークフローの作成または変更

 

_**トピックの最終更新日:** 2013-09-11_

対話ワークフローを作成または変更するには、以下のいずれかの手順を使用します。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lync Server 管理シェルまたは 応答グループ構成ツールを使用して、対話ワークフローを作成および変更できます。 Lync Server コントロール パネルから 応答グループ構成ツールにアクセスするか、次の URL を入力して Web ブラウザーから Web ページを直接開くことができます。 <strong>https://</strong> <em>&lt;webPoolFqdn&gt;</em> <strong>/RgsConfig</strong></td>
</tr>
</tbody>
</table>


## 応答グループ構成ツールを使用して対話ワークフローを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**応答グループ**\] をクリックし、\[**ワークフロー**\] をクリックします。

4.  \[**ワークフロー**\] ページで、\[**ワークフローの作成または編集**\] をクリックします。

5.  \[**サービスの選択**\] 検索フィールドに、作成または変更するワークフローをホストする **ApplicationServer** サービスの名前または名前の一部を入力します。表示されたサービスの一覧で、目的のサービスをクリックし、\[**OK**\] をクリックします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>応答グループ構成ツールが開きます。次の URL を入力して、Web ブラウザーから 応答グループ構成ツールを直接開くこともできます。 <strong>https://</strong> <em>&lt;webPoolFqdn&gt;</em> <strong>/RgsConfig</strong></td>
    </tr>
    </tbody>
    </table>


6.  次のいずれかの操作を行います。
    
      - \[**新規ワークフローの作成**\] の \[**対話型**\] の横にある \[**作成**\] をクリックします。
    
      - \[**既存ワークフローの管理**\] で変更するワークフローを見つけて、\[**アクション**\] の \[**編集**\] をクリックします。

7.  ユーザーがワークフローへの通話を開始できる状態ではない場合は、\[**ワークフローのアクティブ化**\] チェック ボックスをオフにします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>管理ワークフローを作成する場合は、[<strong>ワークフローのアクティブ化</strong>] を選択する必要があります。アクティブな管理ワークフローを保存した後、そのワークフローを変更したり、非アクティブ化したりできます。</td>
    </tr>
    </tbody>
    </table>


8.  フェデレーション ユーザーにグループへの通話を許可するには、\[**フェデレーションを有効にする**\] チェック ボックスをオンにします。また、フェデレーション用に構成されている 応答グループ アプリケーションに適用される外部アクセス ポリシーを保持する必要があります。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>グローバル外部アクセス ポリシーは、 応答グループ アプリケーションに適用されます。 Lync Server コントロール パネルを使用するか、 <strong>Set-CsExternalAccessPolicy</strong> コマンドレットを使用して、EnableOutsideAccess パラメーターを True に設定することにより、応答グループ フェデレーション用のグローバル ポリシーを構成することができます。グローバル ポリシー設定は、サイトやユーザー ポリシーに割り当てられていない限り、すべてのユーザーに適用されることに注意してください。そのため、応答グループ向けにこの設定を変更する前に、フェデレーション設定が組織の要件を満たしていることを確認してください。ポリシーをユーザーに適用する方法の詳細については、「<a href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013 での組織の外部アクセス ポリシーの管理</a>」を参照してください。フェデレーション設定の詳細については、「Lync Server 管理シェル」ドキュメントの「<strong>Set-CsExternalAccessPolicy</strong>」を参照してください。</td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Lync Online でホストされているユーザーは、社内展開でホストされている応答グループに通話を発信できません。これは、ハイブリッド展開と、社内展開が Lync Online 展開とフェデレーションされている場合の両方に該当します。</td>
    </tr>
    </tbody>
    </table>


9.  通話中、エージェントの ID を非表示にするには、\[**エージェントの匿名性を有効にする**\] チェック ボックスをオンにします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>匿名の通話は、インスタント メッセージング (IM) やビデオから開始することはできません。ただし、通話の確立後、エージェントまたは発信者が IM やビデオを追加することはできます。匿名のエージェントは、通話の保留、通話の転送 (無条件転送と取次転送)、および通話の保留と保留解除を行うこともできます。匿名の通話では、会議、アプリケーション共有とデスクトップ共有、ファイル転送、ホワイトボードとデータのグループ作業、および通話の記録はサポートされません。Lync VDI プラグインを使用するエージェントは、着信通話を匿名で受信できますが、発信通話を匿名で行うことはできません。</td>
    </tr>
    </tbody>
    </table>


10. \[**通話を受けるグループのアドレスを入力します**\] に、ワークフローへの通話に応答するグループのプライマリ SIP Uniform Resource Identifier (URI) アドレスを入力します。

11. \[**表示名**\] に、ワークフローを表示する名前を入力します (入力例: Sales IVR Response Group)。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>表示名に「&lt;」または「&gt;」という文字を含めないでください。次の表示名は予約されているため、使用しないでください。RGS Presence Watcher または Announcement Service。</td>
    </tr>
    </tbody>
    </table>


12. \[**電話番号**\] に、応答グループの回線 URI を入力します (入力例 +14255550165)。

13. \[**表示番号**\] に、応答グループを表示する番号を入力します (入力例 +1 (425) 555-0165)。

14. (オプション) \[**説明**\] に、 Lync クライアントに連絡先カードを表示するワークフローの説明を入力します。

15. このワークフローを応答グループのマネージャーが管理する場合は、\[**ワークフローの種類**\] で \[**管理**\] を選択します。ワークフローを 応答グループのマネージャーに割り当てるには、次の操作を実行します。
    
    1.  このワークフローのマネージャーの SIP URI を入力して、\[**追加**\] をクリックします。
    
    2.  ワークフローに追加するマネージャーの SIP URI を入力して、\[**追加**\] をクリックします。
    

    > [!IMPORTANT]
    > 応答グループのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。このロールが割り当てられていない場合、ユーザーは応答グループを管理できません。



16. \[**ステップ 2 言語の選択**\] で、音声認識と音声合成で使用する言語をクリックします。

17. 開始メッセージを構成する場合は、\[**ステップ 3 開始メッセージの構成**\] で \[**開始メッセージを再生する**\] チェック ボックスをオンにして、次のいずれかの操作を行います。
    
      - 発信者用の音声に変換される開始メッセージをテキストとして入力するには、\[**音声合成を使用する**\] をクリックして、テキスト ボックスに開始メッセージを入力します。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</td>
        </tr>
        </tbody>
        </table>
    
      - 開始メッセージに Wave または Windows Media オーディオ ファイルの録音を使用するには、\[**録音を選択する**\] をクリックします。新しいオーディオ ファイルをアップロードする場合は、\[**録音**\] リンクをクリックしてください。新しいブラウザー ウィンドウで \[**参照**\] をクリックし、使用するオーディオ ファイルを選択して、\[**開く**\] をクリックします。\[**アップロード**\] をクリックしてオーディオ ファイルを読み込みます。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているファイル形式の詳細については、「<a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</a>」を参照してください。</td>
        </tr>
        </tbody>
        </table>


18. \[**ステップ 4 営業時間の指定**\] の \[**タイム ゾーン**\] ボックスで、ワークフローのタイム ゾーンをクリックします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>このタイム ゾーンは、ワークフローの発信者とエージェントの所在地のタイム ゾーンです。これを使用して、始業時間と終業時間が計算されます。たとえば、北アメリカ東部標準時を使用するようにワークフローが構成されており、ワークフローで始業が午前 7:00、終業が 11:00:00 にスケジュールされている場合は、東部標準時の 7:00 と 23:00 がそれぞれ始業時刻と終業時刻になります (時間は 24 時間表記で入力する必要があります)。</td>
    </tr>
    </tbody>
    </table>


19. 次のいずれかの操作を実行して、使用する営業時間スケジュールの種類を選択します。
    
      - 事前に定義した営業時間スケジュールを使用するには、\[**事前設定したスケジュールを使用する**\] をクリックして、ドロップダウン リストから使用するスケジュールを選択します。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>このオプションを選択できるようにするには、あらかじめ少なくとも 1 つの事前設定スケジュールを定義しておく必要があります。 <strong>New-CSRgsHoursOfBusiness</strong> コマンドレットを使用して事前設定スケジュールを定義します。詳細については、「<a href="lync-server-2013-optional-define-response-group-business-hours.md">(オプション) Lync Server 2013 での応答グループの営業時間の定義</a>」を参照してください。事前設定したスケジュールを選択すると、応答グループの対応日時で、[<strong>曜日</strong>]、[<strong>始業</strong>]、[<strong>終業</strong>] が自動的に設定されます。</td>
        </tr>
        </tbody>
        </table>
    
      - このワークフローのみに適用するカスタム スケジュールを使用するには、\[**カスタム スケジュールを使用する**\] をクリックします。

20. このワークフロー用のカスタム スケジュールを作成する場合は、応答グループが対応可能な曜日のチェック ボックスをオンにします。

21. カスタム スケジュールを作成する場合は、応答グループが対応可能な \[**始業**\] 時間と \[**終業**\] 時間を入力します。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>[<strong>始業</strong>] 時間と [<strong>終業</strong>] 時間は 24 時間表記で入力する必要があります。たとえば、職場の営業時間が営業日の 9 ～ 5 時までで、昼休みのために正午にオフィスを一度閉める場合、営業時間は [<strong>始業</strong>] 9:00、[<strong>終業</strong>] 12:00、[<strong>始業</strong>] 13:00、[<strong>終業</strong>] 17:00 として指定します。</td>
    </tr>
    </tbody>
    </table>


22. 営業時間外にメッセージを再生するには、\[**応答グループの営業時間外にメッセージを再生する**\] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。
    
      - 発信者用に音声に変換されるメッセージをテキストとして入力するには、\[**音声合成を使用する**\] をクリックして、テキスト ボックスにメッセージを入力します。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</td>
        </tr>
        </tbody>
        </table>
    
      - メッセージにオーディオ ファイルの録音を使用するには、\[**録音を選択する**\] をクリックします。新しいオーディオ ファイルをアップロードする場合は、\[**録音**\] リンクをクリックしてください。新しいブラウザー ウィンドウで \[**参照**\] をクリックし、使用するファイルを選択して、\[**開く**\] をクリックします。\[**アップロード**\] をクリックしてオーディオ ファイルを読み込みます。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているファイル形式の詳細については、「<a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</a>」を参照してください。</td>
        </tr>
        </tbody>
        </table>


23. メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。
    
      - 通話を終了するには、\[**終話**\] をクリックします。
    
      - 通話をボイス メールに転送するには、\[**ボイス メールに転送**\] をクリックして、ボイス メール アドレスを入力します。ボイス メール アドレスの形式は *\<user name\>*@ *\<domain name\>* (例: bob@contoso.com) です。
    
      - 通話を別のユーザーに転送するには、\[**SIP URI に転送**\] をクリックして、ユーザー アドレスを入力します。ユーザー アドレスの形式は *\<user name\>*@ *\<domain name\>* です。
    
      - 通話を別の電話番号に転送するには、\[**電話番号に転送**\] をクリックして、電話番号を入力します。電話番号の形式は *\<number\>*@ *\<domain name\>* (例: +14255550121@contoso.com) です。発信者は、ドメイン名を使用して適切な宛先にルーティングされます。

24. \[**ステップ 5 休日の指定**\] で、応答グループが営業しない日を定義する、1 つまたは複数の休日セットのチェック ボックスをオンにします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>ワークフローを構成する前に、休日および休日セットを定義する必要があります。休日および休日セットを定義するには、 <strong>New-CsRgsHoliday</strong> コマンドレットおよび <strong>New-CsRgsHolidaySet</strong> コマンドレットを使用します。詳細については、「<a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(オプション) 応答グループ休日セットの定義</a>」を参照してください。</td>
    </tr>
    </tbody>
    </table>


25. 休日にメッセージを再生するには、\[**休日にメッセージを再生する**\] チェック ボックスをオンにしてから、次のいずれかの操作を実行して再生するメッセージを指定します。
    
      - 発信者用に音声に変換されるメッセージをテキストとして入力するには、\[**音声合成を使用する**\] をクリックして、テキスト ボックスにメッセージを入力します。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</td>
        </tr>
        </tbody>
        </table>
    
      - メッセージにオーディオ ファイルの録音を使用するには、\[**録音を選択する**\] をクリックします。新しいオーディオ ファイルをアップロードする場合は、\[**録音**\] リンクをクリックしてください。新しいブラウザー ウィンドウで \[**参照**\] をクリックし、使用するファイルを選択して、\[**開く**\] をクリックします。\[**アップロード**\] をクリックしてオーディオ ファイルを読み込みます。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているオーディオ ファイル形式の詳細については、「<a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</a>」を参照してください。</td>
        </tr>
        </tbody>
        </table>


26. メッセージが構成されている場合は、メッセージ再生後の通話の処理方法を次のように指定します。
    
      - 通話を終了するには、\[**終話**\] をクリックします。
    
      - 通話をボイス メールに転送するには、\[**ボイス メールに転送**\] をクリックして、ボイス メール アドレスを入力します。ボイス メール アドレスの形式は *\<user name\>*@ *\<domain name\>* (例: bob@contoso.com) です。
    
      - 通話を別のユーザーに転送するには、\[**SIP URI に転送**\] をクリックして、ユーザー アドレスを入力します。ユーザー アドレスの形式は *\<user name\>*@ *\<domain name\>* です。
    
      - 通話を別の電話番号に転送するには、\[**電話番号に転送**\] をクリックして、電話番号を入力します。電話番号の形式は *\<number\>*@ *\<domain name\>* (例: +14255550121@contoso.com) です。発信者は、ドメイン名を使用して適切な宛先にルーティングされます。

27. \[**ステップ 6 保留音の構成**\] で、次のいずれかの操作を実行して、発信者がエージェントの応答を待機しているときの保留音を選択します。
    
      - 既定の保留音の録音を使用する場合は、\[**既定値を使用する**\] をクリックします。
    
      - 保留音にオーディオ ファイルの録音を使用するには、\[**音楽ファイルを選択する**\] をクリックします。新しいオーディオ ファイルをアップロードする場合は、\[**音楽ファイル**\] リンクをクリックします。新しいブラウザー ウィンドウで \[**参照**\] をクリックし、使用するファイルを選択して、\[**開く**\] をクリックします。\[**アップロード**\] をクリックしてオーディオ ファイルを読み込みます。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているファイル形式の詳細については、「<a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</a>」を参照してください。</td>
        </tr>
        </tbody>
        </table>


28. \[**ステップ 7 対話型音声応答の構成**\] の \[**ユーザーには、次のテキストまたは録音メッセージを再生します**\] という見出しの下で、次のように発信者に対する質問を指定します。
    
      - 質問をテキスト形式で入力するには、\[**音声合成を使用する**\] をクリックして、テキスト ボックスに質問を入力します。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>入力するテキストに HTML タグを含めないでください。HTML タグを含めると、エラー メッセージが表示されます。</td>
        </tr>
        </tbody>
        </table>
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>&quot;#&quot; 記号は、音声合成エンジンによって &quot;番号&quot; という語に変換されます。# キーを示す必要がある場合は、記号ではなく、キーの名前を質問に使用してください。たとえば、「営業部門へお問い合わせの場合は、シャープを押してください」のようにします。</td>
        </tr>
        </tbody>
        </table>
    
      - 質問を含む録音済みのオーディオ ファイルを使用する場合は、\[**録音を選択する**\] をクリックし、\[**録音**\] リンクをクリックしてファイルをアップロードします。新しいブラウザー ウィンドウで \[**参照**\] をクリックし、オーディオ ファイルを選択して、\[**開く**\] をクリックします。\[**アップロード**\] をクリックしてファイルを読み込んでから、必要な場合はテキスト ボックスに質問を入力します (これにより、質問と発信者の応答が応答エージェントに転送されます)。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>ユーザーが指定したすべてのオーディオ ファイルは、特定の要件を満たしている必要があります。サポートされているファイル形式の詳細については、「<a href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013 の応答グループの技術要件</a>」を参照してください。</td>
        </tr>
        </tbody>
        </table>


29. \[**応答 1**\] で次の操作を実行して、質問に対する 1 つ目の回答を指定します。
    

    > [!IMPORTANT]
    > いずれの音声応答にも引用符 (") を使用しないでください。引用符は IVR が失敗する原因になります。

    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>発信者が音声、英数字のキーパッド入力、または両方を使用して回答できるようにすることもできます。</td>
    </tr>
    </tbody>
    </table>
    
      - 発信者が音声で応答できるようにする場合は、\[**音声応答の入力**\] に応答を入力します。
    
      - 発信者がキーパッドのキー入力で応答できるようにする場合は、\[**数字**\] で、目的のキーパッドの数字をクリックします。

30. 次のように、発信者をキューにルーティングするか、もう 1 つ質問するかを指定します。
    
      - 発信者をキューにルーティングするには \[**キューに送る**\] をクリックし、\[**キューの選択**\] で使用するキューをクリックします。
    
      - もう 1 つ質問をするには、\[**もう 1 つ質問する**\] をクリックしてから、\[**音声合成を使用する**\] をクリックして質問を入力するか、\[**録音を選択する**\] をクリックします。このセクションにある応答グループを使用して、追加の質問に対する最大 4 つの応答と、各応答で使用するキューを指定します。3 番目または 4 番目の応答を指定するには、\[**応答 3**\] チェック ボックスまたは \[**応答 4**\] チェック ボックスをオンにします。

31. 手順 28 と 29 を繰り返して応答と各応答に対するアクションを指定し、元の質問に対する回答を最大 3 つ追加します。3 番目または 4 番目の回答を指定するには、\[**応答 3**\] チェック ボックスまたは \[**応答 4**\] チェック ボックスをオンにします。

32. \[**展開**\] をクリックします。

## Windows PowerShellを使用して対話ワークフローを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  応答グループ サービスのサービス名を取得し、変数に割り当てます。コマンド ラインで、次のコマンドを実行します。
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  対話ワークフローには、2 つ以上のキューと 2 つ以上のエージェント グループが必要です。まず、エージェント グループを作成します。次のコマンドを実行します。
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  キューを作成します。次のコマンドを実行します。
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  応答グループ プロンプトを作成します。次のコマンドを実行します。
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  次に、プロンプトの後に実行するアクションを作成します。次のコマンドを実行します。
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  最初の応答グループ回答を作成します。次のコマンドを実行します。
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  2 番目のプロンプト、通話アクション、および回答を作成します。まず、プロンプトを作成します。次のコマンドを実行します。
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. 2 番目の通話アクションを作成します。次のコマンドを実行します。
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. 2 番目の応答グループ回答を作成します。次のコマンドを実行します。
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. 最上位のプロンプトを作成します。次のコマンドを実行します。
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. 最上位の質問を作成します。次のコマンドを実行します。
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. ここで、ワークフローを作成します。次のコマンドを実行します。
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>応答グループのマネージャーに指定されているすべてのユーザーに CsResponseGroupManager ロールを割り当てる必要があります。このロールが割り当てられていない場合、ユーザーは応答グループを管理できません。</td>
    </tr>
    </tbody>
    </table>
