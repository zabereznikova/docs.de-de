---
title: 'Gewusst wie: Auslösen und Behandeln von Ereignissen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], raising
- raising events
- events [.NET Framework], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
ms.openlocfilehash: 4d0b24b8a6f1b914745d819b90b973752e32447c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279957"
---
# <a name="how-to-raise-and-consume-events"></a><span data-ttu-id="10c76-102">Gewusst wie: Auslösen und Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="10c76-102">How to: Raise and Consume Events</span></span>
<span data-ttu-id="10c76-103">Mithilfe der Beispiele in diesem Thema wird veranschaulicht, wie mit Ereignissen gearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="10c76-103">The examples in this topic show how to work with events.</span></span> <span data-ttu-id="10c76-104">Sie schließen Beispiele für den <xref:System.EventHandler>-Delegaten, den <xref:System.EventHandler%601>-Delegaten und einen benutzerdefinierten Delegaten ein, um Ereignisse mit und ohne Daten zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="10c76-104">They include examples of the <xref:System.EventHandler> delegate, the <xref:System.EventHandler%601> delegate, and a custom delegate, to illustrate events with and without data.</span></span>  
  
 <span data-ttu-id="10c76-105">In den Beispielen werden die im Artikel [Ereignisse](index.md) beschriebenen Konzepte verwendet.</span><span class="sxs-lookup"><span data-stu-id="10c76-105">The examples use concepts described in the [Events](index.md) article.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10c76-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10c76-106">Example</span></span>  
 <span data-ttu-id="10c76-107">Im ersten Beispiel wird das Auslösen und Nutzen eines Ereignisses ohne Daten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="10c76-107">The first example shows how to raise and consume an event that doesn't have data.</span></span> <span data-ttu-id="10c76-108">Es ist eine Klasse namens `Counter` enthalten, die über ein Ereignis namens `ThresholdReached` verfügt.</span><span class="sxs-lookup"><span data-stu-id="10c76-108">It contains a class named `Counter` that has an event named `ThresholdReached`.</span></span> <span data-ttu-id="10c76-109">Dieses Ereignis wird ausgelöst, wenn ein Leistungsindikatorwert einem Schwellenwert entspricht oder diesen überschreitet.</span><span class="sxs-lookup"><span data-stu-id="10c76-109">This event is raised when a counter value equals or exceeds a threshold value.</span></span> <span data-ttu-id="10c76-110">Der <xref:System.EventHandler>-Delegat wird dem Ereignis zugeordnet, da keine Ereignisdaten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="10c76-110">The <xref:System.EventHandler> delegate is associated with the event, because no event data is provided.</span></span>  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="10c76-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10c76-111">Example</span></span>  
 <span data-ttu-id="10c76-112">Im nächsten Beispiel wird das Auslösen und Nutzen eines Daten bereitstellenden Ereignisses dargestellt.</span><span class="sxs-lookup"><span data-stu-id="10c76-112">The next example shows how to raise and consume an event that provides data.</span></span> <span data-ttu-id="10c76-113">Der <xref:System.EventHandler%601>-Delegat wird dem Ereignis zugeordnet, und die Instanz eines benutzerdefinierten Ereignisdatenobjekts wird bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="10c76-113">The <xref:System.EventHandler%601> delegate is associated with the event, and an instance of a custom event data object is provided.</span></span>  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="10c76-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10c76-114">Example</span></span>  
 <span data-ttu-id="10c76-115">Im nächsten Beispiel wird das Deklarieren eines Delegaten für ein Ereignis dargestellt.</span><span class="sxs-lookup"><span data-stu-id="10c76-115">The next example shows how to declare a delegate for an event.</span></span> <span data-ttu-id="10c76-116">Der Delegat wird `ThresholdReachedEventHandler` genannt.</span><span class="sxs-lookup"><span data-stu-id="10c76-116">The delegate is named `ThresholdReachedEventHandler`.</span></span> <span data-ttu-id="10c76-117">Das ist nur eine Abbildung.</span><span class="sxs-lookup"><span data-stu-id="10c76-117">This is just an illustration.</span></span> <span data-ttu-id="10c76-118">In der Regel müssen Sie einen Delegaten für ein Ereignis nicht deklarieren, da Sie entweder den <xref:System.EventHandler>-Delegaten oder den <xref:System.EventHandler%601>-Delegaten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="10c76-118">Typically, you do not have to declare a delegate for an event, because you can use either the <xref:System.EventHandler> or the <xref:System.EventHandler%601> delegate.</span></span> <span data-ttu-id="10c76-119">Sie sollten einen Delegaten nur in seltenen Szenarien deklarieren, zum Beispiel wenn Sie eine Klasse für Legacy-Code, in dem keine Generics verwendet werden können, verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="10c76-119">You should declare a delegate only in rare scenarios, such as making your class available to legacy code that cannot use generics.</span></span>  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="10c76-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10c76-120">See also</span></span>

- [<span data-ttu-id="10c76-121">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="10c76-121">Events</span></span>](index.md)
