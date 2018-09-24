---
title: Empfohlene Vorgehensweise für das verwaltete Threading
ms.date: 11/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threading [.NET Framework], design guidelines
- threading [.NET Framework], best practices
- managed threading
ms.assetid: e51988e7-7f4b-4646-a06d-1416cee8d557
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f95fb3ccab7362021a7a195ea199a1370e003dd2
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562371"
---
# <a name="managed-threading-best-practices"></a>Empfohlene Vorgehensweise für das verwaltete Threading
Wenn Sie mehrere Threads verwenden, ist eine sorgfältige Programmierung erforderlich. Für die meisten Aufgaben können Sie die Komplexität reduzieren, indem Sie Ausführungsanforderungen mithilfe von Threadpoolthreads in Warteschlangen einfügen. Dieses Thema behandelt problematische Situationen wie die Koordinierung der Verarbeitung von mehreren Threads oder die Behandlung von blockierenden Threads.  
  
> [!NOTE]
> Ab .NET Framework 4 stellen die Task Parallel Library und PLINQ APIs bereit, die die Komplexität und Risiken der Multithreadprogrammierung etwas reduzieren. Weitere Informationen finden Sie unter [Parallele Programmierung in .NET](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="deadlocks-and-race-conditions"></a>Deadlocks und Racebedingungen  
 Das Multithreading löst Probleme mit dem Durchsatz und der Ansprechempfindlichkeit, verursacht dabei jedoch neue Probleme: Deadlocks und Racebedingungen.  
  
### <a name="deadlocks"></a>Deadlocks  
 Ein Deadlock liegt vor, wenn zwei Threads gleichzeitig versuchen, eine Ressource zu sperren, die der jeweils andere Thread bereits gesperrt hat. Keiner der beiden Threads kann weiter fortgesetzt werden.  
  
 Viele Methoden der Klassen des verwalteten Threadings stellen Timeouts bereit, mit deren Hilfe Sie Deadlocks entdecken können. Im folgenden Code wird beispielsweise versucht, ein Objekt namens `lockObject` zu sperren. Wenn die Sperrung nicht innerhalb von 300 Millisekunden erfolgt, gibt <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> den Wert `false` zurück.  
  
```vb  
If Monitor.TryEnter(lockObject, 300) Then  
    Try  
        ' Place code protected by the Monitor here.  
    Finally  
        Monitor.Exit(lockObject)  
    End Try  
Else  
    ' Code to execute if the attempt times out.  
End If  
```  
  
```csharp  
if (Monitor.TryEnter(lockObject, 300)) {  
    try {  
        // Place code protected by the Monitor here.  
    }  
    finally {  
        Monitor.Exit(lockObject);  
    }  
}  
else {  
    // Code to execute if the attempt times out.  
}  
```  
  
### <a name="race-conditions"></a>Racebedingungen  
 Bei einer Racebedingung handelt es sich um einen Fehler, der auftritt, wenn das Ergebnis eines Programms davon abhängt, welcher von zwei oder mehr Threads einen bestimmten Codeblock zuerst erreicht. Wenn Sie das Programm mehrmals ausführen, werden verschiedene Ergebnisse erzeugt, und das Ergebnis einer bestimmten Ausführung lässt sich nicht vorhersagen.  
  
 Ein einfaches Beispiel einer Racebedingung ist die Erhöhung eines Feldes. Angenommen, eine Klasse besitzt ein privates **static**-Feld (**Shared** in Visual Basic), das jedes Mal, wenn eine Instanz der Klasse erstellt wird, mit Code wie `objCt++;` (C#) oder `objCt += 1` (Visual Basic) erhöht wird. Für diesen Vorgang muss der Wert von `objCt` in ein Register geladen, der Wert erhöht und in `objCt` gespeichert werden.  
  
 In einer Multithreadanwendung kann ein Thread, der den Wert geladen und erhöht hat, von einem anderen Thread präemptiv unterbrochen werden, der dann alle drei Schritte ausführt. Wenn der erste Thread die Ausführung fortsetzt und den Wert speichert, überschreibt er `objCt`, ohne dass dabei berücksichtigt wird, dass der Wert in der Zwischenzeit geändert wurde.  
  
 Diese spezielle Racebedingung lässt sich mit den Methoden der <xref:System.Threading.Interlocked>-Klasse (z. B. <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>) problemlos vermeiden. Weitere Techniken zum Synchronisieren von Daten zwischen mehreren Threads finden Sie unter [Synchronizing Data for Multithreading (Synchronisieren von Daten für Multithreading)](../../../docs/standard/threading/synchronizing-data-for-multithreading.md).  
  
 Racebedingungen können auch auftreten, wenn Sie die Aktivitäten von mehreren Threads synchronisieren. Bei jeder Codezeile, die Sie schreiben, müssen Sie sich überlegen, was passieren kann, wenn ein Thread vor der Ausführung der Zeile (oder jeder einzelnen Anweisung, aus denen die Zeile besteht) präemptiv unterbrochen und die Ausführung von einem anderen Thread fortgesetzt wird.  
  
## <a name="number-of-processors"></a>Anzahl der Prozessoren  
 Die meisten Computer verfügen jetzt über mehrere Prozessoren (auch als Kerne bezeichnet), selbst kleine Geräte wie Tablets und Telefone. Wenn Sie wissen, dass Sie Software entwickeln, die auch auf Computern mit nur einem Prozessor ausgeführt wird, sollten Sie beachten, dass Multithreading auf Computern mit einem Prozessor andere Probleme löst, als auf Computern mit mehreren Prozessoren.  
  
### <a name="multiprocessor-computers"></a>Multiprozessorcomputer  
 Multithreading ermöglicht einen höheren Durchsatz. Zehn Prozessoren können das Zehnfache von einem Prozessor leisten. Dies ist jedoch nur möglich, wenn die Aufgaben so verteilt werden, dass alle zehn gleichzeitig Verarbeitungsschritte ausführen können. Threads stellen eine einfache Methode dar, um die Aufgaben aufzuteilen und die zusätzliche Verarbeitungsleistung auszunutzen. Bei Verwendung von Multithreading auf einem Multiprozessorcomputer gelten die folgenden Grundsätze:  
  
-   Die Anzahl der gleichzeitig ausführbaren Threads ist begrenzt auf die Anzahl der Prozessoren.  
  
-   Ein Hintergrundthread wird nur dann ausgeführt, wenn die Anzahl der ausgeführten Vordergrundthreads kleiner als die Anzahl der Prozessoren ist.  
  
-   Wenn Sie für einen Thread die <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>-Methode aufrufen, hängt es von der Anzahl der Prozessoren und der Anzahl der aktuell auf ihre Ausführung wartenden Threads ab, ob dieser Thread sofort ausgeführt wird oder nicht.  
  
-   Racebedingungen können nicht nur auftreten, weil Threads in einem nicht erwarteten Moment präemptiv unterbrochen werden, sondern auch weil zwei mit verschiedenen Prozessoren ausgeführte Threads miteinander konkurrieren können, um denselben Codeblock zu erreichen.  
  
### <a name="single-processor-computers"></a>Computer mit einem Prozessor  
 Durch Multithreading sorgen Sie für eine höhere Ansprechempfindlichkeit für den Benutzer und nutzen Leerlaufzeiten für Hintergrundaufgaben. Bei Verwendung von Multithreading auf einem Computer mit einem Prozessor gelten die folgenden Grundsätze:  
  
-   Zu jedem Zeitpunkt wird immer nur ein Thread ausgeführt.  
  
-   Ein Hintergrundthread wird nur dann ausgeführt, wenn sich der Hauptbenutzerthread im Leerlauf befindet. Ein Vordergrundthread, der konstant ausgeführt wird, entzieht den Hintergrundthreads Prozessorzeit.  
  
-   Wenn Sie für einen Thread die <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>-Methode aufrufen, wird die Ausführung des Threads erst dann gestartet, wenn der aktuelle Thread die Ausführung beendet oder vom Betriebssystem präemptiv unterbrochen wird.  
  
-   Racebedingungen treten in der Regel auf, weil der Programmierer nicht bedacht hat, dass ein Thread in einem ungeeigneten Moment präemptiv unterbrochen werden kann, wodurch u. U. ein anderer Thread einen Codeblock zuerst erreicht.  
  
## <a name="static-members-and-static-constructors"></a>Statische Member und statische Konstruktoren  
 Eine Klasse wird erst dann initialisiert, wenn ihr Klassenkonstruktor (`static`-Konstruktor in C#, `Shared Sub New` in Visual Basic) nicht mehr ausgeführt wird. Um die Codeausführung für einen nicht initialisierten Typ zu verhindern, blockiert die Common Language Runtime alle Aufrufe von anderen Threads an `static`-Member der Klasse (`Shared`-Member in Visual Basic), bis der Klassenkonstruktor nicht mehr ausgeführt wird.  
  
 Wenn ein Klassenkonstruktor zum Beispiel einen neuen Thread startet und die Threadprozedur einen `static`-Member der Klasse aufruft, wird der neue Thread blockiert, bis der Klassenkonstruktor beendet wird.  
  
 Dies gilt für jeden Typ, der über einen `static`-Konstruktor verfügen kann.  
  
## <a name="general-recommendations"></a>Allgemeine Empfehlungen  
 Beachten Sie bei Verwendung von mehreren Threads die folgenden Richtlinien:  
  
-   Verwenden Sie <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> nicht, um andere Threads zu beenden. Wenn Sie **Abort** für einen anderen Thread aufrufen, wird für diesen Thread mit hoher Wahrscheinlichkeit eine Ausnahme ausgelöst, ohne dass Sie wissen, an welchem Punkt die Verarbeitung unterbrochen wurde.  
  
-   Verwenden Sie <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> und <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>, nicht, um die Aktivitäten mehrerer Threads zu synchronisieren. Verwenden Sie <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> und <xref:System.Threading.Monitor>.  
  
-   Steuern Sie die Ausführung von Arbeitsthreads nicht vom Hauptprogramm aus (beispielsweise unter Verwendung von Ereignissen). Konzipieren Sie das Programm hingegen so, dass Arbeitsthreads dafür zuständig sind, auf auszuführende Aufgaben zu warten, diese auszuführen und die anderen Teile des Programms darüber zu informieren, dass die Aufgaben erledigt wurden. Bei nicht blockierenden Arbeitsthreads sollten Sie u. U. Threadpoolthreads verwenden. <xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> ist in Situationen nützlich, in denen Arbeitsthreads blockieren.  
  
-   Verwenden Sie keine Typen als Sperrobjekte. Das bedeutet, dass Sie Code wie `lock(typeof(X))` in C# oder `SyncLock(GetType(X))` in Visual Basic genauso wie die Verwendung von <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> mit <xref:System.Type>-Objekten vermeiden sollten. Für einen entsprechenden Typ gibt es nur eine Instanz von <xref:System.Type?displayProperty=nameWithType> pro Anwendungsdomäne. Wenn der von Ihnen gesperrte Typ öffentlich ist, kann er von fremdem Code gesperrt werden, was zu Deadlocks führt. Weitere Informationen finden Sie unter [Reliability Best Practices (Empfohlene Vorgehensweise für Zuverlässigkeit)](../../../docs/framework/performance/reliability-best-practices.md).  
  
-   Seien Sie beim Sperren von Instanzen vorsichtig, zum Beispiel `lock(this)` in C# oder `SyncLock(Me)` in Visual Basic. Wenn anderer, für den Typ externer Code in der Anwendung das Objekt sperrt, könnte dies zu Deadlocks führen.  
  
-   Stellen Sie sicher, dass ein Thread, der in einem Monitor überwacht wird, den Monitor verlässt, auch wenn eine Ausnahme auftritt, während der Thread sich im Monitor befindet. Die C#-Anweisung [lock](~/docs/csharp/language-reference/keywords/lock-statement.md) und die Visual Basic-Anweisung [SyncLock](~/docs/visual-basic/language-reference/statements/synclock-statement.md) stellen dieses Verhalten automatisch bereit, wobei sie einen **finally**-Block verwenden, um sicherzustellen, dass <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> aufgerufen wird. Wenn Sie den Aufruf von **Exit** nicht sicherstellen können, empfiehlt sich stattdessen die Verwendung von **Mutex**. Ein Mutex wird automatisch freigegeben, wenn der Thread, in dessen Besitz er sich befindet, beendet wird.  
  
-   Verwenden Sie mehrere Threads nicht für Aufgaben, für die verschiedene Ressourcen benötigt werden, und vermeiden Sie es, mehrere Threads einer einzelnen Ressource zuzuweisen. Aufgaben, die Ein- und Ausgaben umfassen, sollten beispielsweise über einen eigenen Thread verfügen, da der entsprechende Thread während der E/A-Vorgänge blockiert wird. Dies ermöglicht die Ausführung von anderen Threads. Benutzereingaben sind ein weiteres Beispiel für eine Ressource, die von einem für sie reservierten Thread profitiert. Auf einem Computer mit einem einzelnen Prozessor können eine Aufgabe, die eine ressourcenintensive Berechnung erfordert, und Benutzereingaben oder Aufgaben mit E/A-Vorgängen problemlos gleichzeitig ausgeführt werden. Mehrere rechenintensive Aufgaben machen sich jedoch gegenseitig die Ressourcen streitig.  
  
-   Möglicherweise empfiehlt es sich, für einfache Zustandsänderungen statt der <xref:System.Threading.Interlocked>-Anweisung (`lock` in Visual Basic) Methoden der `SyncLock`-Klasse zu verwenden. Die `lock`-Anweisung ist für allgemeine Zwecke gut geeignet, doch für Aktualisierungen, die atomar sein müssen, bietet die <xref:System.Threading.Interlocked>-Klasse eine bessere Leistung. Sie führt intern ein einzelnes lock-Präfix aus, wenn kein Konflikt vorliegt. Achten Sie bei Codeüberprüfungen auf Code wie in den folgenden Beispielen. Im ersten Beispiel wird eine Zustandsvariable erhöht:  
  
    ```vb  
    SyncLock lockObject  
        myField += 1  
    End SyncLock  
    ```  
  
    ```csharp  
    lock(lockObject)   
    {  
        myField++;  
    }  
    ```  
  
     Sie können die Leistung verbessern, indem Sie statt der <xref:System.Threading.Interlocked.Increment%2A>-Anweisung die `lock`-Methode wie folgt verwenden:  
  
    ```vb  
    System.Threading.Interlocked.Increment(myField)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.Increment(myField);  
    ```  
  
    > [!NOTE]
    >  In .NET Framework, Version 2.0, stellt die <xref:System.Threading.Interlocked.Add%2A>-Methode atomare Aktualisierungen in Schrittweiten bereit, die größer als 1 sind.  
  
     Im zweiten Beispiel wird eine Referenztypvariable nur aktualisiert, wenn es sich um einen NULL-Verweis (`Nothing` in Visual Basic) handelt.  
  
    ```vb  
    If x Is Nothing Then  
        SyncLock lockObject  
            If x Is Nothing Then  
                x = y  
            End If  
        End SyncLock  
    End If  
    ```  
  
    ```csharp  
    if (x == null)  
    {  
        lock (lockObject)  
        {  
            if (x == null)  
            {  
                x = y;  
            }  
        }  
    }  
    ```  
  
     Die Leistung kann verbessert werden, indem stattdessen die <xref:System.Threading.Interlocked.CompareExchange%2A>-Methode wie folgt verwendet wird:  
  
    ```vb  
    System.Threading.Interlocked.CompareExchange(x, y, Nothing)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.CompareExchange(ref x, y, null);  
    ```  
  
    > [!NOTE]
    >  In .NET Framework, Version 2.0, verfügt die <xref:System.Threading.Interlocked.CompareExchange%2A>-Methode über eine generische Überladung, die als typsicherer Ersatz für jeden Referenztyp verwendet werden kann.  
  
## <a name="recommendations-for-class-libraries"></a>Empfehlungen für Klassenbibliotheken  
 Beachten Sie die folgenden Richtlinien, wenn Sie Klassenbibliotheken für Multithreading entwerfen:  
  
-   Vermeiden Sie nach Möglichkeit die Notwendigkeit einer Synchronisierung. Dies gilt besonders für häufig verwendeten Code. Beispielsweise kann ein Algorithmus angepasst werden, um eine Racebedingung zu tolerieren und nicht zu unterbinden. Durch unnötige Synchronisierung wird die Leistung verringert, und es entsteht die Gefahr von Deadlocks und Racebedingungen.  
  
-   Machen Sie statische Daten (`Shared` in Visual Basic) standardmäßig threadsicher.  
  
-   Legen Sie Instanzdaten nicht als standardmäßig threadsicher fest. Durch Hinzufügen von Sperren, um threadsicheren Code zu erstellen, wird die Leistung beeinträchtigt, die Sperrenkonflikte werden erhöht, und es entsteht die Gefahr von Deadlocks. Bei den gängigen Anwendungsmodellen führt immer nur ein Thread Benutzercode aus, wodurch die Notwendigkeit der Threadsicherheit reduziert wird. Aus diesem Grund sind .NET Framework-Klassenbibliotheken nicht standardmäßig threadsicher.  
  
-   Vermeiden Sie die Bereitstellung von statischen Methoden, die den statischen Zustand ändern. Bei den üblichen Serverszenarios wird der statische Zustand in mehreren Anforderungen gemeinsam genutzt, d. h., mehrere Threads können den Code gleichzeitig ausführen. Dadurch werden Threadingfehler möglich. Verwenden Sie u. U. ein Entwurfsmuster, bei dem Daten in Instanzen gekapselt werden, die nicht in mehreren Anforderungen gemeinsam genutzt werden. Darüber hinaus können bei der Synchronisierung statischer Daten Aufrufe zwischen statischen Methoden, die den Zustand ändern, zu Deadlocks oder redundanter Synchronisierung führen und die Leistung beeinträchtigen.  
  
## <a name="see-also"></a>Siehe auch

- [Threading](../../../docs/standard/threading/index.md)  
- [Threads and Threading (Threads und Threading)](../../../docs/standard/threading/threads-and-threading.md)
