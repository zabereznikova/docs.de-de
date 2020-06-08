---
title: 'Gewusst wie: Umschließen von EAP-Mustern in einer Aufgabe'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
ms.openlocfilehash: eab94ac91be0c755a1da74e2f2220e3b76cc4249
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290784"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a><span data-ttu-id="b5df2-102">Gewusst wie: Umschließen von EAP-Mustern in einer Aufgabe</span><span class="sxs-lookup"><span data-stu-id="b5df2-102">How to: Wrap EAP Patterns in a Task</span></span>
<span data-ttu-id="b5df2-103">Das folgende Beispiel zeigt, wie eine beliebige Abfolge von Vorgängen des ereignisbasierten asynchronen Musters (Event-Based Asynchronous Pattern, EAP) mithilfe einer <xref:System.Threading.Tasks.TaskCompletionSource%601> als einzelne Aufgabe verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="b5df2-103">The following example shows how to expose an arbitrary sequence of Event-Based Asynchronous Pattern (EAP) operations as one task by using a <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span></span> <span data-ttu-id="b5df2-104">Das Beispiel zeigt auch, wie eine <xref:System.Threading.CancellationToken> zum Aufrufen der integrierten Abbruchmethoden für die <xref:System.Net.WebClient>-Objekte aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b5df2-104">The example also shows how to use a <xref:System.Threading.CancellationToken> to invoke the built-in cancellation methods on the <xref:System.Net.WebClient> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5df2-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5df2-105">Example</span></span>  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="b5df2-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5df2-106">See also</span></span>

- [<span data-ttu-id="b5df2-107">TPL und herkömmliche asynchrone .NET Framework-Programmierung</span><span class="sxs-lookup"><span data-stu-id="b5df2-107">TPL and Traditional .NET Framework Asynchronous Programming</span></span>](tpl-and-traditional-async-programming.md)
