---
title: 'Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 3cb66aed71195d2fd2335fbd59cc499b3dbf808e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="8b967-102">Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b967-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="8b967-103">Es gibt mehrere Umstände es ist wichtig, einem Ereignishandler nicht nachfolgenden Ereignishandlern blockiert.</span><span class="sxs-lookup"><span data-stu-id="8b967-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="8b967-104">Benutzerdefinierte Ereignisse ermöglichen das Ereignis, dessen Ereignishandler asynchron aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8b967-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="8b967-105">Standardmäßig wird der Sicherungsspeicher Feld für eine Ereignisdeklaration ein multicast-Delegat, der seriell alle Ereignishandler kombiniert.</span><span class="sxs-lookup"><span data-stu-id="8b967-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="8b967-106">Dies bedeutet, dass wenn ein Ereignishandler eine lange Zeit in Anspruch nimmt, er die anderen Handler blockiert, bis er abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="8b967-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="8b967-107">(Gut konzipierte Ereignishandler sollten niemals langwierige oder potenziell blockierende Vorgänge ausführen.)</span><span class="sxs-lookup"><span data-stu-id="8b967-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="8b967-108">Statt die standardmäßige Implementierung von Ereignissen, die Visual Basic bietet zu verwenden, können Sie ein benutzerdefiniertes Ereignis, der die Ereignishandler asynchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8b967-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b967-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b967-109">Example</span></span>  
 <span data-ttu-id="8b967-110">In diesem Beispiel die `AddHandler` Accessor fügt der Delegat für jeden Handler des der `Click` Ereignis, um eine <xref:System.Collections.ArrayList> gespeichert, der `EventHandlerList` Feld.</span><span class="sxs-lookup"><span data-stu-id="8b967-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="8b967-111">Wenn code löst die `Click` Ereignis, das `RaiseEvent` Accessor Ruft alle Ereignishandlerdelegaten, die asynchron mit der <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="8b967-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="8b967-112">Diese Methode ruft jeden Handler in einem Arbeitsthread und sofort zurückgegeben werden, sodass Handler untereinander blockieren können.</span><span class="sxs-lookup"><span data-stu-id="8b967-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8b967-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b967-113">See Also</span></span>  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [<span data-ttu-id="8b967-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="8b967-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="8b967-115">Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen</span><span class="sxs-lookup"><span data-stu-id="8b967-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
