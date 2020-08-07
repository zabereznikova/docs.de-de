---
title: 'Vorgehensweise: Auslösen von Basisklassenereignissen in abgeleiteten Klassen (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie Basisklassenereignisse in abgeleiteten Klassen auslösen. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: b0b0a16a1fd165e437fc79ccacb20d406f5cff63
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302099"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="ef871-104">Vorgehensweise: Auslösen von Basisklassenereignissen in abgeleiteten Klassen (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="ef871-104">How to raise base class events in derived classes (C# Programming Guide)</span></span>
<span data-ttu-id="ef871-105">Das folgende einfache Beispiel zeigt das Standardverfahren zum Deklarieren von Ereignissen in einer Basisklasse, sodass sie auch von abgeleiteten Klassen ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="ef871-105">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="ef871-106">Dieses Muster wird häufig in Windows Forms-Klassen in .NET-Klassenbibliotheken verwendet.</span><span class="sxs-lookup"><span data-stu-id="ef871-106">This pattern is used extensively in Windows Forms classes in the .NET class libraries.</span></span>  
  
 <span data-ttu-id="ef871-107">Wenn Sie eine Klasse erstellen, die als Basisklasse für andere Klassen verwendet werden kann, sollten Sie den Fakt bedenken, dass Ereignisse ein spezieller Typ von Delegaten sind, die nur von innerhalb der Klasse, die sie deklariert hat, aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="ef871-107">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="ef871-108">Abgeleitete Klassen können nicht direkt Ereignisse aufrufen, die innerhalb der Basisklasse deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="ef871-108">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="ef871-109">Mitunter kann es zwar erwünscht sein, dass ein Ereignis nur von der Basisklasse ausgelöst werden kann, in den meisten Fällen sollten Sie jedoch der abgeleiteten Klasse das Aufrufen von Basisklassenereignissen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ef871-109">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="ef871-110">Zu diesem Zweck können Sie eine geschützte aufrufende Methode in der Basisklasse erstellen, die das Ereignis umschließt.</span><span class="sxs-lookup"><span data-stu-id="ef871-110">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="ef871-111">Durch Aufrufen oder Überschreiben dieser aufrufenden Methode, können abgeleitete Klassen das Ereignis indirekt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ef871-111">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef871-112">Deklarieren Sie keine virtuellen Ereignisse in einer Basisklasse, und überschreiben Sie sie nicht in einer abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="ef871-112">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="ef871-113">Der C#-Compiler verarbeitet diese nicht ordnungsgemäß, und es nicht vorhersehbar, ob ein Abonnent des abgeleiteten Ereignisses tatsächlich das Ereignis der Basisklasse abonnieren wird.</span><span class="sxs-lookup"><span data-stu-id="ef871-113">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef871-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef871-114">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ef871-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef871-115">See also</span></span>

- [<span data-ttu-id="ef871-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ef871-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ef871-117">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="ef871-117">Events</span></span>](./index.md)
- [<span data-ttu-id="ef871-118">Delegaten</span><span class="sxs-lookup"><span data-stu-id="ef871-118">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="ef871-119">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="ef871-119">Access Modifiers</span></span>](../classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="ef871-120">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef871-120">Creating Event Handlers in Windows Forms</span></span>](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
