---
title: AddHandler-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: db8131dc82aed40e725c9375efef274fb6917d41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603651"
---
# <a name="addhandler-statement"></a><span data-ttu-id="a22d0-102">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a22d0-102">AddHandler Statement</span></span>
<span data-ttu-id="a22d0-103">Ordnet ein Ereignis mit einem Ereignishandler zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="a22d0-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a22d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a22d0-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="a22d0-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a22d0-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="a22d0-106">Der Name des zu behandelnden Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="a22d0-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="a22d0-107">Der Name einer Prozedur, die das Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="a22d0-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a22d0-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a22d0-108">Remarks</span></span>  
 <span data-ttu-id="a22d0-109">Die `AddHandler` und `RemoveHandler` Anweisungen ermöglichen das Starten und Beenden der Ereignisbehandlung zu einem beliebigen Zeitpunkt während der Ausführung des Programms.</span><span class="sxs-lookup"><span data-stu-id="a22d0-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="a22d0-110">Die Signatur der `eventhandler` Prozedur muss die Signatur des Ereignisses übereinstimmen `event`.</span><span class="sxs-lookup"><span data-stu-id="a22d0-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="a22d0-111">Mit dem Schlüsselwort `Handles` und der Anweisung `AddHandler` können Sie angeben, dass diese bestimmten Prozeduren bestimmte Ereignisse verarbeiten. Es bestehen jedoch keine Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="a22d0-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="a22d0-112">Die Anweisung `AddHandler` verbindet Prozeduren zur Laufzeit mit Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="a22d0-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="a22d0-113">Verwenden Sie das Schlüsselwort `Handles`, wenn Sie eine Prozedur definieren, um anzugeben, dass sie ein bestimmtes Ereignis verarbeitet. </span><span class="sxs-lookup"><span data-stu-id="a22d0-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="a22d0-114">Weitere Informationen finden Sie unter [behandelt](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a22d0-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a22d0-115">Für benutzerdefinierte Ereignisse die `AddHandler` -Anweisung ruft des Ereignis `AddHandler` Accessor.</span><span class="sxs-lookup"><span data-stu-id="a22d0-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="a22d0-116">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a22d0-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a22d0-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a22d0-117">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a22d0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a22d0-118">See Also</span></span>  
 [<span data-ttu-id="a22d0-119">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a22d0-119">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="a22d0-120">Handles</span><span class="sxs-lookup"><span data-stu-id="a22d0-120">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="a22d0-121">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a22d0-121">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="a22d0-122">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a22d0-122">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
