﻿---
title: 外部ユーザーに対するリモート アクセスおよびフェデレーションの確認
TOCTitle: 外部ユーザーに対するリモート アクセスおよびフェデレーションの確認
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49887085
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 外部ユーザーに対するリモート アクセスおよびフェデレーションの確認

 

_**トピックの最終更新日:** 2012-09-18_

フェデレーション ルートを Lync Server 2013 の エッジ サーバーに移行した後、いくつかの機能テストを実行して、フェデレーションが期待どおりに動作していることを確認する必要があります。外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各種類の外部ユーザーを含める必要があります。

## 外部ユーザーの接続と外部アクセスをテストするには

  - 少なくとも 1 つのフェデレーション ドメインのユーザー、 Lync Server 2013 の内部ユーザー、および Lync Server 2010 のユーザー。インスタント メッセージング (IM)、プレゼンス、音声ビデオ (A/V)、およびデスクトップ共有をテストします。

  - Lync Server 2013 のユーザーおよび Lync Server 2010 のユーザーと通信している、組織がサポート (およびプロビジョニングが完了) している各パブリック IM プロバイダーのユーザー。

  - 匿名ユーザーが会議に参加できることを確認します。

  - リモート ユーザー アクセスを使用する Lync Server 2010 でホストされたユーザー (イントラネットの外部から Lync Server 2010 にログイン、ただし VPN は不使用) と、 Lync Server 2013 上のユーザーおよび Lync Server 2010 上のユーザー。IM、プレゼンス、A/V、およびデスクトップ共有をテストします。

  - リモート ユーザー アクセスを使用する Lync Server 2013 でホストされたユーザー (イントラネットの外部から Lync Server 2013 にログイン、ただし VPN は不使用) と、 Lync Server 2013 上のユーザーおよび Lync Server 2010 上のユーザー。IM、プレゼンス、A/V、およびデスクトップ共有をテストします。
