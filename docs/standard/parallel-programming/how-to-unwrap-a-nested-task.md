---
title: "How to: Unwrap a Nested Task | Microsoft Docs"
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
  - "tasks, how to unwrap nested tasks"
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Unwrap a Nested Task
Sie können eine Aufgabe von einer Methode zurückgeben und anschließend warten und bei dieser Aufgabe fortfahren \(siehe folgendes Beispiel\).  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 Im vorherigen Beispiel ist die <xref:System.Threading.Tasks.Task%601.Result%2A>\-Eigenschaft vom Typ `string` \(`String` in Visual Basic\).  
  
 In einigen Szenarien möchten Sie jedoch unter Umständen eine Aufgabe innerhalb einer anderen Aufgabe erstellen und anschließend die geschachtelte Aufgabe zurückgeben.  In diesem Fall ist das `TResult`\-Objekt der übergeordneten Aufgabe selbst eine Aufgabe.  Im folgenden Beispiel ist die Result\-Eigenschaft ein `Task<Task<string>>` in C\# oder `Task(Of Task(Of String))` in Visual Basic.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 Obwohl es möglich ist, Code zu schreiben, um die äußere Aufgabe zu entwrappen und die ursprüngliche Aufgabe und die entsprechende <xref:System.Threading.Tasks.Task%601.Result%2A>\-Eigenschaft abzurufen, ist das Schreiben von derartigem Code nicht einfach, da Ausnahmen und auch Abbruchanforderungen behandelt werden müssen.  In dieser Situation empfiehlt es sich, eine der <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>\-Erweiterungsmethoden zu verwenden \(siehe folgendes Beispiel\).  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 Mithilfe der <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>\-Methoden kann jedes beliebige `Task<Task>`\-Objekt oder `Task<Task<TResult>>`\-Objekt \(`Task(Of Task)` oder `Task(Of Task(Of TResult))` in Visual Basic\) in ein `Task`\-Objekt oder `Task<TResult>` \-Objekt umgewandelt werden \(`Task(Of TResult)` in Visual Basic\).  Die neue Aufgabe stellt vollständig die innere geschachtelte Aufgabe und alle Ausnahmen dar.  
  
## Beispiel  
 Im folgenden Beispiel wird die Verwendung der <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>\-Erweiterungsmethoden veranschaulicht.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## Siehe auch  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=fullName>   
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)