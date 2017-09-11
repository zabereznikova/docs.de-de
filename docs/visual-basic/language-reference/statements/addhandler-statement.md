---
title: AddHandler-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
dev_langs:
- VB
helpviewer_keywords:
- AddHandler statement
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cd821a568a35f33c722c1631eb7fbaf8f877cf4f
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="addhandler-statement"></a><span data-ttu-id="a6bf7-102">AddHandler-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a6bf7-102">AddHandler Statement</span></span>
<span data-ttu-id="a6bf7-103">Ordnet ein Ereignis zur Laufzeit einen Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6bf7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6bf7-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="a6bf7-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a6bf7-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="a6bf7-106">Der Name des zu behandelnden Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="a6bf7-107">Der Name einer Prozedur, die das Ereignis behandelt.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6bf7-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6bf7-108">Remarks</span></span>  
 <span data-ttu-id="a6bf7-109">Die `AddHandler` und `RemoveHandler` -Anweisungen ermöglichen Ihnen das Starten und Beenden der Ereignisbehandlung zu einem beliebigen Zeitpunkt während der Ausführung des Programms.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="a6bf7-110">Die Signatur der `eventhandler` Verfahren muss der Signatur des Ereignisses entsprechen `event`.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="a6bf7-111">Mit dem Schlüsselwort `Handles` und der Anweisung `AddHandler` können Sie angeben, dass diese bestimmten Prozeduren bestimmte Ereignisse verarbeiten. Es bestehen jedoch keine Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="a6bf7-112">Die Anweisung `AddHandler` verbindet Prozeduren zur Laufzeit mit Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="a6bf7-113">Verwenden Sie das Schlüsselwort `Handles`, wenn Sie eine Prozedur definieren, um anzugeben, dass sie ein bestimmtes Ereignis verarbeitet. </span><span class="sxs-lookup"><span data-stu-id="a6bf7-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="a6bf7-114">Weitere Informationen finden Sie unter [behandelt](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a6bf7-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6bf7-115">Für benutzerdefinierte Ereignisse die `AddHandler` -Anweisung ruft des Ereignis `AddHandler` Accessor.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="a6bf7-116">Weitere Informationen zu benutzerdefinierten Ereignissen finden Sie unter [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a6bf7-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6bf7-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6bf7-117">Example</span></span>  
 <span data-ttu-id="a6bf7-118">[!code-vb[VbVbalrEvents&17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a6bf7-118">[!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6bf7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6bf7-119">See Also</span></span>  
 <span data-ttu-id="a6bf7-120">[RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a6bf7-120">[RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span></span>  
<span data-ttu-id="a6bf7-121"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="a6bf7-121"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="a6bf7-122"> [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a6bf7-122"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="a6bf7-123"> [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="a6bf7-123"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
