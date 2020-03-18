---
title: 'Gewusst wie: Schreiben einer einfachen Parallel.For-Schleife'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Parallel.For, How to Write
- for loop, parallel construction in .NET
- parallel for loops, how to use
ms.assetid: 9029ba7f-a9d1-4526-8c84-c88716dba5d4
ms.openlocfilehash: 78f07a4f0118c6bce7a043f111988281ddd6add0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139659"
---
# <a name="how-to-write-a-simple-parallelfor-loop"></a>Gewusst wie: Schreiben einer einfachen Parallel.For-Schleife

Dieses Thema enthält zwei Beispiele, die die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Methode veranschaulichen. Im ersten Beispiel wird die <xref:System.Threading.Tasks.Parallel.For%28System.Int64%2CSystem.Int64%2CSystem.Action%7BSystem.Int64%7D%29?displayProperty=nameWithType>-Methodenüberladung und im zweiten Beispiel wird die <xref:System.Threading.Tasks.Parallel.For%28System.Int32%2CSystem.Int32%2CSystem.Action%7BSystem.Int32%7D%29?displayProperty=nameWithType>-Überladung verwendet. Dies beiden Überladungen sind die einfachsten Überladungen der <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Methode. Sie können diese beiden Überladungen der <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Methode verwenden, wenn keiner der folgenden Vorgänge erforderlich ist: Abbrechen der Schleife, vorzeitiges Beenden der Schleifeniterationen oder Beibehalten eines threadlokalen Zustands.

> [!NOTE]
> Diese Dokumentation definiert Delegaten in TPL mithilfe von Lambdaausdrücken. Falls Sie mit der Verwendung von Lambda-Ausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

Im ersten Beispiel wird die Größe der Dateien in einem einzelnen Verzeichnis berechnet. Im zweiten Beispiel wird das Produkt von zwei Matrizen berechnet.

## <a name="directory-size-example"></a>Größenbeispiel für ein Verzeichnis

Dieses Beispiel ist ein einfaches Befehlszeilenprogramm, das die Gesamtgröße der Dateien in einem Verzeichnis berechnet. Das Programm erwartet einen einzelnen Verzeichnispfad als Argument und meldet die Anzahl sowie die Gesamtgröße der Dateien in diesem Verzeichnis. Nachdem das Programm überprüft hat, ob das Verzeichnis vorhanden ist, verwendet es die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Methode, um die Dateien im Verzeichnis aufzuzählen und deren Größen zu bestimmen. Jede Dateigröße wird dann der `totalSize`-Variablen hinzugefügt. Beachten Sie, dass die Addition durch Aufrufen der<xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType>-Methode ausgeführt wird, sodass die Addition als atomarer Vorgang ausgeführt wird. Andernfalls könnten mehrere Aufgaben versuchen, die `totalSize`-Variable gleichzeitig zu aktualisieren.

[!code-csharp[Conceptual.Parallel.For#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.parallel.for/cs/for1.cs#1)]
[!code-vb[Conceptual.Parallel.For#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.parallel.for/vb/for1.vb#1)]

## <a name="matrix-and-stopwatch-example"></a>Matrix- und Stopwatch-Beispiel

In diesem Beispiel wird die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Methode verwendet, um das Produkt von zwei Matrizen zu berechnen. In diesem Beispiel wird außerdem gezeigt, wie die <xref:System.Diagnostics.Stopwatch?displayProperty=nameWithType>-Klasse verwendet werden kann, um die Leistung einer parallelen Schleife mit der einer nicht parallelen Schleife zu vergleichen. Weil in dem Beispiel sehr viel Ausgabe generiert werden kann, wird in ihm ermöglicht, Ausgabe in eine Datei umzuleiten.

[!code-csharp[TPL_Parallel#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleparallelfor.cs#01)]
[!code-vb[TPL_Parallel#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleparallelfor.vb#01)]

Wenn Code, einschließlich Schleifen, parallelisiert wird, besteht ein wichtiges Ziel darin, die Prozessoren so viel wie möglich zu nutzen, ohne den Punkt für die Parallelisierung zu überschreiten, ab dem der Aufwand für die parallele Verarbeitung jegliche Leistungsvorteile negiert. In diesem speziellen Beispiel wird nur die äußere Schleife parallelisiert, weil in der inneren Schleife nicht sehr viel Arbeit ausgeführt wird. Die Kombination aus einer kleinen Menge von Arbeit und unerwünschten Cacheeffekten kann zu Leistungseinbußen in geschachtelten parallelen Schleifen führen. Daher ist eine Parallelisierung der äußeren Schleife die beste Möglichkeit, die Vorteile der Parallelität in den meisten Systemen zu maximieren.

## <a name="the-delegate"></a>Der Delegat

Der dritte Parameter dieser Überladung von <xref:System.Threading.Tasks.Parallel.For%2A> ist ein Delegat des Typs `Action<int>` in C# oder `Action(Of Integer)` in Visual Basic. Ein `Action`-Delegat gibt unabhängig davon, ob er keinen, einen oder sechzehn Typparameter hat, immer „void“ zurück. In Visual Basic wird das Verhalten eines `Action`-Delegaten mit einer `Sub`-Prozedur definiert. Im Beispiel wird ein Lambdaausdruck verwendet, um den Delegaten zu erstellen. Sie können den Delegaten jedoch auch auf andere Art und Weise erstellen. Weitere Informationen finden Sie unter [Lambdaausdrücke in PLINQ und TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

## <a name="the-iteration-value"></a>Der Iterationswert

Der Delegat hat einen einzelnen Eingabeparameter, dessen Wert der aktuellen Iteration entspricht. Dieser Iterationswert wird von der Runtime bereitgestellt, und sein Startwert ist der Index des ersten Elements im Segment (Partition) der Quelle, die im aktuellen Thread verarbeitet wird.

Wenn Sie mehr Kontrolle über den Parallelitätsumfang benötigen, verwenden Sie eine der Überladungen, die einen <xref:System.Threading.Tasks.ParallelOptions?displayProperty=nameWithType>-Eingabeparameter hat, wie z. B.:<xref:System.Threading.Tasks.Parallel.For%28System.Int32%2CSystem.Int32%2CSystem.Threading.Tasks.ParallelOptions%2CSystem.Action%7BSystem.Int32%2CSystem.Threading.Tasks.ParallelLoopState%7D%29?displayProperty=nameWithType>.

## <a name="return-value-and-exception-handling"></a>Rückgabewert und Ausnahmebehandlung

<xref:System.Threading.Tasks.Parallel.For%2A> gibt ein <xref:System.Threading.Tasks.ParallelLoopResult?displayProperty=nameWithType>-Objekt zurück, wenn alle Threads abgeschlossen sind. Dieser Rückgabewert ist hilfreich, wenn Sie eine Schleifeniteration manuell stoppen oder abbrechen, weil im <xref:System.Threading.Tasks.ParallelLoopResult>-Objekt Informationen wie die letzte Iteration, die vollständig ausgeführt wurde, gespeichert sind. Tritt in einem der Threads mindestens eine Ausnahme auf, wird eine <xref:System.AggregateException?displayProperty=nameWithType> ausgelöst.

Im Code dieses Beispiels wird der Rückgabewert von <xref:System.Threading.Tasks.Parallel.For%2A> nicht verwendet.

## <a name="analysis-and-performance"></a>Analyse und Leistung

Mit dem Leistung-Assistenten können die CPU-Nutzung auf Ihrem Computer anzeigen. Zum Experimentieren erhöhen Sie die Anzahl von Spalten und Zeilen in den Matrizen. Je größer die Matrizen sind, desto größer ist der Leistungsunterschied zwischen der parallelen und sequenziellen Version der Berechnung. Wenn die Matrix klein ist, wird die sequenzielle Version wegen des Mehraufwands für das Einrichten der parallelen Schleife schneller ausgeführt.

Synchrone Aufrufe freigegebener Ressourcen, wie die Konsole oder das Dateisystem, verringern die Leistung einer parallelen Schleife erheblich. Wenn Sie die Leistung messen, sollten Sie möglichst versuchen, Aufrufe wie <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> innerhalb der Schleife zu vermeiden.

## <a name="compile-the-code"></a>Kompilieren des Codes

Kopieren Sie diesen Code, und fügen Sie ihn in ein Visual Studio-Projekt ein.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.Tasks.Parallel.For%2A>
- <xref:System.Threading.Tasks.Parallel.ForEach%2A>
- [Datenparallelität](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)
