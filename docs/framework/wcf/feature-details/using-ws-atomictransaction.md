---
title: Verwenden von WS-AtomicTransaction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 124c5dc0f6db94ae459fe140bd7a4290aa56e04a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-ws-atomictransaction"></a>Verwenden von WS-AtomicTransaction
WS-Atomic-Transaktion (WS-AT) ist ein interoperables Transaktionsprotokoll. Mit diesem Protokoll können Sie verteilte Transaktionen unter Verwendung von Webdienstnachrichten übergeben und interoperativ zwischen heterogenen Transaktionsinfrastrukturen koordinieren. WS-AT verwendet das Zwei-Phasen-Commitprotokoll, um eine unteilbare Ausgabe zwischen verteilten Anwendungen, Transaktions-Managern und Ressourcen-Managern zu erzielen.  
  
 Die von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zur Verfügung gestellte WS-AT-Implementierung umfasst einen im Transaktions-Manager von Microsoft Distributed Transaction Coordinator (MSDTC) integrierten Protokolldienst. Mit WS-AT können [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen Transaktionen an andere Anwendungen übergeben, einschließlich interoperabler Webdienste, die mit der Technologie von Fremdanbietern erstellt wurden.  
  
 Beim Übergeben einer Transaktion zwischen einer Clientanwendung und einer Serveranwendung wird das verwendete Transaktionsprotokoll anhand der Bindung bestimmt, die der Server an dem vom Client ausgewählten Endpunkt verfügbar macht. Einige vom System zur Verfügung gestellte [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Bindungen geben standardmäßig das `OleTransactions`-Protokoll als Transaktionsweitergabeformat an, während andere standardmäßig WS-AT angeben. Sie können die Auswahl des Transaktionsprotokolls in einer vorhandenen Bindung auch programmgesteuert ändern.  
  
 Die Protokollauswahl beeinflusst Folgendes:  
  
-   Das Format der Nachrichtenheader, das zur Weitergabe der Transaktion vom Client an den Server verwendet wird.  
  
-   Das Netzwerkprotokoll, mit dem das Zwei-Phasen-Commitprotokoll zwischen dem Transaktions-Manager des Clients und der Transaktion des Servers ausgeführt wird, um das Ergebnis der Transaktion aufzulösen.  
  
 Wenn Server und Client mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] geschrieben werden, müssen Sie kein WS-AT verwenden. Sie können stattdessen die Standardeinstellungen von `NetTcpBinding` mit aktiviertem `TransactionFlow`-Attribut verwenden. Dieses nutzt dann stattdessen das `OleTransactions`-Protokoll. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][ \<NetTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md). Andernfalls müssen Sie bei der Weitergabe von Transaktionen an Webdienste, die mit der Technologie von Fremdanbietern erstellt wurden, WS-AT verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren der Unterstützung von WS-Atomic-Transaction](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
