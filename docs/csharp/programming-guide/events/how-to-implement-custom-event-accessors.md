---
title: 'Vorgehensweise: Implementieren benutzerdefinierter Ereignisaccessoren (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie benutzerdefinierte Ereignisaccessoren implementieren. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 4094aa1fedbceb68790b484608b3ea0ebc1e5cf6
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302138"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="439b2-104">Vorgehensweise: Implementieren benutzerdefinierter Ereignisaccessoren (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="439b2-104">How to implement custom event accessors (C# Programming Guide)</span></span>
<span data-ttu-id="439b2-105">Ein Ereignis ist eine besondere Art eines Multitaskdelegaten, der nur aus der Klasse , in der er deklariert ist, aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="439b2-105">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="439b2-106">Der Client abonniert das Ereignis durch Bereitstellen eines Verweises auf eine Methode, die aufgerufen werden soll, wenn das Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="439b2-106">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="439b2-107">Diese Methoden werden der Aufrufliste des Delegaten über Ereignisaccessoren hinzugefügt, die Eigenschaftenaccessoren ähneln, mit der Ausnahme, dass Ereignisaccessoren mit `add` und `remove` bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="439b2-107">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="439b2-108">In den meisten Fällen müssen Sie keine benutzerdefinierten Ereignisaccessoren angeben.</span><span class="sxs-lookup"><span data-stu-id="439b2-108">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="439b2-109">Wenn keine benutzerdefinierten Ereignisaccessoren im Code angegeben werden, werden sie durch den Compiler automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="439b2-109">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="439b2-110">In einigen Fällen müssen Sie möglicherweise jedoch benutzerdefiniertes Verhalten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="439b2-110">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="439b2-111">Einen solchen Fall enthält das Thema [Vorgehensweise: Implementieren von Schnittstellenereignissen](./how-to-implement-interface-events.md).</span><span class="sxs-lookup"><span data-stu-id="439b2-111">One such case is shown in the topic [How to implement interface events](./how-to-implement-interface-events.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="439b2-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="439b2-112">Example</span></span>  
 <span data-ttu-id="439b2-113">Das folgende Beispiel veranschaulicht das Implementieren von Ereignisaccessoren zum Hinzufügen und Entfernen.</span><span class="sxs-lookup"><span data-stu-id="439b2-113">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="439b2-114">Obwohl Sie Code innerhalb der Accessoren ersetzen können, wird empfohlen, dass Sie das Ereignis sperren, bevor Sie eine neue Ereignishandlermethode hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="439b2-114">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
[!code-csharp[IDrawingObject.OnDraw](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a><span data-ttu-id="439b2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="439b2-115">See also</span></span>

- [<span data-ttu-id="439b2-116">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="439b2-116">Events</span></span>](./index.md)
- [<span data-ttu-id="439b2-117">event</span><span class="sxs-lookup"><span data-stu-id="439b2-117">event</span></span>](../../language-reference/keywords/event.md)
