---
title: "Potential Pitfalls in Data and Task Parallelism | Microsoft Docs"
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
  - "parallel programming, pitfalls"
ms.assetid: 1e357177-e699-4b8f-9e49-56d3513ed128
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Potential Pitfalls in Data and Task Parallelism
In vielen Fällen können <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> für beträchtliche Leistungssteigerungen im Vergleich zu gewöhnlichen sequenziellen Schleifen sorgen.  Die Parallelisierung der Schleife erhöht jedoch die Komplexität des Vorgangs, was Probleme nach sich ziehen kann, die in sequenziellem Code weniger häufig oder gar nicht vorkommen.  In diesem Thema sind bestimmte Fehlerquellen aufgeführt, die beim Schreiben von parallelen Schleifen vermieden werden sollten.  
  
## Gehen Sie nicht davon aus, dass eine parallele Ausführung immer schneller ist.  
 In bestimmten Fällen kann eine parallele Schleife langsamer als deren sequenzielle Entsprechung ausgeführt werden.  Eine Faustregel besagt, dass die Geschwindigkeit von parallelen Schleifen mit wenigen Iterationen und schnellen Benutzerdelegaten wahrscheinlich kaum zunimmt.  Da jedoch viele Faktoren Einfluss auf die Leistung haben, wird empfohlen, immer die tatsächlichen Ergebnisse zu messen.  
  
## Vermeiden Sie es, in gemeinsam genutzte Speicherpositionen zu schreiben.  
 Bei sequenziellem Code wird regelmäßig aus statischen Variablen oder Klassenfeldern gelesen bzw. in diese geschrieben.  Wenn jedoch mehrere Threads gleichzeitig auf diese Variablen zugreifen, besteht eine hohe Wahrscheinlichkeit für Racebedingungen.  Sie können den Zugriff auf die Variable mithilfe von Sperren zwar synchronisieren, die Synchronisierung geht jedoch zu Lasten der Leistung.  Es empfiehlt sich daher, den Zugriff auf den Freigabezustand in einer parallelen Schleife zu vermeiden oder so weit wie möglich einzuschränken.  Die beste Möglichkeit hierzu ist, die Überladungen von <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> zu verwenden, die eine <xref:System.Threading.ThreadLocal%601?displayProperty=fullName>\-Variable verwenden, um während der Schleifenausführung den threadlokalen Zustand zu speichern.  Weitere Informationen finden Sie unter [How to: Write a Parallel.For Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md) und [How to: Write a Parallel.ForEach Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-thread-local-variables.md).  
  
## Vermeiden Sie eine zu starke Parallelisierung.  
 Mithilfe von parallelen Schleifen übernehmen Sie die Mehrkosten für das Partitionieren der Quellauflistung und das Synchronisieren der Arbeitsthreads.  Die Vorteile der Parallelisierung werden zudem durch die Anzahl der Prozessoren auf dem Computer beschränkt.  Die Ausführung von mehreren rechnergebundenen Threads auf nur einem Prozessor ermöglicht keine Geschwindigkeitssteigerung.  Achten Sie daher darauf, dass Sie eine Schleife nicht zu stark parallelisieren.  
  
 Eine zu starke Parallelisierung tritt vor allem in geschachtelten Schleifen auf, wie im folgenden Ausschnitt angezeigt.  In den meisten Fällen sollte am besten nur die äußere Schleife parallelisiert werden, sofern nicht eine oder mehrere der folgenden Bedingungen erfüllt sind:  
  
-   Die innere Schleife ist bekanntermaßen sehr lang.  
  
-   Sie führen für jede Bestellung eine umfangreiche Berechnung aus. \(Der im Beispiel gezeigte Vorgang ist nicht sehr rechenintensiv.\)  
  
-   Das Zielsystem verfügt über genug Prozessoren für die Verarbeitung der Anzahl von Threads, die durch die Parallelisierung der Abfrage von `cust.Orders` erzeugt werden.  
  
 In allen diesen Fällen empfiehlt es sich, die optimale Abfrageform mithilfe von Tests und Messungen zu ermitteln.  
  
## Vermeiden Sie den Aufruf nicht threadsicherer Methoden.  
 Das Schreiben in nicht threadsichere Instanzmethoden von einer parallelen Schleife aus kann zu Datenbeschädigung führen, die im Programm möglicherweise unerkannt bleiben.  Dies kann Ausnahmen zur Folge haben.  Im folgenden Beispiel würden mehrere Threads gleichzeitig versuchen, die <xref:System.IO.FileStream.WriteByte%2A?displayProperty=fullName>\-Methode aufzurufen, was von der Klasse nicht unterstützt wird.  
  
 [!code-csharp[TPL_Pitfalls#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#04)]
 [!code-vb[TPL_Pitfalls#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#04)]  
  
## Beschränken Sie Aufrufe auf threadsichere Methoden.  
 Die meisten statischen Methoden in .NET Framework sind threadsicher und können von mehreren Threads gleichzeitig aufgerufen werden.  Die damit verbundene Synchronisierung kann jedoch auch in diesen Fällen zu einer erheblichen Verlangsamung der Abfrage führen.  
  
> [!NOTE]
>  Sie können dies testen, indem Sie in den Abfragen Aufrufe von <xref:System.Console.WriteLine%2A> einfügen.  Diese Methode wird jedoch nur in den Dokumentationsbeispielen zu Demonstrationszwecken verwendet. Nutzen Sie sie nur in parallelen Schleifen, wenn dies erforderlich ist.  
  
## Beachten Sie Threadaffinitätsprobleme.  
 Einige Technologien, z. B. COM\-Interoperabilität für STA\-Komponenten \(Singlethread\-Apartment\), Windows Forms und Windows Presentation Foundation \(WPF\), erzeugen Threadaffinitätseinschränkungen, aufgrund derer Code in einem bestimmten Thread ausgeführt werden muss.  Beispielsweise kann sowohl in Windows Forms als auch in WPF nur in einem Thread auf ein Steuerelement zugegriffen werden, in dem es erstellt wurde.  Dies bedeutet z. B., dass Sie kein Listensteuerelement von einer parallelen Schleife aktualisieren können, außer wenn Sie den Threadplaner konfigurieren, um die Arbeit nur im UI\-Thread zu planen.  Weitere Informationen finden Sie unter [How to: Schedule Work on the User Interface \(UI\) Thread](../Topic/How%20to:%20Schedule%20Work%20on%20the%20User%20Interface%20\(UI\)%20Thread.md).  
  
## Seien Sie vorsichtig, wenn Sie in Delegaten warten, die von Parallel.Invoke aufgerufen werden.  
 In bestimmten Umständen wird ein Task von der Task Parallel Library inline ausgeführt, d. h., die Ausführung erfolgt im derzeit ausgeführten Thread. \(Weitere Informationen finden Sie unter [Task Schedulers](../Topic/Task%20Schedulers.md).\) Diese Leistungsoptimierung kann in bestimmten Fällen einen Deadlock zur Folge haben.  Beispiel: Bei zwei Tasks wird möglicherweise der gleiche Delegatcode ausgeführt, der signalisiert, wenn ein Ereignis auftritt und anschließend auf die Signalisierung des anderen Tasks wartet.  Wenn der zweite Task im gleichen Thread wie der erste Task inline ausgeführt wird und der erste Task in einen Wartezustand versetzt wird, kann der zweite Task das Ereignis niemals signalisieren.  Um dies zu vermeiden, können Sie für den Wartevorgang ein Timeout angeben oder explizite Threadkonstruktoren verwenden, um sicherzustellen, dass ein Task nicht den anderen blockieren kann.  
  
## Gehen Sie nicht davon aus, dass Iterationen von "ForEach", "For" und "ForAll" immer parallel ausgeführt werden.  
 Berücksichtigen Sie, dass einzelne Iterationen in einer <xref:System.Threading.Tasks.Parallel.For%2A>\-Schleife, einer <xref:System.Threading.Tasks.Parallel.ForEach%2A>\-Schleife oder einer <xref:System.Linq.ParallelEnumerable.ForAll%2A>\-Schleife möglicherweise, jedoch nicht zwingend, parallel ausgeführt werden.  Schreiben Sie daher nach Möglichkeit keinen Code, dessen Korrektheit von der parallelen Ausführung von Iterationen oder der Ausführung von Iterationen in einer bestimmten Reihenfolge abhängig ist.  Beim folgenden Code ist z. B. ein Deadlock wahrscheinlich:  
  
 [!code-csharp[TPL_Pitfalls#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#01)]
 [!code-vb[TPL_Pitfalls#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#01)]  
  
 In diesem Beispiel wird durch eine Iteration ein Ereignis festgelegt, und alle anderen Iterationen warten auf das Ereignis.  Die wartenden Iterationen können erst nach Abschluss der Ereigniseinstellungsiteration abgeschlossen werden.  Es ist jedoch möglich, dass die wartenden Iterationen alle Threads blockieren, die zur Ausführung der parallelen Schleife verwendet werden, bevor die Ereigniseinstellungsiteration überhaupt ausgeführt werden kann.  Dies führt zu einem Deadlock. Die Ereigniseinstellungsiteration wird niemals ausgeführt, und die wartenden Iterationen werden zu keinem Zeitpunkt aktiviert.  
  
 Insbesondere sollte eine Iteration einer parallelen Schleife nie auf den Fortschritt einer anderen Iteration der Schleife warten.  Wenn von der parallelen Schleife entschieden wird, die Iterationen sequenziell zu planen, jedoch in der entgegengesetzten Reihenfolge, tritt ein Deadlock auf.  
  
## Vermeiden der Ausführung paralleler Schleifen im UI\-Thread  
 Es ist wichtig, die Reaktionsfähigkeit der Benutzeroberfläche der Anwendung zu erhalten.  Wenn ein Vorgang genug Arbeit enthält, um Parallelisierung zu garantieren, darf der Vorgang wahrscheinlich nicht im UI\-Thread ausgeführt werden.  Stattdessen sollte der Vorgang abgeladen werden, um eine Ausführung als Hintergrundthread zu ermöglichen.  Wenn Sie z. B. eine parallele Schleife verwenden möchten, um einige Daten zu berechnen, die dann in ein UI\-Steuerelement gerendert werden sollen möchten, führen Sie die Schleife ggf. innerhalb einer Aufgabeninstanz und nicht direkt in einem UI\-Ereignishandler aus.  Erst nach der Kernberechnung können Sie die Aktualisierung der Benutzeroberfläche zurück zum UI\-Thread marshallen.  
  
 Wenn Sie parallele Schleifen im UI\-Thread ausführen, aktualisieren Sie innerhalb der Schleife keine Benutzeroberflächenelemente.  Der Versuch, UI\-Steuerelemente innerhalb einer parallelen Schleife zu aktualisieren, die im UI\-Thread ausgeführt wird, kann zu Zustandsbeschädigung, Ausnahmen, verzögerten Updates und sogar Deadlocks führen, und zwar abhängig davon, wie das Update der Benutzeroberfläche aufgerufen wird.  Im folgenden Beispiel blockiert die parallele Schleife den UI\-Thread, in dem sie ausgeführt wird, bis alle Iterationen abgeschlossen wurden.  Wenn eine Iteration der Schleife jedoch in einem Hintergrundthread ausgeführt wird \(möglicherweise wie bei <xref:System.Threading.Tasks.Parallel.For%2A>\), verursacht der Aufruf von "Invoke" die Übermittlung einer Meldung an den UI\-Thread, und er blockiert das Warten auf die Verarbeitung der Nachricht.  Da der UI\-Thread, in dem <xref:System.Threading.Tasks.Parallel.For%2A> ausgeführt wird, blockiert ist, kann die Nachricht nie verarbeitet werden, und im UI\-Thread kommt es zu einem Deadlock.  
  
 [!code-csharp[TPL_Pitfalls#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#02)]
 [!code-vb[TPL_Pitfalls#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#02)]  
  
 Im folgenden Beispiel wird gezeigt, wie der Deadlock vermieden wird, indem die Schleife in einer Aufgabeninstanz ausgeführt wird.  Der UI\-Thread wird nicht von der Schleife blockiert, und die Meldung kann verarbeitet werden.  
  
 [!code-csharp[TPL_Pitfalls#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#03)]
 [!code-vb[TPL_Pitfalls#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#03)]  
  
## Siehe auch  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [Potential Pitfalls with PLINQ](../../../docs/standard/parallel-programming/potential-pitfalls-with-plinq.md)   
 [Muster für parallele Programmierung: Verstehen und parallele Muster mit .NET Framework 4 analog](http://go.microsoft.com/fwlink/?LinkID=185142)