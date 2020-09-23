---
title: 'Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: a9350470836652f65532068402c78375b4c5495c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077097"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="6512c-102">Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6512c-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>

<span data-ttu-id="6512c-103">Es gibt mehrere Situationen, in denen es wichtig ist, dass ein Ereignishandler nachfolgende Ereignishandler nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="6512c-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="6512c-104">Benutzerdefinierte Ereignisse ermöglichen es dem Ereignis, seine Ereignishandler asynchron aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6512c-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="6512c-105">Standardmäßig handelt es sich bei dem Feld für den Sicherungs Speicher einer Ereignis Deklaration um einen Multicast Delegat, der alle Ereignishandler serialisiert.</span><span class="sxs-lookup"><span data-stu-id="6512c-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="6512c-106">Dies bedeutet, dass, wenn ein Handler lange Zeit benötigt, die anderen Handler blockiert werden, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6512c-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="6512c-107">(Wohl verhaltene Ereignishandler sollten niemals lange oder potenziell blockierende Vorgänge ausführen.)</span><span class="sxs-lookup"><span data-stu-id="6512c-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="6512c-108">Anstatt die Standard Implementierung von Ereignissen zu verwenden, die Visual Basic bereitstellt, können Sie ein benutzerdefiniertes Ereignis verwenden, um die Ereignishandler asynchron auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6512c-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6512c-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6512c-109">Example</span></span>  

 <span data-ttu-id="6512c-110">In diesem Beispiel fügt der- `AddHandler` Accessor den-Delegaten für jeden `Click` Ereignishandler zu einem <xref:System.Collections.ArrayList> im-Feld gespeicherten hinzu `EventHandlerList` .</span><span class="sxs-lookup"><span data-stu-id="6512c-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="6512c-111">Wenn Code das- `Click` Ereignis auslöst, `RaiseEvent` ruft der-Accessor alle Ereignishandlerdelegaten mithilfe der-Methode asynchron auf <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> .</span><span class="sxs-lookup"><span data-stu-id="6512c-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="6512c-112">Diese Methode ruft jeden Handler auf einem Arbeits Thread auf und gibt sofort zurück, sodass Handler einander nicht blockieren können.</span><span class="sxs-lookup"><span data-stu-id="6512c-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a><span data-ttu-id="6512c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6512c-113">See also</span></span>

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [<span data-ttu-id="6512c-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="6512c-114">Events</span></span>](index.md)
- [<span data-ttu-id="6512c-115">How to: Deklarieren von benutzerdefinierten Ereignissen zum Einsparen von Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="6512c-115">How to: Declare Custom Events To Conserve Memory</span></span>](how-to-declare-custom-events-to-conserve-memory.md)
