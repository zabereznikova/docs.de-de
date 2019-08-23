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
ms.openlocfilehash: 3a839a7d05d05066f6c0f774a683c8fc83c19643
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957725"
---
# <a name="removehandler-statement"></a><span data-ttu-id="0f931-102">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f931-102">RemoveHandler Statement</span></span>
<span data-ttu-id="0f931-103">Entfernt die Zuordnung zwischen einem Ereignis und einem Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="0f931-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f931-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f931-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="0f931-105">Teile</span><span class="sxs-lookup"><span data-stu-id="0f931-105">Parts</span></span>  
  
|<span data-ttu-id="0f931-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="0f931-106">Term</span></span>|<span data-ttu-id="0f931-107">Definition</span><span class="sxs-lookup"><span data-stu-id="0f931-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="0f931-108">Der Name des behandelten Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="0f931-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="0f931-109">Der Name der Prozedur, die das Ereignis momentan behandelt.</span><span class="sxs-lookup"><span data-stu-id="0f931-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f931-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f931-110">Remarks</span></span>  
 <span data-ttu-id="0f931-111">Mit `AddHandler` der `RemoveHandler` -Anweisung und der-Anweisung können Sie die Ereignis Behandlung für ein bestimmtes Ereignis zu einem beliebigen Zeitpunkt während der Programmausführung starten und Abbrechen.</span><span class="sxs-lookup"><span data-stu-id="0f931-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f931-112">Für benutzerdefinierte Ereignisse ruft `RemoveHandler` die-Anweisung den- `RemoveHandler` Accessor des Ereignisses auf.</span><span class="sxs-lookup"><span data-stu-id="0f931-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="0f931-113">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0f931-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f931-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f931-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="0f931-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f931-115">See also</span></span>

- [<span data-ttu-id="0f931-116">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f931-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="0f931-117">Handles</span><span class="sxs-lookup"><span data-stu-id="0f931-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="0f931-118">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f931-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="0f931-119">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="0f931-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
