---
title: "Gewusst wie: Auslösen von Basisklassenereignissen in abgeleiteten Klassen (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c9da65958ce827fab642f4a6310d0c68dfb951a6
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="d8ffc-102">Gewusst wie: Auslösen von Basisklassenereignissen in abgeleiteten Klassen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d8ffc-102">How to: Raise Base Class Events in Derived Classes (C# Programming Guide)</span></span>
<span data-ttu-id="d8ffc-103">Das folgende einfache Beispiel zeigt das Standardverfahren zum Deklarieren von Ereignissen in einer Basisklasse, sodass sie auch von abgeleiteten Klassen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="d8ffc-103">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="d8ffc-104">Dieses Muster wird häufig in Windows Forms-Klassen in der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Klassenbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8ffc-104">This pattern is used extensively in Windows Forms classes in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library.</span></span>  
  
 <span data-ttu-id="d8ffc-105">Wenn Sie eine Klasse erstellen, die als Basisklasse für andere Klassen verwendet werden kann, sollten Sie den Fakt bedenken, dass Ereignisse ein spezieller Typ von Delegaten sind, die nur von innerhalb der Klasse, die sie deklariert hat, aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="d8ffc-105">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="d8ffc-106">Abgeleitete Klassen können nicht direkt Ereignisse aufrufen, die innerhalb der Basisklasse deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="d8ffc-106">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="d8ffc-107">Mitunter kann es zwar erwünscht sein, dass ein Ereignis nur von der Basisklasse ausgelöst werden kann, in den meisten Fällen sollten Sie jedoch der abgeleiteten Klasse das Aufrufen von Basisklassenereignissen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d8ffc-107">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="d8ffc-108">Zu diesem Zweck können Sie eine geschützte aufrufende Methode in der Basisklasse erstellen, die das Ereignis umschließt.</span><span class="sxs-lookup"><span data-stu-id="d8ffc-108">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="d8ffc-109">Durch Aufrufen oder Überschreiben dieser aufrufenden Methode, können abgeleitete Klassen das Ereignis indirekt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d8ffc-109">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8ffc-110">Deklarieren Sie keine virtuellen Ereignisse in einer Basisklasse, und überschreiben Sie sie nicht in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="d8ffc-110">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="d8ffc-111">Der C#-Compiler verarbeitet diese nicht ordnungsgemäß, und es nicht vorhersehbar, ob ein Abonnent des abgeleiteten Ereignisses tatsächlich das Ereignis der Basisklasse abonnieren wird.</span><span class="sxs-lookup"><span data-stu-id="d8ffc-111">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8ffc-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d8ffc-112">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d8ffc-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8ffc-113">See Also</span></span>  
 [<span data-ttu-id="d8ffc-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d8ffc-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d8ffc-115">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d8ffc-115">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="d8ffc-116">Delegaten</span><span class="sxs-lookup"><span data-stu-id="d8ffc-116">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="d8ffc-117">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="d8ffc-117">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="d8ffc-118">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d8ffc-118">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
