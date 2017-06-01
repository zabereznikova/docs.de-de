---
title: "How to: Handle Exceptions in Parallel Loops | Microsoft Docs"
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
  - "parallel loops, how to handle exceptions"
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# How to: Handle Exceptions in Parallel Loops
Die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>\- und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>\-Überladungen verfügen über keinen speziellen Mechanismus zur Behandlung von Ausnahmen, die möglicherweise ausgelöst werden.  In dieser Hinsicht ähneln sie regulären `for`\- und `foreach`\-Schleifen \(`For` und `For Each` in Visual Basic\). Eine nicht behandelte Ausnahme bewirkt, dass die Schleife sofort beendet wird.  
  
 Wenn Sie Parallelschleifen eigene Logik zur Ausnahmebehandlung hinzufügen, behandeln Sie den Fall, in dem ähnliche Ausnahmen in mehreren Threads gleichzeitig ausgelöst werden können, sowie den Fall, in dem eine in einem Thread ausgelöste Ausnahme bewirkt, dass eine andere Ausnahme in einem anderen Thread ausgelöst wird.  Sie können beide Fälle behandeln, indem Sie alle Ausnahmen der Schleife in einer <xref:System.AggregateException?displayProperty=fullName> umschließen.  Im folgenden Beispiel wird ein möglicher Ansatz gezeigt.  
  
> [!NOTE]
>  Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen.  Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das im nachstehenden Beispiel veranschaulichte Ausnahmebehandlungsverhalten angewendet.  Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen "Nur eigenen Code".  
  
## Beispiel  
 In diesem Beispiel werden alle Ausnahmen abgefangen und dann in einer <xref:System.AggregateException?displayProperty=fullName> umschlossen, die ausgelöst wird.  Der Aufrufer kann entscheiden, welche Ausnahmen behandelt werden.  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## Siehe auch  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)