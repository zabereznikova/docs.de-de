---
title: Der Custom-Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert wurden.
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 169cb49cc5abc76b7c52785392d0083b81a99450
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300943"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="92fa5-102">Der Custom-Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="92fa5-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="92fa5-103">Im Gegensatz zu einem nicht-Custom-Ereignis eine `Custom Event` erfordert, dass ein `As` hinter den Ereignisnamen, die explizit den Typ des Delegaten für das Ereignis angibt.</span><span class="sxs-lookup"><span data-stu-id="92fa5-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="92fa5-104">Nicht benutzerdefinierte Ereignisse können werden entweder mit einer `As` -Klausel einen expliziten Delegattyp und mit einem Parameter Liste sofort nach dem Ereignisnamen.</span><span class="sxs-lookup"><span data-stu-id="92fa5-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="92fa5-105">**Fehler-ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="92fa5-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="92fa5-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="92fa5-106">To correct this error</span></span>  
  
1. <span data-ttu-id="92fa5-107">Definieren Sie einen Delegaten mit derselben Parameterliste als das benutzerdefinierte Ereignis.</span><span class="sxs-lookup"><span data-stu-id="92fa5-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="92fa5-108">Z. B. wenn die `Custom Event` definiert wurde `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, und klicken Sie dann der entsprechende Delegaten würde folgendermaßen lauten.</span><span class="sxs-lookup"><span data-stu-id="92fa5-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. <span data-ttu-id="92fa5-109">Ersetzen Sie die Parameterliste des benutzerdefinierten Ereignisses mit einem `As` -Klausel, die den Delegattyp angibt.</span><span class="sxs-lookup"><span data-stu-id="92fa5-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="92fa5-110">Im Beispiel, `Custom Event` Deklaration würde wie folgt umgeschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="92fa5-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="92fa5-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92fa5-111">Example</span></span>  
 <span data-ttu-id="92fa5-112">Das folgende Beispiel deklariert eine `Custom Event` und die erforderliche `As` -Klausel mit einen Delegattyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="92fa5-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="92fa5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92fa5-113">See also</span></span>

- [<span data-ttu-id="92fa5-114">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="92fa5-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="92fa5-115">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="92fa5-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="92fa5-116">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="92fa5-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
