---
title: 'Gewusst wie: Implementieren benutzerdefinierter Ereigniszugriffsmethoden (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c27becec6b5d298c31198fe9470a65baa32e32bf
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="20243-102">Gewusst wie: Implementieren benutzerdefinierter Ereigniszugriffsmethoden (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="20243-102">How to: Implement Custom Event Accessors (C# Programming Guide)</span></span>
<span data-ttu-id="20243-103">Ein Ereignis ist eine besondere Art eines Multitaskdelegaten, der nur aus der Klasse , in der er deklariert ist, aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="20243-103">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="20243-104">Der Client abonniert das Ereignis durch Bereitstellen eines Verweises auf eine Methode, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="20243-104">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="20243-105">Diese Methoden werden der Aufrufliste des Delegaten über Ereignisaccessoren hinzugefügt, die Eigenschaftenaccessoren ähneln, mit der Ausnahme, dass Ereignisaccessoren mit `add` und `remove` bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="20243-105">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="20243-106">In den meisten Fällen müssen Sie keine benutzerdefinierten Ereignisaccessoren angeben.</span><span class="sxs-lookup"><span data-stu-id="20243-106">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="20243-107">Wenn keine benutzerdefinierten Ereignisaccessoren im Code angegeben werden, werden sie durch den Compiler automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="20243-107">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="20243-108">In einigen Fällen müssen Sie möglicherweise jedoch benutzerdefiniertes Verhalten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="20243-108">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="20243-109">Einen solchen Fall enthält das Thema [Vorgehensweise: Implementieren von Schnittstellenereignissen](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span><span class="sxs-lookup"><span data-stu-id="20243-109">One such case is shown in the topic [How to:  Implement Interface Events](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="20243-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20243-110">Example</span></span>  
 <span data-ttu-id="20243-111">Das folgende Beispiel veranschaulicht das Implementieren von Ereignisaccessoren zum Hinzufügen und Entfernen.</span><span class="sxs-lookup"><span data-stu-id="20243-111">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="20243-112">Obwohl Sie Code innerhalb der Accessoren ersetzen können, wird empfohlen, dass Sie das Ereignis sperren, bevor Sie eine neue Ereignishandlermethode hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="20243-112">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
```csharp
event EventHandler IDrawingObject.OnDraw  
{  
    add  
    {  
        lock (PreDrawEvent)  
        {  
            PreDrawEvent += value;  
        }  
    }  
    remove  
    {  
        lock (PreDrawEvent)  
        {  
            PreDrawEvent -= value;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="20243-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20243-113">See Also</span></span>  
 [<span data-ttu-id="20243-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="20243-114">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="20243-115">event</span><span class="sxs-lookup"><span data-stu-id="20243-115">event</span></span>](../../../csharp/language-reference/keywords/event.md)