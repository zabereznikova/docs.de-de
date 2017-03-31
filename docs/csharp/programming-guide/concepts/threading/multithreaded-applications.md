---
title: Multithreadanwendungen (C#) | Microsoft-Dokumentation
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
ms.assetid: b7015cfb-d506-4eac-b2f8-b2caaa9cc977
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
ms.openlocfilehash: a36fd71ff41eb219f4c4de36d4fa8da9b8ee179a
ms.lasthandoff: 03/13/2017

---
# <a name="multithreaded-applications-c"></a>Multithreadanwendungen (C#)
Sie können mit C# Anwendungen schreiben, die mehrere Aufgaben zur gleichen Zeit ausführen. Aufgaben, die möglicherweise andere Aufgaben aufhalten, können in separaten Threads ausgeführt werden. Dieser Prozess ist als *Multithreading* oder *Freies Threading* bekannt.  
  
 Clientanwendungen, die Multithreading verwenden, reagieren besser auf Benutzereingaben, weil die Benutzeroberfläche aktiv bleibt, da prozessorintensive Aufgaben in separaten Threads ausgeführt werden. Multithreading ist auch nützlich, wenn Sie skalierbare Aufgaben erstellen, da Sie Threads bei steigender Arbeitsauslastung hinzufügen können.  
  
## <a name="creating-and-using-threads"></a>Erstellen und Verwenden von Threads  
 Wenn Sie mehr Kontrolle über das Verhalten von Threads der Anwendung benötigen, können Sie die Threads selbst verwalten. Beachten Sie jedoch, dass das Schreiben fehlerfreier Multithreadanwendungen schwierig sein kann: Ihre Anwendung reagiert vielleicht nicht mehr oder stößt auf vorübergehende Fehler, die durch Racebedingungen verursacht werden. Weitere Informationen finden Sie unter [Threadsichere Komponenten](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).  
  
 Sie erstellen einen neuen Thread, indem Sie eine Variable des Typs <xref:System.Threading.Thread> deklarieren und den Konstruktor aufrufen, der den Namen der Prozedur oder Methode bereitstellt, die Sie in einem neuen Thread ausführen möchten. Der folgende Code veranschaulicht dies.  
  
```csharp  
System.Threading.Thread newThread =  
    new System.Threading.Thread(AMethod);  
```  
  
### <a name="starting-and-stopping-threads"></a>Starten und Beenden von Threads  
 Verwenden Sie zum Starten eines neuen Threads die Methode <xref:System.Threading.Thread.Start%2A>, wie im folgenden Code gezeigt wird.  
  
```csharp  
newThread.Start();  
```  
  
 Verwenden Sie zum Beenden eines Threads die Methode <xref:System.Threading.Thread.Abort%2A>, wie im folgenden Code gezeigt wird.  
  
```csharp  
newThread.Abort();  
```  
  
 Neben dem Starten und Beenden von Threads können Sie Threads auch mithilfe der Methoden <xref:System.Threading.Thread.Sleep%2A> oder <xref:System.Threading.Thread.Suspend%2A> anhalten. Sie setzen einen angehaltenen Thread mithilfe der Methode <xref:System.Threading.Thread.Resume%2A> fort, und löschen einen Thread mithilfe der Methode <xref:System.Threading.Thread.Abort%2A>.  
  
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
 Jeder Thread hat eine Prioritätseigenschaft, die bestimmt, wie groß oder klein ein Segment der Prozessorzeit ist, das er ausführen muss. Das Betriebssystem ordnet Threads mit hoher Priorität größere Zeiträume und Threads mit niedriger Priorität kürzere Zeiträume zu. Neue Threads werden mit dem Wert `Normal` erstellt, aber Sie können die Eigenschaft <xref:System.Threading.Thread.Priority%2A> auf einen beliebigen Wert in der <xref:System.Threading.ThreadPriority>-Enumeration ändern.  
  
 Eine genauere Beschreibung der verschiedenen Threadprioritäten finden Sie unter <xref:System.Threading.ThreadPriority>.  
  
## <a name="foreground-and-background-threads"></a>Vordergrund- und Hintergrundthreads  
 Ein *Vordergrundthread* wird dauerhaft ausgeführt, während ein *Hintergrundthread* beendet wird, sobald der letzte Vordergrundthread beendet wurde. Sie können die Eigenschaft <xref:System.Threading.Thread.IsBackground%2A> verwenden, um den Hintergrundzustand eines Threads zu bestimmen oder zu ändern.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Thread>   
 [Thread Synchronization (C#) (Threadsynchronisierung (C#))](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)   
 [Parameter und Rückgabewerte für Multithreadprozeduren (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)   
 [Treading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)
