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
ms.openlocfilehash: 47f35bd76d7734878e7b5b206b4aecd856276593
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582019"
---
# <a name="removehandler-statement"></a><span data-ttu-id="e8fd1-102">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e8fd1-102">RemoveHandler Statement</span></span>
<span data-ttu-id="e8fd1-103">Entfernt die Zuordnung zwischen einem Ereignis und einem Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="e8fd1-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8fd1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8fd1-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="e8fd1-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e8fd1-105">Parts</span></span>  
  
|<span data-ttu-id="e8fd1-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="e8fd1-106">Term</span></span>|<span data-ttu-id="e8fd1-107">Definition</span><span class="sxs-lookup"><span data-stu-id="e8fd1-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="e8fd1-108">Der Name des behandelten Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="e8fd1-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="e8fd1-109">Der Name der Prozedur, die das Ereignis momentan behandelt.</span><span class="sxs-lookup"><span data-stu-id="e8fd1-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8fd1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8fd1-110">Remarks</span></span>  
 <span data-ttu-id="e8fd1-111">Die Anweisungen `AddHandler` und `RemoveHandler` ermöglichen das Starten und Abbrechen der Ereignis Behandlung für ein bestimmtes Ereignis während der Programmausführung.</span><span class="sxs-lookup"><span data-stu-id="e8fd1-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8fd1-112">Für benutzerdefinierte Ereignisse ruft die `RemoveHandler`-Anweisung den `RemoveHandler` Accessor des Ereignisses auf.</span><span class="sxs-lookup"><span data-stu-id="e8fd1-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="e8fd1-113">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e8fd1-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8fd1-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8fd1-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="e8fd1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8fd1-115">See also</span></span>

- [<span data-ttu-id="e8fd1-116">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e8fd1-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="e8fd1-117">Handles</span><span class="sxs-lookup"><span data-stu-id="e8fd1-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="e8fd1-118">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e8fd1-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="e8fd1-119">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="e8fd1-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
