---
title: 'Gewusst wie: Abbrechen einer PLINQ-Abfrage'
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
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8031758462df45c030b8b75a3507f1bfb44bfd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-plinq-query"></a>Gewusst wie: Abbrechen einer PLINQ-Abfrage
In den folgenden Beispielen werden zwei Möglichkeiten zum Abbrechen einer PLINQ-Abfrage veranschaulicht. Das erste Beispiel zeigt, wie Sie eine Abfrage abgebrochen wird, aus die Daten Durchlauf größtenteils besteht. Im zweite Beispiel wird gezeigt, wie eine Abfrage abbrechen mit einer Funktion, die rechenintensive wird.  
  
> [!NOTE]
>  Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio wird in der Zeile, die die Ausnahme auslöst und zeigt eine Fehlermeldung an, die besagt, dass "nicht vom Benutzercode behandelten Ausnahme." Dieser Fehler hat keine Auswirkungen. Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet. Zum verhindern, dass Visual Studio den ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.  
>   
>  Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 PLINQ-Framework erfolgt kein Rollback für eine einzelne <xref:System.OperationCanceledException> in einer <xref:System.AggregateException?displayProperty=nameWithType>; das <xref:System.OperationCanceledException> müssen in einem separaten Catch-Block behandelt werden. Wenn eine oder mehrere Benutzerdelegaten eine OperationCanceledException(externalCT) (mithilfe ein externen <xref:System.Threading.CancellationToken?displayProperty=nameWithType>), aber keine anderen Ausnahmen und die Abfrage definiert wurde, als `AsParallel().WithCancellation(externalCT)`, dann PLINQ die eine einzelne ausstellen, <xref:System.OperationCanceledException> (ExternalCT) anstelle einer <xref:System.AggregateException?displayProperty=nameWithType>. Löst Sie jedoch, wenn ein Benutzer delegieren einer <xref:System.OperationCanceledException>, ein anderer Delegat löst einen anderen Ausnahmetyp aus, und beide Ausnahmen werden zurückgesetzt, in eine <xref:System.AggregateException>.  
  
 Die allgemeinen Leitfaden zum Abbruch lautet wie folgt:  
  
1.  Wenn Sie Benutzerdelegaten Abbruch ausführen sollten Sie PLINQ informieren Sie über externe <xref:System.Threading.CancellationToken> und löst eine <xref:System.OperationCanceledException>(ExternalCT).  
  
2.  Wenn ein Abbruch auftritt und keine anderen Ausnahmen ausgelöst werden, dann sollten behandelt eine <xref:System.OperationCanceledException> anstelle einer <xref:System.AggregateException>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie zum Abbruch behandelt wird, wenn Sie eine rechenintensive Funktion im Benutzercode haben.  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 Wenn Sie den Abbruch im Benutzercode behandeln, müssen Sie nicht verwenden <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in der Abfragedefinition. Allerdings wird empfohlen, dass Sie da hierzu <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> hat keine Auswirkung auf die abfrageleistung und ermöglicht den Abbruch von Abfrageoperatoren und Benutzercode behandelt werden.  
  
 Um die Reaktionsfähigkeit des Systems zu gewährleisten, wird empfohlen, nach einem Abbruch um einmal pro Millisekunde gesucht; Allerdings wird jedem Zeitraum von bis zu 10 Millisekunden als akzeptabel betrachtet. Diese Häufigkeit sollte nicht negativ auf die Leistung Ihres Codes haben.  
  
 Wenn ein Enumerator verworfen wird, z. B. wenn Code unterbricht aus einer Schleife Foreach (For Each in Visual Basic), die Ergebnisse der Abfrage durchläuft wird die Abfrage abgebrochen wird, jedoch wird keine Ausnahme ausgelöst.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)
