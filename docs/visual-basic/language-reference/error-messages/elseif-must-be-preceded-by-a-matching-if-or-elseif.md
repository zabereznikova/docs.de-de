---
title: "\"#ElseIf\" muss ein entsprechendes \"#If\" oder \"#ElseIf\" voranstehen."
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: d6fa76b2aba45e3455cef6ceafc0f737ef56225d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271550"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="399d8-102">"#ElseIf" muss ein entsprechendes "#If" oder "#ElseIf" voranstehen.</span><span class="sxs-lookup"><span data-stu-id="399d8-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>
<span data-ttu-id="399d8-103">`#ElseIf` ist eine Direktive für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="399d8-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="399d8-104">Ein `#ElseIf` Klausel muss ein entsprechendes stehen `#If` oder `#ElseIf` Klausel.</span><span class="sxs-lookup"><span data-stu-id="399d8-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="399d8-105">**Fehler-ID:** BC30014</span><span class="sxs-lookup"><span data-stu-id="399d8-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="399d8-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="399d8-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="399d8-107">Überprüfen Sie, ob eine vorangestellte `#If` oder `#ElseIf` nicht von dieser getrennt wurde `#ElseIf` durch einen dazwischen liegenden Block für die bedingte Kompilierung oder ein falsch platziertes `#End If`.</span><span class="sxs-lookup"><span data-stu-id="399d8-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="399d8-108">Wenn die `#ElseIf` vorangestellt ist eine `#Else` -Direktive, entfernen Sie entweder die `#Else` oder ändern Sie ihn in ein `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="399d8-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="399d8-109">Falls der Code ansonsten in Ordnung ist, fügen Sie am Anfang des Blocks für die bedingte Kompilierung eine `#If` -Direktive hinzu.</span><span class="sxs-lookup"><span data-stu-id="399d8-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399d8-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="399d8-110">See also</span></span>
- [<span data-ttu-id="399d8-111">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="399d8-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
