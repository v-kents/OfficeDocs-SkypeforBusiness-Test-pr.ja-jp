﻿---
title: 'Lync Server 2013: エッジ コンポーネントの証明書を要求する'
TOCTitle: エッジ コンポーネントの証明書を要求する
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48272781
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でエッジ コンポーネントの証明書を要求する

 

_**トピックの最終更新日:** 2013-11-07_

外部ユーザー アクセスのサポートに必要な証明書には、パブリック証明機関 (CA) が発行する証明書および内部のエンタープライズ CA が発行する証明書があります。

  - エッジ サーバーとリバース プロキシの外部インターフェイスに必要な証明書は、パブリック CA から発行される必要があります。

  - 内部インターフェイスに必要な証明書は、パブリック CA または内部のエンタープライズ CA から発行できます。これらの証明書を作成するときは、内部の Windows Server 2008 CA、Windows Server 2008 R2 CA、Windows Server 2012 CA、または Windows Server 2012 R2 CA を使用して、パブリック証明書を使用するコストを節約することをお勧めします。


> [!IMPORTANT]
> 証明書の要求、特にパブリック CA に証明書を要求した場合は、処理に時間がかかる可能性があります。したがって、エッジ サーバーの証明書は早めに要求し、エッジ サーバー コンポーネントの展開を開始するときには証明書を使用できるようになっている必要があります。 エッジ サーバーの証明書要件の概要については、「<A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 における外部ユーザー アクセスに対する証明書要件</A>」を参照してください。



内部エッジの証明書にパブリック CA を使用するという選択肢もありますが、証明書のコストを最小限に抑える代わりに、これらの他の証明書には内部エンタープライズ CA を使用することをお勧めします。 エッジ サーバーの証明書要件の概要については、「[Lync Server 2013 における外部ユーザー アクセスに対する証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>エッジ サーバーをインストールするときは、証明書ウィザードを実行します。このウィザードを使用すると、「<a href="lync-server-2013-set-up-edge-certificates.md">Lync Server 2013 用のエッジ証明書のセットアップ</a>」に記載される証明書の要求、割り当て、およびインストール作業を容易に実行できます。エッジ サーバーをインストールする前に証明書を要求する場合 (たとえば、エッジ サーバー コンポーネントの実際の展開時に時間を節約するために)、証明書がエクスポート可能で、かつ必要なすべてのサブジェクトの別名が含まれていれば、内部サーバーを使用して証明書を要求できます。このドキュメントでは、内部サーバーを使用して証明書を要求する手順については説明しません。</td>
</tr>
</tbody>
</table>


## 証明書をパブリック CA に要求する

エッジ サーバーの展開には、エッジ サーバーの外部インターフェイス用にパブリック証明書が 1 つ必要です。この証明書は、アクセス エッジ サービス、Web 会議エッジ サービス、および音声ビデオ認証サービスに使用されます。この証明書には、エクスポート可能な秘密キーが必要で、音声ビデオ認証サービスはプール内のすべての エッジ サーバーで同じキーを使用する必要があります。Microsoft Internet Security and Acceleration (ISA) Server 2006 や Microsoft Forefront Threat Management Gateway 2010 で使用されるリバース プロキシにも、パブリック証明書が必要です。

## 証明書を内部エンタープライズ CA に要求する

内部エッジ インターフェイスに必要な証明書は、パブリック証明機関 (CA) または内部 CA から発行されます。内部エンタープライズ CA を使用して、証明書のコストを最小限に抑えることができます。組織で内部 CA が展開されている場合、内部エッジの証明書は内部 CA から発行されます。内部証明書に内部エンタープライズ CA を使用すると、証明書のコストを削減できます。

エッジ コンポーネントの証明書要件の概要については、「[Lync Server 2013 における外部ユーザー アクセスに対する証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。パブリック CA を使用して証明書を取得する方法の詳細については、「[Lync Server 2013 でエッジ コンポーネントの証明書を要求する](lync-server-2013-request-certificates-for-edge-components.md)」を参照してください。証明書の要求、インストール、および割り当ての詳細については、「[Lync Server 2013 用のエッジ証明書のセットアップ](lync-server-2013-set-up-edge-certificates.md)」を参照してください。
