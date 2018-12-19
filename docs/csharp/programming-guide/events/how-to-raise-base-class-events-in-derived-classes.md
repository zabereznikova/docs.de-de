---
title: 'Vorgehensweise: Auslösen von Basisklassenereignissen in abgeleiteten Klassen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: 11f34e230a1f953ba3d886e416f1ece4253e3c8d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239617"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="d03e1-102">Vorgehensweise: Auslösen von Basisklassenereignissen in abgeleiteten Klassen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d03e1-102">How to: Raise Base Class Events in Derived Classes (C# Programming Guide)</span></span>
<span data-ttu-id="d03e1-103">Das folgende einfache Beispiel zeigt das Standardverfahren zum Deklarieren von Ereignissen in einer Basisklasse, sodass sie auch von abgeleiteten Klassen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="d03e1-103">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="d03e1-104">Dieses Muster wird häufig in Windows Forms-Klassen in der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Klassenbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="d03e1-104">This pattern is used extensively in Windows Forms classes in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library.</span></span>  
  
 <span data-ttu-id="d03e1-105">Wenn Sie eine Klasse erstellen, die als Basisklasse für andere Klassen verwendet werden kann, sollten Sie den Fakt bedenken, dass Ereignisse ein spezieller Typ von Delegaten sind, die nur von innerhalb der Klasse, die sie deklariert hat, aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="d03e1-105">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="d03e1-106">Abgeleitete Klassen können nicht direkt Ereignisse aufrufen, die innerhalb der Basisklasse deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="d03e1-106">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="d03e1-107">Mitunter kann es zwar erwünscht sein, dass ein Ereignis nur von der Basisklasse ausgelöst werden kann, in den meisten Fällen sollten Sie jedoch der abgeleiteten Klasse das Aufrufen von Basisklassenereignissen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d03e1-107">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="d03e1-108">Zu diesem Zweck können Sie eine geschützte aufrufende Methode in der Basisklasse erstellen, die das Ereignis umschließt.</span><span class="sxs-lookup"><span data-stu-id="d03e1-108">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="d03e1-109">Durch Aufrufen oder Überschreiben dieser aufrufenden Methode, können abgeleitete Klassen das Ereignis indirekt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d03e1-109">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d03e1-110">Deklarieren Sie keine virtuellen Ereignisse in einer Basisklasse, und überschreiben Sie sie nicht in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="d03e1-110">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="d03e1-111">Der C#-Compiler verarbeitet diese nicht ordnungsgemäß, und es nicht vorhersehbar, ob ein Abonnent des abgeleiteten Ereignisses tatsächlich das Ereignis der Basisklasse abonnieren wird.</span><span class="sxs-lookup"><span data-stu-id="d03e1-111">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d03e1-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d03e1-112">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d03e1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d03e1-113">See Also</span></span>

- [<span data-ttu-id="d03e1-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d03e1-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d03e1-115">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d03e1-115">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="d03e1-116">Delegaten</span><span class="sxs-lookup"><span data-stu-id="d03e1-116">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="d03e1-117">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="d03e1-117">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [<span data-ttu-id="d03e1-118">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d03e1-118">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
