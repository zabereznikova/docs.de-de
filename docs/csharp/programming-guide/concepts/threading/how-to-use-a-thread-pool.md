---
title: 'Vorgehensweise: Verwenden von Threadpools (C#)'
ms.date: 07/20/2015
ms.assetid: 210a9235-83a6-420b-af52-2d6a58e5133f
ms.openlocfilehash: c89093bcff82715482b2ddb822916cfa5ff8ed72
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-thread-pool-c"></a>Vorgehensweise: Verwenden von Threadpools (C#)
*Threadpooling* ist eine Form des Multithreadings, bei dem Aufgaben einer Warteschlange hinzugefügt werden und automatisch gestartet werden, wenn Threads erstellt werden. Weitere Informationen finden Sie unter [Threadpooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md).  
  
 In folgendem Beispiel wird der Threadpool des .NET Frameworks verwendet, um das `Fibonacci`-Ergebnis für zehn Zahlen zwischen 20 und 40 zu berechnen. Jedes `Fibonacci`-Ergebnis wird von der `Fibonacci`-Klasse repräsentiert, die eine Methode mit dem Namen `ThreadPoolCallback` bietet, die die Berechnung durchführt. Ein Objekt, das jeden `Fibonacci`-Wert repräsentiert, wird erstellt, und die `ThreadPoolCallback`-Methode wird an <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> übergeben, das dem Pool einen verfügbaren Thread zuweist, um die Methode auszuführen.  
  
 Weil jedem `Fibonacci`-Objekt ein halb-zufälliger Wert zum Berechnen zugewiesen wird, und weil alle Threads um Prozessorzeit konkurrieren, könne Sie nicht im Voraus abschätzen, wie viel Zeit die Berechnung aller zehn Ergebnisse in Anspruch nehmen wird. Deshalb wird jedem `Fibonacci`-Objekt eine Instanz der <xref:System.Threading.ManualResetEvent>-Klasse während der Konstruktion übergeben. Jedes Objekt gibt dem angegebenen Ereignisobjekt Bescheid, wenn seine Berechnung abgeschlossen ist; dies ermöglicht es dem Thread, die Ausführung mit <xref:System.Threading.WaitHandle.WaitAll%2A> zu blockieren, bis alle zehn `Fibonacci`-Objekte ein Ergebnis berechnet haben. Die `Main`-Methode zeigt dann jedes `Fibonacci`-Ergebnis an.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
using System;  
using System.Threading;  
  
public class Fibonacci  
{  
    private int _n;  
    private int _fibOfN;  
    private ManualResetEvent _doneEvent;  
  
    public int N { get { return _n; } }  
    public int FibOfN { get { return _fibOfN; } }  
  
    // Constructor.  
    public Fibonacci(int n, ManualResetEvent doneEvent)  
    {  
        _n = n;  
        _doneEvent = doneEvent;  
    }  
  
    // Wrapper method for use with thread pool.  
    public void ThreadPoolCallback(Object threadContext)  
    {  
        int threadIndex = (int)threadContext;  
        Console.WriteLine("thread {0} started...", threadIndex);  
        _fibOfN = Calculate(_n);  
        Console.WriteLine("thread {0} result calculated...", threadIndex);  
        _doneEvent.Set();  
    }  
  
    // Recursive method that calculates the Nth Fibonacci number.  
    public int Calculate(int n)  
    {  
        if (n <= 1)  
        {  
            return n;  
        }  
  
        return Calculate(n - 1) + Calculate(n - 2);  
    }  
}  
  
public class ThreadPoolExample  
{  
    static void Main()  
    {  
        const int FibonacciCalculations = 10;  
  
        // One event is used for each Fibonacci object.  
        ManualResetEvent[] doneEvents = new ManualResetEvent[FibonacciCalculations];  
        Fibonacci[] fibArray = new Fibonacci[FibonacciCalculations];  
        Random r = new Random();  
  
        // Configure and start threads using ThreadPool.  
        Console.WriteLine("launching {0} tasks...", FibonacciCalculations);  
        for (int i = 0; i < FibonacciCalculations; i++)  
        {  
            doneEvents[i] = new ManualResetEvent(false);  
            Fibonacci f = new Fibonacci(r.Next(20, 40), doneEvents[i]);  
            fibArray[i] = f;  
            ThreadPool.QueueUserWorkItem(f.ThreadPoolCallback, i);  
        }  
  
        // Wait for all threads in pool to calculate.  
        WaitHandle.WaitAll(doneEvents);  
        Console.WriteLine("All calculations are complete.");  
  
        // Display the results.  
        for (int i= 0; i<FibonacciCalculations; i++)  
        {  
            Fibonacci f = fibArray[i];  
            Console.WriteLine("Fibonacci({0}) = {1}", f.N, f.FibOfN);  
        }  
    }  
}  
```  
  
 Im Folgenden finden Sie ein Beispiel für die Ausgabe.  
  
```  
launching 10 tasks...  
thread 0 started...  
thread 1 started...  
thread 1 result calculated...  
thread 2 started...  
thread 2 result calculated...  
thread 3 started...  
thread 3 result calculated...  
thread 4 started...  
thread 0 result calculated...  
thread 5 started...  
thread 5 result calculated...  
thread 6 started...  
thread 4 result calculated...  
thread 7 started...  
thread 6 result calculated...  
thread 8 started...  
thread 8 result calculated...  
thread 9 started...  
thread 9 result calculated...  
thread 7 result calculated...  
All calculations are complete.  
Fibonacci(38) = 39088169  
Fibonacci(29) = 514229  
Fibonacci(25) = 75025  
Fibonacci(22) = 17711  
Fibonacci(38) = 39088169  
Fibonacci(29) = 514229  
Fibonacci(29) = 514229  
Fibonacci(38) = 39088169  
Fibonacci(21) = 10946  
Fibonacci(27) = 196418  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.WaitHandle.WaitAll%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.EventWaitHandle.Set%2A>  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [Thread Pooling (C#) (Pooling von Threads (C#))](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  
 [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [Sicherheit](../../../../standard/security/index.md)
