---
title: "How to: Handle Exceptions in a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to handle exceptions"
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# How to: Handle Exceptions in a PLINQ Query
Im ersten Beispiel in diesem Thema wird gezeigt, wie die <xref:System.AggregateException?displayProperty=fullName> behandelt wird, die beim Ausführen einer PLINQ\-Abfrage ausgelöst werden kann.  Im zweiten Beispiel wird gezeigt, wie try\/catch\-Blöcke in Delegate möglichst nah an der Position eingefügt werden, an der die Ausnahme ausgelöst wird.  Auf diese Weise können Sie die Ausnahmen sofort erfassen und die Abfrageausführung möglicherweise fortsetzen.  Wenn Ausnahmen mittels Bubbling wieder an den Verbindungsthread übergeben werden können, ist es möglich, dass eine Abfrage nach dem Auslösen der Ausnahme weiterhin einige Elemente verarbeitet.  
  
 Wenn PLINQ auf die sequenzielle Ausführung zurückgreift und eine Ausnahme auftritt, kann die Ausnahme in einigen Fällen direkt weitergegeben werden, ohne sie in eine <xref:System.AggregateException> einzuschließen.  Zudem werden <xref:System.Threading.ThreadAbortException>s immer direkt weitergegeben.  
  
> [!NOTE]
>  Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen.  Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den unten stehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.  Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.  
>   
>  Dieses Beispiel soll die Verwendung veranschaulichen, und es wird möglicherweise nicht schneller als die entsprechende sequenzielle LINQ to Objects\-Abfrage ausgeführt.  Weitere Informationen über Geschwindigkeitssteigerungen finden Sie unter [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Beispiel  
 In diesem Beispiel wird gezeigt, wie Sie die try\/catch\-Blöcke um den Code platzieren, der die Abfrage ausführt, sodass alle ausgelösten <xref:System.AggregateException?displayProperty=fullName>\-Ausnahmen erfasst werden.  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 In diesem Beispiel kann die Abfrage nicht fortgesetzt werden, nachdem die Ausnahme ausgelöst wurde.  Wenn der Anwendungscode die Ausnahme erfasst, hat PLINQ die Abfrage bereits in allen Threads beendet.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie einen try\/catch\-Block in einen Delegaten einfügen, um eine Ausnahme erfassen und die Abfrageausführung fortsetzen zu können.  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## Kompilieren des Codes  
  
-   Um diese Beispiele zu kompilieren und auszuführen, kopieren Sie sie in das PLINQ\-Datenbeispiel, und rufen Sie die Methode vom Hauptmenü aus auf.  
  
## Robuste Programmierung  
 Erfassen Sie Ausnahmen nur, wenn Sie wissen, wie diese behandelt werden, damit der Zustand des Programms nicht beschädigt wird.  
  
## Siehe auch  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)