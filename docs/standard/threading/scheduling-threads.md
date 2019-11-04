---
title: Scheduling von Threads
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
ms.openlocfilehash: abcdf56b90513b937adefc38583e0312fec69785
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73106227"
---
# <a name="scheduling-threads"></a>Scheduling von Threads

Jedem Thread ist eine Threadpriorität zugewiesen. Threads, die innerhalb der Common Language Runtime erstellt werden, erhalten anfänglich die Priorität <xref:System.Threading.ThreadPriority.Normal?displayProperty=nameWithType>. Threads, die außerhalb der Runtime erstellt werden, behalten die Priorität bei, die sie vor dem Eintritt in die verwaltete Umgebung innehatten. Sie können die Priorität jedes Threads mithilfe der <xref:System.Threading.Thread.Priority?displayProperty=nameWithType>-Eigenschaft abrufen oder festlegen.  
  
 Die Ausführung von Threads wird basierend auf ihrer Priorität geplant. Auch wenn Threads innerhalb der Runtime ausgeführt werden, weist das Betriebssystem allen Threads Prozessorzeitsegmente zu. Die Details des Planungsalgorithmus, der zum Ermitteln der Ausführungsreihenfolge der Threads verwendet wird, variieren je nach Betriebssystem. In einigen Betriebssystemen erfolgt die Planung so, dass der Thread mit der höchsten Priorität (aller ausführbaren Threads) immer zuerst ausgeführt wird. Wenn mehrere Threads mit der gleichen Priorität verfügbar sind, durchläuft der Planer diese Threads und weist jedem Thread ein festgelegtes Zeitsegment zu, innerhalb dessen die Ausführung erfolgt. Solange ein Thread mit höherer Priorität für die Ausführung verfügbar ist, werden Threads mit niedrigerer Priorität nicht ausgeführt. Wenn keine ausführbaren Threads mit einer bestimmten Priorität mehr verfügbar sind, fährt der Planer mit der nächstniedrigeren Priorität fort und plant die Ausführung der Threads mit dieser Priorität. Wenn ein Thread mit einer höheren Priorität für die Ausführung verfügbar wird, erhält er Vorrang vor dem Thread mit der niedrigeren Priorität und wird erneut ausgeführt. Darüber hinaus kann das Betriebssystem Threadprioritäten auch dynamisch anpassen, wenn die Benutzeroberfläche einer Anwendung vom Vordergrund in den Hintergrund oder zurück wechselt. Andere Betriebssysteme können einen anderen Planungsalgorithmus einsetzen.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Threads und Threading](../../../docs/standard/threading/using-threads-and-threading.md)
- [Verwaltetes und nicht verwaltetes Threading in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
