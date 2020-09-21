---
title: Empfohlene Vorgehensweise für das verwaltete Threading
description: Lernen Sie Best Practices für verwaltetes Threading in .NET kennen. Bewältigen Sie schwierige Situationen wie das Koordinieren vieler Threads oder das Behandeln blockierter Threads.
ms.date: 10/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threading [.NET Framework], design guidelines
- threading [.NET Framework], best practices
- managed threading
ms.assetid: e51988e7-7f4b-4646-a06d-1416cee8d557
ms.openlocfilehash: 8d5c37bf2ed80e9b6ea071fcd2080c43be8f6247
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546366"
---
# <a name="managed-threading-best-practices"></a>Best Practices für verwaltetes Threading
Wenn Sie mehrere Threads verwenden, ist eine sorgfältige Programmierung erforderlich. Für die meisten Aufgaben können Sie die Komplexität reduzieren, indem Sie Ausführungsanforderungen mithilfe von Threadpoolthreads in Warteschlangen einfügen. Dieses Thema behandelt problematische Situationen wie die Koordinierung der Verarbeitung von mehreren Threads oder die Behandlung von blockierenden Threads.  
  
> [!NOTE]
> Ab .NET Framework 4 stellen die Task Parallel Library und PLINQ APIs bereit, die die Komplexität und Risiken der Multithreadprogrammierung etwas reduzieren. Weitere Informationen finden Sie unter [Parallele Programmierung in .NET](../parallel-programming/index.md).  
  
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
  
 Diese spezielle Racebedingung lässt sich mit den Methoden der <xref:System.Threading.Interlocked>-Klasse (z. B. <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>) problemlos vermeiden. Weitere Techniken zum Synchronisieren von Daten zwischen mehreren Threads finden Sie unter [Synchronizing Data for Multithreading (Synchronisieren von Daten für Multithreading)](synchronizing-data-for-multithreading.md).  
  
 Racebedingungen können auch auftreten, wenn Sie die Aktivitäten von mehreren Threads synchronisieren. Bei jeder Codezeile, die Sie schreiben, müssen Sie sich überlegen, was passieren kann, wenn ein Thread vor der Ausführung der Zeile (oder jeder einzelnen Anweisung, aus denen die Zeile besteht) präemptiv unterbrochen und die Ausführung von einem anderen Thread fortgesetzt wird.  
  
## <a name="static-members-and-static-constructors"></a>Statische Member und statische Konstruktoren  
 Eine Klasse wird erst dann initialisiert, wenn ihr Klassenkonstruktor (`static`-Konstruktor in C#, `Shared Sub New` in Visual Basic) nicht mehr ausgeführt wird. Um die Codeausführung für einen nicht initialisierten Typ zu verhindern, blockiert die Common Language Runtime alle Aufrufe von anderen Threads an `static`-Member der Klasse (`Shared`-Member in Visual Basic), bis der Klassenkonstruktor nicht mehr ausgeführt wird.  
  
 Wenn ein Klassenkonstruktor zum Beispiel einen neuen Thread startet und die Threadprozedur einen `static`-Member der Klasse aufruft, wird der neue Thread blockiert, bis der Klassenkonstruktor beendet wird.  
  
 Dies gilt für jeden Typ, der über einen `static`-Konstruktor verfügen kann.  

## <a name="number-of-processors"></a>Anzahl von Prozessoren

Die Multithreadarchitektur kann davon beeinflusst werden, ob das System mehrere Prozessoren oder nur einen Prozessor enthält. Weitere Informationen finden Sie unter [Anzahl von Prozessoren](/previous-versions/dotnet/netframework-1.1/1c9txz50(v=vs.71)#number-of-processors).

Verwenden Sie die Eigenschaft <xref:System.Environment.ProcessorCount?displayProperty=nameWithType>, um die zur Laufzeit verfügbare Anzahl von Prozessoren zu bestimmen.
  
## <a name="general-recommendations"></a>Allgemeine Empfehlungen  
 Beachten Sie bei Verwendung von mehreren Threads die folgenden Richtlinien:  
  
- Verwenden Sie <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> nicht, um andere Threads zu beenden. Wenn Sie **Abort** für einen anderen Thread aufrufen, wird für diesen Thread mit hoher Wahrscheinlichkeit eine Ausnahme ausgelöst, ohne dass Sie wissen, an welchem Punkt die Verarbeitung unterbrochen wurde.  
  
- Verwenden Sie <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> und <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>, nicht, um die Aktivitäten mehrerer Threads zu synchronisieren. Verwenden Sie <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> und <xref:System.Threading.Monitor>.  
  
- Steuern Sie die Ausführung von Arbeitsthreads nicht vom Hauptprogramm aus (beispielsweise unter Verwendung von Ereignissen). Konzipieren Sie das Programm hingegen so, dass Arbeitsthreads dafür zuständig sind, auf auszuführende Aufgaben zu warten, diese auszuführen und die anderen Teile des Programms darüber zu informieren, dass die Aufgaben erledigt wurden. Bei nicht blockierenden Arbeitsthreads sollten Sie u. U. Threadpoolthreads verwenden. <xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> ist in Situationen nützlich, in denen Arbeitsthreads blockieren.  
  
- Verwenden Sie keine Typen als Sperrobjekte. Das bedeutet, dass Sie Code wie `lock(typeof(X))` in C# oder `SyncLock(GetType(X))` in Visual Basic genauso wie die Verwendung von <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> mit <xref:System.Type>-Objekten vermeiden sollten. Für einen entsprechenden Typ gibt es nur eine Instanz von <xref:System.Type?displayProperty=nameWithType> pro Anwendungsdomäne. Wenn der von Ihnen gesperrte Typ öffentlich ist, kann er von fremdem Code gesperrt werden, was zu Deadlocks führt. Weitere Informationen finden Sie unter [Reliability Best Practices (Empfohlene Vorgehensweise für Zuverlässigkeit)](../../framework/performance/reliability-best-practices.md).  
  
- Seien Sie beim Sperren von Instanzen vorsichtig, zum Beispiel `lock(this)` in C# oder `SyncLock(Me)` in Visual Basic. Wenn anderer, für den Typ externer Code in der Anwendung das Objekt sperrt, könnte dies zu Deadlocks führen.  
  
- Stellen Sie sicher, dass ein Thread, der in einem Monitor überwacht wird, den Monitor verlässt, auch wenn eine Ausnahme auftritt, während der Thread sich im Monitor befindet. Die C#-Anweisung [lock](../../csharp/language-reference/keywords/lock-statement.md) und die Visual Basic-Anweisung [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) stellen dieses Verhalten automatisch bereit, wobei sie einen **finally**-Block verwenden, um sicherzustellen, dass <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> aufgerufen wird. Wenn Sie den Aufruf von **Exit** nicht sicherstellen können, empfiehlt sich stattdessen die Verwendung von **Mutex**. Ein Mutex wird automatisch freigegeben, wenn der Thread, in dessen Besitz er sich befindet, beendet wird.  
  
- Verwenden Sie mehrere Threads nicht für Aufgaben, für die verschiedene Ressourcen benötigt werden, und vermeiden Sie es, mehrere Threads einer einzelnen Ressource zuzuweisen. Aufgaben, die Ein- und Ausgaben umfassen, sollten beispielsweise über einen eigenen Thread verfügen, da der entsprechende Thread während der E/A-Vorgänge blockiert wird. Dies ermöglicht die Ausführung von anderen Threads. Benutzereingaben sind ein weiteres Beispiel für eine Ressource, die von einem für sie reservierten Thread profitiert. Auf einem Computer mit einem einzelnen Prozessor können eine Aufgabe, die eine ressourcenintensive Berechnung erfordert, und Benutzereingaben oder Aufgaben mit E/A-Vorgängen problemlos gleichzeitig ausgeführt werden. Mehrere rechenintensive Aufgaben machen sich jedoch gegenseitig die Ressourcen streitig.  
  
- Möglicherweise empfiehlt es sich, für einfache Zustandsänderungen statt der <xref:System.Threading.Interlocked>-Anweisung (`lock` in Visual Basic) Methoden der `SyncLock`-Klasse zu verwenden. Die `lock`-Anweisung ist für allgemeine Zwecke gut geeignet, doch für Aktualisierungen, die atomar sein müssen, bietet die <xref:System.Threading.Interlocked>-Klasse eine bessere Leistung. Sie führt intern ein einzelnes lock-Präfix aus, wenn kein Konflikt vorliegt. Achten Sie bei Codeüberprüfungen auf Code wie in den folgenden Beispielen. Im ersten Beispiel wird eine Zustandsvariable erhöht:  
  
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
    > Verwenden Sie im .NET Framework 2.0 und höher die <xref:System.Threading.Interlocked.Add%2A>-Methode für unteilbare Inkremente größer als 1.  
  
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
            x ??= y;
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
    > Ab .NET Framework 2.0 bietet die Überladung der <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>-Methoden eine typsichere Alternative für Verweistypen.
  
## <a name="recommendations-for-class-libraries"></a>Empfehlungen für Klassenbibliotheken  
 Beachten Sie die folgenden Richtlinien, wenn Sie Klassenbibliotheken für Multithreading entwerfen:  
  
- Vermeiden Sie nach Möglichkeit die Notwendigkeit einer Synchronisierung. Dies gilt besonders für häufig verwendeten Code. Beispielsweise kann ein Algorithmus angepasst werden, um eine Racebedingung zu tolerieren und nicht zu unterbinden. Durch unnötige Synchronisierung wird die Leistung verringert, und es entsteht die Gefahr von Deadlocks und Racebedingungen.  
  
- Machen Sie statische Daten (`Shared` in Visual Basic) standardmäßig threadsicher.  
  
- Legen Sie Instanzdaten nicht als standardmäßig threadsicher fest. Durch Hinzufügen von Sperren, um threadsicheren Code zu erstellen, wird die Leistung beeinträchtigt, die Sperrenkonflikte werden erhöht, und es entsteht die Gefahr von Deadlocks. Bei den gängigen Anwendungsmodellen führt immer nur ein Thread Benutzercode aus, wodurch die Notwendigkeit der Threadsicherheit reduziert wird. Aus diesem Grund sind .NET Framework-Klassenbibliotheken nicht standardmäßig threadsicher.  
  
- Vermeiden Sie die Bereitstellung von statischen Methoden, die den statischen Zustand ändern. Bei den üblichen Serverszenarios wird der statische Zustand in mehreren Anforderungen gemeinsam genutzt, d. h., mehrere Threads können den Code gleichzeitig ausführen. Dadurch werden Threadingfehler möglich. Verwenden Sie u. U. ein Entwurfsmuster, bei dem Daten in Instanzen gekapselt werden, die nicht in mehreren Anforderungen gemeinsam genutzt werden. Darüber hinaus können bei der Synchronisierung statischer Daten Aufrufe zwischen statischen Methoden, die den Zustand ändern, zu Deadlocks oder redundanter Synchronisierung führen und die Leistung beeinträchtigen.  
  
## <a name="see-also"></a>Siehe auch

- [Threading](index.md)
- [Threads and Threading (Threads und Threading)](threads-and-threading.md)
