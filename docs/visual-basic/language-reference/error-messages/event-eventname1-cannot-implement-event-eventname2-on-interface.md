---
title: Das "<eventname1>"-Ereignis kann das "<eventname2>"-Ereignis für die "<interface>"-Schnittstelle nicht implementieren, da die entsprechenden Delegattypen "<delegate1>" und "<delegate2>" nicht übereinstimmen.
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: b1e0728a4f865b432b142df4ded1efddb376201e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874334"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a><span data-ttu-id="22839-102">Das "\<eventname1>"-Ereignis kann das "\<eventname2>"-Ereignis für die "\<interface>"-Schnittstelle nicht implementieren, da die entsprechenden Delegattypen "\<delegate1>" und "\<delegate2>" nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="22839-102">Event '\<eventname1>' cannot implement event '\<eventname2>' on interface '\<interface>' because their delegate types '\<delegate1>' and '\<delegate2>' do not match</span></span>

<span data-ttu-id="22839-103">Visual Basic kann kein Ereignis implementieren, da der Delegattyp des Ereignisses nicht mit dem Delegattyp des Ereignisses in der Schnittstelle identisch ist.</span><span class="sxs-lookup"><span data-stu-id="22839-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="22839-104">Dieser Fehler kann auftreten, wenn Sie mehrere Ereignisse in einer Schnittstelle definieren und anschließend versuchen, sie mit demselben Ereignis zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="22839-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="22839-105">Ein Ereignis kann zwei oder mehrere Ereignisse nur implementieren, wenn alle implementierten Ereignisse mit der `As` -Syntax deklariert werden und denselben Delegattyp angeben.</span><span class="sxs-lookup"><span data-stu-id="22839-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="22839-106">**Fehler-ID:** BC31423</span><span class="sxs-lookup"><span data-stu-id="22839-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="22839-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="22839-107">To correct this error</span></span>  
  
- <span data-ttu-id="22839-108">Implementieren Sie die Ereignisse separat.</span><span class="sxs-lookup"><span data-stu-id="22839-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="22839-109">– oder –</span><span class="sxs-lookup"><span data-stu-id="22839-109">—or—</span></span>  
  
- <span data-ttu-id="22839-110">Definieren Sie die Ereignisse in der Schnittstelle mithilfe der `As` -Syntax, und geben Sie den gleichen Delegattyp an.</span><span class="sxs-lookup"><span data-stu-id="22839-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22839-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22839-111">See also</span></span>

- [<span data-ttu-id="22839-112">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="22839-112">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="22839-113">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="22839-113">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="22839-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="22839-114">Events</span></span>](../../programming-guide/language-features/events/index.md)
