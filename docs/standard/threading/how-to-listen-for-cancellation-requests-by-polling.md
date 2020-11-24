---
title: 'Gewusst wie: Lauschen auf Abbruchanforderungen durch Abruf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
ms.openlocfilehash: ae7a2e0269c0c12c4dabe5e561e9bef53100aac1
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819863"
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a>Gewusst wie: Lauschen auf Abbruchanforderungen durch Abruf
Das folgende Beispiel zeigt eine Möglichkeit, wie Benutzercode ein Abbruchtoken in regelmäßigen Abständen abfragen kann, um festzustellen, ob vom aufrufenden Thread ein Abbruch angefordert wurde. In diesem Beispiel wird der <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Typ verwendet, aber das gleiche Muster gilt für asynchrone Vorgänge, die direkt vom <xref:System.Threading.ThreadPool?displayProperty=nameWithType>- oder <xref:System.Threading.Thread?displayProperty=nameWithType>-Typ erstellt werden.  
  
## <a name="example"></a>Beispiel  
 Abrufen erfordert eine Schleife oder rekursiven Code, der den Wert der booleschen <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>-Eigenschaft in regelmäßigen Abständen lesen kann. Bei Verwendung des <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Typs und Warten auf den Abschluss der Aufgabe im aufrufenden Thread können Sie mithilfe der <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>-Methode die Eigenschaft überprüfen und die Ausnahme auslösen. Mithilfe dieser Methode stellen Sie sicher, dass die richtige Ausnahme als Reaktion auf eine Anforderung ausgelöst wird. Bei Verwendung eines <xref:System.Threading.Tasks.Task> ist das Aufrufen dieser Methode besser als das manuelle Auslösen einer <xref:System.OperationCanceledException>. Wenn Sie keine Ausnahme auslösen müssen, reicht es aus, wenn Sie einfach die Eigenschaft überprüfen und aus der Methode zurückkehren, wenn die Eigenschaft `true` ist.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 Das Aufrufen von <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> ist äußerst schnell und nicht mit bedeutendem Aufwand in Schleifen verbunden.  
  
 Beim Aufrufen von <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> müssen Sie die <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>-Eigenschaft nur dann explizit überprüfen, wenn als Reaktion auf den Abbruch neben dem Auslösen der Ausnahme noch Anderes erforderlich ist. In diesem Beispiel sehen Sie, dass der Code tatsächlich zweimal auf die Eigenschaft zugreift: einmal mit explizitem Zugriff und erneut in der <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>-Methode. Da jedoch das Lesen der <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>-Eigenschaft nur eine flüchtige Leseanweisung pro Zugriff beinhaltet, ist der doppelte Zugriff im Hinblick auf die Leistung nicht signifikant. Dennoch ist der Methodenaufruf dem manuellen Auslösen der <xref:System.OperationCanceledException> vorzuziehen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Abbruch in verwalteten Threads](cancellation-in-managed-threads.md)
