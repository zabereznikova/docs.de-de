---
title: Multithreadanwendungen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 02b0444b-2e68-4f2c-bc28-28c046004017
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5bde7f49a2f2bc8a2e6c1eeab3722428b8a37a95
ms.lasthandoff: 03/13/2017

---
# <a name="multithreaded-applications-visual-basic"></a>Multithreadanwendungen (Visual Basic)
In Visual Basic können Sie Anwendungen schreiben, die mehrere Aufgaben gleichzeitig ausführen. Tasks, die möglicherweise andere Tasks aufhalten, können in separaten Threads ausgeführt *multithreading* oder *freies threading*.  
  
 Clientanwendungen, die Verwendung von multithreading mehr auf Benutzereingaben reagieren, da die Benutzeroberfläche aktiv bleibt, wie prozessorintensive Tasks in separaten Threads ausgeführt werden. Multithreading ist auch nützlich, beim Erstellen von skalierbarer Anwendungen, da Sie Threads als Workloads hinzufügen können.  
  
## <a name="creating-and-using-threads"></a>Erstellen und Verwenden von Threads  
 Wenn Sie mehr Kontrolle über das Verhalten des Threads der Anwendung benötigen, können Sie die Threads selbst verwalten. Beachten Sie jedoch, dass das Schreiben fehlerfreier Multithreadanwendungen schwierig sein kann: Ihre Anwendung nicht mehr reagiert oder vorübergehenden Fehler zurückzuführen, dass Racebedingungen auftreten. Weitere Informationen finden Sie unter [Threadsichere Komponenten](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).  
  
 Sie erstellen einen neuen Thread durch Deklarieren einer Variablen vom Typ <xref:System.Threading.Thread>und Aufrufen des Konstruktors, der mit dem Namen der Prozedur oder der Methode, die für den neuen Thread ausgeführt werden soll.</xref:System.Threading.Thread> Der folgende Code veranschaulicht dies.  
  
```vb  
Dim newThread As New System.Threading.Thread(AddressOf AMethod)  
```  
  
### <a name="starting-and-stopping-threads"></a>Starten und Beenden von Threads  
 Um die Ausführung eines neuen Threads zu starten, verwenden Sie die <xref:System.Threading.Thread.Start%2A>Methode, wie im folgenden Code gezeigt.</xref:System.Threading.Thread.Start%2A>  
  
```vb  
newThread.Start()  
```  
  
 Um die Ausführung eines Threads zu beenden, verwenden Sie die <xref:System.Threading.Thread.Abort%2A>Methode, wie im folgenden Code gezeigt.</xref:System.Threading.Thread.Abort%2A>  
  
```vb  
newThread.Abort()  
```  
  
 Neben dem Starten und beenden, können Sie auch den Threads anhalten, durch Aufrufen der <xref:System.Threading.Thread.Sleep%2A>oder <xref:System.Threading.Thread.Suspend%2A>-Methode fortsetzen einen angehaltenen Thread mithilfe der <xref:System.Threading.Thread.Resume%2A>-Methode, und löschen Sie einen Thread mithilfe der <xref:System.Threading.Thread.Abort%2A>Methode</xref:System.Threading.Thread.Abort%2A> </xref:System.Threading.Thread.Resume%2A> </xref:System.Threading.Thread.Suspend%2A> </xref:System.Threading.Thread.Sleep%2A>  
  
### <a name="thread-methods"></a>Thread-Methoden  
 Die folgende Tabelle zeigt einige der Methoden, mit denen Sie einzelne Threads steuern.  
  
|Methode|Aktion|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A>|Bewirkt, dass einen Thread ausgeführt.|  
|<xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A>|Hält einen Thread für eine bestimmte Zeit.|  
|<xref:System.Threading.Thread.Suspend%2A></xref:System.Threading.Thread.Suspend%2A>|Hält einen Thread aus, wenn es sich um einen sicheren Punkt erreicht.|  
|<xref:System.Threading.Thread.Abort%2A></xref:System.Threading.Thread.Abort%2A>|Einen Thread wird beendet, wenn es sich um einen sicheren Punkt erreicht.|  
|<xref:System.Threading.Thread.Resume%2A></xref:System.Threading.Thread.Resume%2A>|Setzt einen angehaltenen thread|  
|<xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A>|Bewirkt, dass den aktuellen Thread eine Ende eines anderen Threads warten. Wenn Sie mit einem Timeoutwert verwendet wird, gibt diese Methode `True` , wenn der Thread in der zugewiesenen Zeit beendet wird.|  
  
### <a name="safe-points"></a>Sicherungspunkte  
 Die meisten dieser Methoden sind selbsterklärend, doch der Begriff *Sicherungspunkte* möglicherweise neu für Sie. Sichere Punkte werden im Code, in dem gefahrlos für die common Language Runtime zum automatischen Ausführen *speicherbereinigung*, den Prozess der Freigabe von nicht verwendeter Variablen und nicht verwendetem Speicherplatz. Beim Aufrufen der <xref:System.Threading.Thread.Abort%2A>oder <xref:System.Threading.Thread.Suspend%2A>eines Threads, die common Language Runtime wird der Code analysiert und ermittelt eine geeignete Stelle für den Thread nicht mehr ausgeführt.</xref:System.Threading.Thread.Suspend%2A> </xref:System.Threading.Thread.Abort%2A>  
  
### <a name="thread-properties"></a>Threadeigenschaften  
 Threads enthalten außerdem einige nützliche Eigenschaften, wie in der folgenden Tabelle dargestellt:  
  
|Eigenschaft|Wert|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A></xref:System.Threading.Thread.IsAlive%2A>|Enthält den Wert `True` , wenn ein Thread aktiv ist.|  
|<xref:System.Threading.Thread.IsBackground%2A></xref:System.Threading.Thread.IsBackground%2A>|Ruft ab oder legt einen booleschen Wert ab, der angibt, ob ein Thread ist oder ein Hintergrundthread sein sollte. Hintergrundthreads sind wie Vordergrundthreads, aber ein Hintergrundthread verhindert nicht, dass einen Prozess wird beendet. Sobald alle zu einem Prozess gehörenden Vordergrundthreads beendet wurden, beendet die common Language Runtime den Prozess durch Aufrufen der <xref:System.Threading.Thread.Abort%2A>-Methode für Hintergrundthreads, die noch aktiv sind.</xref:System.Threading.Thread.Abort%2A>|  
|<xref:System.Threading.Thread.Name%2A></xref:System.Threading.Thread.Name%2A>|Ruft ab oder legt den Namen eines Threads. Am häufigsten verwendet zum Erkennen von einzelnen Threads beim Debuggen.|  
|<xref:System.Threading.Thread.Priority%2A></xref:System.Threading.Thread.Priority%2A>|Ruft ab oder legt einen Wert fest, der Threadplanung Prioritäten für Threads vom Betriebssystem verwendet wird.|  
|<xref:System.Threading.Thread.ThreadState%2A></xref:System.Threading.Thread.ThreadState%2A>|Enthält einen Wert, der eines Threads Zustand oder Status beschreibt.|  
  
## <a name="thread-priorities"></a>Thread-Prioritäten  
 Jeder Thread hat eine Priority-Eigenschaft, die bestimmt, wie groß oder klein ein Segment der Prozessorzeit, die für die Ausführung. Das Betriebssystem ordnet Threads mit hoher Priorität größere Zeiträume und Threads mit niedriger Priorität kürzere Zeiträume. Neue Threads werden erstellt, mit dem Wert des `Normal`, kann jedoch geändert werden die <xref:System.Threading.Thread.Priority%2A>Eigenschaft auf einen beliebigen Wert in der <xref:System.Threading.ThreadPriority>-Enumeration.</xref:System.Threading.ThreadPriority> </xref:System.Threading.Thread.Priority%2A>  
  
 Finden Sie unter <xref:System.Threading.ThreadPriority>für eine ausführliche Beschreibung der verschiedenen Threadprioritäten.</xref:System.Threading.ThreadPriority>  
  
## <a name="foreground-and-background-threads"></a>Vordergrund- und Hintergrundthreads  
 Ein *Vordergrundthread* wird dauerhaft ausgeführt, während ein *Hintergrundthread* beendet, sobald der letzte Vordergrundthread beendet wurde. Sie können die <xref:System.Threading.Thread.IsBackground%2A>-Eigenschaft bestimmen oder ändern Sie den Hintergrundstatus eines Threads.</xref:System.Threading.Thread.IsBackground%2A>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Thread></xref:System.Threading.Thread>   
 [Threadsynchronisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)   
 [Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)   
 [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)
