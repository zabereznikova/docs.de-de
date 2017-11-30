---
title: 'Gewusst wie: Lauschen auf Abbruchanforderungen durch Abruf'
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
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f0e05e3f66d591a28d7e84d358934959764dab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a>Gewusst wie: Lauschen auf Abbruchanforderungen durch Abruf
Das folgende Beispiel zeigt eine Möglichkeit, die Benutzercode ein Abbruchtoken, das in regelmäßigen Abständen, um festzustellen, ob ein Abbruch angefordert wurde, von dem aufrufenden Thread abrufen kann. Dieses Beispiel verwendet die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> aufweisen, aber das gleiche Muster gilt für asynchrone Vorgänge, die direkt über erstellt die <xref:System.Threading.ThreadPool?displayProperty=nameWithType> Typ oder die <xref:System.Threading.Thread?displayProperty=nameWithType> Typ.  
  
## <a name="example"></a>Beispiel  
 Abruf erfordert eine Art von Schleifen oder Rekursionen Code, der den Wert des booleschen Werts in regelmäßigen Abständen zu lesen, kann <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> Eigenschaft. Bei Verwendung der <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> und Warten auf die Aufgabe im aufrufenden Thread abgeschlossen, können Sie mithilfe der <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> -Methode auf, überprüfen Sie die Eigenschaft und die Ausnahme. Mithilfe dieser Methode zu verwenden, stellen Sie sicher, dass die richtige Ausnahme, als Antwort auf eine Anforderung ausgelöst wird. Bei Verwendung einer <xref:System.Threading.Tasks.Task>, besser als manuell auszulösen ist beim Aufrufen dieser Methode eine <xref:System.OperationCanceledException>. Wenn Sie keine Ausnahme auslösen, können Sie nur überprüfen Sie die Eigenschaft und von der Methode zurückgegeben wird, wenn die Eigenschaft `true`.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 Aufrufen von <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> ist äußerst schnell und führt bedeutenden Aufwand in Schleifen.  
  
 Beim Aufrufen <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, Sie müssen nur explizit der <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> Eigenschaft, wenn Sie andere Vorgänge als Reaktion auf den Abbruch neben dem Auslösen der Ausnahme ausführen müssen. In diesem Beispiel sehen Sie, dass der Code tatsächlich zweimal auf die Eigenschaft zugreift: einmal in der expliziten Zugriff und erneut in die <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> Methode. Da jedoch das Act des Lesens der <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> Eigenschaft nur eine flüchtige read-Anweisung pro Zugriff, die doppelte Zugriff ist nicht im Hinblick auf Leistung signifikant. Dennoch ist es besser, manuell auslösen, sondern rufen Sie die Methode der <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>Siehe auch  
 [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)
