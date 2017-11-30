---
title: Abrufen des Status einer asynchronen Operation
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
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1f7f74a8b38c06f6a042d55c0def76ddfc5da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a>Abrufen des Status einer asynchronen Operation
Anwendungen, die andere arbeiten, die während des Wartens auf die Ergebnisse eines asynchronen Vorgangs durchführen können, sollten keine Blockierung warten, bis der Vorgang abgeschlossen ist. Fortsetzen der Ausführung von Anweisungen beim Warten auf Abschluss eines asynchronen Vorgangs mithilfe einer der folgenden Optionen:  
  
-   Verwenden der <xref:System.IAsyncResult.IsCompleted%2A> Eigenschaft von der <xref:System.IAsyncResult> zurückgegeben, die für des asynchronen Vorgangs **beginnen** *OperationName* Methode, um zu bestimmen, ob der Vorgang abgeschlossen wurde. Dieser Ansatz wird als Abrufintervall bezeichnet und wird in diesem Thema veranschaulicht.  
  
-   Verwenden einer <xref:System.AsyncCallback> Delegat, der die Ergebnisse des asynchronen Vorgangs in einem separaten Thread zu verarbeiten. Ein Beispiel für diesen Ansatz finden Sie unter [Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die Verwendung asynchroner Methoden in der <xref:System.Net.Dns> Klasse Domain Name System-Informationen für einen Benutzer angegebenen Computer abgerufen. In diesem Beispiel startet den asynchronen Vorgang, und gibt dann Punkte (".") in der Konsole aus, bis der Vorgang abgeschlossen ist. Beachten Sie, dass **null** (**nichts** in Visual Basic) übergeben wird, für die <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> und <xref:System.Object> Parameter, da diese Argumente bei dieser Vorgehensweise nicht erforderlich sind.  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
