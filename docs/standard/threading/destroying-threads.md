---
title: Zerstören von Threads
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
ms.openlocfilehash: 842ca4ff17f9cbab3a1518d2dea37436c9b23f9d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78155931"
---
# <a name="destroying-threads"></a>Zerstören von Threads

Um die Ausführung eines Threads zu beenden, verwenden Sie im Normalfall die [kooperative Abbruchmethode](cancellation-in-managed-threads.md). Manchmal ist es nicht möglich, einen Thread kooperativ anzuhalten, weil darin Drittanbietercode ausgeführt wird, der für einen kooperativen Abbruch nicht geeignet ist. Die <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-Methode in .NET Framework kann verwendet werden, um die Beendigung eines verwalteten Threads zu erzwingen. Beim Aufruf von <xref:System.Threading.Thread.Abort%2A> löst die Common Language Runtime eine <xref:System.Threading.ThreadAbortException> im Zielthread aus, die der Zielthread abfangen kann. Weitere Informationen finden Sie unter <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. Die Methode <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> wird in .NET Core nicht unterstützt. Wenn Sie die Beendigung der Ausführung von Drittanbietercode in .NET Core erzwingen müssen, führen Sie den Code in einem separaten Prozess aus und verwenden <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType>.

> [!NOTE]
> Wenn ein Thread nicht verwalteten Code ausführt, wenn seine <xref:System.Threading.Thread.Abort%2A>-Methode aufgerufen wird, markiert die Runtime ihn mit <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>. Die Ausnahme wird ausgelöst, wenn der Thread zu verwaltetem Code zurückkehrt.  
  
 Sobald ein Thread abgebrochen wird, kann er nicht erneut gestartet werden.  
  
 Die <xref:System.Threading.Thread.Abort%2A>-Methode bewirkt keinen sofortigen Abbruch des Threads, da der Zielthread die <xref:System.Threading.ThreadAbortException> abfangen und beliebige Mengen von Code in einem `finally`-Block ausführen kann. Sie können <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> aufrufen, wenn Sie warten müssen, bis der Thread beendet ist. <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> ist ein blockierender Aufruf, von dem keine Rückgabe erfolgt, bis die Ausführung des Threads tatsächlich beendet wurde oder ein optionales Timeoutintervall verstrichen ist. Der abgebrochene Thread könnte die <xref:System.Threading.Thread.ResetAbort%2A>-Methode aufrufen oder unbegrenzte Verarbeitung in einem `finally`-Block ausführen – wenn Sie also keinen Timeout angeben, ist nicht garantiert, dass das Warten endet.  
  
 Threads, die auf einen Aufruf der <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>-Methode warten, können von anderen Threads unterbrochen werden, die <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> aufrufen.  
  
## <a name="handling-threadabortexception"></a>Behandeln von ThreadAbortException  
 Wenn Sie davon ausgehen, dass Ihr Thread entweder als Folge eines Aufrufs von <xref:System.Threading.Thread.Abort%2A> aus Ihrem eigenen Code oder als Ergebnis des Entladens einer Anwendungsdomäne, in der der Thread ausgeführt wird (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> verwendet <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>, um Threads zu beenden), abgebrochen wird, muss Ihr Thread die <xref:System.Threading.ThreadAbortException> behandeln und jegliche endgültige Verarbeitung in einer `finally`-Klausel ausführen, wie im folgenden Code gezeigt.  
  
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
  
 Ihr Bereinigungscode muss sich in der `catch`- oder `finally`-Klausel befinden, da eine <xref:System.Threading.ThreadAbortException> erneut am Ende der `finally`-Klausel bzw. am Ende der `catch`-Klausel vom System ausgelöst wird, wenn es keine `finally`-Klausel gibt.  
  
 Sie können das erneute Auslösen der Ausnahme durch das System mit Aufrufen der <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType>-Methode verhindern. Allerdings sollten Sie dies nur tun, wenn Ihr eigener Code die <xref:System.Threading.ThreadAbortException> verursacht hat.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.ThreadAbortException>
- <xref:System.Threading.Thread>
- [Verwenden von Threads und Threading](../../../docs/standard/threading/using-threads-and-threading.md)
