---
title: Einführung in PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, introduction to
ms.assetid: eaa720d8-8999-4eb7-8df5-3c19ca61cad0
ms.openlocfilehash: e9ef72c2691a4dbb9c68202b29e0f5c77dcdaa74
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588181"
---
# <a name="introduction-to-plinq"></a>Einführung in PLINQ

Parallel LINQ (PLINQ) ist eine parallele Implementierung des [LINQ-Musters (Language-Integrated Query)](../../csharp/programming-guide/concepts/linq/index.md). PLINQ implementiert den kompletten Satz von LINQ-Standardabfrageoperatoren als Erweiterungsmethoden für den <xref:System.Linq>-Namespace und verfügt über zusätzliche Operatoren für parallele Vorgänge. PLINQ kombiniert die Einfachheit und Lesbarkeit der LINQ-Syntax mit der Leistungsfähigkeit der parallelen Programmierung.

> [!TIP]
> LINQ bietet ein einheitliches Modell für die typsichere Abfrage beliebiger aufzählbarer Datenquellen. LINQ to Objects ist der Name für LINQ-Abfragen von Auflistungen im Arbeitsspeicher, z. B. <xref:System.Collections.Generic.List%601>, und Arrays. Dieser Artikel setzt Grundkenntnisse in LINQ voraus. Weitere Informationen finden Sie unter [Language-Integrated Query (LINQ)](../../csharp/programming-guide/concepts/linq/index.md).

## <a name="what-is-a-parallel-query"></a>Was ist eine parallele Abfrage?

Eine PLINQ-Abfrage entspricht weitgehend einer nicht parallelen LINQ to Objects-Abfrage. PLINQ-Abfragen werden, ebenso wie sequenzielle LINQ-Abfragen, auf alle <xref:System.Collections.IEnumerable>- oder <xref:System.Collections.Generic.IEnumerable%601>-Datenquellen im Arbeitsspeicher angewendet und weisen eine verzögerte Ausführung auf, d. h. sie werden erst ausgeführt, wenn die Abfrage aufgelistet wird. Der Hauptunterschied besteht darin, dass PLINQ versucht, alle Prozessoren im System vollständig auszuschöpfen. PLINQ partitioniert hierzu die Datenquelle in Segmente und führt dann die Abfrage für jedes Segment parallel in separaten Arbeitsthreads und auf mehreren Prozessoren aus. In vielen Fällen bedeutet eine parallele Ausführung, dass die Abfrage deutlich schneller ausgeführt wird.

Durch die parallele Ausführung kann PLINQ für bestimmte Abfragen eine erheblich höhere Leistung als Legacycode erzielen. Häufig muss hierzu lediglich der <xref:System.Linq.ParallelEnumerable.AsParallel%2A>-Abfragevorgang zur Datenquelle hinzugefügt werden. Die Parallelität kann jedoch eigene Komplexitäten mit sich bringen, und nicht alle Abfragevorgänge werden in PLINQ schneller ausgeführt. Im Gegenteil, manche Abfragen werden durch die Parallelisierung sogar verlangsamt. Sie sollten daher wissen, wie sich bestimmte Aspekte, z. B. Sortierung, auf parallele Abfragen auswirken. Weitere Informationen finden Sie unter [Understanding Speedup in PLINQ (Grundlagen zur Beschleunigung in PLINQ)](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).

> [!NOTE]
> In dieser Dokumentation werden Delegaten in PLINQ mithilfe von Lambdaausdrücken definiert. Falls Sie mit der Verwendung von Lambda-Ausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).

Der Rest dieses Artikels bietet eine Übersicht über die wichtigsten PLINQ-Klassen und erläutert, wie PLINQ-Abfragen erstellt werden. Jeder Abschnitt enthält Links zu ausführlicheren Informationen und Codebeispielen.

## <a name="the-parallelenumerable-class"></a>Die ParallelEnumerable-Klasse

Die <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>-Klasse stellt nahezu die gesamte Funktionalität von PLINQ zur Verfügung. Diese Klasse sowie die restlichen Typen des <xref:System.Linq?displayProperty=nameWithType>-Namespace werden in der Assembly "System.Core.dll" kompiliert. Die standardmäßigen C#- und Visual Basic-Projekte in Visual Studio verweisen auf die Assembly und importiert den Namespace.

<xref:System.Linq.ParallelEnumerable> enthält Implementierungen aller Standardabfrageoperatoren, die von LINQ to Objects unterstützt werden, auch wenn nicht für jeden eine Parallelisierung angestrebt wird. Wenn Sie nicht mit LINQ vertraut sind, lesen Sie [Einführung in LINQ (C#)](../../csharp/programming-guide/concepts/linq/index.md) und [Einführung in LINQ (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md).

Zusätzlich zu den Standardabfrageoperatoren enthält die <xref:System.Linq.ParallelEnumerable>-Klasse einen Satz von Methoden, die spezielle Verhaltensweisen für die parallele Ausführung unterstützen. Diese PLINQ-spezifischen Methoden sind in der folgenden Tabelle aufgeführt.

|ParallelEnumerable-Operator|Beschreibung|
|---------------------------------|-----------------|
|<xref:System.Linq.ParallelEnumerable.AsParallel%2A>|Der Einstiegspunkt für PLINQ. Gibt an, dass der Rest der Abfrage nach Möglichkeit parallelisiert werden soll.|
|<xref:System.Linq.ParallelEnumerable.AsSequential%2A>|Gibt an, dass der Rest der Abfrage sequenziell, als nicht parallele LINQ-Abfrage ausgeführt werden soll.|
|<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>|Gibt an, diese PLINQ die Reihenfolge der Quellsequenz im Rest der Abfrage oder bis zu einer Änderung der Reihenfolge, z. B. durch eine orderby-Klausel (Ordner By in Vlsual Basic), beibehalten soll.|
|<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>|Gibt an, dass PLINQ die Reihenfolge der Quellsequenz im Rest der Abfrage nicht beibehalten muss.|
|<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>|Gibt an, diese PLINQ den Zustand des bereitgestellten Abbruchtokens in regelmäßigen Abständen überwachen und die Ausführung auf Anforderung abbrechen soll.|
|<xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>|Gibt die maximale Anzahl von Prozessoren an, die PLINQ zum Parallelisieren der Abfrage verwenden soll.|
|<xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>|Gibt an, wie PLINQ parallele Ergebnisse im Consumerthread wieder in einer Sequenz zusammenführen soll, sofern dies möglich ist.|
|<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>|Gibt an, ob PLINQ die Abfrage parallelisieren soll, selbst wenn diese standardmäßig sequenziell ausgeführt würde.|
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Eine Multithreadenumerationsmethode, die, im Gegensatz zum Durchlaufen der Ergebnisse der Abfrage, eine parallele Verarbeitung der Ergebnisse ermöglicht, ohne dass diese zuvor im Consumerthread zusammengeführt werden.|
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>-Überladung|Eine spezielle Überladung für PLINQ, die eine Zwischenaggregation über lokale Threadpartitionen sowie eine abschließende Aggregationsfunktion zum Kombinieren der Ergebnisse aller Partitionen ermöglicht.|

## <a name="the-opt-in-model"></a>Das Opt-in-Modell

Beim Schreiben einer Abfrage entscheiden Sie sich für PLINQ, indem Sie in der Datenquelle die <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType>-Erweiterungsmethode aufrufen, wie im folgenden Beispiel gezeigt.

[!code-csharp[PLINQ#1](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#1)]
[!code-vb[PLINQ#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#1)]

Die <xref:System.Linq.ParallelEnumerable.AsParallel%2A>-Erweiterungsmethode bindet die nachfolgenden Abfrageoperatoren, in diesem Fall, `where` und `select`, an die <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>-Implementierungen.

## <a name="execution-modes"></a>Ausführungsmodi

Standardmäßig wird PLINQ konservativ ausgeführt. Die PLINQ-Infrastruktur analysiert zur Laufzeit die Gesamtstruktur der Abfrage. Wenn die Abfrage voraussichtlich durch eine Parallelisierung beschleunigt werden kann, partitioniert PLINQ die Quellsequenz in Aufgaben, die gleichzeitig ausgeführt werden können. Kann eine Abfrage nicht sicher parallelisiert werden, führt PLINQ die Abfrage sequenziell aus. Wenn PLINQ die Wahl zwischen einem potenziell rechenintensiven parallelen Algorithmus und einem einfachen sequenziellen Algorithmus hat, entscheidet es sich standardmäßig für den sequenziellen Algorithmus. Mit der <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>-Methode und der <xref:System.Linq.ParallelExecutionMode?displayProperty=nameWithType>-Enumeration können Sie PLINQ anweisen, den parallelen Algorithmus auszuwählen. Dies ist sinnvoll, wenn Sie aufgrund von Tests und Messungen wissen, dass eine bestimmte Abfrage im parallelen Modus schneller ausgeführt wird. Weitere Informationen finden Sie unter [Vorgehensweise: Angeben des Ausführungsmodus in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).

## <a name="degree-of-parallelism"></a>Grad der Parallelität

Standardmäßig verwendet PLINQ alle Prozessoren des Hostcomputers. Mit der <xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>-Methode können Sie PLINQ anweisen, nicht mehr als eine angegebene Anzahl von Prozessoren zu verwenden. Sie können so sicherstellen, dass andere auf dem Computer ausgeführt Prozesse eine bestimmte Menge an CPU-Zeit erhalten. Der folgende Codeausschnitt beschränkt die Abfrage auf maximal zwei Prozessoren.

[!code-csharp[PLINQ#5](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#5)]
[!code-vb[PLINQ#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#5)]

Wenn eine Abfrage eine große Mengen an nicht rechnergebundenen Aufgaben ausführt, z. B. Datei-E/A, kann es von Vorteil sein, einen höheren Grad an Parallelität als die auf dem Rechner verfügbare Anzahl von Kernen anzugeben.

## <a name="ordered-versus-unordered-parallel-queries"></a>Geordnete und ungeordnete parallele Abfragen

Bei einigen Abfragen muss ein Abfrageoperator Ergebnisse erzeugen, die die Reihenfolge der Quellsequenz beibehalten. PLINQ stellt für diesen Zweck den <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>-Operator bereit. <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> unterscheidet sich von <xref:System.Linq.ParallelEnumerable.AsSequential%2A>. Eine <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>-Sequenz wird weiterhin parallel ausgeführt, die Ergebnisse werden jedoch gepuffert und sortiert. Da die Beibehaltung der Reihenfolge in der Regel einen gewissen Mehraufwand bedeutet, wird eine <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>-Sequenz ggf. langsamer verarbeitet als die standardmäßige <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>-Sequenz. Ob ein bestimmter geordneter paralleler Vorgang schneller ist als eine sequenzielle Version des Vorgangs, hängt von vielen Faktoren ab.

Im folgenden Codebeispiel wird gezeigt, wie Sie die Beibehaltung der Reihenfolge aktivieren.

[!code-csharp[PLINQ#3](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#3)]
[!code-vb[PLINQ#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#3)]

Weitere Informationen finden Sie unter [Order Preservation in PLINQ (Beibehaltung der Reihenfolge in PLINQ)](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).

## <a name="parallel-vs-sequential-queries"></a>Parallele und sequenzielle Abfragen

Einige Vorgänge erfordern, dass die Quelldaten sequenziell übergeben werden. Die <xref:System.Linq.ParallelEnumerable>-Abfrageoperatoren stellen automatisch den sequenziellen Modus wieder her, wenn dies erforderlich ist. Für benutzerdefinierte Abfrageoperatoren und Benutzerdelegaten, die eine sequenzielle Ausführung erfordern, stellt PLINQ die <xref:System.Linq.ParallelEnumerable.AsSequential%2A>-Methode bereit. Bei Verwendung von <xref:System.Linq.ParallelEnumerable.AsSequential%2A> werden alle nachfolgenden Operatoren in der Abfrage sequenziell ausgeführt, bis <xref:System.Linq.ParallelEnumerable.AsParallel%2A> erneut aufgerufen wird. Weitere Informationen finden Sie unter [Vorgehensweise: Kombinieren von parallelen und sequenziellen LINQ-Abfragen](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md).

## <a name="options-for-merging-query-results"></a>Optionen für das Zusammenführen von Abfrageergebnissen

Wenn eine PLINQ-Abfrage parallel ausgeführt wird, müssen die Ergebnisse aller Arbeitsthreads wieder im Hauptthread zusammengeführt werden, damit sie in einer `foreach`-Schleife (`For Each` in Visual Basics) verwendet oder in eine Liste bzw. ein Array eingefügt werden können. In einigen Fällen ist es hilfreich, eine bestimmte Art von Merge anzugeben, z. B. um Ergebnisse schneller zu erzeugen. Zu diesem Zweck unterstützt PLINQ die <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>-Methode und die <xref:System.Linq.ParallelMergeOptions>-Enumeration. Weitere Informationen finden Sie unter [Merge Options in PLINQ (Zusammenführungsoptionen in PLINQ)](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).

## <a name="the-forall-operator"></a>Der ForAll-Operator

In sequenziellen LINQ-Abfragen wird die Ausführung verzögert, bis die Abfrage entweder in einer `foreach`-Schleife (`For Each` in Visual Basic) oder durch das Aufrufen einer Methode, z. B. <xref:System.Linq.ParallelEnumerable.ToList%2A>, <xref:System.Linq.ParallelEnumerable.ToArray%2A> oder <xref:System.Linq.ParallelEnumerable.ToDictionary%2A>, aufgezählt wird. In PLINQ können Sie zudem `foreach` verwenden, um die Abfrage auszuführen und die Ergebnisse zu durchlaufen. `foreach` selbst wird jedoch nicht parallel ausgeführt, sodass die Ausgabe aller parallelen Aufgaben wieder in dem Thread, in dem die Schleife ausgeführt wird, zusammengeführt werden muss. In PLINQ können Sie `foreach` verwenden, wenn Sie die abschließende Reihenfolge der Abfrageergebnisse beibehalten möchten oder wenn Sie die Ergebnisse seriell verarbeiten, z. B. wenn Sie für jedes Element `Console.WriteLine` aufrufen. Wenn die Beibehaltung der Reihenfolge nicht erforderlich ist und die Verarbeitung der Ergebnisse selbst parallelisiert werden kann, verwenden Sie die <xref:System.Linq.ParallelEnumerable.ForAll%2A>-Methode, um die Ausführung der PLINQ-Abfrage zu beschleunigen. <xref:System.Linq.ParallelEnumerable.ForAll%2A> führt die abschließende Zusammenführung nicht aus. Im folgenden Codebeispiel wird die Verwendung der <xref:System.Linq.ParallelEnumerable.ForAll%2A>-Methode veranschaulicht. <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType> wird hier verwendet, da sie für mehrere Threads optimiert ist, die gleichzeitig Elemente hinzufügen, ohne dass versucht wird, Elemente zu entfernen.

[!code-csharp[PLINQ#4](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#4)]
[!code-vb[PLINQ#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#4)]

Die folgende Abbildung zeigt den Unterschied zwischen `foreach` und <xref:System.Linq.ParallelEnumerable.ForAll%2A> hinsichtlich der Abfrageausführung.

![ForAll im Vergleich zu ForEach](../../../docs/standard/parallel-programming/media/vs-isvnt-allvseach.png "VS_ISVNT_ALLvsEACH")

## <a name="cancellation"></a>Abbruch

PLINQ ist in die Abbruchtypen in .NET Framework 4 integriert. (Weitere Informationen finden Sie unter [Cancellation in Managed Threads (Abbruch in verwalteten Threads)](../../../docs/standard/threading/cancellation-in-managed-threads.md).) Daher können PLINQ-Abfragen im Gegensatz zu sequenziellen LINQ to Objects-Abfragen abgebrochen werden. Um eine abbrechbare PLINQ-Abfrage zu erstellen, verwenden Sie den <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>-Operator in der Abfrage, und stellen Sie eine <xref:System.Threading.CancellationToken>-Instanz als Argument bereit. Wenn die <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>-Eigenschaft im Token auf „true“ festgelegt ist, erkennt PLINQ dies. Die Verarbeitung wird in diesem Fall in allen Threads abgebrochen, und eine <xref:System.OperationCanceledException> wird ausgelöst.

Es ist möglich, dass eine PLINQ-Abfrage nach dem Festlegen des Abbruchtokens weiterhin einige Elemente verarbeitet.

Um kürzere Reaktionszeiten zu erzielen, können Sie auch auf Abbruchanforderungen in Benutzerdelegaten mit langer Laufzeit reagieren. Weitere Informationen finden Sie unter [Vorgehensweise: Abbrechen einer PLINQ-Abfrage](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md).

## <a name="exceptions"></a>Ausnahmen

Bei der Ausführung einer PLINQ-Abfrage können mehrere Ausnahmen von verschiedenen Threads gleichzeitig ausgelöst werden. Zudem kann sich der Code für die Behandlung einer Ausnahme in einem anderen Thread befinden als der Code, der die Ausnahme ausgelöst hat. PLINQ kapselt alle Ausnahmen, die von einer Abfrage ausgelöst wurden, mithilfe des <xref:System.AggregateException>-Typs und marshallt diese Ausnahmen zurück an den aufrufenden Thread. Im aufrufenden Thread ist nur ein try/catch-Block erforderlich. Sie können jedoch alle Ausnahmen durchlaufen, die in <xref:System.AggregateException> gekapselt sind, und die Ausnahmen erfassen, die Sie sicher beheben können. In seltenen Fällen können Ausnahmen ausgelöst werden, die nicht in einer <xref:System.AggregateException> eingeschlossen sind. <xref:System.Threading.ThreadAbortException>s sind ebenfalls nicht eingeschlossen.

Wenn Ausnahmen mittels Bubbling wieder an den Verbindungsthread übergeben werden können, ist es möglich, dass eine Abfrage nach dem Auslösen der Ausnahme weiterhin einige Elemente verarbeitet.

Weitere Informationen finden Sie unter [Vorgehensweise: Behandeln von Ausnahmen in einer PLINQ-Abfrage](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).

## <a name="custom-partitioners"></a>Benutzerdefinierte Partitionierer

Sie können die Abfrageleistung teilweise erhöhen, indem Sie einen benutzerdefinierten Partitionierer schreiben, der bestimmte Merkmale der Quelldaten nutzt. In der Abfrage ist der benutzerdefinierte Partitionierer das auflistbare Objekt, das abgefragt wird.

[!code-csharp[PLINQ#2](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#2)]
[!code-vb[PLINQ#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq3.vb#2)]

PLINQ unterstützt eine feste Anzahl von Partitionen (auch wenn die Daten während der Laufzeit diesen Partitionen dynamisch neu zugeordnet werden können, um einen Lastenausgleich zu gewährleisten). <xref:System.Threading.Tasks.Parallel.For%2A> und <xref:System.Threading.Tasks.Parallel.ForEach%2A> unterstützen nur die dynamische Partitionierung, d. h. die Anzahl der Partitionen ändert sich zur Laufzeit. Weitere Informationen finden Sie unter [Custom Partitioners for PLINQ and TPL (Benutzerdefinierte Partitionierer für PLINQ und TPL)](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).

## <a name="measuring-plinq-performance"></a>Messen der PLINQ-Leistung

In vielen Fällen kann eine Abfrage parallelisiert werden, der mit dem Einrichten der parallelen Abfrage verbundene Mehraufwand überwiegt jedoch die erzielte Leistungssteigerung. Wenn eine Abfrage nur wenige Berechnung ausführt oder wenn die Datenquelle klein ist, ist eine PLINQ-Abfrage möglicherweise langsamer als ein sequenzielle LINQ to Objects-Abfrage. Mithilfe des Parallel Performance Analyzer in Visual Studio Team Server können Sie die Leistung verschiedener Abfragen vergleichen, Verarbeitungsengpässe suchen und bestimmen, ob die Abfrage parallel oder sequenziell ausgeführt wird. Weitere Informationen finden Sie unter [Parallelitätsschnellansicht](/visualstudio/profiling/concurrency-visualizer) und [Vorgehensweise: Messen der Leistung von PLINQ-Abfragen](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).

## <a name="see-also"></a>Siehe auch

- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
- [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)
