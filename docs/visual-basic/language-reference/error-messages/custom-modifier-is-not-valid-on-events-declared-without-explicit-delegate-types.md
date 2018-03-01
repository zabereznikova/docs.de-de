---
title: "&#39; Benutzerdefinierte &#39; Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert werden."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 844bd033ea05e373b04a04f80777af77179c1263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="ca511-102">&#39; Benutzerdefinierte &#39; Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="ca511-102">&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="ca511-103">Im Gegensatz zu einem Ereignis nicht benutzerdefinierte eine `Custom Event` Deklaration erfordert eine `As` -Klausel nach dem Ereignisnamen, die explizit den Typ des Delegaten für das Ereignis angibt.</span><span class="sxs-lookup"><span data-stu-id="ca511-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="ca511-104">Nicht benutzerdefinierte Ereignisse kann entweder mit einem `As` -Klausel und einem expliziten Delegattyp oder mit einem Parameter Liste sofort nach dem Ereignisnamen.</span><span class="sxs-lookup"><span data-stu-id="ca511-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="ca511-105">**Fehler-ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="ca511-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ca511-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ca511-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="ca511-107">Definieren Sie einen Delegaten mit derselben Parameterliste, wie das benutzerdefinierte Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ca511-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="ca511-108">Z. B. wenn die `Custom Event` wurde definiert, mit `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, und klicken Sie dann der entsprechende Delegaten Folgendes wäre.</span><span class="sxs-lookup"><span data-stu-id="ca511-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  <span data-ttu-id="ca511-109">Ersetzen Sie die Parameterliste des benutzerdefinierten Ereignisses mit einem `As` -Klausel, die den Typ des Delegaten angibt.</span><span class="sxs-lookup"><span data-stu-id="ca511-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="ca511-110">Fahren Sie mit dem Beispiel `Custom Event` Deklaration würde wie folgt umgeschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ca511-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="ca511-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca511-111">Example</span></span>  
 <span data-ttu-id="ca511-112">Dieses Beispiel deklariert eine `Custom Event` und gibt die erforderliche `As` -Klausel mit einem Delegattyp als Typ.</span><span class="sxs-lookup"><span data-stu-id="ca511-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ca511-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca511-113">See Also</span></span>  
 [<span data-ttu-id="ca511-114">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ca511-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="ca511-115">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ca511-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="ca511-116">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="ca511-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
