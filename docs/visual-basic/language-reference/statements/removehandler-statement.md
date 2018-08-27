---
title: RemoveHandler-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: c1e6ffec64bc01936955a2e94aa9c110b317109f
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925165"
---
# <a name="removehandler-statement"></a><span data-ttu-id="242fc-102">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="242fc-102">RemoveHandler Statement</span></span>
<span data-ttu-id="242fc-103">Entfernt die Zuordnung zwischen einem Ereignis und einen Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="242fc-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="242fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="242fc-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="242fc-105">Teile</span><span class="sxs-lookup"><span data-stu-id="242fc-105">Parts</span></span>  
  
|<span data-ttu-id="242fc-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="242fc-106">Term</span></span>|<span data-ttu-id="242fc-107">Definition</span><span class="sxs-lookup"><span data-stu-id="242fc-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="242fc-108">Der Name des behandelten Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="242fc-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="242fc-109">Der Name der Prozedur zurzeit verarbeitet das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="242fc-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="242fc-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="242fc-110">Remarks</span></span>  
 <span data-ttu-id="242fc-111">Die `AddHandler` und `RemoveHandler` Anweisungen ermöglichen das Starten und Beenden der Ereignisbehandlung für ein bestimmtes Ereignis zu einem beliebigen Zeitpunkt während der programmausführung.</span><span class="sxs-lookup"><span data-stu-id="242fc-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="242fc-112">Für benutzerdefinierte Ereignisse die `RemoveHandler` -Anweisung ruft des Ereignisses `RemoveHandler` Accessor.</span><span class="sxs-lookup"><span data-stu-id="242fc-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="242fc-113">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="242fc-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="242fc-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="242fc-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="242fc-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="242fc-115">See Also</span></span>  
 [<span data-ttu-id="242fc-116">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="242fc-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [<span data-ttu-id="242fc-117">Handles</span><span class="sxs-lookup"><span data-stu-id="242fc-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="242fc-118">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="242fc-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="242fc-119">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="242fc-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
