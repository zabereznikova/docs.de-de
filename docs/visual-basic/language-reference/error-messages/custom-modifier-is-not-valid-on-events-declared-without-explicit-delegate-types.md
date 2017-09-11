---
title: "Der Custom-Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
dev_langs:
- VB
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
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
ms.openlocfilehash: 449e5a690f06ce35d1ccc799daf5f2c1ad1c6dac
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="b5c52-102">Der Custom-Modifizierer ist nicht gültig für Ereignisse, die ohne expliziten Delegattyp deklariert</span><span class="sxs-lookup"><span data-stu-id="b5c52-102">&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="b5c52-103">Im Gegensatz zu einem Ereignis nicht benutzerdefiniert eine `Custom Event` Deklaration erfordert eine `As` -Klausel nach dem Ereignisnamen, die Typ des Delegaten für das Ereignis explizit angibt.</span><span class="sxs-lookup"><span data-stu-id="b5c52-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="b5c52-104">Nicht benutzerdefinierte Ereignisse kann entweder mit einem `As` -Klausel und einem expliziten Delegattyp oder mit einem Parameter Liste sofort nach dem Ereignisnamen.</span><span class="sxs-lookup"><span data-stu-id="b5c52-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="b5c52-105">**Fehler-ID:** BC31122</span><span class="sxs-lookup"><span data-stu-id="b5c52-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b5c52-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b5c52-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b5c52-107">Definieren Sie einen Delegaten mit einer Parameterliste, wie das benutzerdefinierte Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b5c52-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="b5c52-108">Zum Beispiel wenn die `Custom Event` definiert wurde `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, und klicken Sie dann der entsprechende Delegaten würde folgendermaßen lauten.</span><span class="sxs-lookup"><span data-stu-id="b5c52-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     <span data-ttu-id="b5c52-109">[!code-vb[VbVbalrEventError&18;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b5c52-109">[!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]</span></span>  
  
2.  <span data-ttu-id="b5c52-110">Ersetzen Sie die Parameterliste des benutzerdefinierten Ereignisses durch eine `As` -Klausel, die dem Typ des Delegaten angibt.</span><span class="sxs-lookup"><span data-stu-id="b5c52-110">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="b5c52-111">Ausgehend vom Beispiel `Custom Event` Deklaration wie folgt umgeschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5c52-111">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     <span data-ttu-id="b5c52-112">[!code-vb[VbVbalrEventError Nr.&19;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b5c52-112">[!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5c52-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5c52-113">Example</span></span>  
 <span data-ttu-id="b5c52-114">Dieses Beispiel deklariert eine `Custom Event` und die erforderliche `As` -Klausel mit einem Delegattyp angegeben.</span><span class="sxs-lookup"><span data-stu-id="b5c52-114">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 <span data-ttu-id="b5c52-115">[!code-vb[VbVbalrEventError&#2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b5c52-115">[!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5c52-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5c52-116">See Also</span></span>  
 <span data-ttu-id="b5c52-117">[Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b5c52-117">[Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="b5c52-118"> [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b5c52-118"> [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="b5c52-119"> [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="b5c52-119"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
