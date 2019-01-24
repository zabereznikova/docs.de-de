---
title: Führende &#39;. &#39; oder &#39;! &#39; darf nur innerhalb einer &#39;mit&#39; Anweisung
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: e64318d4ececbd887f55a1a202cc2d58c90c8fc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625951"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a><span data-ttu-id="b47ce-102">Führende &#39;. &#39; oder &#39;! &#39; darf nur innerhalb einer &#39;mit&#39; Anweisung</span><span class="sxs-lookup"><span data-stu-id="b47ce-102">Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement</span></span>
<span data-ttu-id="b47ce-103">Ein Punkt (.) oder ein Ausrufezeichen (!) ist, die nicht innerhalb einer `With` Blockierung tritt auf, ohne einen Ausdruck auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="b47ce-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="b47ce-104">Memberzugriff (`.`) und wörterbuchmemberzugriff (`!`) erfordern einen Ausdruck, der das Element, das den Member enthält.</span><span class="sxs-lookup"><span data-stu-id="b47ce-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="b47ce-105">Dadurch muss sofort angezeigt, auf der linken Seite des Accessors oder als Ziel einer `With` -Block mit den Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="b47ce-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="b47ce-106">**Fehler-ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="b47ce-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b47ce-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b47ce-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="b47ce-108">Sicherstellen, dass die `With` -Block korrekt formatiert.</span><span class="sxs-lookup"><span data-stu-id="b47ce-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="b47ce-109">Es ist keine `With` blockieren, Hinzufügen eines Ausdrucks auf der linken Seite des Accessors, der ausgewertet wird, um ein definiertes Element, das den Member enthält.</span><span class="sxs-lookup"><span data-stu-id="b47ce-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b47ce-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b47ce-110">See also</span></span>
- [<span data-ttu-id="b47ce-111">Sonderzeichen in Code</span><span class="sxs-lookup"><span data-stu-id="b47ce-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="b47ce-112">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b47ce-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
