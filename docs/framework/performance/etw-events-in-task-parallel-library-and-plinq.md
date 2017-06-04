---
title: "ETW-Ereignisse in der Task Parallel Library und PLINQ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Aufgaben, ETW-Ereignisse"
ms.assetid: 87a9cff5-d86f-4e44-a06e-d12764d0dce2
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# ETW-Ereignisse in der Task Parallel Library und PLINQ
Von der Task Parallel Library und PLINQ werden ETW \(Ereignisablaufverfolgung für Windows\)\-Ereignisse generiert, die mit Tools wie dem Windows\-Leistung\-Analyzer zur Profilerstellung und Fehlerbehebung für Anwendungen verwendet werden können.  In den meisten Szenarios, ist die beste Methode, ein Profil für parallelen Anwendungscode erstellt, [Parallelitätsschnellansicht](../Topic/Concurrency%20Visualizer.md) in [!INCLUDE[vsUltShort](../../../includes/vsultshort-md.md)].  
  
## Task Parallel Library\-ETW\-Ereignisse  
 In der EVENT\_HEADER\-Struktur lautet die ProviderId\-GUID für von <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> und <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=fullName> generierte Ereignisse wie folgt:  
  
```  
0x2e5dba47, 0xa3d2, 0x4d16, 0x8e, 0xe0, 0x66, 0x71, 0xff, 0xdc, 0xd7, 0xb5  
```  
  
### Beginn der parallelen Schleife  
 EVENT\_DESCRIPTOR.Task \= 1  
  
 EVENT\_DESCRIPTOR.Id \= 1  
  
#### Benutzerdaten  
  
|**Name**|**Typ**|****Beschreibung****|  
|--------------|-------------|--------------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Die ID des TaskScheduler, von dem die Schleife gestartet wurde.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Die ID der Aufgabe, von der die Schleife gestartet wurde.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|Ein eindeutiger Bezeichner, mit dem Schachtelung und Paare für Ereignisse mit Gabelung\/Join\-Semantik angegeben werden.|  
|OperationType|<xref:System.Int32?displayProperty=fullName>|Gibt den Typ der Schleife an:<br /><br /> 1 \= ParallelInvoke<br /><br /> 2 \= ParallelFor<br /><br /> 3 \= ParallelForEach|  
|InclusiveFrom|<xref:System.Int64?displayProperty=fullName>|Der Startwert des Schleifenzählers|  
|ExclusiveTo|<xref:System.Int64?displayProperty=fullName>|Der Endwert des Schleifenzählers|  
  
### Ende der parallelen Schleife  
 EVENT\_DESCRIPTOR.Task \= 2  
  
 EVENT\_DESCRIPTOR.Id \= 2  
  
#### Benutzerdaten  
  
|**Name**|**Typ**|****Beschreibung****|  
|--------------|-------------|--------------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Die ID des TaskScheduler, von dem die Schleife gestartet wurde.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Die ID der Aufgabe, von der die Schleife gestartet wurde.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|Ein eindeutiger Bezeichner, mit dem Schachtelung und Paare für Ereignisse mit Gabelung\/Join\-Semantik angegeben werden.|  
|totalIterations|<xref:System.Int64?displayProperty=fullName>|Die Gesamtanzahl der Iterationen|  
  
### Beginn des parallelen Aufrufs  
 EVENT\_DESCRIPTOR.Task \= 3  
  
 EVENT\_DESCRIPTOR.Id \= 3  
  
#### Benutzerdaten  
  
|**Name**|**Typ**|****Beschreibung****|  
|--------------|-------------|--------------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Die ID des TaskScheduler, von dem die Schleife gestartet wurde.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Die ID der Aufgabe, von der die Schleife gestartet wurde.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|Ein eindeutiger Bezeichner, mit dem Schachtelung und Paare für Ereignisse mit Gabelung\/Join\-Semantik angegeben werden.|  
|totalIterations|<xref:System.Int64?displayProperty=fullName>|Die Gesamtanzahl der Iterationen|  
|operationType|<xref:System.Int32?displayProperty=fullName>|Gibt den Typ der Schleife an:<br /><br /> 1 \= ParallelInvoke<br /><br /> 2 \= ParallelFor<br /><br /> 3 \= ParallelForEach|  
|ActionCount|<xref:System.Int32?displayProperty=fullName>|Die Anzahl der Aktionen, die im parallelen Aufruf ausgeführt werden.|  
  
### Ende des parallelen Aufrufs  
 EVENT\_DESCRIPTOR.Task \= 4  
  
 EVENT\_DESCRIPTOR.Id \= 4  
  
#### Benutzerdaten  
  
|**Name**|**Typ**|****Beschreibung****|  
|--------------|-------------|--------------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Die ID des TaskScheduler, von dem die Schleife gestartet wurde.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Die ID der Aufgabe, von der die Schleife gestartet wurde.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|Ein eindeutiger Bezeichner, mit dem Schachtelung und Paare für Ereignisse mit Gabelung\/Join\-Semantik angegeben werden.|  
  
## PLINQ\-ETW\-Ereignisse  
 Die EVENT\_HEADER.ProviderId\-GUID für PLINQ lautet:  
  
```  
0x159eeeec, 0x4a14, 0x4418, 0xa8, 0xfe, 0xfa, 0xab, 0xcd, 0x98, 0x78, 0x87  
```  
  
### Beginn der parallelen Abfrage  
 EVENT\_DESCRIPTOR.Task \= 1  
  
 EVENT\_DESCRIPTOR.Id \= 1  
  
#### Benutzerdaten  
  
|**Name**|**Typ**|****Beschreibung****|  
|--------------|-------------|--------------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Die ID des TaskScheduler, von dem die Schleife gestartet wurde.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Die ID der Aufgabe, von der die Schleife gestartet wurde.|  
|QueryID|<xref:System.Int32?displayProperty=fullName>|Ein eindeutiger Abfragebezeichner.|  
  
### Ende der parallelen Abfrage  
 EVENT\_DESCRIPTOR.Task \= 2  
  
 EVENT\_DESCRIPTOR.Id \= 2  
  
#### Benutzerdaten  
  
|**Name**|**Typ**|****Beschreibung****|  
|--------------|-------------|--------------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Die ID des TaskScheduler, von dem die Schleife gestartet wurde.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Die ID der Aufgabe, von der die Schleife gestartet wurde.|  
|QueryID|<xref:System.Int32?displayProperty=fullName>|Ein eindeutiger Abfragebezeichner.|  
  
## Siehe auch  
 [ETW Events in the .NET Framework](../../../docs/framework/performance/etw-events.md)   
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)