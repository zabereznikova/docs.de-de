---
title: Threadsynchronisierung (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 04f485d1-8333-4510-9e72-c334e7427e7e
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ec8fa89c8921eadee428a90971d9ae4ce305a109
ms.lasthandoff: 03/13/2017

---
# <a name="thread-synchronization-visual-basic"></a>Threadsynchronisierung (Visual Basic)
In den folgenden Abschnitten wird beschrieben, Funktionen und Klassen, die zum Synchronisieren des Zugriffs auf Ressourcen in Multithreadanwendungen verwendet werden können.  
  
 Einer der Vorteile der Verwendung von mehreren Threads in einer Anwendung ist, dass jeder Thread asynchron ausgeführt wird. Für Windows-Clientanwendungen können zeitintensive Aufgaben im Hintergrund während des Anwendungsfensters ausgeführt werden, und Steuerelemente reaktionsfähig bleiben. Für Server-Applications multithreading bietet die Möglichkeit, jede eingehende Anforderung mit einem anderen Thread zu behandeln. Andernfalls würde jede neue Anforderung erst verarbeitet, erhalten die vorherige Anforderung vollständig erfüllt wurde.  
  
 Allerdings muss der asynchrone Natur des Threads bedeutet, die Zugriff auf Ressourcen wie Dateihandles, Netzwerkschnittstellen und Speicher koordiniert werden. Andernfalls konnte in zwei oder mehr Threads dieselbe Ressource zur gleichen Zeit, jede keine Kenntnis von den anderen Aktionen zugegriffen werden. Das Ergebnis ist unvorhersehbar Daten beschädigt.  
  
 Für einfache Operationen für ganzzahlige numerische Datentypen Synchronisieren von Threads mit Mitgliedern der <xref:System.Threading.Interlocked>Klasse</xref:System.Threading.Interlocked> möglich Für alle anderen Daten können Typen und nicht threadsicheren Ressourcen kann multithreading nur sicher ausgeführt werden mit den Konstrukten in diesem Thema.  
  
 Hintergrundinformationen zur Multithreadprogrammierung finden Sie unter:  
  
-   [Grundlagen des verwalteten Threadings](http://msdn.microsoft.com/library/b2944911-0e8f-427d-a8bb-077550618935)  
  
-   [Verwenden von Threads und Threading](http://msdn.microsoft.com/library/9b5ec2cd-121b-4d49-b075-222cf26f2344)  
  
-   [Verwaltetes Threading Best Practices](http://msdn.microsoft.com/library/e51988e7-7f4b-4646-a06d-1416cee8d557)  
  
## <a name="the-lock-and-synclock-keywords"></a>Die lock- und SyncLock-Schlüsselwörter  
 Visual Basic `SyncLock` Anweisung um sicherzustellen, dass ein Codeblock ohne Unterbrechung vollständig ausgeführt wird von anderen Threads verwendet werden kann. Dies geschieht durch Abrufen einer Sperre gegenseitigen Ausschluss für ein bestimmtes Objekt für die Dauer des Codeblocks.  
  
 Ein `SyncLock` -Anweisung wird ein Objekt als Argument zugewiesen, und ist ein Codeblock, der nur von einem Thread zu einem Zeitpunkt ausgeführt werden soll. Zum Beispiel:  
  
```vb  
Public Class TestThreading  
    Dim lockThis As New Object  
  
    Public Sub Process()  
        SyncLock lockThis  
            ' Access thread-sensitive resources.  
        End SyncLock  
    End Sub  
End Class  
```  
  
 Das Argument bereitgestellt, um die `SyncLock` Schlüsselwort muss ein Objekt basierend auf ein Verweistyp sein und wird verwendet, um den Umfang der Sperre zu definieren. Im obigen Beispiel der sperrenbereich ist für diese Funktion beschränkt, da keine Verweise auf das Objekt `lockThis` außerhalb der Funktion vorhanden ist. Wenn Sie ein solchen Verweis vorhanden war, würde Sperre auf dieses Objekt erweitern. Genau genommen wird das bereitgestellte Objekt verwendet, ausschließlich für die Identifizierung der Ressourcen von mehreren Threads freigegeben wird, sodass sie bezeichnen werden kann. In der Praxis jedoch dieses Objekt dargestellt in der Regel die Ressource, für die die Threadaktivität Synchronisierung erforderlich ist. Beispielsweise ist ein Container-Objekt von mehreren Threads verwendet werden, dann kann der Container übergeben werden, um Sperren und der synchronisierte Codeblock hinter der Sperre werden auf den Container zugreifen. Solange andere Threads Sperren für die gleiche enthalten, bevor Sie darauf zugreifen und dann Zugriff auf das Objekt sicher synchronisiert.  
  
 Im Allgemeinen ist es am besten vermeiden Sie das Sperren auf einer `public` Typ oder Objektinstanzen außerhalb der Kontrolle Ihrer Anwendung. Z. B. `lockThis` kann da Sperrung Code außerhalb Ihrer Kontrolle auf das Objekt ebenfalls problematisch, wenn die Instanz öffentlich zugegriffen werden kann. Dies könnte Deadlocks verursachen, in denen zwei oder mehr Threads für die Version des gleichen Objekts warten. Sperren von öffentlichen Datentypen, im Gegensatz zu einem Objekt können Sie aus demselben Grund Probleme verursachen. Sperren von Zeichenfolgenliteralen ist besonders riskant, da Literalzeichenfolgen sind *Internpool* von der common Language Runtime (CLR). Dies bedeutet, dass eine Instanz von jedem Zeichenfolgenliteral für das gesamte Programm vorhanden ist, genaue das gleiche Objekt dar, das Literal in allen Anwendungsdomänen, die auf allen Threads ausgeführt. Daher führt eine Sperre für eine Zeichenfolge mit dem gleichen Inhalt an einer beliebigen Stelle in den Prozess Anwendungssperren alle Instanzen der Zeichenfolge in der Anwendung. Daher empfiehlt es sich um eine private oder geschützte Member zu sperren, der nicht intern gespeichert werden. Einige Klassen bieten Member speziell für Sperren. Der <xref:System.Array>Typ, z. B. bietet <xref:System.Array.SyncRoot%2A>.</xref:System.Array.SyncRoot%2A> </xref:System.Array> Viele Auflistungstypen bieten eine `SyncRoot` auch Member.  
  
 Weitere Informationen zu den `SyncLock` -Anweisung finden Sie unter den folgenden Themen:  
  
-   [SyncLock-Anweisung](../../../../visual-basic/language-reference/statements/synclock-statement.md)  
  
-   @System.Threading.Monitor  
  
## <a name="monitors"></a>Monitore  
 Wie die `SyncLock` Schlüsselwort Monitore verhindern von Codeblöcken gleichzeitige Ausführung von mehreren Threads. Die <xref:System.Threading.Monitor.Enter%2A>Methode kann nur ein Thread in die folgenden Anweisungen fortgesetzt; alle anderen Threads werden blockiert, bis der Ausführende Thread <xref:System.Threading.Monitor.Exit%2A>.</xref:System.Threading.Monitor.Exit%2A> ruft</xref:System.Threading.Monitor.Enter%2A> Dies ist vergleichbar mit dem `SyncLock` Schlüsselwort. Zum Beispiel:  
  
```vb  
SyncLock x  
    DoSomething()  
End SyncLock  
```  
  
 Dies ist äquivalent zu:  
  
```vb  
Dim obj As Object = CType(x, Object)  
System.Threading.Monitor.Enter(obj)  
Try  
    DoSomething()  
Finally  
    System.Threading.Monitor.Exit(obj)  
End Try  
```  
  
 Mithilfe der `SyncLock` Schlüsselwort ist im allgemeinen Verwendung der <xref:System.Threading.Monitor>direkte, sowohl da `SyncLock` ist präziser, und da `SyncLock` wird sichergestellt, dass der zugrunde liegenden Monitor freigegeben wird, selbst wenn der geschützte Code eine Ausnahme auslöst.</xref:System.Threading.Monitor> Dies erfolgt mit der `Finally` -Schlüsselwort, die ausgeführt werden, den zugehörigen Codeblock unabhängig davon, ob eine Ausnahme ausgelöst wird.  
  
## <a name="synchronization-events-and-wait-handles"></a>Synchronisierungsereignisse und Wait-Handles  
 Mithilfe einer Sperre oder einem Monitor wird verhindert, dass die gleichzeitige Ausführung von Codeblöcken Thread unterschieden, aber diese Konstrukte lassen sich nicht auf einen Thread ein Ereignis in einen anderen zu kommunizieren. Dies erfordert *Synchronisierungsereignisse*, sind Objekte, die einen der beiden Zustände haben signalisiert "und" nicht signalisiert ", können, zu aktivieren und Anhalten von Threads verwendet werden. Threads können vom wird versucht, auf die Synchronisation warten, die zwischen unterbrochen, und durch Ändern des Ereignisstatus signalisiert aktiviert werden können. Wenn ein Thread versucht, auf ein Ereignis zu warten, das bereits signalisiert wird, wird der Thread ohne Verzögerung fortgesetzt.  
  
 Es gibt zwei Arten von Synchronisierungsereignisse: <xref:System.Threading.AutoResetEvent>, und <xref:System.Threading.ManualResetEvent>.</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent> Unterscheiden sich nur in <xref:System.Threading.AutoResetEvent>ändert sich von signalisiert zu nicht signalisierten automatisch es jeweils einen Thread aktiviert.</xref:System.Threading.AutoResetEvent> Dagegen eine <xref:System.Threading.ManualResetEvent>kann eine beliebige Anzahl von Threads über den signalisierten Zustand zu aktivieren und wird nur in den signalisierten Zustand über, wenn die <xref:System.Threading.EventWaitHandle.Reset%2A>wird aufgerufen.</xref:System.Threading.EventWaitHandle.Reset%2A> </xref:System.Threading.ManualResetEvent>  
  
 Threads können erfolgen, und Warten auf Ereignisse durch Aufrufen einer der Wait-Methoden, wie z. B. <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, oder <xref:System.Threading.WaitHandle.WaitAll%2A>.</xref:System.Threading.WaitHandle.WaitAll%2A> </xref:System.Threading.WaitHandle.WaitAny%2A> </xref:System.Threading.WaitHandle.WaitOne%2A> <xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName>bewirkt, dass der Thread wartet, bis ein einzelnes Ereignis signalisiert wird, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName>blockiert einen Thread, bis ein oder mehrere angegebene Ereignisse signalisiert werden, und <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName>den Thread blockiert, bis alle angegebenen Ereignisse signalisiert werden.</xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> </xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName></xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName> Ein Ereignis wird signalisiert, wenn seine <xref:System.Threading.EventWaitHandle.Set%2A>wird aufgerufen.</xref:System.Threading.EventWaitHandle.Set%2A>  
  
 Im folgenden Beispiel ein Thread erstellt und gestartet, indem die `Main` Funktion. Der neue Thread wartet auf ein Ereignis mit der <xref:System.Threading.WaitHandle.WaitOne%2A>-Methode.</xref:System.Threading.WaitHandle.WaitOne%2A> Der Thread wird angehalten, bis das Ereignis durch den primären Thread signalisiert wird, die ausgeführt wird, die `Main` Funktion. Sobald das Ereignis signalisiert wird, gibt die zusätzlichen Threads zurück. In diesem Fall, da das Ereignis nur entweder für einen Thread-Aktivierung verwendet wird die <xref:System.Threading.AutoResetEvent>oder <xref:System.Threading.ManualResetEvent>Klassen verwendet werden.</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent>  
  
```vb  
Imports System.Threading  
  
Module Module1  
    Dim autoEvent As AutoResetEvent  
  
    Sub DoWork()  
        Console.WriteLine("   worker thread started, now waiting on event...")  
        autoEvent.WaitOne()  
        Console.WriteLine("   worker thread reactivated, now exiting...")  
    End Sub  
  
    Sub Main()  
        autoEvent = New AutoResetEvent(False)  
  
        Console.WriteLine("main thread starting worker thread...")  
        Dim t As New Thread(AddressOf DoWork)  
        t.Start()  
  
        Console.WriteLine("main thread sleeping for 1 second...")  
        Thread.Sleep(1000)  
  
        Console.WriteLine("main thread signaling worker thread...")  
        autoEvent.Set()  
    End Sub  
End Module  
```  
  
## <a name="mutex-object"></a>Mutex-Objekt  
 Ein *Mutex* ähnelt einem Monitor; es wird verhindert, dass die gleichzeitige Ausführung eines Codeblocks durch mehrere Threads gleichzeitig. Tatsächlich ist der Name "Mutex" eine Kurzform des Begriffs "sich gegenseitig ausschließende." Im Gegensatz zu Monitoren kann jedoch ein Mutex verwendet werden, prozessübergreifend Threads zu synchronisieren. Ein Mutex wird durch die <xref:System.Threading.Mutex>Klasse</xref:System.Threading.Mutex> dargestellt.  
  
 Ein Mutex wird aufgerufen, wenn für die prozessübergreifende Synchronisierung verwendet wird, eine *benannten Mutex* daran, dass es in einer anderen Anwendung verwendet wird und daher nicht mithilfe einer globalen oder statischen Variablen gemeinsam genutzt werden kann. Es muss ein Name zugewiesen werden, so, dass beide Anwendungen dieselbe Mutex-Objekt zugreifen können.  
  
 Obwohl ein Mutex für die prozessinterne Threadsynchronisierung verwendet werden kann, <xref:System.Threading.Monitor>wird im Allgemeinen empfohlen, da Monitore speziell für .NET Framework entwickelt wurden und daher eine bessere Nutzung der Ressourcen.</xref:System.Threading.Monitor> Im Gegensatz dazu die <xref:System.Threading.Mutex>ist ein Wrapper für ein Win32-Konstrukt.</xref:System.Threading.Mutex> Zwar leistungsstärker als ein Monitor, benötigt ein Mutex Interop-Übergänge, die rechenintensiver sind als die von der <xref:System.Threading.Monitor>Klasse.</xref:System.Threading.Monitor> Ein Beispiel für die Verwendung eines Mutex, finden Sie unter [Mutexe](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).  
  
## <a name="interlocked-class"></a>Interlocked-Klasse  
 Sie können die Methoden der die <xref:System.Threading.Interlocked>Klasse, um Probleme zu vermeiden, die auftreten können, wenn mehrere Threads gleichzeitig versuchen, aktualisieren oder den gleichen Wert vergleichen.</xref:System.Threading.Interlocked> Die Methoden dieser Klasse können Sie problemlos erhöhen, verringern, austauschen und Vergleichen von Werten aus einem beliebigen Thread.  
  
## <a name="readerwriter-locks"></a>ReaderWriter-Sperren  
 In einigen Fällen empfiehlt es sich um eine Ressource zu sperren, nur, wenn Daten geschrieben werden und mehrere Clients gleichzeitig Daten lesen, wenn Daten nicht aktualisiert werden. Die <xref:System.Threading.ReaderWriterLock>-Klasse gewährleistet exklusiven Zugriff auf eine Ressource, während ein Thread die Ressource ändert, erlaubt jedoch einen nicht exklusiven Zugriff beim Lesen der Ressource.</xref:System.Threading.ReaderWriterLock> ReaderWriter-Sperren sind eine nützliche Alternative zu exklusiven Sperren, die andere Threads wartet, selbst wenn diese Threads keine Daten aktualisieren müssen.  
  
## <a name="deadlocks"></a>Deadlocks  
 Threadsynchronisierung in Multithreadanwendungen sehr nützlich ist, aber es besteht immer die Gefahr einer `deadlock`, bei dem mehrere Threads aufeinander warten und die Anwendung zu unterbrechen. Ein Deadlock ist analog zu einer Situation, in der Autos an eine vier-Wege-Stop beendet werden, und jede Person wartet auf den anderen wechseln. Vermeiden von Deadlocks ist wichtig. der Schlüssel ist eine sorgfältige Planung. Sie können häufig Deadlocks Vorhersagen von Multithreadanwendungen abbilden, bevor Sie mit dem Programmieren beginnen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Thread></xref:System.Threading.Thread>   
 <xref:System.Threading.WaitHandle.WaitOne%2A></xref:System.Threading.WaitHandle.WaitOne%2A>   
 <xref:System.Threading.WaitHandle.WaitAny%2A></xref:System.Threading.WaitHandle.WaitAny%2A>   
 <xref:System.Threading.WaitHandle.WaitAll%2A></xref:System.Threading.WaitHandle.WaitAll%2A>   
 <xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A>   
 <xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A>   
 <xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A>   
 <xref:System.Threading.Monitor></xref:System.Threading.Monitor>   
 <xref:System.Threading.Mutex></xref:System.Threading.Mutex>   
 <xref:System.Threading.AutoResetEvent></xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent></xref:System.Threading.ManualResetEvent>   
 <xref:System.Threading.Interlocked></xref:System.Threading.Interlocked>   
 <xref:System.Threading.WaitHandle></xref:System.Threading.WaitHandle>   
 <xref:System.Threading.EventWaitHandle></xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading></xref:System.Threading>   
 <xref:System.Threading.EventWaitHandle.Set%2A></xref:System.Threading.EventWaitHandle.Set%2A>   
 [Multithreadanwendungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)   
 [SyncLock-Anweisung](../../../../visual-basic/language-reference/statements/synclock-statement.md)   
 [Mutexe](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2)   
 @System.Threading.Monitor   
 [Interlocked-Vorgänge](http://msdn.microsoft.com/library/cbda7114-c752-4f3e-ada1-b1e8dd262f2b)   
 [AutoResetEvent](http://msdn.microsoft.com/library/6d39c48d-6b37-4a9b-8631-f2924cfd9c18)   
 [Synchronisieren von Daten für Multithreading](http://msdn.microsoft.com/library/b980eb4c-71d5-4860-864a-6dfe3692430a)
