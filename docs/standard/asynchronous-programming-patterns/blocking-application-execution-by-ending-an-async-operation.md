---
title: "Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
dev_langs:
- csharp
- vb
ms.openlocfilehash: ccca6e1e4f6b5cdf098018b59426fb2262e2b346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a>Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs
Anwendungen, die nicht fortgesetzt werden können, andere Aufgaben während des Wartens auf die Ergebnisse eines asynchronen Vorgangs blockiert, bis der Vorgang abgeschlossen ist. Hauptthread der Anwendung blockiert wird, beim Abschluss eines asynchronen Vorgangs warten, verwenden Sie eine der folgenden Optionen:  
  
-   Rufen Sie die asynchronen Vorgänge **End** *OperationName* Methode. Dieser Ansatz wird in diesem Thema veranschaulicht.  
  
-   Verwenden der <xref:System.IAsyncResult.AsyncWaitHandle%2A> Eigenschaft von der <xref:System.IAsyncResult> zurückgegeben, die für des asynchronen Vorgangs **beginnen** *OperationName* Methode. Ein Beispiel für diesen Ansatz finden Sie unter [blockieren Anwendung Ausführung mithilfe von AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Anwendungen, die die **End** *OperationName* Methode blockiert, bis ein asynchroner Vorgang abgeschlossen ist in der Regel ruft der **beginnen**  *OperationName* -Methode, führen Sie alle Daten, die ausgeführt werden kann, ohne die Ergebnisse des Vorgangs, und rufen dann **End** *OperationName*.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die Verwendung asynchroner Methoden in der <xref:System.Net.Dns> Klasse Domain Name System-Informationen für einen Benutzer angegebenen Computer abgerufen. Beachten Sie, dass `null` (`Nothing` in Visual Basic) übergeben wird, für die <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` und `stateObject` Parameter, da diese Argumente bei dieser Vorgehensweise nicht erforderlich sind.  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
