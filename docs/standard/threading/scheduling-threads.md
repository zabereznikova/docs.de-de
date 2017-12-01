---
title: Scheduling von Threads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e1fb7d61b8e250884b2c57cad8c5106bc77787a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="scheduling-threads"></a>Scheduling von Threads
Jeder Thread verfügt über eine Threadpriorität zugewiesen. Threads, die innerhalb der common Language Runtime erstellt werden zunächst die Priorität zugewiesen **ThreadPriority.Normal**. Threads, die außerhalb der Runtime erstellt behalten die Priorität, die ihnen zugewiesen waren, bevor sie die verwaltete Umgebung eingegeben haben. Sie können abrufen oder Festlegen der Priorität einen beliebigen Thread mit der **Thread.Priority** Eigenschaft.  
  
 Threads werden basierend auf deren Priorität Ausführung geplant. Obwohl Threads innerhalb der Runtime ausgeführt werden, werden alle Threads Zeitscheiben Prozessor vom Betriebssystem zugewiesen. Die Details der Planungsalgorithmus bestimmt die Reihenfolge, in der Threads ausgeführt werden, je nach ausgewähltem jedes Betriebssystem. Unter einigen Betriebssystemen erfolgt der Thread mit der höchsten Priorität (der Threads, die ausgeführt werden können) immer zuerst ausgeführt. Wenn mehrere Threads mit gleicher Priorität alle verfügbar sind, durchläuft der Planer die Threads, Priorität, erteilen jeder Thread eine feste Zeitscheibe in dem ausgeführt. Solange ein Thread mit einer höheren Priorität zum Ausführen verfügbar ist, erhalte Threads mit niedrigerer Priorität nicht ausführen. Wenn an einer bestimmten Priorität nicht mehr ausführbar Threads vorhanden sind, wird der Planer verschiebt auf der nächstniedrigeren Priorität und der Priorität für die Ausführung der Threads plant. Wenn ein Thread mit höherer Priorität ausführbar ist, wird der niedrigere Priorität Thread präemptiv unterbrochen wird, und der Thread mit höhere Priorität erneut ausführen zulässig ist. Über die können das Betriebssystem auch Threadprioritäten dynamisch anpassen wie die Benutzeroberfläche einer Anwendung zwischen Vordergrund- und verschoben werden. Andere Betriebssysteme könnten Sie wahlweise einen anderen Planungsalgorithmus verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Threads und Threading](../../../docs/standard/threading/using-threads-and-threading.md)  
 [Verwaltetes und nicht verwaltetes Threading in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
