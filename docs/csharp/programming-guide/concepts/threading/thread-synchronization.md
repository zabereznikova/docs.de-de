---
title: Threadsynchronisierung (C#) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e42b1be6-c93c-479f-a148-be0759f1a4e1
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 31b206eb01d778b67acc1a25d3c69e2e1dfd553d
ms.lasthandoff: 03/13/2017

---
# <a name="thread-synchronization-c"></a>Threadsynchronisierung (C#)
In den folgenden Abschnitten werden Funktionen und Klassen beschrieben, die zum Synchronisieren des Zugriffs auf Ressourcen in Multithreadanwendungen verwendet werden können.  
  
 Einer der Vorteile bei der Verwendung von mehreren Threads in einer Anwendung ist, dass jeder Thread asynchron ausgeführt wird. Für Windows-Anwendungen können zeitintensive Aufgaben im Hintergrund ausgeführt werden, während das Anwendungsfenster und Steuerelement reaktionsfähig bleiben. Für Serveranwendungen bietet Multithreading die Möglichkeit, jede eingehende Aufforderung mit einem anderen Thread zu bearbeiten. Andernfalls würde jede neue Anforderung erst dann bearbeitet werden, nachdem die vorherige Anforderung vollständig erfüllt wurde.  
  
 Die asynchrone Eigenschaft des Threads bedeutet jedoch, dass Zugriff auf Ressourcen, wie z.B. Dateihandles, Netzwerkverbindungen und Arbeitsspeicher, koordiniert werden muss. Andernfalls könnten zwei oder mehr Threads auf die selbe Ressource zugreifen, wobei kein Thread weiß, was der andere macht. Die Folge ist eine unvorhersehbare Datenbeschädigung.  
  
 Für einfache Operationen bei ganzzahligen numerischen Datentypen kann das Synchronisieren von Threads mit Membern der Klasse <xref:System.Threading.Interlocked> erreicht werden. Für alle anderen Datentypen sowie nicht threadsichere Ressourcen kann Multithreading nur mithilfe der Konstrukte in diesem Thema ausgeführt werden.  
  
 Hintergrundinformationen zur Multithreadprogrammierung finden Sie unter:  
  
-   [Grundlagen des verwalteten Threadings](http://msdn.microsoft.com/library/b2944911-0e8f-427d-a8bb-077550618935)  
  
-   [Verwenden von Threads und Threading](http://msdn.microsoft.com/library/9b5ec2cd-121b-4d49-b075-222cf26f2344)  
  
-   [Empfohlene Vorgehensweise für das verwaltete Threading](http://msdn.microsoft.com/library/e51988e7-7f4b-4646-a06d-1416cee8d557)  
  
## <a name="the-lock-keyword"></a>Das lock-Schlüsselwort  
 Die `lock`-Anweisung in C# kann verwendet werden, um sicherzugehen, dass ein Codeblock ohne Unterbrechung durch andere Threads vollständig ausgeführt werden kann. Dies geschieht durch das Abrufen einer Sperre für gegenseitigen Ausschluss für ein bestimmtes Objekt für die Dauer des Codeblocks.  
  
 Einer `lock`-Anweisung wird ein Objekt als Argument zugewiesen, gefolgt von einem Codeblock, der nur von einem Thread ausgeführt werden soll. Zum Beispiel:  
  
```csharp  
public class TestThreading  
{  
    private System.Object lockThis = new System.Object();  
  
    public void Process()  
    {  
  
        lock (lockThis)  
        {  
            // Access thread-sensitive resources.  
        }  
    }  
  
}  
```  
  
 Das Argument, das dem Schlüsselwort `lock` bereitgestellt wird, muss ein Objekt sein, dass auf einem Verweistyp basiert und zur Definition des Geltungsbereichs der Sperre verwendet wird. Im obigen Beispiel ist der Geltungsbereich der Sperre auf die Funktion begrenzt, da kein Verweis auf das Objekt `lockThis` außerhalb der Funktion existiert. Wenn solch ein Verweis existieren würde, würde sich der Geltungsbereich der Sperre bis zu diesem Objekt erweitern. Genau genommen wird das bereitgestellte Objekt nur verwendet, um ausschließlich die Ressource zu identifizieren, die in mehreren Threads vorkommt, sodass sie eine beliebige Klasseninstanz sein kann. Jedoch stellt dieses Objekt in der Praxis normalerweise die Ressource dar, für die die Threadsynchronisierung benötigt wird. Wenn z.B. ein Containerobjekt von mehreren Threads verwendet werden soll, kann der Container anschließend zum Sperren übergeben werden, und der synchronisierte Codeblock, der der Sperre folgt, würde dem Container folgen. Solange andere Threads denselben Container sperren, bevor sie darauf zugreifen, ist der Zugriff auf das Objekt anschließend sicher synchronisiert.  
  
 Es ist allgemein am Besten, das Sperren eines `public`-Typs oder einer Objektinstanz außerhalb der Kontrolle Ihrer Anwendung zu vermeiden. `lock(this)` kann z.B. problematisch sein, wenn auf die Instanz öffentlich zugegriffen werden kann, da ein Code außerhalb Ihrer Kontrolle vielleicht auch das Objekt sperrt. Das könnte eine Deadlock-Situation erzeugen, bei der zwei oder mehr Threads auf die Freigabe des gleichen Objekts warten. Das Sperren von öffentlichen Datentypen kann im Gegensatz zu einem Objekt aus demselben Grund Probleme verursachen. Sperren von Zeichenfolgenliteralen ist besonders riskant, da Literalzeichenfolgen von der Common Language Runtime (CLR) *internalisiert* sind. Das bedeutet, dass es eine Instanz jedes Zeichenfolgenliterals für das gesamte Programm gibt. Dieselben Objekte stellen das Literal in jeder laufenden Anwendungsdomäne bei allen Threads dar. Daher sperrt eine Sperre, die an einer Zeichenfolge mit dem gleichen Inhalt an einer beliebigen Stelle angebracht wurde, jede Instanz des Strings in der Anwendung. Deshalb ist es am Besten, ein privates oder geschütztes Member zu sperren, dass nicht internalisiert ist. Einige Klassen bieten Member, die speziell fürs Sperren vorgesehen sind. Der Typ <xref:System.Array> stellt beispielsweise <xref:System.Array.SyncRoot%2A> bereit. Viele Auflistungstypen stellen auch einen `SyncRoot`-Member bereit.  
  
 Weitere Informationen zur `lock`-Anweisung finden Sie unter den folgenden Themen:  
  
-   [lock-Anweisung](../../../../csharp/language-reference/keywords/lock-statement.md)  
  
-   @System.Threading.Monitor  
  
## <a name="monitors"></a>Monitore  
 Monitore verhindern, so wie das Schlüsselwort `lock`, dass Codeblöcke von mehreren Threads gleichzeitig ausgeführt werden. Die Methode <xref:System.Threading.Monitor.Enter%2A> ermöglicht es einem einzigen Thread, mit den folgenden Anweisungen fortzufahren, bis der auszuführende Thread <xref:System.Threading.Monitor.Exit%2A> aufruft. Dies ist vergleichbar mit dem Einsatz des Schlüsselworts `lock`. Zum Beispiel:  
  
```csharp  
lock (x)  
{  
    DoSomething();  
}  
```  
  
 Das entspricht:  
  
```csharp  
System.Object obj = (System.Object)x;  
System.Threading.Monitor.Enter(obj);  
try  
{  
    DoSomething();  
}  
finally  
{  
    System.Threading.Monitor.Exit(obj);  
}  
```  
  
 Die Verwendung des Schlüsselworts `lock` statt des direkten Gebrauchs der Klasse <xref:System.Threading.Monitor> wird allgemein bevorzugt, da `lock` präziser ist und `lock` sicherstellt, dass der zugrunde liegende Monitor freigegeben wird, auch wenn der geschützte Code eine Ausnahme auslöst. Dies erfolgt mit dem Schlüsselwort `finally`, das seinen zugehörigen Codeblock ausführt, egal ob eine Ausnahme ausgelöst wird.  
  
## <a name="synchronization-events-and-wait-handles"></a>Synchronisierungsereignisse und Wait-Handles  
 Das Verwenden einer Sperre oder eines Monitors ist nützlich, um die gleichzeitige Ausführung einer threadempfindlichen Codesperre zu verhindern. Jedoch erlauben diese Konstrukte nicht, dass ein Thread ein Ereignis an einen anderen weitergibt. Dafür sind *Synchronisierungsereignisse* erforderlich, die Objekte sind, die aus einem oder zwei Zuständen – signalisiert und nicht signalisiert – bestehen, die zum Aktivieren und Anhalten von Threads verwendet werden können. Threads können angehalten werden, indem man sie auf ein nicht signalisiertes Synchronisierungsereignis warten lässt, und können aktiviert werden, indem der Ereigniszustand in „signalisiert“ geändert wird. Wenn ein Thread versucht, auf ein Ereignis zu warten, das bereits signalisiert ist, wird der Thread ohne Verzögerung fortgesetzt.  
  
 Es gibt zwei Arten von Synchronisierungsereignissen: <xref:System.Threading.AutoResetEvent> und <xref:System.Threading.ManualResetEvent>. Sie unterscheiden sich nur dadurch, dass <xref:System.Threading.AutoResetEvent> jedes Mal, wenn es einen Thread aktiviert, automatisch von „signalisiert“ auf „nicht signalisiert“ wechselt. Dagegen erlaubt <xref:System.Threading.ManualResetEvent> einer belieben Anzahl von Threads mithilfe seines signalisierten Zustands aktiviert zu werden. Sie werden nur dann in einen nicht signalisierten Zustand zurückversetzt, wenn seine Methode <xref:System.Threading.EventWaitHandle.Reset%2A> aufgerufen wird.  
  
 Threads können dazu gebracht werden, auf Ereignisse zu warten, indem ein Ereignis der Wait-Methoden wie z.B. <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A> oder <xref:System.Threading.WaitHandle.WaitAll%2A> aufgerufen wird. <xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName> bewirkt, dass der Thread solange wartet, bis ein einziges Ereignis signalisiert wird. <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName> sperrt einen Thread, bis ein oder mehrere angegebene Ereignisse signalisiert werden, und <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> sperrt den Thread, bis alle der angegebenen Ereignisse signalisiert werden. Ein Ereignis wird signalisiert, wenn seine Methode <xref:System.Threading.EventWaitHandle.Set%2A> aufgerufen wird.  
  
 Im folgenden Beispiel wird ein Thread von der Funktion `Main` erstellt und gestartet. Der neue Thread wartet auf ein Ereignis mit der Methode <xref:System.Threading.WaitHandle.WaitOne%2A>. Der Thread wird angehalten, bis das Ereignis durch den primären Thread, der die Funktion `Main` ausführt, signalisiert wird. Sobald das Ereignis signalisiert wird, kommt der Hilfsthread zurück. Da in diesem Fall das Ereignis nur für eine Threadaktivierung verwendet wird, könnten entweder die Klassen <xref:System.Threading.AutoResetEvent> oder <xref:System.Threading.ManualResetEvent> verwendet werden.  
  
```csharp  
using System;  
using System.Threading;  
  
class ThreadingExample  
{  
    static AutoResetEvent autoEvent;  
  
    static void DoWork()  
    {  
        Console.WriteLine("   worker thread started, now waiting on event...");  
        autoEvent.WaitOne();  
        Console.WriteLine("   worker thread reactivated, now exiting...");  
    }  
  
    static void Main()  
    {  
        autoEvent = new AutoResetEvent(false);  
  
        Console.WriteLine("main thread starting worker thread...");  
        Thread t = new Thread(DoWork);  
        t.Start();  
  
        Console.WriteLine("main thread sleeping for 1 second...");  
        Thread.Sleep(1000);  
  
        Console.WriteLine("main thread signaling worker thread...");  
        autoEvent.Set();  
    }  
}  
```  
  
## <a name="mutex-object"></a>Mutex-Objekt  
 Ein *Mutex* ähnelt einem Monitor; es wird verhindert, dass die gleichzeitige Ausführung eines Codeblocks durch mehrere Threads zur selben Zeit erfolgt. Tatsächlich ist der Name „Mutex“ eine Kurzform der Bezeichnung „mutually exclusive“ (einander ausschließend). Im Gegensatz zu Monitoren kann ein Mutex jedoch verwendet werden, um Threads prozessübergreifend zu synchronisieren. Ein Mutex wird durch die Klasse <xref:System.Threading.Mutex> dargestellt.  
  
 Wenn ein Mutex für prozessübergreifende Synchronisierungen verwendet wird, wird es als *benanntes Mutex* bezeichnet, da es in einer anderen Anwendung verwendet werden soll, und deshalb nicht durch eine globale oder statische Variable geteilt werden kann. Es muss benannt werden, sodass beide Anwendungen auf das gleiche Mutex-Objekt zugreifen können.  
  
 Obwohl ein Mutex für prozessübergreifende Threadsynchronisierung verwendet werden kann, wird die Verwendung von <xref:System.Threading.Monitor> generell bevorzugt, da Monitore speziell für .NET Framework entwickelt wurden und deshalb Ressourcen besser verwenden. Im Gegensatz dazu ist die Klasse <xref:System.Threading.Mutex> ein Wrapper für ein Win32-Konstrukt. Obwohl es leistungsstärker als ein Monitor ist, braucht ein Mutex Interop-Übergänge, die rechenintensiver sind, als diejenigen, die von der Klasse <xref:System.Threading.Monitor> benötigt werden. Ein Beispiel für die Verwendung eines Mutex finden Sie unter [Mutexe](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).  
  
## <a name="interlocked-class"></a>Interlocked-Klasse  
 Sie können die Methoden der Klasse <xref:System.Threading.Interlocked> verwenden, um Probleme zu verhindern, die auftreten, wenn mehrere Threads gleichzeitig versuchen, den selben Wert zu aktualisieren oder zu vergleichen. Mit den Methoden dieser Klasse können Sie auf sichere Weise Werte eines beliebigen Threads erhöhen, verringern, tauschen und vergleichen.  
  
## <a name="readerwriter-locks"></a>ReaderWriter-Sperren  
 In einigen Fällen möchten Sie möglicherweise eine Ressource nur dann sperren, wenn Daten gerade geschrieben werden, und mehreren Clients erlauben, gleichzeitig Daten zu lesen, wenn sie nicht aktualisiert werden. Die Klasse <xref:System.Threading.ReaderWriterLock> gewährt exklusiven Zugriff auf eine Ressource, während ein Thread die Ressource ändert, erlaubt jedoch einen nicht exklusiven Zugriff beim Lesen der Ressource. Reader/Writer-Sperren sind eine nützliche Alternative zu exklusiven Sperren, die andere Threads warten lassen, selbst wenn diese Threads keine Daten aktualisieren müssen.  
  
## <a name="deadlocks"></a>Deadlocks  
 Threadsynchronisierung ist in Multithreadanwendungen unabdingbar; es besteht jedoch immer die Gefahr, eine `deadlock` zu erzeugen, bei dem mehrere Threads aufeinander warten, und die Anwendung unterbrochen wird. Ein Deadlock kann mit einer Situation verglichen werden, bei der Autos an einer Kreuzung halten und jede Person darauf wartet, dass die andere losfährt. Es ist wichtig, Deadlocks zu vermeiden; der Schlüssel liegt in der sorgfältigen Planung. Sie können häufig Deadlock-Situationen vorhersehen, indem Sie Multithreadanwendungen abbilden, bevor Sie mit dem Programmieren beginnen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Thread>   
 <xref:System.Threading.WaitHandle.WaitOne%2A>   
 <xref:System.Threading.WaitHandle.WaitAny%2A>   
 <xref:System.Threading.WaitHandle.WaitAll%2A>   
 <xref:System.Threading.Thread.Join%2A>   
 <xref:System.Threading.Thread.Start%2A>   
 <xref:System.Threading.Thread.Sleep%2A>   
 <xref:System.Threading.Monitor>   
 <xref:System.Threading.Mutex>   
 <xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent>   
 <xref:System.Threading.Interlocked>   
 <xref:System.Threading.WaitHandle>   
 <xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading>   
 <xref:System.Threading.EventWaitHandle.Set%2A>   
 [Multithreaded Applications (C#) (Multithreadanwendungen (C#))](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)   
 [lock-Anweisung](../../../../csharp/language-reference/keywords/lock-statement.md)   
 [Mutexe](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2)   
 @System.Threading.Monitor   
 [Interlocked-Vorgänge](http://msdn.microsoft.com/library/cbda7114-c752-4f3e-ada1-b1e8dd262f2b)   
 [AutoResetEvent](http://msdn.microsoft.com/library/6d39c48d-6b37-4a9b-8631-f2924cfd9c18)   
 [Datensynchronisierung für Multithreading](http://msdn.microsoft.com/library/b980eb4c-71d5-4860-864a-6dfe3692430a)
