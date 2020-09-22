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
ms.openlocfilehash: a815241f20be12b3b7b4f2b87d50a8965021bbf0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871936"
---
# <a name="removehandler-statement"></a><span data-ttu-id="76520-102">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="76520-102">RemoveHandler Statement</span></span>

<span data-ttu-id="76520-103">Entfernt die Zuordnung zwischen einem Ereignis und einem Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="76520-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76520-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="76520-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="76520-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="76520-105">Parts</span></span>  
  
|<span data-ttu-id="76520-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="76520-106">Term</span></span>|<span data-ttu-id="76520-107">Definition</span><span class="sxs-lookup"><span data-stu-id="76520-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="76520-108">Der Name des behandelten Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="76520-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="76520-109">Der Name der Prozedur, die das Ereignis momentan behandelt.</span><span class="sxs-lookup"><span data-stu-id="76520-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76520-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="76520-110">Remarks</span></span>  

 <span data-ttu-id="76520-111">Mit der `AddHandler` -Anweisung und der- `RemoveHandler` Anweisung können Sie die Ereignis Behandlung für ein bestimmtes Ereignis zu einem beliebigen Zeitpunkt während der Programmausführung starten und Abbrechen.</span><span class="sxs-lookup"><span data-stu-id="76520-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76520-112">Für benutzerdefinierte Ereignisse `RemoveHandler` Ruft die-Anweisung den- `RemoveHandler` Accessor des Ereignisses auf.</span><span class="sxs-lookup"><span data-stu-id="76520-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="76520-113">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="76520-113">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76520-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76520-114">Example</span></span>  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="76520-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76520-115">See also</span></span>

- [<span data-ttu-id="76520-116">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="76520-116">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="76520-117">Ziehpunkte</span><span class="sxs-lookup"><span data-stu-id="76520-117">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="76520-118">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="76520-118">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="76520-119">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="76520-119">Events</span></span>](../../programming-guide/language-features/events/index.md)
