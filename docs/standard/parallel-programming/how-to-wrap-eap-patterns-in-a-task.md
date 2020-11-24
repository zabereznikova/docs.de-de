---
title: 'Gewusst wie: Umschließen von EAP-Mustern in einer Aufgabe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
ms.openlocfilehash: 2d6788634fe03bed7a380184c0e954954e224aec
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826683"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a>Gewusst wie: Umschließen von EAP-Mustern in einer Aufgabe
Das folgende Beispiel zeigt, wie eine beliebige Abfolge von Vorgängen des ereignisbasierten asynchronen Musters (Event-Based Asynchronous Pattern, EAP) mithilfe einer <xref:System.Threading.Tasks.TaskCompletionSource%601> als einzelne Aufgabe verfügbar gemacht wird. Das Beispiel zeigt auch, wie eine <xref:System.Threading.CancellationToken> zum Aufrufen der integrierten Abbruchmethoden für die <xref:System.Net.WebClient>-Objekte aufgerufen wird.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a>Weitere Informationen

- [TPL und herkömmliche asynchrone .NET-Programmierung](tpl-and-traditional-async-programming.md)
