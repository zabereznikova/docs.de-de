---
title: Verwenden von AsyncCallback-Delegat und Zustandsobjekt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e8793a78289e9b58407038f41cc9d403ff9f9940
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a>Verwenden von AsyncCallback-Delegat und Zustandsobjekt
Bei Verwendung einer <xref:System.AsyncCallback> delegieren, um die Ergebnisse des asynchronen Vorgangs in einem separaten Thread zu verarbeiten, können Sie ein Zustandsobjekt verwenden, um Informationen zwischen den Rückrufen zu übergeben und einem Endergebnis abzurufen. In diesem Thema veranschaulicht, die sich durch erweitern das Beispiel in [Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die Verwendung asynchroner Methoden in der <xref:System.Net.Dns> Klasse Domain Name System (DNS) für den Benutzer angegebenen Computer abgerufen. In diesem Beispiel definiert und verwendet die `HostRequest` Klasse zum Speichern von Zustandsinformationen. Ein `HostRequest` Objekt ruft für jeden vom Benutzer eingegebenen Computernamen erstellt. Dieses Objekt wird zum Übergeben der <xref:System.Net.Dns.BeginGetHostByName%2A> Methode. Die `ProcessDnsInformation` aufgerufen wird jedes Mal eine Anforderung abgeschlossen wird. Die `HostRequest` Objekt abgerufen wird, mit der <xref:System.IAsyncResult.AsyncState%2A> Eigenschaft. Die `ProcessDnsInformation` -Methode verwendet die `HostRequest` Objekt zum Speichern der <xref:System.Net.IPHostEntry> von der Anforderung zurückgegebenen oder eine <xref:System.Net.Sockets.SocketException> , die von der Anforderung ausgelöst. Wenn alle Anforderungen abgeschlossen sind, die Anwendung führt eine Iteration durch die `HostRequest` Objekten und zeigt die DNS-Informationen oder <xref:System.Net.Sockets.SocketException> Fehlermeldung.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
