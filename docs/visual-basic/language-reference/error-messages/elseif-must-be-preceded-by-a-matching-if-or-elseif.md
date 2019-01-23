---
title: '&#39;#ElseIf&#39; muss durch eine entsprechende stehen &#39;#If&#39; oder &#39;#ElseIf&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 1e63595ee573e9356f6870a02b2131897c725baf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505782"
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a><span data-ttu-id="bbefb-102">&#39;#ElseIf&#39; muss durch eine entsprechende stehen &#39;#If&#39; oder &#39;#ElseIf&#39;</span><span class="sxs-lookup"><span data-stu-id="bbefb-102">&#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39;</span></span>
<span data-ttu-id="bbefb-103">`#ElseIf` ist eine Direktive für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="bbefb-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="bbefb-104">Ein `#ElseIf` Klausel muss ein entsprechendes stehen `#If` oder `#ElseIf` Klausel.</span><span class="sxs-lookup"><span data-stu-id="bbefb-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="bbefb-105">**Fehler-ID:** BC30014</span><span class="sxs-lookup"><span data-stu-id="bbefb-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bbefb-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="bbefb-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="bbefb-107">Überprüfen Sie, ob eine vorangestellte `#If` oder `#ElseIf` nicht von dieser getrennt wurde `#ElseIf` durch einen dazwischen liegenden Block für die bedingte Kompilierung oder ein falsch platziertes `#End If`.</span><span class="sxs-lookup"><span data-stu-id="bbefb-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="bbefb-108">Wenn die `#ElseIf` vorangestellt ist eine `#Else` -Direktive, entfernen Sie entweder die `#Else` oder ändern Sie ihn in ein `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="bbefb-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="bbefb-109">Falls der Code ansonsten in Ordnung ist, fügen Sie am Anfang des Blocks für die bedingte Kompilierung eine `#If` -Direktive hinzu.</span><span class="sxs-lookup"><span data-stu-id="bbefb-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbefb-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbefb-110">See also</span></span>
- [<span data-ttu-id="bbefb-111">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="bbefb-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
