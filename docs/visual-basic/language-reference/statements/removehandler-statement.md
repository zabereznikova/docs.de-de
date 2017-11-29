---
title: RemoveHandler-Anweisung
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 82d130c6536df7d72977a028333293b4e0ee89de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="removehandler-statement"></a><span data-ttu-id="b4cb2-102">RemoveHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b4cb2-102">RemoveHandler Statement</span></span>
<span data-ttu-id="b4cb2-103">Entfernt die Zuordnung zwischen einem Ereignis und einen Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="b4cb2-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4cb2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4cb2-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="b4cb2-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b4cb2-105">Parts</span></span>  
  
|<span data-ttu-id="b4cb2-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="b4cb2-106">Term</span></span>|<span data-ttu-id="b4cb2-107">Definition</span><span class="sxs-lookup"><span data-stu-id="b4cb2-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="b4cb2-108">Der Name des Ereignisses verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="b4cb2-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="b4cb2-109">Der Name der Prozedur, die derzeit Behandlung des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="b4cb2-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4cb2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4cb2-110">Remarks</span></span>  
 <span data-ttu-id="b4cb2-111">Die `AddHandler` und `RemoveHandler` Anweisungen ermöglichen das Starten und Beenden der Ereignisbehandlung für ein bestimmtes Ereignis zu einem beliebigen Zeitpunkt während der Ausführung des Programms.</span><span class="sxs-lookup"><span data-stu-id="b4cb2-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4cb2-112">Für benutzerdefinierte Ereignisse die `RemoveHandler` -Anweisung ruft des Ereignis `RemoveHandler` Accessor.</span><span class="sxs-lookup"><span data-stu-id="b4cb2-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="b4cb2-113">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b4cb2-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4cb2-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4cb2-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b4cb2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4cb2-115">See Also</span></span>  
 [<span data-ttu-id="b4cb2-116">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b4cb2-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [<span data-ttu-id="b4cb2-117">Handles</span><span class="sxs-lookup"><span data-stu-id="b4cb2-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="b4cb2-118">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b4cb2-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="b4cb2-119">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b4cb2-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
