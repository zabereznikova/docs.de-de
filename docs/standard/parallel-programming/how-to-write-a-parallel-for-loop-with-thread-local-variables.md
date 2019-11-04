---
title: 'Vorgehensweise: Schreiben einer Parallel.For-Schleife mit threadlokalen Variablen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel for loops, how to use local state
ms.assetid: 68384064-7ee7-41e2-90e3-71f00bde01bb
ms.openlocfilehash: 14f4f1402f564d38bb508e893521a3951c1509f4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139709"
---
# <a name="how-to-write-a-parallelfor-loop-with-thread-local-variables"></a>Vorgehensweise: Schreiben einer Parallel.For-Schleife mit threadlokalen Variablen
Dieses Beispiel zeigt, wie Sie threadlokale Variablen verwenden, um den Status in jeder separaten Aufgabe zu speichern und abzurufen, die von einer <xref:System.Threading.Tasks.Parallel.For%2A>-Schleife erstellt wird. Durch die Verwendung von threadlokalen Daten können Sie den mit der Synchronisierung einer großen Anzahl von Zugriffen auf einen Freigabezustand verbundenen Mehraufwand vermeiden. Statt an eine freigegebene Ressourcen in jeder Iteration zu schreiben, berechnen und speichern Sie den Wert, bis alle Iterationen für die Aufgabe abgeschlossen sind. Sie können dann das endgültige Ergebnis einmal an die freigegebene Ressource schreiben oder sie an eine andere Methoden übergeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Parallel.For%60%601%28System.Int32%2CSystem.Int32%2CSystem.Func%7B%60%600%7D%2CSystem.Func%7BSystem.Int32%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%600%2C%60%600%7D%2CSystem.Action%7B%60%600%7D%29>-Methode aufgerufen, um die Summe der Werte in einem Array zu berechnen, das eine Million Elemente enthält. Der Wert für jedes Element entspricht dem Index.  
  
 [!code-csharp[TPL_Parallel#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/forandforeach_simple.cs#05)]
 [!code-vb[TPL_Parallel#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/forwiththreadlocal.vb#05)]  
  
 Die ersten zwei Parameter jeder <xref:System.Threading.Tasks.Parallel.For%2A>-Methode geben die Anfangs- und Enditerationswerte an. In dieser Überladung der Methode ist der dritte Parameter die Stelle, an der Sie Ihren lokalen Zustand initialisieren. In diesem Kontext bedeutet lokaler Zustand eine Variable, deren Lebensdauer sich von dem Zeitpunkt gerade vor der ersten Iteration der Schleife im aktuellen Thread bis zu dem Zeitpunkt gerade nach der letzten Iteration erstreckt.  
  
 Der dritte Parameter ist vom Typ <xref:System.Func%601>, wobei `TResult` der Variablentyp ist, der den threadlokalen Zustand speichert. Der Typ wird von dem generischen Typargument beim Aufrufen der generischen <xref:System.Threading.Tasks.Parallel.For%60%601%28System.Int32%2CSystem.Int32%2CSystem.Func%7B%60%600%7D%2CSystem.Func%7BSystem.Int32%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%600%2C%60%600%7D%2CSystem.Action%7B%60%600%7D%29>-Methode definiert, in diesem Fall <xref:System.Int64>. Das Typargument teilt dem Computer den Typ der temporären Variable mit, die verwendet wird, um den threadlokalen Zustand zu speichern. In diesem Beispiel initialisiert der Ausdruck `() => 0` (oder `Function() 0` in Visual Basic) die lokale Threadvariable auf Null. Wenn das generische Typargument ein Referenztyp oder ein benutzerdefinierter Werttyp ist, würde der Ausdruck wie folgt aussehen:  
  
```csharp  
() => new MyClass()  
```  
  
```vb  
Function() new MyClass()  
```  
  
 Der vierte Parameter definiert die Schleifenlogik. Er muss ein Delegat oder Lambdaausdruck sein, dessen Signatur `Func<int, ParallelLoopState, long, long>` in C# oder `Func(Of Integer, ParallelLoopState, Long, Long)` in Visual Basic ist. Der erste Parameter ist der Wert des Schleifenzählers für diese Iteration der Schleife. Der zweite ist ein <xref:System.Threading.Tasks.ParallelLoopState>-Objekt, das verwendet werden kann, um die Schleife zu unterbrechen. Dieses Objekt wird von der <xref:System.Threading.Tasks.Parallel>-Klasse für jedes Auftreten der Schleife bereitgestellt. Der dritte Parameter ist die lokale Threadvariable. Der letzte Parameter ist der Rückgabetyp. In diesem Fall ist der Typ <xref:System.Int64>, weil wir diesen Typ im <xref:System.Threading.Tasks.Parallel.For%2A>-Typargument angegeben haben. Diese Variable hat den Namen `subtotal` und wird vom Lambda-Ausdruck zurückgegeben. Die Rückgabewert wird verwendet, um `subtotal` in jeder folgenden Iteration der Schleife zu initialisieren. Sie können sich diesen letzten Parameter auch als einen Wert vorstellen, der an jede Iteration und dann an den `localFinally`-Delegaten übergeben wird, wenn die letzte Iteration abgeschlossen ist.  
  
 Der fünfte Parameter definiert die Methode, die einmal aufgerufen wird, nachdem alle Iterationen in einem bestimmten Thread abgeschlossen wurden. Der Typ des Eingabearguments entspricht erneut dem Typargument der <xref:System.Threading.Tasks.Parallel.For%60%601%28System.Int32%2CSystem.Int32%2CSystem.Func%7B%60%600%7D%2CSystem.Func%7BSystem.Int32%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%600%2C%60%600%7D%2CSystem.Action%7B%60%600%7D%29>-Methode und dem vom Text-Lambda-Ausdruck zurückgegebenen Typ. In diesem Beispiel wird der Wert zu einer Variable im Gültigkeitsbereich einer Klasse auf eine threadsichere Weise hinzugefügt, indem die <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType>-Methode aufgerufen wird. Durch die Verwendung einer lokalen Threadvariable haben wir das Schreiben an diese Klassenvariable in jeder Iteration der Schleife vermieden.  
  
 Weitere Informationen zur Verwendung von Lambdaausdrücken finden Sie unter [Lambdaausdrücke in PLINQ und TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datenparallelität](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)
- [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
- [Lambdaausdrücke in PLINQ und TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
