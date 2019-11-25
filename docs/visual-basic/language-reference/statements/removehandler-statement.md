---
title: RemoveHandler-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 177952acf362ccb36a36b5f09b11a1a93dbefa29
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333034"
---
# <a name="removehandler-statement"></a><span data-ttu-id="e5d97-102">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e5d97-102">RemoveHandler Statement</span></span>
<span data-ttu-id="e5d97-103">Removes the association between an event and an event handler.</span><span class="sxs-lookup"><span data-stu-id="e5d97-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5d97-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="e5d97-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e5d97-105">Parts</span></span>  
  
|<span data-ttu-id="e5d97-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="e5d97-106">Term</span></span>|<span data-ttu-id="e5d97-107">Definition</span><span class="sxs-lookup"><span data-stu-id="e5d97-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="e5d97-108">The name of the event being handled.</span><span class="sxs-lookup"><span data-stu-id="e5d97-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="e5d97-109">The name of the procedure currently handling the event.</span><span class="sxs-lookup"><span data-stu-id="e5d97-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5d97-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5d97-110">Remarks</span></span>  
 <span data-ttu-id="e5d97-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span><span class="sxs-lookup"><span data-stu-id="e5d97-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5d97-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span><span class="sxs-lookup"><span data-stu-id="e5d97-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="e5d97-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e5d97-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5d97-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5d97-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="e5d97-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5d97-115">See also</span></span>

- [<span data-ttu-id="e5d97-116">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e5d97-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="e5d97-117">Handles</span><span class="sxs-lookup"><span data-stu-id="e5d97-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="e5d97-118">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e5d97-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="e5d97-119">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="e5d97-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
