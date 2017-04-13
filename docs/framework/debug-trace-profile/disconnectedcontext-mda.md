---
title: "disconnectedContext MDA | Microsoft Docs"
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
  - "DisconnectedContext MDA"
  - "MDAs (managed debugging assistants), disconnected context"
  - "dead context"
  - "transitioning disconnected apartment or context"
  - "context disconnections"
  - "managed debugging assistants (MDAs), disconnected context"
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# disconnectedContext MDA
Der `disconnectedContext`\-Assistent für verwaltetes Debuggen \(MDA\) wird aktiviert, wenn die CLR versucht, einen Übergang zu einem getrennten Apartment oder Kontext durchzuführen, während gerade eine Anforderung für ein COM\-Objekt verarbeitet wird.  
  
## Symptome  
 Aufrufe, die auf einem [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) \(RCW\) ausgeführt werden, werden an die zugrunde liegende COM\-Komponente im aktuellen Apartment oder Kontext zugestellt, statt an den, in dem sie vorhanden sind.  Dies kann zur Beschädigung oder zu Datenverlusten führen, wenn die COM\-Komponente keine Multithread\-Komponente ist, wie im Fall von Singlethread\-Apartment\-Komponenten \(Single Thread Apartment, STA\).  Alternativ kann der Aufruf, wenn der RCW selbst ein Proxy ist, dazu führen, dass eine <xref:System.Runtime.InteropServices.COMException> mit einem HRESULT von RPC\_E\_WRONG\_THREAD ausgelöst wird.  
  
## Ursache  
 Das OLE\-Apartment oder der OLE\-Kontext wurde heruntergefahren, als die CLR versucht hat, darin überzugehen.  Dies wird meist durch STA\-Apartments verursacht, die heruntergefahren werden, bevor alle COM\-Komponenten, die im Besitz des Apartments sind, vollständig freigegeben wurden. Dies kann als Ergebnis eines expliziten Aufrufs aus Benutzercode von einem RCW auftreten, oder während die CLR selbst die COM\-Komponente manipuliert, z. B. wenn die CLR die COM\-Komponente freigibt, nachdem für den zugeordneten RCW eine Garbage Collection durchgeführt wurde.  
  
## Lösung  
 Um dieses Problem zu vermeiden, stellen Sie sicher, dass der Thread, der das STA besitzt, nicht beendet wird, bevor die Anwendung mit allen Objekten fertig ist, die in diesem Apartment vorhanden sind.  Dasselbe gilt für Kontexte. Stellen Sie sicher, dass Kontexte nicht heruntergefahren werden, bevor die Anwendung mit allen COM\-Komponenten vollständig fertig ist, die in diesem Kontext vorhanden sind.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  Es werden nur Daten zu dem getrennten Kontext gemeldet.  
  
## Ausgabe  
 Meldet das Kontextcookie des getrennten Apartments oder Kontexts.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)