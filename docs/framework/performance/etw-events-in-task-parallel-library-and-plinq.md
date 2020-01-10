---
title: ETW-Ereignisse in der Task Parallel Library und PLINQ
ms.date: 03/30/2017
helpviewer_keywords:
- tasks, ETW events
ms.assetid: 87a9cff5-d86f-4e44-a06e-d12764d0dce2
ms.openlocfilehash: 93fcd3215bdcbb30960f19e23ae15f32bb9ddd84
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716098"
---
# <a name="etw-events-in-task-parallel-library-and-plinq"></a>ETW-Ereignisse in der Task Parallel Library und PLINQ

Die Task Parallel Library und PLINQ generieren Ereignisse für die Ereignisablaufverfolgung für Windows (ETW), die Sie zur Profilerstellung und Problembehebung für Anwendungen verwenden können, indem Sie Tools wie den Windows Performance Analyzer verwenden. In den meisten Szenarien ist es jedoch am besten, den parallelen Anwendungscode zu erstellen, indem die Parallelitäts schnell [Ansicht in Visual](/visualstudio/profiling/concurrency-visualizer) Studio verwendet wird.

## <a name="task-parallel-library-etw-events"></a>Task Parallel Library-ETW-Ereignisse

In der EVENT_HEADER-Struktur, ist Folgendes die ProviderId-GUID für Ereignisse, die durch <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> generiert wurden:

`0x2e5dba47, 0xa3d2, 0x4d16, 0x8e, 0xe0, 0x66, 0x71, 0xff, 0xdc, 0xd7, 0xb5`

### <a name="parallel-loop-begin"></a>Beginn der parallelen Schleife

EVENT_DESCRIPTOR.Task = 1

EVENT_DESCRIPTOR.Id = 1

#### <a name="user-data"></a>Benutzerdaten

|**Name**|**Type**|**Beschreibung**|
|--------------|--------------|---------------------|
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|Die ID des TaskScheduler, der die Schleife gestartet hat.|
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|Die ID der Aufgabe, die die Schleife gestartet hat.|
|ForkJoinContextID|<xref:System.Int32?displayProperty=nameWithType>|Ein eindeutiger Bezeichner, der verwendet wird, um Schachteln und Paare für Ereignisse mit einer Semantik für Abzweigungen und Zusammenführungen anzugeben.|
|OperationType|<xref:System.Int32?displayProperty=nameWithType>|Gibt den Typ der Schleife an:<br /><br /> 1 = ParallelInvoke<br /><br /> 2 = ParallelFor<br /><br /> 3 = ParallelForEach|
|InclusiveFrom|<xref:System.Int64?displayProperty=nameWithType>|Der Anfangswert des Schleifenzählers|
|ExclusiveTo|<xref:System.Int64?displayProperty=nameWithType>|Der Endwert des Schleifenzählers|

### <a name="parallel-loop-end"></a>Ende der parallelen Schleife
 EVENT_DESCRIPTOR.Task = 2

 EVENT_DESCRIPTOR.Id = 2

#### <a name="user-data"></a>Benutzerdaten

|**Name**|**Type**|**Beschreibung**|
|--------------|--------------|---------------------|
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|Die ID des TaskScheduler, der die Schleife gestartet hat.|
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|Die ID der Aufgabe, die die Schleife gestartet hat.|
|ForkJoinContextID|<xref:System.Int32?displayProperty=nameWithType>|Ein eindeutiger Bezeichner, der verwendet wird, um Schachteln und Paare für Ereignisse mit einer Semantik für Abzweigungen und Zusammenführungen anzugeben.|
|totalIterations|<xref:System.Int64?displayProperty=nameWithType>|Gesamtanzahl von Iterationen|

### <a name="parallel-invoke-begin"></a>Beginn des parallelen Aufrufs
 EVENT_DESCRIPTOR.Task = 3

 EVENT_DESCRIPTOR.Id = 3

#### <a name="user-data"></a>Benutzerdaten

|**Name**|**Type**|**Beschreibung**|
|--------------|--------------|---------------------|
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|Die ID des TaskScheduler, der die Schleife gestartet hat.|
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|Die ID der Aufgabe, die die Schleife gestartet hat.|
|ForkJoinContextID|<xref:System.Int32?displayProperty=nameWithType>|Ein eindeutiger Bezeichner, der verwendet wird, um Schachteln und Paare für Ereignisse mit einer Semantik für Abzweigungen und Zusammenführungen anzugeben.|
|totalIterations|<xref:System.Int64?displayProperty=nameWithType>|Gesamtanzahl von Iterationen|
|operationType|<xref:System.Int32?displayProperty=nameWithType>|Gibt den Typ der Schleife an:<br /><br /> 1 = ParallelInvoke<br /><br /> 2 = ParallelFor<br /><br /> 3 = ParallelForEach|
|ActionCount|<xref:System.Int32?displayProperty=nameWithType>|Die Anzahl der Aktionen, die im parallelen Aufruf ausgeführt wird.|

### <a name="parallel-invoke-end"></a>Ende des parallelen Aufrufs
 EVENT_DESCRIPTOR.Task = 4

 EVENT_DESCRIPTOR.Id = 4

#### <a name="user-data"></a>Benutzerdaten

|**Name**|**Type**|**Beschreibung**|
|--------------|--------------|---------------------|
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|Die ID des TaskScheduler, der die Schleife gestartet hat.|
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|Die ID der Aufgabe, die die Schleife gestartet hat.|
|ForkJoinContextID|<xref:System.Int32?displayProperty=nameWithType>|Ein eindeutiger Bezeichner, der verwendet wird, um Schachteln und Paare für Ereignisse mit einer Semantik für Abzweigungen und Zusammenführungen anzugeben.|

## <a name="plinq-etw-events"></a>PLINQ-ETW-Ereignisse
 Die EVENT_HEADER.ProviderId-GUID für PLINQ ist:

`0x159eeeec, 0x4a14, 0x4418, 0xa8, 0xfe, 0xfa, 0xab, 0xcd, 0x98, 0x78, 0x87`

### <a name="parallel-query-begin"></a>Beginn der parallelen Abfrage
 EVENT_DESCRIPTOR.Task = 1

 EVENT_DESCRIPTOR.Id = 1

#### <a name="user-data"></a>Benutzerdaten

|**Name**|**Type**|**Beschreibung**|
|--------------|--------------|---------------------|
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|Die ID des TaskScheduler, der die Schleife gestartet hat.|
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|Die ID der Aufgabe, die die Schleife gestartet hat.|
|QueryID|<xref:System.Int32?displayProperty=nameWithType>|Ein eindeutiger Bezeichner der Abfrage.|

### <a name="parallel-query-end"></a>Ende der parallelen Abfrage
 EVENT_DESCRIPTOR.Task = 2

 EVENT_DESCRIPTOR.Id = 2

#### <a name="user-data"></a>Benutzerdaten

|**Name**|**Type**|**Beschreibung**|
|--------------|--------------|---------------------|
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=nameWithType>|Die ID des TaskScheduler, der die Schleife gestartet hat.|
|OriginatingTaskID|<xref:System.Int32?displayProperty=nameWithType>|Die ID der Aufgabe, die die Schleife gestartet hat.|
|QueryID|<xref:System.Int32?displayProperty=nameWithType>|Ein eindeutiger Bezeichner der Abfrage.|

## <a name="see-also"></a>Siehe auch

- [ETW Events in the .NET Framework (ETW-Ereignisse in .NET Framework)](etw-events.md)
- [Task Parallel Library (TPL)](../../standard/parallel-programming/task-parallel-library-tpl.md)
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../standard/parallel-programming/parallel-linq-plinq.md)
