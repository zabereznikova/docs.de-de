---
title: 'Gewusst wie: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
ms.openlocfilehash: 4e0e783a4dfe3bf3a55795d7baef461369d7405a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73134208"
---
# <a name="how-to-cancel-a-task-and-its-children"></a>Gewusst wie: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente
In diesen Beispielen wird gezeigt, wie Sie die folgenden Aufgaben ausführen:  
  
1. Erstellen und Starten einer abbrechbare Aufgabe  
  
2. Übergeben eines Abbruchtokens an den Benutzerdelegaten und optional an die Aufgabeninstanz  
  
3. Erkennen der Abbruchanforderung im Benutzerdelegaten und Reagieren auf diese  
  
4. Hinzufügen eines optionalen Hinweises, dass die Aufgabe abgebrochen wurde, zum aufrufenden Thread  
  
 Der aufrufende Thread erzwingt nicht die Beendigung der Aufgabe, er kennzeichnet nur, dass der Abbruch angefordert wurde. Wenn die Aufgabe bereits ausgeführt wird, muss der Benutzerdelegat die Anforderung erkennen und entsprechend reagieren. Wenn der Abbruch vor Auführung der Aufgabe angefordert wird, wird der Benutzerdelegat nicht ausgeführt; und das Aufgabenobjekt geht in den abgebrochenen Zustand über.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird gezeigt, wie Sie <xref:System.Threading.Tasks.Task> und die zugehörigen untergeordneten Elemente als Reaktion auf eine Abbruchanforderung beenden. Darüber hinaus wird gezeigt, dass beim Beenden eines Benutzerdelegaten durch eine <xref:System.Threading.Tasks.TaskCanceledException> der aufrufende Thread optional die <xref:System.Threading.Tasks.Task.Wait%2A>-Methode oder <xref:System.Threading.Tasks.Task.WaitAll%2A>-Methode verwenden kann, um auf das Ende der Aufgaben zu warten. In diesem Fall müssen Sie einen `try/catch`-Block verwenden, um die Ausnahmen im aufrufenden Thread zu behandeln.  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 Die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse ist vollständig in das Abbruchmodell integriert, das auf dem <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>-Typ und dem <xref:System.Threading.CancellationToken?displayProperty=nameWithType>-Typ basiert. Weitere Informationen finden Sie unter [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md) und [Aufgabenabbruch](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>
- <xref:System.Threading.CancellationToken?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [Aufgabenbasierte asynchrone Programmierung](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
- [Angefügte und getrennte untergeordnete Aufgaben](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)
- [Lambdaausdrücke in PLINQ und TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
