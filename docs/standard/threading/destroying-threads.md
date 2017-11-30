---
title: "Zerstören von Threads"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a41dce5db707d0be49c283256de665d316e1a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="destroying-threads"></a>Zerstören von Threads
Die <xref:System.Threading.Thread.Abort%2A> Methode wird verwendet, um einen verwalteten Thread dauerhaft zu beenden. Beim Aufruf <xref:System.Threading.Thread.Abort%2A>, löst die common Language Runtime eine <xref:System.Threading.ThreadAbortException> in der Zielthread, die der Zielthread abfangen kann. Weitere Informationen finden Sie unter <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Lange nicht verwaltet, wenn ein Thread ausgeführt wird, wenn code seine <xref:System.Threading.Thread.Abort%2A> -Methode aufgerufen wird, wird es von der Laufzeitmoduls <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>. Die Ausnahme wird ausgelöst, wenn der Thread zu verwaltetem Code zurückgegeben.  
  
 Sobald ein Thread abgebrochen wird, kann er nicht erneut gestartet werden.  
  
 Die <xref:System.Threading.Thread.Abort%2A> Methode bewirkt nicht sofort, Abbruch des Threads, da der Zielthread abfangen kann die <xref:System.Threading.ThreadAbortException> und Ausführen von beliebigen Mengen von Code in einem `finally` Block. Sie können Aufrufen <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> Wenn müssen Sie warten, bis der Thread beendet wurde. <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>Stellt einen blockierender Aufruf, der nicht zurückgegeben wird, bis die Ausführung der Threads tatsächlich beendet wurde oder ein optionales Timeout-Intervall verstrichen. Der abgebrochene Thread Aufrufen der <xref:System.Threading.Thread.ResetAbort%2A> Methode oder unbegrenzte verarbeiten in einem `finally` blockieren, wenn Sie einen Timeout nicht angeben, die Wartezeit nicht zum Beenden unbedingt.  
  
 Threads, die bei einem Aufruf von Warten der <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> Methode kann unterbrochen werden, von anderen Threads, die aufgerufen werden <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.  
  
## <a name="handling-threadabortexception"></a>Behandeln von ThreadAbortException  
 Wenn Sie davon ausgehen, dass den Thread entweder als Folge eines Aufrufs abgebrochen werden <xref:System.Threading.Thread.Abort%2A> aus Ihrem eigenen Code oder als Ergebnis Entladen einer Anwendungsdomäne, in der der Thread ausgeführt wird (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> verwendet <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> um Threads zu beenden), muss Ihr Thread verarbeiten die <xref:System.Threading.ThreadAbortException> und führen Sie die endgültige Verarbeitung in einer `finally` -Klausel, wie im folgenden Code gezeigt.  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.   
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception   
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try   
{  
    // Code that is executing when the thread is aborted.  
}   
catch (ThreadAbortException ex)   
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.   
}  
// Do not put clean-up code here, because the exception   
// is rethrown at the end of the Finally clause.  
```  
  
 Bereinigung Code muss der `catch` Klausel oder die `finally` -Klausel, da eine <xref:System.Threading.ThreadAbortException> wird erneut ausgelöst, durch das System am Ende der `finally` -Klausel, oder am Ende der `catch` -Klausel, wenn es ist keine `finally` Klausel.  
  
 Sie können verhindern, dass das System das erneute Auslösen der Ausnahme durch Aufrufen der <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> Methode. Allerdings gehen Sie so vor diesen nur, wenn Code verursacht die <xref:System.Threading.ThreadAbortException>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [Verwenden von Threads und Threading](../../../docs/standard/threading/using-threads-and-threading.md)
