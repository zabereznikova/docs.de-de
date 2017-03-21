---
title: Threadpooling (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6037d7ea17e260d44bae571aa25d413996f5a123
ms.lasthandoff: 03/13/2017

---
# <a name="thread-pooling-visual-basic"></a>Threadpooling (Visual Basic)
Ein *Threadpool* ist eine Auflistung von Threads, die verwendet werden kann, um verschiedene Aufgaben im Hintergrund ausgeführt. (Siehe [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) Hintergrundinformationen.) Dies bewirkt, dass der primären Thread asynchron andere Aufgaben ausführen.  
  
 Threadpools sind häufig in serveranwendungen verwendet. Jede eingehende Anforderung wird einem Thread aus dem Threadpool zugewiesen, sodass die Anforderung asynchron verarbeitet werden kann, ohne den primären Thread binden oder die Verarbeitung von nachfolgenden Anforderungen zu verzögern.  
  
 Wenn ein Thread im Pool seine Aufgabe abgeschlossen ist, wird es zurückgegeben an eine Warteschlange der wartenden Threads, in dem es wiederverwendet werden. Diese wiederverwenden können Clientanwendungen, die Kosten für das Erstellen eines neuen Threads für jeden Vorgang zu vermeiden.  
  
 Threadpools haben in der Regel eine maximale Anzahl von Threads. Wenn alle Threads aktiv sind, werden zusätzliche Aufgaben in Warteschlange eingereiht, bis sie von wieder verfügbaren Threads verarbeitet werden können.  
  
 Sie können einen eigenen Threadpool implementieren, aber es ist einfacher, die von .NET Framework durch die <xref:System.Threading.ThreadPool>Klasse</xref:System.Threading.ThreadPool> bereitgestellten Threadpool zu verwenden  
  
 Beim pooling von Threads rufen Sie die <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>-Methode mit einem Delegaten für die Prozedur, die Sie ausführen möchten, und Visual Basic wird der Thread erstellt und führt die Prozedur.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>  
  
## <a name="thread-pooling-example"></a>Beispiel für Pooling von Threads  
 Das folgende Beispiel zeigt, wie Sie mehrere Aufgaben gestartet pooling von Threads verwenden können.  
  
```vb  
Public Sub DoWork()  
    ' Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf SomeLongTask))  
    ' Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf AnotherLongTask))  
End Sub  
Private Sub SomeLongTask(ByVal state As Object)  
    ' Insert code to perform a long task.  
End Sub  
Private Sub AnotherLongTask(ByVal state As Object)  
    ' Insert code to perform another long task.  
End Sub  
```  
  
 Ein Vorteil der pooling von Threads ist, dass Argumente ein Zustandsobjekt an den Task-Prozedur übergeben werden kann. Wenn die aufgerufene Prozedur mehr als ein Argument erfordert, können Sie eine Struktur oder eine Instanz einer Klasse in Umwandeln einer `Object` -Datentyp.  
  
## <a name="thread-pool-parameters-and-return-values"></a>Thread-Pool-Parameter und Rückgabewerte  
 Rückgabe von Werten aus einem Threadpool-Thread ist nicht einfach. Das Standardverfahren für die Rückgabe von Werten aus einem Funktionsaufruf ist nicht zulässig, da `Sub` Verfahren sind die einzige Art von Prozedur, die einen Threadpool in die Warteschlange gestellt werden kann. Eine Möglichkeit, Sie können Parameter angeben und Werte wird durch die Parameter, Rückgabewerte und Methoden in einem Wrapper gemäß [Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).  
  
 Ein einfacheres Verfahren geben Sie Parameter und Rückgabewerte wird mithilfe des optionalen `ByVal` Objektvariable des Status der <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>-Methode.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> Wenn Sie diese Variable verwenden, um einen Verweis auf eine Instanz einer Klasse zu übergeben, können die Member der Instanz durch den Threadpool-Thread geändert und als Rückgabewerte verwendet werden.  
  
 Zunächst kann es nicht offensichtlich, ändern Sie ein Objekt verweist auf eine Variable, die als Wert übergeben wird. Dies ist möglich, da nur der Objektverweis als Wert übergeben wird. Wenn Sie Member des Objekts gemäß den Objektverweis ändern, werden die Änderungen auf die tatsächliche Instanz anwenden.  
  
 Strukturen können zum Zurückgeben von Werten in Statusobjekten verwendet werden. Da Strukturen Werttypen sind, ändern Änderungen, die der asynchrone Prozess vornimmt nicht die Elemente der Originalstruktur. Verwenden Sie Strukturen, um Parameter bereitzustellen, wenn keine Rückgabewerte benötigt werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>   
 <xref:System.Threading></xref:System.Threading>   
 <xref:System.Threading.ThreadPool></xref:System.Threading.ThreadPool>   
 [Gewusst wie: Verwenden eines Threadpools (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)   
 [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)   
 [Multithreadanwendungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)   
 [Threadsynchronisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)
