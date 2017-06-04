---
title: "dangerousThreadingAPI MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "suspending threads"
  - "DangerousThreadingAPI MDA"
  - "managed debugging assistants (MDAs), dangerous threading operations"
  - "threading [.NET Framework], suspending"
  - "MDAs (managed debugging assistants), dangerous threading operations"
  - "Suspend method"
  - "threading [.NET Framework], managed debugging assistants"
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# dangerousThreadingAPI MDA
Der `dangerousThreadingAPI`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn für einen anderen als den aktuellen Thread die <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>\-Methode aufgerufen wird.  
  
## Symptome  
 Eine Anwendung reagiert nicht mehr.  System\- oder Anwendungsdaten befinden sich vorübergehend oder selbst nach dem Beenden der Anwendung in einem nicht vorhersagbaren Zustand.  Einige Vorgänge werden nicht wie erwartet abgeschlossen.  
  
 Aufgrund des willkürlichen Auftretens dieses Problems ist ein breites Spektrum unterschiedlicher Symptome möglich.  
  
## Ursache  
 Ein Thread wird asynchron von einem anderen Thread mit der <xref:System.Threading.Thread.Suspend%2A>\-Methode unterbrochen.  Es gibt keine Möglichkeit festzustellen, wann ein anderer Thread gefahrlos unterbrochen werden kann, der möglicherweise gerade einen Vorgang ausführt.  Das Unterbrechen des Threads kann zur Beschädigung von Daten oder Invarianten führen.  Wenn ein Thread in einen Unterbrechungszustand versetzt und niemals mit der <xref:System.Threading.Thread.Resume%2A>\-Methode fortgesetzt wird, reagiert die Anwendung nicht mehr, und es kommt möglicherweise zur Beschädigung von Anwendungsdaten.  Diese Methoden wurden als veraltet gekennzeichnet.  
  
 Wenn Synchronisierungsgrundelemente vom Zielthread angehalten wurden, bleiben sie während der Unterbrechung in diesem Zustand.  Dies kann zu Deadlocks führen, wenn ein anderer Thread \(z. B. der Thread für das <xref:System.Threading.Thread.Suspend%2A>\) versucht, das Grundelement zu sperren.  In dieser Situation macht sich das Problem als Deadlock bemerkbar.  
  
## Lösung  
 Vermeiden Sie Entwürfe, die die Verwendung von <xref:System.Threading.Thread.Suspend%2A> und <xref:System.Threading.Thread.Resume%2A> erfordern.  Verwenden Sie für die Interaktion zwischen Threads Synchronisierungsgrundelemente wie <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> oder die C\#\-Anweisung `lock`.  Wenn Sie diese Methoden unbedingt einsetzen müssen, verringern Sie das Zeitfenster und die Menge des Codes, der während der Unterbrechung des Threads ausgeführt wird.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  Es werden nur Angaben zu risikobehafteten Threadingvorgängen gemeldet.  
  
## Ausgabe  
 Der MDA meldet die risikobehaftete Threadingmethode, die zur Aktivierung des Assistenten führte.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## Beispiel  
 Im folgenden Codebeispiel wird ein Aufruf der <xref:System.Threading.Thread.Suspend%2A>\-Methode veranschaulicht, der zur Aktivierung des `dangerousThreadingAPI`\-MDA führt.  
  
```  
using System.Threading;  
void FireMda()  
{  
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## Siehe auch  
 <xref:System.Threading.Thread>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [lock\-Anweisung](../Topic/lock%20Statement%20\(C%23%20Reference\).md)