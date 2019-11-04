---
title: Potenzielle Fehler bei Daten- und Aufgabenparallelität
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel programming, pitfalls
ms.assetid: 1e357177-e699-4b8f-9e49-56d3513ed128
ms.openlocfilehash: ff6ac9e8c41ee203ae72e1b28c088f462ddf6a54
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140021"
---
# <a name="potential-pitfalls-in-data-and-task-parallelism"></a>Potenzielle Fehler bei Daten- und Aufgabenparallelität
In vielen Fällen können <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> erhebliche Leistungssteigerungen gegenüber gewöhnlichen sequenziellen Schleifen bieten. Die Parallelisierung der Schleife erhöht jedoch die Komplexität des Vorgangs, was Probleme nach sich ziehen kann, die in sequenziellem Code weniger häufig oder gar nicht vorkommen. In diesem Thema sind bestimmte Fehlerquellen aufgeführt, die beim Schreiben von parallelen Schleifen vermieden werden sollten.  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a>Gehen Sie nicht davon aus, dass eine parallele Ausführung immer schneller ist.  
 In bestimmten Fällen kann eine parallele Schleife langsamer als deren sequenzielle Entsprechung ausgeführt werden. Eine Faustregel besagt, dass die Geschwindigkeit von parallelen Schleifen mit wenigen Iterationen und schnellen Benutzerdelegaten wahrscheinlich kaum zunimmt. Da jedoch viele Faktoren Einfluss auf die Leistung haben, wird empfohlen, immer die tatsächlichen Ergebnisse zu messen.  
  
## <a name="avoid-writing-to-shared-memory-locations"></a>Vermeiden Sie es, in gemeinsam genutzte Speicherpositionen zu schreiben.  
 Bei sequenziellem Code wird regelmäßig aus statischen Variablen oder Klassenfeldern gelesen bzw. in diese geschrieben. Wenn jedoch mehrere Threads gleichzeitig auf diese Variablen zugreifen, besteht eine hohe Wahrscheinlichkeit für Racebedingungen. Sie können den Zugriff auf die Variable mithilfe von Sperren zwar synchronisieren, die Synchronisierung geht jedoch zu Lasten der Leistung. Es empfiehlt sich daher, den Zugriff auf den Freigabezustand in einer parallelen Schleife zu vermeiden oder so weit wie möglich einzuschränken. Dies geschieht am besten durch Verwendung der Überladungen von <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>, die eine <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>-Variable zum Speichern des threadlokalen Zustands während der Schleifenausführung verwenden. Weitere Informationen finden Sie unter [Vorgehensweise: Schreiben einer Parallel.For-Schleife mit threadlokalen Variablen](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md) und [Vorgehensweise: Schreiben einer Parallel.ForEach-Schleife mit partitionslokalen Variablen](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-partition-local-variables.md).  
  
## <a name="avoid-over-parallelization"></a>Vermeiden Sie eine zu starke Parallelisierung.  
 Mithilfe von parallelen Schleifen übernehmen Sie die Mehrkosten für das Partitionieren der Quellauflistung und das Synchronisieren der Arbeitsthreads. Die Vorteile der Parallelisierung werden zudem durch die Anzahl der Prozessoren auf dem Computer beschränkt. Die Ausführung von mehreren rechnergebundenen Threads auf nur einem Prozessor ermöglicht keine Geschwindigkeitssteigerung. Achten Sie daher darauf, dass Sie eine Schleife nicht zu stark parallelisieren.  
  
 Eine zu starke Parallelisierung tritt vor allem in geschachtelten Schleifen auf, wie im folgenden Ausschnitt gezeigt wird. In den meisten Fällen sollte idealerweise nur die äußere Schleife parallelisiert werden, sofern nicht eine oder mehrere der folgenden Bedingungen erfüllt sind:  
  
- Die innere Schleife ist bekanntermaßen sehr lang.  
  
- Sie führen für jede Bestellung eine umfangreiche Berechnung aus. (Der im Beispiel gezeigte Vorgang ist nicht sehr rechenintensiv.)  
  
- Das Zielsystem verfügt über genug Prozessoren für die Verarbeitung der Anzahl von Threads, die durch die Parallelisierung der Abfrage von `cust.Orders` erzeugt werden.  
  
 In allen diesen Fällen empfiehlt es sich, die optimale Abfrageform mithilfe von Tests und Messungen zu ermitteln.  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a>Vermeiden Sie den Aufruf nicht threadsicherer Methoden.  
 Das Schreiben in nicht threadsichere Instanzmethoden von einer parallelen Schleife aus kann zu Datenbeschädigungen führen, die im Programm möglicherweise unerkannt bleiben. Dies kann auch zu Ausnahmen führen. Im folgenden Beispiel würden mehrere Threads gleichzeitig versuchen, die <xref:System.IO.FileStream.WriteByte%2A?displayProperty=nameWithType>-Methode aufzurufen, was von der Klasse nicht unterstützt wird.  
  
 [!code-csharp[TPL_Pitfalls#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#04)]
 [!code-vb[TPL_Pitfalls#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#04)]  
  
## <a name="limit-calls-to-thread-safe-methods"></a>Beschränken Sie Aufrufe auf threadsichere Methoden.  
 Die meisten statischen Methoden in .NET Framework sind threadsicher und können von mehreren Threads gleichzeitig aufgerufen werden. Die damit verbundene Synchronisierung kann jedoch auch in diesen Fällen zu einer erheblichen Verlangsamung der Abfrage führen.  
  
> [!NOTE]
> Sie können dies testen, indem Sie in Ihre Abfragen Aufrufe von <xref:System.Console.WriteLine%2A> einfügen. Diese Methode wird jedoch nur in den Dokumentationsbeispielen zu Demonstrationszwecken verwendet. Nutzen Sie sie nur in parallelen Schleifen, wenn dies erforderlich ist.  
  
## <a name="be-aware-of-thread-affinity-issues"></a>Beachten Sie Threadaffinitätsprobleme.  
 Einige Technologien, z. B. COM-Interoperabilität für STA-Komponenten (Singlethread-Apartment), Windows Forms und Windows Presentation Foundation (WPF), erzeugen Threadaffinitätseinschränkungen, aufgrund derer Code in einem bestimmten Thread ausgeführt werden muss. Beispielsweise kann sowohl in Windows Forms als auch in WPF nur in einem Thread auf ein Steuerelement zugegriffen werden, in dem es erstellt wurde. Dies bedeutet beispielsweise, dass Sie kein Listensteuerelement von einer parallelen Schleife aktualisieren können, außer wenn Sie den Threadplaner konfigurieren, um die Arbeit nur im UI-Thread zu planen. Weitere Informationen finden Sie unter [Angeben eines Synchronisierungskontexts](xref:System.Threading.Tasks.TaskScheduler#specifying-a-synchronization-context).  
  
## <a name="use-caution-when-waiting-in-delegates-that-are-called-by-parallelinvoke"></a>Seien Sie vorsichtig, wenn Sie in Delegaten warten, die von Parallel.Invoke aufgerufen werden.  
 Unter bestimmten Umständen wird ein Task von der Task Parallel Library inline ausgeführt, d.h. die Ausführung erfolgt im derzeit ausgeführten Thread. (Weitere Informationen finden Sie unter [TaskScheduler-Klasse](xref:System.Threading.Tasks.TaskScheduler).) Diese Leistungsoptimierung kann in bestimmten Fällen einen Deadlock zur Folge haben. Beispiel: Bei zwei Tasks wird möglicherweise der gleiche Delegatcode ausgeführt, der signalisiert, wenn ein Ereignis auftritt und anschließend auf die Signalisierung des anderen Tasks wartet. Wenn der zweite Task im gleichen Thread wie der erste Task inline ausgeführt wird und der erste Task in einen Wartezustand versetzt wird, kann der zweite Task das Ereignis niemals signalisieren. Um dies zu vermeiden, können Sie für den Wartevorgang ein Timeout angeben oder explizite Threadkonstruktoren verwenden, um sicherzustellen, dass ein Task nicht den anderen blockieren kann.  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a>Gehen Sie nicht davon aus, dass Iterationen von „ForEach“, „For“ und „ForAll“ immer parallel ausgeführt werden.  
 Beachten Sie unbedingt, dass einzelne Iterationen in einer <xref:System.Threading.Tasks.Parallel.For%2A>-, <xref:System.Threading.Tasks.Parallel.ForEach%2A>- oder <xref:System.Linq.ParallelEnumerable.ForAll%2A>-Schleife parallel ausgeführt werden können, jedoch nicht parallel ausgeführt werden müssen. Schreiben Sie daher nach Möglichkeit keinen Code, dessen Korrektheit von der parallelen Ausführung von Iterationen oder der Ausführung von Iterationen in einer bestimmten Reihenfolge abhängig ist. Beim folgenden Code ist z. B. ein Deadlock wahrscheinlich:  
  
 [!code-csharp[TPL_Pitfalls#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#01)]
 [!code-vb[TPL_Pitfalls#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#01)]  
  
 In diesem Beispiel wird durch eine Iteration ein Ereignis festgelegt, und alle anderen Iterationen warten auf das Ereignis. Die wartenden Iterationen können erst nach Abschluss der ereignisauslösenden Iteration abgeschlossen werden. Es ist jedoch möglich, dass die wartenden Iterationen alle Threads blockieren, die zur Ausführung der parallelen Schleife verwendet werden, bevor die ereignisauslösende Iteration überhaupt ausgeführt werden kann. Dies führt zu einem Deadlock. Die ereignisauslösende Iteration wird niemals ausgeführt, und die wartenden Iterationen werden zu keinem Zeitpunkt aktiviert.  
  
 Insbesondere sollte eine Iteration einer parallelen Schleife nie auf den Fortschritt einer anderen Iteration der Schleife warten. Wenn von der parallelen Schleife entschieden wird, die Iterationen sequenziell zu planen, jedoch in der entgegengesetzten Reihenfolge, tritt ein Deadlock auf.  
  
## <a name="avoid-executing-parallel-loops-on-the-ui-thread"></a>Vermeiden Sie die Ausführung paralleler Schleifen im UI-Thread.  
 Es ist wichtig, die Reaktionsfähigkeit der Benutzeroberfläche der Anwendung zu erhalten. Wenn ein Vorgang genug Arbeit enthält, um Parallelisierung zu garantieren, darf der Vorgang wahrscheinlich nicht im UI-Thread ausgeführt werden.  Stattdessen sollte der Vorgang abgeladen werden, um eine Ausführung als Hintergrundthread zu ermöglichen. Wenn Sie z.B. eine parallele Schleife verwenden möchten, um einige Daten zu berechnen, die dann in ein UI-Steuerelement gerendert werden sollen, führen Sie die Schleife ggf. innerhalb einer Aufgabeninstanz und nicht direkt in einem UI-Ereignishandler aus.  Erst nach der Kernberechnung können Sie die Aktualisierung der Benutzeroberfläche zurück zum UI-Thread marshallen.  
  
 Wenn Sie parallele Schleifen im UI-Thread ausführen, aktualisieren Sie innerhalb der Schleife keine Benutzeroberflächenelemente. Der Versuch, UI-Steuerelemente innerhalb einer parallelen Schleife zu aktualisieren, die im UI-Thread ausgeführt wird, kann zu Zustandsbeschädigung, Ausnahmen, verzögerten Updates und sogar Deadlocks führen, und zwar abhängig davon, wie das Update der Benutzeroberfläche aufgerufen wird. Im folgenden Beispiel blockiert die parallele Schleife den UI-Thread, in dem sie ausgeführt wird, bis alle Iterationen abgeschlossen wurden. Wenn eine Iteration der Schleife jedoch in einem Hintergrundthread ausgeführt wird (möglicherweise wie bei <xref:System.Threading.Tasks.Parallel.For%2A>), verursacht der Aufruf von „Invoke“ die Übermittlung einer Meldung an den UI-Thread, und er blockiert das Warten auf die Verarbeitung der Nachricht. Da der UI-Thread, in dem <xref:System.Threading.Tasks.Parallel.For%2A> ausgeführt wird, blockiert ist, kann die Nachricht nie verarbeitet werden, und im UI-Thread kommt es zu einem Deadlock.  
  
 [!code-csharp[TPL_Pitfalls#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#02)]
 [!code-vb[TPL_Pitfalls#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#02)]  
  
 Im folgenden Beispiel wird gezeigt, wie der Deadlock vermieden wird, indem die Schleife in einer Aufgabeninstanz ausgeführt wird. Der UI-Thread wird nicht von der Schleife blockiert, und die Meldung kann verarbeitet werden.  
  
 [!code-csharp[TPL_Pitfalls#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#03)]
 [!code-vb[TPL_Pitfalls#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#03)]  
  
## <a name="see-also"></a>Siehe auch

- [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)
- [Potential Pitfalls with PLINQ (Potenzielle Fehler bei PLINQ)](../../../docs/standard/parallel-programming/potential-pitfalls-with-plinq.md)
- [Patterns for Parallel Programming: Understanding and Applying Parallel Patterns with the .NET Framework 4 (Muster für die parallele Programmierung: Verstehen und Anwenden von parallelen Mustern mit .NET Framework 4)](https://www.microsoft.com/download/details.aspx?id=19222)
