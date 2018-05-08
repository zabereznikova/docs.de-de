---
title: 'Vorgehensweise: Verwenden eines Threadpools (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 90a0bb24-39f8-41f5-a217-b52a7d4fed0b
ms.openlocfilehash: a61defc2e40662d7fdadb40693e757fa559adb6a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-thread-pool-visual-basic"></a>Vorgehensweise: Verwenden eines Threadpools (Visual Basic)
*Threadpooling* ist eine Form des Multithreadings, bei dem Aufgaben einer Warteschlange hinzugefügt werden und automatisch gestartet werden, wenn Threads erstellt werden. Weitere Informationen finden Sie unter [Pooling von Threads (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md).  
  
 In folgendem Beispiel wird der Threadpool des .NET Frameworks verwendet, um das `Fibonacci`-Ergebnis für zehn Zahlen zwischen 20 und 40 zu berechnen. Jedes `Fibonacci`-Ergebnis wird von der `Fibonacci`-Klasse repräsentiert, die eine Methode mit dem Namen `ThreadPoolCallback` bietet, die die Berechnung durchführt. Ein Objekt, das jeden `Fibonacci`-Wert repräsentiert, wird erstellt, und die `ThreadPoolCallback`-Methode wird an <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> übergeben, das dem Pool einen verfügbaren Thread zuweist, um die Methode auszuführen.  
  
 Weil jedem `Fibonacci`-Objekt ein halb-zufälliger Wert zum Berechnen zugewiesen wird, und weil alle Threads um Prozessorzeit konkurrieren, könne Sie nicht im Voraus abschätzen, wie viel Zeit die Berechnung aller zehn Ergebnisse in Anspruch nehmen wird. Deshalb wird jedem `Fibonacci`-Objekt eine Instanz der <xref:System.Threading.ManualResetEvent>-Klasse während der Konstruktion übergeben. Jedes Objekt gibt dem angegebenen Ereignisobjekt Bescheid, wenn seine Berechnung abgeschlossen ist; dies ermöglicht es dem Thread, die Ausführung mit <xref:System.Threading.WaitHandle.WaitAll%2A> zu blockieren, bis alle zehn `Fibonacci`-Objekte ein Ergebnis berechnet haben. Die `Main`-Methode zeigt dann jedes `Fibonacci`-Ergebnis an.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Imports System.Threading  
  
Module Module1  
  
    Public Class Fibonacci  
        Private _n As Integer  
        Private _fibOfN  
        Private _doneEvent As ManualResetEvent  
  
        Public ReadOnly Property N() As Integer  
            Get  
                Return _n  
            End Get  
        End Property  
  
        Public ReadOnly Property FibOfN() As Integer  
            Get  
                Return _fibOfN  
            End Get  
        End Property  
  
        Sub New(ByVal n As Integer, ByVal doneEvent As ManualResetEvent)  
            _n = n  
            _doneEvent = doneEvent  
        End Sub  
  
        ' Wrapper method for use with the thread pool.  
        Public Sub ThreadPoolCallBack(ByVal threadContext As Object)  
            Dim threadIndex As Integer = CType(threadContext, Integer)  
            Console.WriteLine("thread {0} started...", threadIndex)  
            _fibOfN = Calculate(_n)  
            Console.WriteLine("thread {0} result calculated...", threadIndex)  
            _doneEvent.Set()  
        End Sub  
  
        Public Function Calculate(ByVal n As Integer) As Integer  
            If n <= 1 Then  
                Return n  
            End If  
            Return Calculate(n - 1) + Calculate(n - 2)  
        End Function  
  
    End Class  
  
    <MTAThread()>   
    Sub Main()  
        Const FibonacciCalculations As Integer = 9 ' 0 to 9  
  
        ' One event is used for each Fibonacci object  
        Dim doneEvents(FibonacciCalculations) As ManualResetEvent  
        Dim fibArray(FibonacciCalculations) As Fibonacci  
        Dim r As New Random()  
  
        ' Configure and start threads using ThreadPool.  
        Console.WriteLine("launching {0} tasks...", FibonacciCalculations)  
  
        For i As Integer = 0 To FibonacciCalculations  
            doneEvents(i) = New ManualResetEvent(False)  
            Dim f = New Fibonacci(r.Next(20, 40), doneEvents(i))  
            fibArray(i) = f  
            ThreadPool.QueueUserWorkItem(AddressOf f.ThreadPoolCallBack, i)  
        Next  
  
        ' Wait for all threads in pool to calculate.  
        WaitHandle.WaitAll(doneEvents)  
        Console.WriteLine("All calculations are complete.")  
  
        ' Display the results.  
        For i As Integer = 0 To FibonacciCalculations  
            Dim f As Fibonacci = fibArray(i)  
            Console.WriteLine("Fibonacci({0}) = {1}", f.N, f.FibOfN)  
        Next  
    End Sub  
  
End Module  
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
 [Threadpooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [Sicherheit](../../../../standard/security/index.md)
