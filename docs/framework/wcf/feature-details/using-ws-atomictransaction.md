---
title: Verwenden von WS-AtomicTransaction
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
ms.openlocfilehash: a06d441ad1a48b0ddc8631c362d14a52ae882c3b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584869"
---
# <a name="using-ws-atomictransaction"></a>Verwenden von WS-AtomicTransaction
WS-Atomic-Transaktion (WS-AT) ist ein interoperables Transaktionsprotokoll. Mit diesem Protokoll können Sie verteilte Transaktionen unter Verwendung von Webdienstnachrichten übergeben und interoperativ zwischen heterogenen Transaktionsinfrastrukturen koordinieren. WS-AT verwendet das Zwei-Phasen-Commitprotokoll, um eine unteilbare Ausgabe zwischen verteilten Anwendungen, Transaktions-Managern und Ressourcen-Managern zu erzielen.  
  
 Die WS-AT-Implementierung, die Windows Communication Foundation (WCF) bietet enthält einen der Transaktions-Manager des Microsoft Distributed Transaction Coordinator (MSDTC) integrierten Protokolldienst. Verwenden WS-AT, können WCF-Anwendungen Transaktionen für andere Anwendungen, einschließlich interoperabler Webdienste, die mithilfe von drittanbietertechnologie erstellt fließen.  
  
 Beim Übergeben einer Transaktion zwischen einer Clientanwendung und einer Serveranwendung wird das verwendete Transaktionsprotokoll anhand der Bindung bestimmt, die der Server an dem vom Client ausgewählten Endpunkt verfügbar macht. Einige WCF vom System bereitgestellten Bindungen standardmäßig mit der Angabe der `OleTransactions` Protokoll als transaktionsweitergabeformat an, während andere standardmäßig WS-AT angeben. Sie können die Auswahl des Transaktionsprotokolls in einer vorhandenen Bindung auch programmgesteuert ändern.  
  
 Die Protokollauswahl beeinflusst Folgendes:  
  
-   Das Format der Nachrichtenheader, das zur Weitergabe der Transaktion vom Client an den Server verwendet wird.  
  
-   Das Netzwerkprotokoll, mit dem das Zwei-Phasen-Commitprotokoll zwischen dem Transaktions-Manager des Clients und der Transaktion des Servers ausgeführt wird, um das Ergebnis der Transaktion aufzulösen.  
  
 Wenn der Server und der Client mithilfe von WCF geschrieben werden, müssen Sie keine WS-AT verwenden. Sie können stattdessen die Standardeinstellungen von `NetTcpBinding` mit aktiviertem `TransactionFlow`-Attribut verwenden. Dieses nutzt dann stattdessen das `OleTransactions`-Protokoll. Weitere Informationen finden Sie unter [ \<NetTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md). Andernfalls müssen Sie bei der Weitergabe von Transaktionen an Webdienste, die mit der Technologie von Fremdanbietern erstellt wurden, WS-AT verwenden.  
  
## <a name="see-also"></a>Siehe auch
- [Konfigurieren der Unterstützung von WS-Atomic-Transaction](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
