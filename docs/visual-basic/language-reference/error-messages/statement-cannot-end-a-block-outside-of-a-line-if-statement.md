---
title: Anweisung darf nicht mit einen-Block außerhalb einer Zeile enden &#39;Wenn&#39; Anweisung
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 78fe136acbd09e202b1daeb16dd540cf42ada390
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574715"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a><span data-ttu-id="322c7-102">Anweisung darf nicht mit einen-Block außerhalb einer Zeile enden &#39;Wenn&#39; Anweisung</span><span class="sxs-lookup"><span data-stu-id="322c7-102">Statement cannot end a block outside of a line &#39;If&#39; statement</span></span>
<span data-ttu-id="322c7-103">Einem einzeiligen `If` -Anweisung enthält mehrere Anweisungen, getrennt durch Doppelpunkte (:), von denen eine `End` -Anweisung für einen Kontrollblock außerhalb der einzeiligen `If`.</span><span class="sxs-lookup"><span data-stu-id="322c7-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="322c7-104">Einzeilige `If` Anweisungen verwenden Sie nicht die `End If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="322c7-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="322c7-105">**Fehler-ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="322c7-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="322c7-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="322c7-106">To correct this error</span></span>  
  
-   <span data-ttu-id="322c7-107">Verschieben der einzeilige `If` Anweisung außerhalb der Kontrollblock mit der `End If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="322c7-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="322c7-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="322c7-108">See also</span></span>
- [<span data-ttu-id="322c7-109">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="322c7-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
