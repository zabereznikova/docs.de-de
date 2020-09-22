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
ms.openlocfilehash: 79dbe174209e91f13f5b43e8cdeb0b42edc4d163
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866708"
---
# <a name="addhandler-statement"></a><span data-ttu-id="687f2-102">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="687f2-102">AddHandler Statement</span></span>

<span data-ttu-id="687f2-103">Ordnet ein Ereignis einem Ereignishandler zur Laufzeit zu.</span><span class="sxs-lookup"><span data-stu-id="687f2-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="687f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="687f2-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="687f2-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="687f2-105">Parts</span></span>  

|||
|---|---|
|<span data-ttu-id="687f2-106">event</span><span class="sxs-lookup"><span data-stu-id="687f2-106">event</span></span>|<span data-ttu-id="687f2-107">Der Name des zu behandelnden Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="687f2-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="687f2-108">Der Name einer Prozedur, die das Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="687f2-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="687f2-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="687f2-109">Remarks</span></span>  

 <span data-ttu-id="687f2-110">Mit der `AddHandler` -Anweisung und der- `RemoveHandler` Anweisung können Sie die Ereignis Behandlung jederzeit während der Programmausführung starten und Abbrechen.</span><span class="sxs-lookup"><span data-stu-id="687f2-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="687f2-111">Die Signatur der `eventhandler` Prozedur muss mit der Signatur des Ereignisses identisch sein `event` .</span><span class="sxs-lookup"><span data-stu-id="687f2-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="687f2-112">Mit dem Schlüsselwort `Handles` und der Anweisung `AddHandler` können Sie angeben, dass diese bestimmten Prozeduren bestimmte Ereignisse verarbeiten. Es bestehen jedoch keine Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="687f2-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="687f2-113">Die Anweisung `AddHandler` verbindet Prozeduren zur Laufzeit mit Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="687f2-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="687f2-114">Verwenden Sie das Schlüsselwort `Handles`, wenn Sie eine Prozedur definieren, um anzugeben, dass sie ein bestimmtes Ereignis verarbeitet. </span><span class="sxs-lookup"><span data-stu-id="687f2-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="687f2-115">Weitere Informationen finden Sie unter [Handles](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="687f2-115">For more information, see [Handles](handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="687f2-116">Für benutzerdefinierte Ereignisse `AddHandler` Ruft die-Anweisung den- `AddHandler` Accessor des Ereignisses auf.</span><span class="sxs-lookup"><span data-stu-id="687f2-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="687f2-117">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="687f2-117">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="687f2-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="687f2-118">Example</span></span>  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="687f2-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="687f2-119">See also</span></span>

- [<span data-ttu-id="687f2-120">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="687f2-120">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="687f2-121">Ziehpunkte</span><span class="sxs-lookup"><span data-stu-id="687f2-121">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="687f2-122">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="687f2-122">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="687f2-123">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="687f2-123">Events</span></span>](../../programming-guide/language-features/events/index.md)
