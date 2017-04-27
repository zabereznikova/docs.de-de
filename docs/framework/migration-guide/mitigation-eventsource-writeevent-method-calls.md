---
title: "Entschärfung: EventSource.WriteEvent-Methodenaufrufe | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 327a9fdb-ba8e-40f7-89e5-4c89b46e594f
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cde809989d89c10caeb97ec853c8649a108cd72d
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-eventsourcewriteevent-method-calls"></a>Entschärfung: EventSource.WriteEvent-Methodenaufrufe
[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] erzwingt einen Vertrag zwischen einer ETW-Ereignismethode in einer von <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> abgeleiteten Klasse und der <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A>-Methode ihrer Basisklasse. Die ETW-Ereignismethode muss der <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A>-Methode die Ereignis-ID gefolgt von den gleichen Argumenten übergeben, die an die Ereignismethode übergeben wurden.  
  
## <a name="impact"></a>Auswirkungen  
 Eine ETW-Ereignismethode, die folgendermaßen definiert ist, verstößt gegen den Vertrag:  
  
```  
  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message, "-");  
}  
  
```  
  
 Wenn gegen diesen Vertrag verstoßen wird, wird zur Laufzeit eine <xref:System.IndexOutOfRangeException>-Ausnahme ausgelöst, wenn ein <xref:System.Diagnostics.Tracing.EventListener>-Objekt in Verarbeitung befindliche <xref:System.Diagnostics.Tracing.EventSource>-Daten liest.  
  
 Die Definition für diese ETW-Ereignismethode sollte diesem Muster folgen:  
  
```  
  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message);  
}  
  
```  
  
## <a name="mitigation"></a>Minderung  
 Sie müssen vorhandenen Code so ändern, dass dieser dem erforderlichen Muster entspricht.  
  
 Sie können den Code, den Sie ändern müssen, minimieren, indem Sie wie folgt zwei Methoden zum Aufrufen der <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A>-Methode definieren:  
  
```  
  
[NonEvent]  
public void Info2(string message)  
{  
   Info2Internal(message, "-");  
}  
  
public void Info2Internal(string message, string prefix)  
{  
   WriteEvent(2, message, prefix);  
}  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)
