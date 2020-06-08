---
title: 'Gewusst wie: Behandeln mehrerer Ereignisse mit Ereigniseigenschaften'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET Framework]
- multiple events [.NET Framework]
- event handling [.NET Framework], with multiple events
- events [.NET Framework], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
ms.openlocfilehash: c5be541c1a40c5d16a0502e76adef24f6a41cc89
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288471"
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="9a512-102">Gewusst wie: Behandeln mehrerer Ereignisse mit Ereigniseigenschaften</span><span class="sxs-lookup"><span data-stu-id="9a512-102">How to: Handle Multiple Events Using Event Properties</span></span>
<span data-ttu-id="9a512-103">Zur Verwendung von Ereigniseigenschaften müssen Sie die Ereigniseigenschaften in der Klasse definieren, die die Ereignisse auslöst. Anschließend müssen Sie die Delegaten für die Ereigniseigenschaften in den Klassen festlegen, die die Ereignisse behandeln.</span><span class="sxs-lookup"><span data-stu-id="9a512-103">To use event properties, you define the event properties in the class that raises the events, and then set the delegates for the event properties in classes that handle the events.</span></span> <span data-ttu-id="9a512-104">Zum Implementieren mehrerer Ereigniseigenschaften in einer Klasse muss die Klasse den für jedes Ereignis definierten Delegaten intern speichern und verwalten.</span><span class="sxs-lookup"><span data-stu-id="9a512-104">To implement multiple event properties in a class, the class must internally store and maintain the delegate defined for each event.</span></span> <span data-ttu-id="9a512-105">Ein typischer Ansatz ist, eine Delegatauflistung zu implementieren, die von einem Ereignisschlüssel indiziert wird.</span><span class="sxs-lookup"><span data-stu-id="9a512-105">A typical approach is to implement a delegate collection that is indexed by an event key.</span></span>  
  
 <span data-ttu-id="9a512-106">Zum Speichern der Delegaten für jedes Ereignis können Sie die <xref:System.ComponentModel.EventHandlerList>-Klasse verwenden oder eine eigene Auflistung implementieren.</span><span class="sxs-lookup"><span data-stu-id="9a512-106">To store the delegates for each event, you can use the <xref:System.ComponentModel.EventHandlerList> class, or implement your own collection.</span></span> <span data-ttu-id="9a512-107">Die Auflistungsklasse muss Methoden für das Festlegen, Aufrufen und Abrufen des Ereignishandlerdelegaten auf der Grundlage des Ereignisschlüssels bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9a512-107">The collection class must provide methods for setting, accessing, and retrieving the event handler delegate based on the event key.</span></span> <span data-ttu-id="9a512-108">Zum Beispiel könnten Sie eine <xref:System.Collections.Hashtable>-Klasse verwenden oder eine benutzerdefinierte Klasse von der <xref:System.Collections.DictionaryBase>-Klasse ableiten.</span><span class="sxs-lookup"><span data-stu-id="9a512-108">For example, you could use a <xref:System.Collections.Hashtable> class, or derive a custom class from the <xref:System.Collections.DictionaryBase> class.</span></span> <span data-ttu-id="9a512-109">Die Implementierungsdetails der Delegatauflistung müssen nicht außerhalb der Klasse verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="9a512-109">The implementation details of the delegate collection do not need to be exposed outside your class.</span></span>  
  
 <span data-ttu-id="9a512-110">Jede Ereigniseigenschaft innerhalb der Klasse definiert eine add-Accessor-Methode und eine remove-Accessor-Methode.</span><span class="sxs-lookup"><span data-stu-id="9a512-110">Each event property within the class defines an add accessor method and a remove accessor method.</span></span> <span data-ttu-id="9a512-111">Der add-Accessor für eine Ereigniseigenschaft fügt die Eingabedelegatinstanz der Delegatauflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="9a512-111">The add accessor for an event property adds the input delegate instance to the delegate collection.</span></span> <span data-ttu-id="9a512-112">Der remove-Accessor für eine Ereigniseigenschaft entfernt die Eingabedelegatinstanz aus der Delegatauflistung.</span><span class="sxs-lookup"><span data-stu-id="9a512-112">The remove accessor for an event property removes the input delegate instance from the delegate collection.</span></span> <span data-ttu-id="9a512-113">Die Accessoren für Ereigniseigenschaften verwenden den vordefinierten Schlüssel für die Ereigniseigenschaft, um Instanzen der Delegatauflistung hinzuzufügen bzw. daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9a512-113">The event property accessors use the predefined key for the event property to add and remove instances from the delegate collection.</span></span>  
  
### <a name="to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="9a512-114">So behandeln Sie mehrere Ereignisse mit Ereigniseigenschaften</span><span class="sxs-lookup"><span data-stu-id="9a512-114">To handle multiple events using event properties</span></span>  
  
1. <span data-ttu-id="9a512-115">Definieren Sie eine Delegatauflistung innerhalb der Klasse, die die Ereignisse auslöst.</span><span class="sxs-lookup"><span data-stu-id="9a512-115">Define a delegate collection within the class that raises the events.</span></span>  
  
2. <span data-ttu-id="9a512-116">Definieren Sie einen Schlüssel für jedes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9a512-116">Define a key for each event.</span></span>  
  
3. <span data-ttu-id="9a512-117">Definieren Sie die Ereigniseigenschaften in der Klasse, die die Ereignisse auslöst.</span><span class="sxs-lookup"><span data-stu-id="9a512-117">Define the event properties in the class that raises the events.</span></span>  
  
4. <span data-ttu-id="9a512-118">Verwenden Sie die Delegatauflistung, um die add- und die remove-Accessor-Methode für die Ereigniseigenschaften zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="9a512-118">Use the delegate collection to implement the add and remove accessor methods for the event properties.</span></span>  
  
5. <span data-ttu-id="9a512-119">Verwenden Sie die öffentlichen Ereigniseigenschaften, um Ereignishandlerdelegaten in den Klassen, die die Ereignisse auslösen, hinzuzufügen und zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9a512-119">Use the public event properties to add and remove event handler delegates in the classes that handle the events.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a512-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9a512-120">Example</span></span>  
 <span data-ttu-id="9a512-121">Das folgende C#-Beispiel implementiert die `MouseDown`-Ereigniseigenschaft und die `MouseUp`-Ereigniseigenschaft unter Verwendung einer <xref:System.ComponentModel.EventHandlerList>, um den Delegat jedes Ereignisses zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9a512-121">The following C# example implements the event properties `MouseDown` and `MouseUp`, using an <xref:System.ComponentModel.EventHandlerList> to store each event's delegate.</span></span> <span data-ttu-id="9a512-122">Die Schlüsselwörter der Eigenschaftenkonstrukte für Ereignisse sind fett dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9a512-122">The keywords of the event property constructs are in bold type.</span></span>  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="9a512-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a512-123">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>
- [<span data-ttu-id="9a512-124">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="9a512-124">Events</span></span>](index.md)
- <xref:System.Web.UI.Control.Events%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9a512-125">Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen</span><span class="sxs-lookup"><span data-stu-id="9a512-125">How to: Declare Custom Events To Conserve Memory</span></span>](../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
