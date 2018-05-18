---
title: Pooling von Threads (C#)
ms.date: 07/20/2015
ms.assetid: 98ae68c1-ace8-44b9-9317-8920ac9ef2b6
ms.openlocfilehash: 42e1dcedc1897dc82bbd13f12882cbef6a5da4c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="thread-pooling-c"></a>Pooling von Threads (C#)
Ein *Threadpool* ist eine Auflistung von Threads, die verwendet werden kann, um verschiedene Aufgaben im Hintergrund auszuführen. (Weitere Hintergrundinformationen finden Sie unter [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md).) Dies lässt den primären Thread frei, um andere Aufgaben asynchron auszuführen.  
  
 Threadpools werden häufig in Serveranwendungen verwendet. Jede eingehende Anforderung wird einem Thread aus dem Threadpool zugeordnet, sodass die Anforderung asynchron verarbeitet werden kann, ohne den primären Thread zu beschäftigen oder die Verarbeitung von nachfolgenden Anforderungen zu verzögern.  
  
 Wenn ein Thread im Pool seine Aufgabe abgeschlossen hat, wird er an eine Warteschlange von wartenden Threads zurückgegeben, in der er wiederverwendet werden. Aufgrund der Wiederverwendung müssen Anwendungen nicht für jede Aufgabe einen neuen Threads erstellen.  
  
 Threadpools haben in der Regel eine maximale Anzahl von Threads. Wenn alle Threads aktiv sind, werden zusätzliche Aufgaben in die Warteschlange eingereiht, bis sie von wieder verfügbaren Threads verarbeitet werden können.  
  
 Sie können einen eigenen Threadpool implementieren. Es ist allerdings einfacher, den Threadpool zu verwenden, der von .NET Framework durch die <xref:System.Threading.ThreadPool>-Klasse bereitgestellt wird.  
  
 Beim Pooling von Threads rufen Sie die <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType>-Methode mit einem Delegat für die Prozedur auf, die Sie ausführen wollen. C# erstellt dann den Thread und führt Ihre Prozedur aus.  
  
## <a name="thread-pooling-example"></a>Beispiele zum Pooling von Threads  
 Das folgende Beispiel zeigt, wie Sie das Pooling von Threads zum Starten von mehreren Aufgaben verwenden können.  
  
```csharp  
public void DoWork()  
{  
    // Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(SomeLongTask));  
    // Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(AnotherLongTask));  
}  
  
private void SomeLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
  
private void AnotherLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
```  
  
 Ein Vorteil des Poolings von Threads ist, dass Sie Argumente in einem Zustandsobjekt an die Aufgabenprozedur übergeben können. Wenn die aufgerufene Prozedur mehr als ein Argument erfordert, können Sie eine Struktur oder eine Instanz einer Klasse in einen `Object`-Datentyp umwandeln.  
  
## <a name="thread-pool-parameters-and-return-values"></a>Parameter und Rückgabewerte des Threadpools  
 Die Rückgabe von Werten aus einem Thread des Threadpools ist nicht einfach. Das Standardverfahren für die Rückgabe von Werten von einem Funktionsaufruf ist nicht zulässig, da `Sub`-Prozeduren die einzigen Typen der Prozedur sind, die in einem Threadpool in die Warteschlagen gestellt werden können. Eine Möglichkeit, wie Sie Parameter und Rückgabewerte bereitstellen können, besteht darin, die Parameter, Rückgabewerte und Methoden in einer Wrapperklasse zu umschließen, wie in [Parameters and Return Values for Multithreaded Procedures (C#) (Parameter und Rückgabewerte für Multithreadprozeduren (C#))](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md) beschrieben wird.  
  
 Ein einfacherer Weg zum Bereitstellen von Parametern und Rückgabewerten besteht darin, die optionale Zustandsobjektvariable `ByVal` der Methode <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> zu verwenden. Wenn Sie diese Variable verwenden, um einen Verweis an eine Instanz einer Klasse zu übergeben, können die Member der Instanz durch den Thread des Threadpools geändert und als Rückgabewerte verwendet werden.  
  
 Es liegt nicht unbedingt auf der Hand, dass Sie ein Objekt ändern können, auf das von einer als Wert übergebenen Variable verwiesen wurde. Dies ist allein möglich, da nur der Objektverweis als Wert übergeben wird. Wenn Sie Member des Objekts ändern, auf das vom Objektverweis verwiesen wurde, werden die Änderungen auf die eigentliche Klasseninstanz angewendet.  
  
 Strukturen können nicht zum Zurückgeben von Werten in Zustandsobjekten verwendet werden. Da Strukturen Werttypen sind, haben Änderungen, die der asynchrone Prozess vornimmt, keine Auswirkungen auf die Elemente der ursprünglichen Struktur. Verwenden Sie Strukturen, um Parameter bereitzustellen, wenn keine Rückgabewerte erforderlich sind.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [Vorgehensweise: Verwenden eines Threadpools (C#)](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [Multithreaded Applications (C#) (Multithreadanwendungen (C#))](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Threadsynchronisierung (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)
