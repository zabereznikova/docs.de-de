---
title: 'Vorgehensweise: Auslösen und Verarbeiten von Ereignissen'
description: Lösen Sie in .NET Ereignisse aus, und verarbeiten Sie sie. Dieser Artikel enthält Beispiele, in denen die Delegaten EventHandler, EventHandler<TEventArgs> sowie ein benutzerdefinierter Delegat verwendet werden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET], raising
- raising events
- events [.NET], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
ms.openlocfilehash: c9121c6b2635788ad8ad7abc6d2b5a58448049a6
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93064196"
---
# <a name="how-to-raise-and-consume-events"></a><span data-ttu-id="73ead-104">Vorgehensweise: Auslösen und Verarbeiten von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="73ead-104">How to: Raise and Consume Events</span></span>
<span data-ttu-id="73ead-105">Mithilfe der Beispiele in diesem Thema wird veranschaulicht, wie mit Ereignissen gearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="73ead-105">The examples in this topic show how to work with events.</span></span> <span data-ttu-id="73ead-106">Sie schließen Beispiele für den <xref:System.EventHandler>-Delegaten, den <xref:System.EventHandler%601>-Delegaten und einen benutzerdefinierten Delegaten ein, um Ereignisse mit und ohne Daten zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="73ead-106">They include examples of the <xref:System.EventHandler> delegate, the <xref:System.EventHandler%601> delegate, and a custom delegate, to illustrate events with and without data.</span></span>  
  
 <span data-ttu-id="73ead-107">In den Beispielen werden die im Artikel [Ereignisse](index.md) beschriebenen Konzepte verwendet.</span><span class="sxs-lookup"><span data-stu-id="73ead-107">The examples use concepts described in the [Events](index.md) article.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73ead-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73ead-108">Example</span></span>  
 <span data-ttu-id="73ead-109">Im ersten Beispiel wird das Auslösen und Nutzen eines Ereignisses ohne Daten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="73ead-109">The first example shows how to raise and consume an event that doesn't have data.</span></span> <span data-ttu-id="73ead-110">Es ist eine Klasse namens `Counter` enthalten, die über ein Ereignis namens `ThresholdReached` verfügt.</span><span class="sxs-lookup"><span data-stu-id="73ead-110">It contains a class named `Counter` that has an event named `ThresholdReached`.</span></span> <span data-ttu-id="73ead-111">Dieses Ereignis wird ausgelöst, wenn ein Leistungsindikatorwert einem Schwellenwert entspricht oder diesen überschreitet.</span><span class="sxs-lookup"><span data-stu-id="73ead-111">This event is raised when a counter value equals or exceeds a threshold value.</span></span> <span data-ttu-id="73ead-112">Der <xref:System.EventHandler>-Delegat wird dem Ereignis zugeordnet, da keine Ereignisdaten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="73ead-112">The <xref:System.EventHandler> delegate is associated with the event, because no event data is provided.</span></span>  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="73ead-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73ead-113">Example</span></span>  
 <span data-ttu-id="73ead-114">Im nächsten Beispiel wird das Auslösen und Nutzen eines Daten bereitstellenden Ereignisses dargestellt.</span><span class="sxs-lookup"><span data-stu-id="73ead-114">The next example shows how to raise and consume an event that provides data.</span></span> <span data-ttu-id="73ead-115">Der <xref:System.EventHandler%601>-Delegat wird dem Ereignis zugeordnet, und die Instanz eines benutzerdefinierten Ereignisdatenobjekts wird bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="73ead-115">The <xref:System.EventHandler%601> delegate is associated with the event, and an instance of a custom event data object is provided.</span></span>  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="73ead-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73ead-116">Example</span></span>  
 <span data-ttu-id="73ead-117">Im nächsten Beispiel wird das Deklarieren eines Delegaten für ein Ereignis dargestellt.</span><span class="sxs-lookup"><span data-stu-id="73ead-117">The next example shows how to declare a delegate for an event.</span></span> <span data-ttu-id="73ead-118">Der Delegat wird `ThresholdReachedEventHandler` genannt.</span><span class="sxs-lookup"><span data-stu-id="73ead-118">The delegate is named `ThresholdReachedEventHandler`.</span></span> <span data-ttu-id="73ead-119">Das ist nur eine Abbildung.</span><span class="sxs-lookup"><span data-stu-id="73ead-119">This is just an illustration.</span></span> <span data-ttu-id="73ead-120">In der Regel müssen Sie einen Delegaten für ein Ereignis nicht deklarieren, da Sie entweder den <xref:System.EventHandler>-Delegaten oder den <xref:System.EventHandler%601>-Delegaten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="73ead-120">Typically, you do not have to declare a delegate for an event, because you can use either the <xref:System.EventHandler> or the <xref:System.EventHandler%601> delegate.</span></span> <span data-ttu-id="73ead-121">Sie sollten einen Delegaten nur in seltenen Szenarien deklarieren, zum Beispiel wenn Sie eine Klasse für Legacy-Code, in dem keine Generics verwendet werden können, verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="73ead-121">You should declare a delegate only in rare scenarios, such as making your class available to legacy code that cannot use generics.</span></span>  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="73ead-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73ead-122">See also</span></span>

- [<span data-ttu-id="73ead-123">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="73ead-123">Events</span></span>](index.md)
