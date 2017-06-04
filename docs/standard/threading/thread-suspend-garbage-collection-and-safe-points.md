---
title: "Thread.Suspend, Garbage Collection, and Safe Points | Microsoft Docs"
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
  - "suspending threads"
  - "safe points"
  - "threading [.NET Framework], suspending"
  - "threading [.NET Framework], garbage collection"
  - "garbage collection, threads"
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Thread.Suspend, Garbage Collection, and Safe Points
Wenn Sie für einen Thread <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> aufrufen, nimmt das System die Anforderung einer Threadunterbrechung zur Kenntnis und lässt die Ausführung des Threads bis zum Erreichen eines Sicherungspunkts zu. Erst dann wird der Thread tatsächlich unterbrochen.  Ein Sicherungspunkt für einen Thread ist ein Punkt, an dem die Garbage Collection durchgeführt werden kann.  
  
 Sobald ein Sicherungspunkt erreicht ist, stellt die Common Language Runtime sicher, dass der unterbrochene Thread keinen weiteren verwalteten Code mehr ausführt.  Ein Thread, in dem kein verwalteter Code ausgeführt wird, ist für die Garbage Collection immer sicher. Die Ausführung wird fortgesetzt, bis der Thread versucht, die Ausführung von verwaltetem Code fortzusetzen.  
  
> [!NOTE]
>  Um eine Garbage Collection durchzuführen, müssen alle Threads mit Ausnahme des Threads, in dem die Garbage Collection ausgeführt wird, unterbrochen werden.  Jeder Thread muss vor seiner Unterbrechung einen Sicherungspunkt erreicht haben.  
  
## Siehe auch  
 <xref:System.Threading.Thread>   
 <xref:System.GC>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Automatische Speicherverwaltung](../../../docs/standard/automatic-memory-management.md)