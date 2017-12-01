---
title: 'Gewusst wie: Entpacken einer geschachtelten Aufgabe'
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
helpviewer_keywords: tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2da3de912abb693c4342e1ede02f273348e4b571
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-unwrap-a-nested-task"></a>Gewusst wie: Entpacken einer geschachtelten Aufgabe
Sie können eine Aufgabe zurückgeben, von einer Methode und anschließend gewartet werden soll oder aus dieser Vorgang fortgesetzt werden, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 Im vorherigen Beispiel der <xref:System.Threading.Tasks.Task%601.Result%2A> -Eigenschaft ist vom Typ `string` (`String` in Visual Basic).  
  
 Allerdings kann in einigen Szenarien möchten eine Aufgabe innerhalb einer anderen Aufgabe erstellt, und klicken Sie dann die geschachtelte Aufgabe zurückgeben. In diesem Fall die `TResult` der übergeordneten Aufgabe ist selbst eine Aufgabe. Im folgenden Beispiel wird die Eigenschaft eine `Task<Task<string>>` in c# oder `Task(Of Task(Of String))` in Visual Basic.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 Obwohl es möglich, Schreiben Code zum Entpacken der äußeren Aufgabe und die ursprüngliche Aufgabe abrufen und die zugehörige <xref:System.Threading.Tasks.Task%601.Result%2A> Eigenschaft solcher Code ist nicht einfach zu schreiben, da Ausnahmen und auch auf abbruchanforderungen behandelt werden müssen. In diesem Fall wird empfohlen, dass Sie eine der verwenden die <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> Erweiterungsmethoden, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 Die <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> Methoden können verwendet werden, um eine Transformation `Task<Task>` oder `Task<Task<TResult>>` (`Task(Of Task)` oder `Task(Of Task(Of TResult))` in Visual Basic), eine `Task` oder `Task<TResult>` (`Task(Of TResult)` in Visual Basic). Die neue Aufgabe stellt die geschachtelte innere Aufgabe vollständig und enthält Abbruch sowie alle Ausnahmen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> Erweiterungsmethoden.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [Aufgabenbasierte asynchrone Programmierung](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
