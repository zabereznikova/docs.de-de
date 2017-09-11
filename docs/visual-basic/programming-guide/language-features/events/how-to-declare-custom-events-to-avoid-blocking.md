---
title: 'Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen zu vermeiden (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declaring events, custom
- events [Visual Basic], custom
- custom events
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
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
ms.openlocfilehash: 52181d1c307e4e312f4511719e540fd6d5bfcfa8
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="429c0-102">Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="429c0-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="429c0-103">Es gibt mehrere Umstände es ist wichtig, einen Ereignishandler nachfolgende Ereignishandler nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="429c0-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="429c0-104">Benutzerdefinierte Ereignisse ermöglichen den zugehörigen Ereignishandler asynchron aufrufen.</span><span class="sxs-lookup"><span data-stu-id="429c0-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="429c0-105">Standardmäßig ist das Feld Sicherungsspeichers für eine Ereignisdeklaration Multicastdelegaten, der nacheinander alle Ereignishandler kombiniert.</span><span class="sxs-lookup"><span data-stu-id="429c0-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="429c0-106">Dies bedeutet, dass wenn ein Ereignishandler eine lange Zeit in Anspruch nimmt, die anderen Handler blockiert, bis er abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="429c0-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="429c0-107">(Gut konzipierte Ereignishandler sollten niemals langwierige oder potenziell blockierende Operationen ausführen.)</span><span class="sxs-lookup"><span data-stu-id="429c0-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="429c0-108">Statt die standardmäßige Implementierung der Ereignisse, die Visual Basic bietet, können Sie ein benutzerdefiniertes Ereignis, der die Ereignishandler asynchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="429c0-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="429c0-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="429c0-109">Example</span></span>  
 <span data-ttu-id="429c0-110">In diesem Beispiel die `AddHandler` Accessor fügt den Delegaten für jeden Handler des der `Click` Ereignis ein <xref:System.Collections.ArrayList>gespeichert, der `EventHandlerList` Feld.</xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="429c0-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="429c0-111">Wenn code löst die `Click` -Ereignis, das `RaiseEvent` Accessor Ruft alle Ereignishandlerdelegaten, die asynchron mit der <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>Methode.</xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span><span class="sxs-lookup"><span data-stu-id="429c0-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="429c0-112">Diese Methode ruft jeden Handler in einem Arbeitsthread und wird sofort beendet, sodass Handler gegenseitig blockieren können.</span><span class="sxs-lookup"><span data-stu-id="429c0-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 <span data-ttu-id="429c0-113">[!code-vb[VbVbalrEvents&#27;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="429c0-113">[!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="429c0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="429c0-114">See Also</span></span>  
 <span data-ttu-id="429c0-115"><xref:System.Collections.ArrayList></xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="429c0-115"><xref:System.Collections.ArrayList></span></span>   
 <span data-ttu-id="429c0-116"><xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span><span class="sxs-lookup"><span data-stu-id="429c0-116"><xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></span></span>   
<span data-ttu-id="429c0-117"> [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="429c0-117"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="429c0-118"> [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)</span><span class="sxs-lookup"><span data-stu-id="429c0-118"> [How to: Declare Custom Events To Conserve Memory](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)</span></span>
