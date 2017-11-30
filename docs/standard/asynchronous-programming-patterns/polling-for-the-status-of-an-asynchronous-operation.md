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
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a><span data-ttu-id="4730e-102">Abrufen des Status einer asynchronen Operation</span><span class="sxs-lookup"><span data-stu-id="4730e-102">Polling for the Status of an Asynchronous Operation</span></span>
<span data-ttu-id="4730e-103">Anwendungen, die andere arbeiten, die während des Wartens auf die Ergebnisse eines asynchronen Vorgangs durchführen können, sollten keine Blockierung warten, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4730e-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="4730e-104">Fortsetzen der Ausführung von Anweisungen beim Warten auf Abschluss eines asynchronen Vorgangs mithilfe einer der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="4730e-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="4730e-105">Verwenden der <xref:System.IAsyncResult.IsCompleted%2A> Eigenschaft von der <xref:System.IAsyncResult> zurückgegeben, die für des asynchronen Vorgangs **beginnen** *OperationName* Methode, um zu bestimmen, ob der Vorgang abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="4730e-105">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method to determine whether the operation has completed.</span></span> <span data-ttu-id="4730e-106">Dieser Ansatz wird als Abrufintervall bezeichnet und wird in diesem Thema veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4730e-106">This approach is known as polling and is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="4730e-107">Verwenden einer <xref:System.AsyncCallback> Delegat, der die Ergebnisse des asynchronen Vorgangs in einem separaten Thread zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4730e-107">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="4730e-108">Ein Beispiel für diesen Ansatz finden Sie unter [Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="4730e-108">For an example that demonstrates this approach, see [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4730e-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4730e-109">Example</span></span>  
 <span data-ttu-id="4730e-110">Das folgende Codebeispiel veranschaulicht die Verwendung asynchroner Methoden in der <xref:System.Net.Dns> Klasse Domain Name System-Informationen für einen Benutzer angegebenen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4730e-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="4730e-111">In diesem Beispiel startet den asynchronen Vorgang, und gibt dann Punkte (".") in der Konsole aus, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="4730e-111">This example starts the asynchronous operation and then prints periods (".") at the console until the operation is complete.</span></span> <span data-ttu-id="4730e-112">Beachten Sie, dass **null** (**nichts** in Visual Basic) übergeben wird, für die <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> und <xref:System.Object> Parameter, da diese Argumente bei dieser Vorgehensweise nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4730e-112">Note that **null** (**Nothing** in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> and <xref:System.Object> parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="4730e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4730e-113">See Also</span></span>  
 [<span data-ttu-id="4730e-114">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="4730e-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="4730e-115">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="4730e-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
