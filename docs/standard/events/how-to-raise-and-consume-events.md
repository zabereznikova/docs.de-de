---
title: 'Vorgehensweise: Auslösen und Verarbeiten von Ereignissen'
description: Lösen Sie in .NET Ereignisse aus, und verarbeiten Sie sie. Dieser Artikel enthält Beispiele, in denen die Delegaten EventHandler, EventHandler<TEventArgs> sowie ein benutzerdefinierter Delegat verwendet werden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET], raising
- raising events
- events [.NET], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
ms.openlocfilehash: 22e62dd8e14696273923873353b1bd19d8507ab7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697453"
---
# <a name="how-to-raise-and-consume-events"></a>Vorgehensweise: Auslösen und Verarbeiten von Ereignissen

Mithilfe der Beispiele in diesem Thema wird veranschaulicht, wie mit Ereignissen gearbeitet wird. Sie schließen Beispiele für den <xref:System.EventHandler>-Delegaten, den <xref:System.EventHandler%601>-Delegaten und einen benutzerdefinierten Delegaten ein, um Ereignisse mit und ohne Daten zu veranschaulichen.  
  
 In den Beispielen werden die im Artikel [Ereignisse](index.md) beschriebenen Konzepte verwendet.  
  
## <a name="example"></a>Beispiel  

 Im ersten Beispiel wird das Auslösen und Nutzen eines Ereignisses ohne Daten dargestellt. Es ist eine Klasse namens `Counter` enthalten, die über ein Ereignis namens `ThresholdReached` verfügt. Dieses Ereignis wird ausgelöst, wenn ein Leistungsindikatorwert einem Schwellenwert entspricht oder diesen überschreitet. Der <xref:System.EventHandler>-Delegat wird dem Ereignis zugeordnet, da keine Ereignisdaten bereitgestellt werden.  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a>Beispiel  

 Im nächsten Beispiel wird das Auslösen und Nutzen eines Daten bereitstellenden Ereignisses dargestellt. Der <xref:System.EventHandler%601>-Delegat wird dem Ereignis zugeordnet, und die Instanz eines benutzerdefinierten Ereignisdatenobjekts wird bereitgestellt.  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a>Beispiel  

 Im nächsten Beispiel wird das Deklarieren eines Delegaten für ein Ereignis dargestellt. Der Delegat wird `ThresholdReachedEventHandler` genannt. Das ist nur eine Abbildung. In der Regel müssen Sie einen Delegaten für ein Ereignis nicht deklarieren, da Sie entweder den <xref:System.EventHandler>-Delegaten oder den <xref:System.EventHandler%601>-Delegaten verwenden können. Sie sollten einen Delegaten nur in seltenen Szenarien deklarieren, zum Beispiel wenn Sie eine Klasse für Legacy-Code, in dem keine Generics verwendet werden können, verfügbar machen.  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisse](index.md)
