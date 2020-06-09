---
title: Verwenden von WS-AtomicTransaction
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
ms.openlocfilehash: 71090efbb096bc3b7b3d6bcf40ff496b78ac6252
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600684"
---
# <a name="using-ws-atomictransaction"></a>Verwenden von WS-AtomicTransaction
WS-Atomic-Transaktion (WS-AT) ist ein interoperables Transaktionsprotokoll. Mit diesem Protokoll können Sie verteilte Transaktionen unter Verwendung von Webdienstnachrichten übergeben und interoperativ zwischen heterogenen Transaktionsinfrastrukturen koordinieren. WS-AT verwendet das Zwei-Phasen-Commitprotokoll, um eine unteilbare Ausgabe zwischen verteilten Anwendungen, Transaktions-Managern und Ressourcen-Managern zu erzielen.  
  
 Der WS-AT-Implementierungs Windows Communication Foundation (WCF) umfasst einen Protokolldienst, der in den Transaktions-Manager von Microsoft Distributed Transaction Coordinator (MSDTC) integriert ist. Mithilfe von WS-AT können WCF-Anwendungen Transaktionen an andere Anwendungen übertragen, einschließlich interoperablen Webdiensten, die mithilfe von Drittanbieter Technologie erstellt wurden.  
  
 Beim Übergeben einer Transaktion zwischen einer Clientanwendung und einer Serveranwendung wird das verwendete Transaktionsprotokoll anhand der Bindung bestimmt, die der Server an dem vom Client ausgewählten Endpunkt verfügbar macht. Einige vom System bereitgestellte WCF-Bindungen legen standardmäßig fest, dass das `OleTransactions` Protokoll als Transaktions weitergabeformat angegeben wird, während andere standardmäßig WS-AT angeben. Sie können die Auswahl des Transaktionsprotokolls in einer vorhandenen Bindung auch programmgesteuert ändern.  
  
 Die Protokollauswahl beeinflusst Folgendes:  
  
- Das Format der Nachrichtenheader, das zur Weitergabe der Transaktion vom Client an den Server verwendet wird.  
  
- Das Netzwerkprotokoll, mit dem das Zwei-Phasen-Commitprotokoll zwischen dem Transaktions-Manager des Clients und der Transaktion des Servers ausgeführt wird, um das Ergebnis der Transaktion aufzulösen.  
  
 Wenn der Server und der Client mithilfe von WCF geschrieben werden, müssen Sie nicht WS-AT verwenden. Sie können stattdessen die Standardeinstellungen von `NetTcpBinding` mit aktiviertem `TransactionFlow`-Attribut verwenden. Dieses nutzt dann stattdessen das `OleTransactions`-Protokoll. Weitere Informationen finden Sie unter [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md). Andernfalls müssen Sie bei der Weitergabe von Transaktionen an Webdienste, die mit der Technologie von Fremdanbietern erstellt wurden, WS-AT verwenden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Konfigurieren der WS-AtomicTransaction-Unterstützung](configuring-ws-atomic-transaction-support.md)
