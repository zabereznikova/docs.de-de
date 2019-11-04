---
title: Aufgabenabbruch
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, cancellation
- asynchronous task cancellation
ms.assetid: 3ecf1ea9-e399-4a6a-a0d6-8475f48dcb28
ms.openlocfilehash: 17cabde95644dbc1584dd85b99e26ff7c5cb686d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139971"
---
# <a name="task-cancellation"></a>Aufgabenabbruch
Die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> - und <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> -Klasse unterstützen einen Abbruch durch die Verwendung von Abbruchtoken, die in .NET Framework neu sind. Weitere Informationen finden Sie unter [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md). In den Task-Klassen erfordert ein Abbruch eine Zusammenarbeit zwischen dem Benutzerdelegaten, der einen abbrechbaren Vorgang darstellt, und dem Code, der den Abbruch angefordert hat.  Für einen erfolgreichen Abbruch muss der anfordernde Code die <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> -Methode aufrufen und der Benutzerdelegat den Vorgang rechtzeitig beenden. Sie können den Vorgang mithilfe einer dieser Optionen beenden:  
  
- Durch eine einfache Rückkehr vom Delegaten. In vielen Fällen reicht dies aus. Eine auf diese Weise abgebrochene Aufgabeninstanz geht jedoch in den Zustand <xref:System.Threading.Tasks.TaskStatus.RanToCompletion?displayProperty=nameWithType> und nicht in den Zustand <xref:System.Threading.Tasks.TaskStatus.Canceled?displayProperty=nameWithType> über.  
  
- Durch Auslösen einer <xref:System.OperationCanceledException> und Übergeben des Tokens, für das ein Abbruch angefordert wurde. Die bevorzugte Methode hierfür ist die <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> -Methode. Eine auf diese Weise abgebrochene Aufgabe geht in den Zustand "Canceled" über, anhand dessen der aufrufende Code überprüfen kann, ob die Aufgabe auf seine Abbruchanforderung reagiert hat.  
  
 Im folgenden Beispiel wird das grundlegende Muster für den Aufgabenabbruch gezeigt, der die Ausnahme auslöst. Beachten Sie, dass das Token an den Benutzerdelegaten und die Aufgabeninstanz selbst übergeben wird.  
  
 [!code-csharp[TPL_Cancellation#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/snippet02.cs#02)]
 [!code-vb[TPL_Cancellation#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/module1.vb#02)]  
  
 Ein ausführlicheres Beispiel finden Sie unter [Vorgehensweise: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md).  
  
 Wenn eine Aufgabeninstanz eine <xref:System.OperationCanceledException> beobachtet, die von Benutzercode ausgelöst wurde, vergleicht sie das Token der Ausnahme mit dem zugeordneten Token (das an die API übergeben wurde, die die Aufgabe erstellt hat). Wenn diese identisch sind und die <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> -Eigenschaft des Tokens true zurückgibt, interpretiert die Aufgabe dies als Bestätigung des Abbruchs und geht in den Zustand Canceled über. Wenn Sie nicht mithilfe einer <xref:System.Threading.Tasks.Task.Wait%2A> -Methode oder <xref:System.Threading.Tasks.Task.WaitAll%2A> -Methode auf die Aufgabe warten, wird der Status der Aufgabe auf <xref:System.Threading.Tasks.TaskStatus.Canceled>festgelegt.  
  
 Wenn Sie auf eine Aufgabe warten, die in den Zustand „Canceled“ übergeht, wird eine <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> -Ausnahme (eingebunden in eine <xref:System.AggregateException> -Ausnahme) ausgelöst. Beachten Sie, dass diese Ausnahme keinen Fehler, sondern einen erfolgreichen Abbruch kennzeichnet. Daher gibt die Eigenschaft <xref:System.Threading.Tasks.Task.Exception%2A> der Aufgabe `null`zurück.  
  
 Wenn die <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> -Eigenschaft des Tokens false zurückgibt oder das Token der Ausnahme nicht mit dem Token der Aufgabe übereinstimmt, wird die <xref:System.OperationCanceledException> wie eine normale Ausnahme behandelt, durch die die Aufgabe in den Zustand "Faulted" übergeht. Beachten Sie weiterhin, dass die Aufgabe bei weiteren Ausnahmen ebenfalls in den Zustand "Faulted" übergeht. Sie können den Status der abgeschlossenen Aufgabe in der <xref:System.Threading.Tasks.Task.Status%2A> -Eigenschaft abrufen.  
  
 Es ist möglich, dass eine Aufgabe nach dem Anfordern des Abbruchs weiterhin einige Elemente verarbeitet.  
  
## <a name="see-also"></a>Siehe auch

- [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)
- [Vorgehensweise: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)
