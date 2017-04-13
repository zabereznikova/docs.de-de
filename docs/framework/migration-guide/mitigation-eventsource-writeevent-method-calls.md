---
title: "Minderung: EventSource.WriteEvent-Methodenaufrufe | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 327a9fdb-ba8e-40f7-89e5-4c89b46e594f
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Minderung: EventSource.WriteEvent-Methodenaufrufe
[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] setzt einen Vertrag zwischen einer ETW\-Ereignismethode in einer Klasse, die von <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> abgeleitet wird, und der <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A>\-Methode der Basisklasse durch. Die ETW\-Ereignismethode muss der <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A>\-Methode die Ereignis\-ID gefolgt von den gleichen Argumenten übergeben, die an die Ereignismethode übergeben wurden.  
  
## Auswirkungen  
 Eine ETW\-Ereignismethode, die folgendermaßen definiert ist, verstößt gegen den Vertrag:  
  
```  
  
[Event(2, Level = EventLevel.Informational)] public void Info2(string message) { base.WriteEvent(2, message, "-"); }  
  
```  
  
 Wenn gegen diesen Vertrag verstoßen wird, wird eine <xref:System.IndexOutOfRangeException>\-Ausnahme zur Laufzeit ausgelöst, wenn ein <xref:System.Diagnostics.Tracing.EventListener>\-Objekt <xref:System.Diagnostics.Tracing.EventSource>\-Daten im Prozess liest.  
  
 Die Definition für diese ETW\-Ereignismethode sollte diesem Muster folgen:  
  
```  
  
[Event(2, Level = EventLevel.Informational)] public void Info2(string message) { base.WriteEvent(2, message); }  
  
```  
  
## Minderung  
 Sie müssen vorhandenen Code so ändern, dass dieser dem erforderlichen Muster entspricht.  
  
 Sie können den Code, den Sie ändern müssen, minimieren, indem Sie wie folgt zwei Methoden zum Aufrufen der <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A>\-Methode definieren:  
  
```  
  
[NonEvent] public void Info2(string message) { Info2Internal(message, "-"); } public void Info2Internal(string message, string prefix) { WriteEvent(2, message, prefix); }  
  
```  
  
## Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)