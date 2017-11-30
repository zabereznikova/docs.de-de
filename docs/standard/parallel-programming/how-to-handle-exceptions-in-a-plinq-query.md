---
title: 'Gewusst wie: Behandeln von Ausnahmen in einer PLINQ-Abfrage'
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
helpviewer_keywords: PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 209e0c1bf89f231d03647ae4351279bfdb172e68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a>Gewusst wie: Behandeln von Ausnahmen in einer PLINQ-Abfrage
Im erste Beispiel in diesem Thema wird gezeigt, wie behandelt die <xref:System.AggregateException?displayProperty=nameWithType> , die bei der Ausführung einer PLINQ-Abfrage ausgelöst werden kann. Im zweite Beispiel wird gezeigt, wie Try / Catch-Blöcke in Delegate so nah wie möglich an, in dem die Ausnahme ausgelöst wird, versetzt wird. Auf diese Weise können Sie sie abfangen, sobald sie auftreten, und die Ausführung der Abfrage möglicherweise weiterhin. Wenn Ausnahmen mittels Bubbling wieder an den Verbindungsthread übergeben werden können, ist es möglich, dass eine Abfrage nach dem Auslösen der Ausnahme weiterhin einige Elemente verarbeitet.  
  
 In einigen Fällen Wenn PLINQ, auf die sequenzielle Ausführung ausgewichen und eine Ausnahme auftritt, die Ausnahme möglicherweise werden direkt weitergegeben, und nicht umschlossen eine <xref:System.AggregateException>. Darüber hinaus <xref:System.Threading.ThreadAbortException>s immer direkt weitergegeben.  
  
> [!NOTE]
>  Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio wird in der Zeile, die die Ausnahme auslöst und zeigt eine Fehlermeldung an, die besagt, dass "nicht vom Benutzercode behandelten Ausnahme." Dieser Fehler hat keine Auswirkungen. Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet. Zum verhindern, dass Visual Studio den ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.  
>   
>  Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage. Weitere Informationen zur Beschleunigung finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie Sie den Try / Catch-Blöcke, um den Code zu konzentrieren, die Ausführung der Abfrage zum Abfangen von einem <xref:System.AggregateException?displayProperty=nameWithType>s, die ausgelöst werden.  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 Die Abfrage kann nicht in diesem Beispiel fortgesetzt, nachdem die Ausnahme ausgelöst wird. Nach der Dauer der Anwendungscode, der die Ausnahme abfängt, wurde der PLINQ die Abfrage bereits für alle Threads beendet.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie zum Platzieren von eines Try-Catch-Blocks in einen Delegaten, die es ermöglichen, eine Ausnahme abfangen und Fortsetzen der Ausführung der Abfrage möglich wird.  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Kompilieren und Ausführen dieser Beispiele, kopieren Sie sie in PLINQ-Datenbeispiel, und rufen Sie die Methode aus.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Abgefangen Sie eine Ausnahme nicht, es sei denn, Sie wissen, wie Sie sie behandeln, damit Sie den Status des Programms nicht beschädigt werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
