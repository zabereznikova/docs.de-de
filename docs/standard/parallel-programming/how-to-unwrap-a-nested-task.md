---
title: 'Gewusst wie: Entpacken einer geschachtelten Aufgabe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
ms.openlocfilehash: 3eec3b7e8cc76ee171d88a7886b4983000848084
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722621"
---
# <a name="how-to-unwrap-a-nested-task"></a>Gewusst wie: Entpacken einer geschachtelten Aufgabe

Sie können eine Aufgabe aus einer Methode zurückgeben und anschließend warten oder von dieser Aufgabe aus fortfahren, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 Im vorherigen Beispiel ist die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft vom Typ `string` (in Visual Basic `String`).  
  
 Allerdings könnten Sie in einigen Szenarien eine Aufgabe innerhalb einer anderen Aufgabe erstellen und dann die geschachtelte Aufgabe zurückgeben. In diesem Fall ist `TResult` der einschließenden Aufgabe selbst eine Aufgabe. Im folgenden Beispiel ist die Result-Eigenschaft `Task<Task<string>>` in C# oder `Task(Of Task(Of String))` in Visual Basic.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 Es ist zwar möglich, Code zum Enthüllen der äußeren Aufgabe zu schreiben und die ursprüngliche Aufgabe sowie die zugehörige <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft abzurufen, doch solcher Code ist nicht einfach zu schreiben, da Ausnahmen und auch Abbruchanforderungen behandelt werden müssen. In diesem Fall sollten Sie eine der <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>-Erweiterungsmethoden verwenden, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 Mit der <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>-Methode kann eine beliebige `Task<Task>` oder `Task<Task<TResult>>` (in Visual Basic `Task(Of Task)` oder `Task(Of Task(Of TResult))`) in eine `Task` oder `Task<TResult>` (in Visual Basic `Task(Of TResult)`) umgewandelt werden. Die neue Aufgabe stellt die geschachtelte innere Aufgabe vollständig dar und enthält den Abbruchstatus sowie alle Ausnahmen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird die Verwendung der <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>-Erweiterungsmethoden erläutert.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>
- [Aufgabenbasierte asynchrone Programmierung](task-based-asynchronous-programming.md)
