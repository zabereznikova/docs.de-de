---
title: "How to: Listen for Cancellation Requests by Polling | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "cancellation, how to poll for requests"
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Listen for Cancellation Requests by Polling
Im folgenden Beispiel wird eine Methode veranschaulicht, wie in Benutzercode ein Abbruchtoken abgefragt werden kann, um in regelmäßigen Abständen zu überprüfen, ob vom aufrufenden Thread ein Abbruch angefordert wurde.  In diesem Beispiel wird der <xref:System.Threading.Tasks.Task?displayProperty=fullName>\-Typ verwendet, das gleiche Muster gilt jedoch auch für asynchrone Vorgänge, die direkt vom <xref:System.Threading.ThreadPool?displayProperty=fullName>\-Typ oder <xref:System.Threading.Thread?displayProperty=fullName>\-Typ erstellt werden.  
  
## Beispiel  
 Für das Abrufen ist Code mit Schleifen oder Rekursionen erforderlich, der regelmäßig den Wert der booleschen <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>\-Eigenschaft lesen kann.  Wenn Sie den <xref:System.Threading.Tasks.Task?displayProperty=fullName>\-Typ verwenden und darauf warten, dass die Aufgabe für den aufrufenden Thread abgeschlossen wird, können Sie mithilfe der <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>\-Methode die Eigenschaft überprüfen und die Ausnahme auslösen.  Mit dieser Methode wird sichergestellt, dass die richtige Ausnahme als Reaktion auf eine Anforderung ausgelöst wird.  Wenn Sie einen <xref:System.Threading.Tasks.Task> verwenden, ist das Aufrufen dieser Methode dem manuellen Auslösen einer <xref:System.OperationCanceledException> vorzuziehen.  Wenn Sie die Ausnahme nicht auslösen müssen, dann können Sie die Eigenschaft und Rückgabe der Methode einfach überprüfen, wenn die Eigenschaft `true` ist.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 Das Aufrufen von <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> ist äußerst schnell und führt nicht zu bedeutendem Mehraufwand durch Schleifen.  
  
 Wenn Sie <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> aufrufen, müssen Sie die <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>\-Eigenschaft nur dann explizit überprüfen, wenn als Reaktion auf den Abbruch weitere Reaktionen als das Auslösen der Ausnahme erforderlich sind.  In diesem Beispiel können Sie sehen, dass der Code eigentlich zweimal auf die Eigenschaft zugreift: einmal explizit und dann mit der <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>\-Methode.  Da jedoch für das Lesen der <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>\-Eigenschaft nur eine flüchtige read\-Anweisung pro Zugriff erforderlich ist, ist der zweifache Zugriff im Hinblick auf die Leistung unerheblich.  Das Aufrufen der Methode ist weiterhin dem manuellen Auslösen der <xref:System.OperationCanceledException> vorzuziehen.  
  
## Siehe auch  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)