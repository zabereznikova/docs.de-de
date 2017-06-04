---
title: "How to: Cancel a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to cancel"
  - "cancellation, PLINQ"
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# How to: Cancel a PLINQ Query
In den folgenden Beispielen werden zwei Möglichkeiten dargestellt, eine PLINQ\-Abfrage abzubrechen.  Im ersten Beispiel wird gezeigt, wie Sie eine hauptsächlich aus Datendurchläufen bestehende Abfrage abbrechen.  Im zweiten Beispiel wird gezeigt, wie Sie eine Abfrage abbrechen, die eine rechenintensive Benutzerfunktion enthält.  
  
> [!NOTE]
>  Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt. Dieser Fehler hat keine Auswirkungen.  Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den unten stehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.  Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.  
>   
>  Dieses Beispiel soll die Verwendung veranschaulichen, und es wird möglicherweise nicht schneller als die entsprechende sequenzielle LINQ to Objects\-Abfrage ausgeführt.  Weitere Informationen über Geschwindigkeitssteigerungen finden Sie unter [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Beispiel  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 Das PLINQ\-Framework wandelt eine einzelne <xref:System.OperationCanceledException> nicht in eine <xref:System.AggregateException?displayProperty=fullName> um. Die <xref:System.OperationCanceledException> muss in einem separaten catch\-Block behandelt werden.  Wenn ein oder mehrere Benutzerdelegaten eine OperationCanceledException\(externalCT\) \(durch Verwendung eines externen <xref:System.Threading.CancellationToken?displayProperty=fullName>\) und keine andere Ausnahme auslösen und die Abfrage zudem als `AsParallel().WithCancellation(externalCT)` definiert wurde, gibt PLINQ eine einzelne <xref:System.OperationCanceledException> \(externalCT\) anstelle einer <xref:System.AggregateException?displayProperty=fullName> aus.  Wenn jedoch ein Benutzerdelegat eine <xref:System.OperationCanceledException> und ein anderer Delegat einen anderen Ausnahmetyp auslöst, werden beide Ausnahmen in eine <xref:System.AggregateException> umgewandelt.  
  
 Die Faustregel für einen Abbruch lautet wie folgt:  
  
1.  Beim Abbruch eines Benutzerdelegaten sollten Sie PLINQ über das externe <xref:System.Threading.CancellationToken> informieren und eine <xref:System.OperationCanceledException>\(externalCT\) auslösen.  
  
2.  Wenn im Falle eines Abbruchs keine anderen Ausnahmen ausgelöst werden, sollten Sie eine <xref:System.OperationCanceledException> anstelle einer <xref:System.AggregateException> behandeln.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie einen Abbruch behandeln, wann eine rechenintensive Funktion im Benutzercode enthalten ist.  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 Wenn Sie den Abbruch im Benutzercode behandeln, müssen Sie <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in der Abfragedefinition nicht verwenden.  Dies ist jedoch empfehlenswert, da <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> keine Auswirkungen auf die Abfrageleistung hat, der Abbruch so jedoch von Abfrageoperatoren und dem Benutzercode behandelt werden kann.  
  
 Um die Reaktionsgeschwindigkeit des Systems sicherzustellen, empfiehlt es sich, einmal pro Millisekunde nach einem Abbruch zu suchen. Es sind jedoch Intervalle von bis zu 10 Millisekunden zulässig.  Dieses Intervall hat in der Regel keine negativen Auswirkungen auf die Leistung des Codes.  
  
 Wenn ein Enumerator verworfen wird, z. B. wenn Code aus einer foreach\-Schleife \(For Each in Visual Basic\) ausbricht, die Abfrageergebnisse durchläuft, wird die Abfrage abgebrochen, aber keine Ausnahme ausgelöst.  
  
## Siehe auch  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)