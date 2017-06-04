---
title: "Destroying Threads | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "destroying threads"
  - "threading [.NET Framework], destroying threads"
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Destroying Threads
Mithilfe der <xref:System.Threading.Thread.Abort%2A>\-Methode wird ein verwalteter Thread dauerhaft angehalten.  Beim Aufruf von <xref:System.Threading.Thread.Abort%2A> löst die Common Language Runtime im Zielthread eine <xref:System.Threading.ThreadAbortException> aus, die der Zielthread abfangen kann.  Weitere Informationen finden Sie unter <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>.  
  
> [!NOTE]
>  Wenn ein Thread beim Aufruf seiner <xref:System.Threading.Thread.Abort%2A>\-Methode nicht verwalteten Code ausführt, wird er von der Laufzeit als <xref:System.Threading.ThreadState?displayProperty=fullName> markiert.  Die Ausnahme wird ausgelöst, wenn der Thread zum verwalteten Code zurückkehrt.  
  
 Sobald ein Thread abgebrochen wurde, kann er nicht mehr gestartet werden.  
  
 Die <xref:System.Threading.Thread.Abort%2A>\-Methode verursacht nicht den sofortigen Abbruch des Threads, da der Zielthread die <xref:System.Threading.ThreadAbortException> abfangen kann und Code beliebiger Länge in einem `finally`\-Block ausführen kann.  Wenn Sie die Beendigung des Threads abwarten müssen, können Sie <xref:System.Threading.Thread.Join%2A?displayProperty=fullName> aufrufen.  <xref:System.Threading.Thread.Join%2A?displayProperty=fullName> ist ein blockierender Aufruf, der erst beendet wird, nachdem die Ausführung des Threads tatsächlich beendet wurde oder ein optionales Timeoutintervall abgelaufen ist.  Der abgebrochene Thread könnte die <xref:System.Threading.Thread.ResetAbort%2A>\-Methode aufrufen oder ungebundene Verarbeitung in einem `finally`\-Block ausführen. Wenn Sie kein Timeout angeben, ist das Ende des Wartevorgangs nicht garantiert.  
  
 Threads, die auf einen Aufruf der <xref:System.Threading.Thread.Join%2A?displayProperty=fullName>\-Methode warten, können durch andere Threads unterbrochen werden, die <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> aufrufen.  
  
## Behandeln von ThreadAbortException  
 Wenn Sie den Abbruch eines Threads erwarten, weil entweder <xref:System.Threading.Thread.Abort%2A> aus Ihrem eigenen Code aufgerufen wurde oder eine Anwendungsdomäne entladen wurde, in der der Thread ausgeführt wird \(<xref:System.AppDomain.Unload%2A?displayProperty=fullName> beendet Threads mit <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>\), muss der Thread die <xref:System.Threading.ThreadAbortException> behandeln und die endgültige Verarbeitung in einer `finally`\-Klausel ausführen, wie im folgenden Code dargestellt.  
  
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
  
 Der Bereinigungscode muss sich in der `catch`\-Klausel oder der `finally`\-Klausel befinden, da das System am Ende der `finally`\-Klausel oder am Ende der `catch`\-Klausel, wenn keine `finally`\-Klausel vorhanden ist, erneut eine <xref:System.Threading.ThreadAbortException> auslöst.  
  
 Sie können das erneute Auslösen der Ausnahme durch Aufrufen der <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=fullName>\-Methode verhindern.  Dies ist jedoch nur sinnvoll, wenn die <xref:System.Threading.ThreadAbortException> von Ihrem eigenen Code verursacht wurde.  
  
## Siehe auch  
 <xref:System.Threading.ThreadAbortException>   
 <xref:System.Threading.Thread>   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)