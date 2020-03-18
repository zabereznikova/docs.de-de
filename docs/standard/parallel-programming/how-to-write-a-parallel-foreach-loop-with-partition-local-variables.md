---
title: 'Vorgehensweise: Schreiben einer Parallel.ForEach-Schleife mit partitionslokalen Variablen'
ms.date: 06/26/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to use local state
ms.assetid: 24b10041-b30b-45cb-aa65-66cf568ca76d
ms.openlocfilehash: cca48889670c3bd67366c879ccede94c89542c8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139681"
---
# <a name="how-to-write-a-parallelforeach-loop-with-partition-local-variables"></a>Vorgehensweise: Schreiben einer Parallel.ForEach-Schleife mit partitionslokalen Variablen

Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Methode geschrieben wird, für die partitionslokale Variablen verwendet werden. Wenn eine <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife ausgeführt wird, wird die Quellauflistung in mehrere Partitionen unterteilt. Jede Partition besitzt eine eigene Kopie der partitionslokalen Variable. Eine partitionslokale Variable ähnelt einer [threadlokalen Variable](xref:System.Threading.ThreadLocal%601). Der Unterschied besteht darin, dass mehrere Partitionen in einem einzelnen Thread ausgeführt werden können.

Der Code und die Parameter in diesem Beispiel ähneln stark der entsprechenden <xref:System.Threading.Tasks.Parallel.For%2A>-Methode. Weitere Informationen finden Sie unter [Gewusst wie: Schreiben einer Parallel.For-Schleife mit threadlokalen Variablen](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md).

Um eine partitionslokale Variable in einer <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife verwenden zu können, müssen Sie eine der Methodenüberladungen aufrufen, die zwei Typparameter erhält. Der erste Typparameter, `TSource`, gibt den Typ des Quellelements, der zweite Typparameter, `TLocal`, den Typ der partitionslokalen Variable an.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType>-Überladung aufgerufen, um die Summe eines Arrays mit einer Million Elementen zu berechnen. Diese Überladung hat vier Parameter:

- `source` ist die Datenquelle. Der Parameter muss <xref:System.Collections.Generic.IEnumerable%601> implementieren. Die Datenquelle in unserem Beispiel ist `IEnumerable<Int32>`-Objekt mit einer Million Mitgliedern, das von der <xref:System.Linq.Enumerable.Range%2A?displayProperty=nameWithType>-Methode zurückgegeben wird.

- `localInit` oder die Funktion, die die partitionslokale Variable initialisiert. Diese Funktion wird einmal für jede Partition aufgerufen, in der der <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Vorgang ausgeführt wird. In unserem Beispiel wird die partitionslokale Variable auf 0 (null) initialisiert.

- `body`, ein <xref:System.Func%604>-Objekt, wird von der parallelen Schleife in jeder Iteration der Schleife aufgerufen. Die Signatur lautet `Func\<TSource, ParallelLoopState, TLocal, TLocal>`. Sie stellen den Code für den Delegaten bereit, und die Schleife übergibt die folgenden Eingabeparameter:

  - Das aktuelle Element von <xref:System.Collections.Generic.IEnumerable%601>.

  - Eine <xref:System.Threading.Tasks.ParallelLoopState>-Variable, die Sie im Code Ihres Delegaten verwenden können, um den Zustand der Schleife zu untersuchen.

  - Die partitionslokale Variable.

  Ihr Delegat gibt die partitionslokale Variable zurück, die dann an die nächste Iteration der Schleife übergeben wird, die in dieser bestimmten Partition ausgeführt wird. Jede Schleifenpartition behält eine separate Instanz dieser Variable bei.

  In dem Beispiel fügt der Delegat den Wert jeder ganzen Zahl zur partitionslokalen Variable hinzu, die einen laufenden Gesamtbetrag der Werte der ganzzahligen Elemente in dieser Partition beibehält.

- `localFinally`, ein `Action<TLocal>`-Delegat, der von <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> aufgerufen wird, wenn die Schleifenvorgänge in jeder Partition abgeschlossen wurden. Die <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Methode übergibt Ihrem `Action<TLocal>`-Delegaten den ersten Wert der partitionslokalen Variable für diese Schleifenpartition, und Sie stellen den Code bereit, der die erforderliche Aktion zum Kombinieren des Ergebnisses von dieser Partition mit den Ergebnissen der anderen Partitionen bereitstellt. Dieser Delegat kann von mehreren Aufgaben gleichzeitig aufgerufen werden. Darum verwendet das Beispiel die <xref:System.Threading.Interlocked.Add%28System.Int32%40%2CSystem.Int32%29?displayProperty=nameWithType>-Methode, um den Zugriff auf die Variable `total` zu synchronisieren. Da der Delegattyp ein <xref:System.Action%601>-Objekt ist, ist kein Rückgabewert vorhanden.

[!code-csharp[TPL_Parallel#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/foreachthreadlocal.cs#04)]
[!code-vb[TPL_Parallel#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/foreachthreadlocal.vb#04)]

## <a name="see-also"></a>Weitere Informationen

- [Datenparallelität](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [How to: Write a Parallel.For Loop with Thread-Local Variables (Vorgehensweise: Schreiben einer Parallel.For-Schleife mit thread-lokalen Variablen)](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)
- [Lambdaausdrücke in PLINQ und TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
