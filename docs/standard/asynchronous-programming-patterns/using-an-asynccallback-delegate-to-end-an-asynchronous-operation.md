---
title: Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation
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
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d71e78ecd5bf365d0a1f3efb8c8e15d4a1de6dc7
ms.sourcegitcommit: 957c696f25e39f923a827fc3ad5e8ab72768838c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2018
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a>Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation
Anwendungen, die während des Wartens auf die Ergebnisse eines asynchronen Vorgangs weiterarbeiten können, sollten nicht blockiert werden, bis der Vorgang abgeschlossen ist. Verwenden Sie eine der folgenden Optionen, um Anweisungen weiter auszuführen, während Sie darauf warten, dass ein asynchroner Vorgang abgeschlossen wird:  
  
-   Verwenden Sie ein <xref:System.AsyncCallback>-Delegat, um die Ergebnisse des asynchronen Vorgangs in einem separaten Thread zu verarbeiten. Dieser Ansatz wird in diesem Thema veranschaulicht.  
  
-   Verwenden Sie die Eigenschaft <xref:System.IAsyncResult.IsCompleted%2A> des Ergebnisses <xref:System.IAsyncResult>, welches durch die Methode **Begin***OperationName* für asynchrone Vorgänge zurückgegeben wird, um zu ermitteln, ob der Vorgang abgeschlossen ist. Ein Beispiel zur Veranschaulichung dieses Ansatzes finden Sie unter [Abrufen des Status einer asynchronen Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel demonstriert die Verwendung von asynchronen Methoden in der <xref:System.Net.Dns>-Klasse, um Informationen aus dem Domain Name System (DNS) für benutzerdefinierte Computer abzurufen. In diesem Beispiel wird ein <xref:System.AsyncCallback>-Delegat erstellt, der die Methode `ProcessDnsInformation` referenziert. Diese Methode wird einmal für jede asynchrone Anforderung von DNS-Informationen aufgerufen.  
  
 Beachten Sie, dass der vom Benutzer angegebene Host an den Parameter <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> weitergegeben wird. Ein Beispiel, das die Definition und Verwendung eines komplexeren Zustandsobjekts demonstriert, finden Sie unter [Verwenden von AsyncCallback-Delegat und Zustandsobjekt](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [Verwenden von AsyncCallback-Delegat und Zustandsobjekt](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
