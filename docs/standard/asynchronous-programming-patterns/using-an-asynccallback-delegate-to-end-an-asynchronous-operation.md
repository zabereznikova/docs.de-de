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
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bbe170588776daa97fec4c736d4b1bdd871de518
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a>Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation
Anwendungen, die andere arbeiten, die während des Wartens auf die Ergebnisse eines asynchronen Vorgangs durchführen können, sollten keine Blockierung warten, bis der Vorgang abgeschlossen ist. Fortsetzen der Ausführung von Anweisungen beim Warten auf Abschluss eines asynchronen Vorgangs mithilfe einer der folgenden Optionen:  
  
-   Verwenden einer <xref:System.AsyncCallback> Delegat, der die Ergebnisse des asynchronen Vorgangs in einem separaten Thread zu verarbeiten. Dieser Ansatz wird in diesem Thema veranschaulicht.  
  
-   Verwenden der <xref:System.IAsyncResult.IsCompleted%2A> Eigenschaft von der <xref:System.IAsyncResult> zurückgegeben, die für des asynchronen Vorgangs **beginnen** *OperationName* Methode, um zu bestimmen, ob der Vorgang abgeschlossen wurde. Ein Beispiel für diesen Ansatz finden Sie unter [Abrufen des Status eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die Verwendung asynchroner Methoden in der <xref:System.Net.Dns> Klasse Domain Name System (DNS) für den Benutzer angegebenen Computer abgerufen. In diesem Beispiel wird ein <xref:System.AsyncCallback> Delegat, verweist der `ProcessDnsInformation` Methode. Diese Methode wird einmal für jede asynchrone Anforderung von DNS-Informationen aufgerufen.  
  
 Der vom Benutzer angegebene Host übergeben, um die <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object> Parameter. Ein Beispiel für definieren und verwenden eine komplexere Zustandsobjekt finden Sie unter [mit AsyncCallback-Delegat und Zustandsobjekt](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [Verwenden von AsyncCallback-Delegat und Zustandsobjekt](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
