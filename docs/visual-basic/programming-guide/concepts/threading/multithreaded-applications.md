---
title: "Multithreadanwendungen verwendet werden können (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02b0444b-2e68-4f2c-bc28-28c046004017
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 19a4fe40e27a9edf8515e2734914aaf02d5e48b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="multithreaded-applications-visual-basic"></a>Multithreadanwendungen verwendet werden können (Visual Basic)
In Visual Basic können Sie Anwendungen schreiben, die mehrere Aufgaben gleichzeitig ausführen. Aufgaben, die möglicherweise andere Aufgaben aufhalten, können in separaten Threads ausgeführt werden. Dieser Prozess ist als *Multithreading* oder *Freies Threading* bekannt.  
  
 Clientanwendungen, die Multithreading verwenden, reagieren besser auf Benutzereingaben, weil die Benutzeroberfläche aktiv bleibt, da prozessorintensive Aufgaben in separaten Threads ausgeführt werden. Multithreading ist auch nützlich, wenn Sie skalierbare Aufgaben erstellen, da Sie Threads bei steigender Arbeitsauslastung hinzufügen können.  
  
## <a name="creating-and-using-threads"></a>Erstellen und Verwenden von Threads  
 Wenn Sie mehr Kontrolle über das Verhalten von Threads der Anwendung benötigen, können Sie die Threads selbst verwalten. Beachten Sie jedoch, dass das Schreiben fehlerfreier Multithreadanwendungen schwierig sein kann: Ihre Anwendung reagiert vielleicht nicht mehr oder stößt auf vorübergehende Fehler, die durch Racebedingungen verursacht werden. Weitere Informationen finden Sie unter [Threadsichere Komponenten](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).  
  
 Sie erstellen einen neuen Thread, indem Sie eine Variable des Typs <xref:System.Threading.Thread> deklarieren und den Konstruktor aufrufen, der den Namen der Prozedur oder Methode bereitstellt, die Sie in einem neuen Thread ausführen möchten. Der folgende Code veranschaulicht dies.  
  
```vb  
Dim newThread As New System.Threading.Thread(AddressOf AMethod)  
```  
  
### <a name="starting-and-stopping-threads"></a>Starten und Beenden von Threads  
 Verwenden Sie zum Starten eines neuen Threads die Methode <xref:System.Threading.Thread.Start%2A>, wie im folgenden Code gezeigt wird.  
  
```vb  
newThread.Start()  
```  
  
 Verwenden Sie zum Beenden eines Threads die Methode <xref:System.Threading.Thread.Abort%2A>, wie im folgenden Code gezeigt wird.  
  
```vb  
newThread.Abort()  
```  
  
 Neben dem Starten und Beenden von Threads können Sie Threads auch mit den Methoden <xref:System.Threading.Thread.Sleep%2A> oder <xref:System.Threading.Thread.Suspend%2A> anhalten, einen angehaltenen Thread mit der <xref:System.Threading.Thread.Resume%2A>-Methode fortsetzen und einen Thread mithilfe der <xref:System.Threading.Thread.Abort%2A>-Methode zerstören.  
  
### <a name="thread-methods"></a>Thread-Methoden  
 Die folgende Tabelle zeigt einige der Methoden, mit denen Sie einzelne Threads steuern.  
  
|Methode|Aktion|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A>|Bewirkt, dass ein Thread gestartet wird|  
|<xref:System.Threading.Thread.Sleep%2A>|Hält einen Thread für eine angegebene Zeit an|  
|<xref:System.Threading.Thread.Suspend%2A>|Hält einen Thread an, wenn er einen sicheren Punkt erreicht|  
|<xref:System.Threading.Thread.Abort%2A>|Beendet einen Thread, wenn er einen sicheren Punkt erreicht|  
|<xref:System.Threading.Thread.Resume%2A>|Startet einen angehaltenen Thread neu|  
|<xref:System.Threading.Thread.Join%2A>|Bewirkt, dass der aktuelle Thread auf das Ende eines anderen Threads wartet. Wird der Thread mit einem Timeoutwert verwendet, gibt diese Methode `True` zurück, wenn er in der zugewiesenen Zeit fertig wird.|  
  
### <a name="safe-points"></a>Sicherungspunkte  
 Die meisten dieser Methoden sind selbsterklärend, doch der Begriff *Sicherungspunkte* ist vielleicht neu für Sie. Sicherungspunkte sind Stellen im Code, an denen die Common Language Runtime die automatische *Speicherbereinigung* – den Prozess zur Freigabe von Speicher und nicht verwendeten Variablen – sicher ausführen kann. Wenn Sie die Methode <xref:System.Threading.Thread.Abort%2A> oder <xref:System.Threading.Thread.Suspend%2A> eines Threads aufrufen, analysiert die Common Language Runtime den Code und ermittelt den Ort einer geeigneten Stelle, an der der Thread nicht mehr ausgeführt wird.  
  
### <a name="thread-properties"></a>Threadeigenschaften  
 Threads enthalten außerdem einige nützliche Eigenschaften, wie in der folgenden Tabelle dargestellt wird:  
  
|Eigenschaft|Wert|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|Enthält den Wert `True`, wenn ein Thread aktiv ist.|  
|<xref:System.Threading.Thread.IsBackground%2A>|Es wird ein boolescher Wert abgerufen oder festgelegt, der angibt, ob ein Thread ein Hintergrundthread ist oder sein sollte. Hintergrundthreads sind wie Vordergrundthreads, aber ein Hintergrundthread verhindert nicht, dass ein Prozess beendet wird. Sobald alle zu einem Prozess gehörenden Vordergrundthreads beendet wurden, beendet die Common Language Runtime den Prozess, indem die Methode <xref:System.Threading.Thread.Abort%2A> in Hintergrundthreads aufgerufen wird, die noch aktiv sind.|  
|<xref:System.Threading.Thread.Name%2A>|Ruft den Namen eines Threads ab oder legt diesen fest. Wird am häufigsten beim Debuggen verwendet, um einzelne Threads zu erkennen.|  
|<xref:System.Threading.Thread.Priority%2A>|Es wird ein Wert abgerufen oder festgelegt, der vom Betriebssystem zum Priorisieren der Threadplanung verwendet wird.|  
|<xref:System.Threading.Thread.ThreadState%2A>|Enthält einen Wert, der Zustand oder Zustände eines Threads beschreibt.|  
  
## <a name="thread-priorities"></a>Threadprioritäten  
 Jeder Thread hat eine Prioritätseigenschaft, die bestimmt, wie groß oder klein ein Segment der Prozessorzeit ist, das er ausführen muss. Das Betriebssystem ordnet Threads mit hoher Priorität größere Zeiträume und Threads mit niedriger Priorität kürzere Zeiträume zu. Neue Threads werden mit dem Wert `Normal` erstellt, aber Sie können die Eigenschaft <xref:System.Threading.Thread.Priority%2A> auf jeden beliebigen Wert in der <xref:System.Threading.ThreadPriority>-Enumeration ändern.  
  
 Unter <xref:System.Threading.ThreadPriority> finden Sie eine ausführliche Beschreibung der verschiedenen Threadprioritäten.  
  
## <a name="foreground-and-background-threads"></a>Vordergrund- und Hintergrundthreads  
 Ein *Vordergrundthread* wird dauerhaft ausgeführt, während ein *Hintergrundthread* beendet wird, sobald der letzte Vordergrundthread beendet wurde. Sie können die Eigenschaft <xref:System.Threading.Thread.IsBackground%2A> verwenden, um den Hintergrundzustand eines Threads zu bestimmen oder zu ändern.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Thread>  
 [Threadsynchronisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)  
 [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)
