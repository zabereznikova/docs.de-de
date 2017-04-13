---
title: "Scheduling Threads | Microsoft Docs"
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
  - "threading [.NET Framework], scheduling"
  - "scheduling threads"
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Scheduling Threads
Jeder Thread hat eine ihm zugewiesene Threadpriorität.  Threads, die innerhalb der Common Language Runtime erstellt wurden, wird zu Beginn die Priorität **ThreadPriority.Normal** zugewiesen.  Außerhalb davon erstellte Threads behalten die Priorität, die sie vor Eintritt in die verwaltete Umgebung hatten.  Mithilfe der **Thread.Priority**\-Eigenschaft kann die Priorität jedes Threads ermittelt und festgelegt werden.  
  
 Der Zeitpunkt der Ausführung eines Thread basiert auf dessen Priorität.  Obwohl die Ausführung innerhalb der Laufzeit stattfindet, werden allen Threads vom Betriebssystem Anteile der CPU\-Zeit zugeordnet.  Die Details des Schedulingalgorithmus, durch den die Ausführungsreihenfolge der Threads bestimmt wird, variieren je nach Betriebssystem.  In einigen Betriebssystemen wird der Thread mit der höchsten Priorität \(bezogen auf ausführbare Threads\) immer als der erste zu startende Thread eingeplant.  Stehen mehrere Threads mit derselben Priorität zur Verfügung, geht der Taskplaner alle Threads dieser Priorität der Reihe nach durch und weist jedem einen festgelegten Zeitanteil für die Ausführung zu.  Solange ein Thread mit höherer Priorität verfügbar ist, können Threads mit niedrigerer Priorität ihre Ausführung nicht beginnen.  Kann kein Thread einer bestimmten Priorität mehr ausgeführt werden, beginnt der Taskplaner mit der Ausführungsplanung der Threads mit der nächstniedrigeren Priorität.  Sobald ein Thread mit höherer Priorität ausführbar wird, wird derjenige mit niedrigerer Priorität verdrängt, sodass der andere erneut ausgeführt werden kann.  Darüber hinaus kann das Betriebssystem Threadprioritäten auch dynamisch einstellen, wenn die Benutzeroberfläche einer Anwendung vom Vordergrund in den Hintergrund wechselt oder umgekehrt.  Der Planungsalgorithmus anderer Betriebssysteme kann sich davon unterscheiden.  
  
## Siehe auch  
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)   
 [Managed and Unmanaged Threading in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)