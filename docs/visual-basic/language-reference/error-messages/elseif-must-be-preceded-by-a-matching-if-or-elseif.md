---
title: "\"#ElseIf\" muss ein entsprechendes \"#If\" oder \"#ElseIf\" voranstehen."
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 808cf35fb05da092cdef560721b2f667778aa78f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409659"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="d273b-102">"#ElseIf" muss ein entsprechendes "#If" oder "#ElseIf" voranstehen.</span><span class="sxs-lookup"><span data-stu-id="d273b-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>
<span data-ttu-id="d273b-103">`#ElseIf` ist eine Direktive für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="d273b-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="d273b-104">Einer- `#ElseIf` Klausel muss eine entsprechende-oder-Klausel vorangestellt sein `#If` `#ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="d273b-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="d273b-105">**Fehler-ID:** BC30014</span><span class="sxs-lookup"><span data-stu-id="d273b-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d273b-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d273b-106">To correct this error</span></span>  
  
1. <span data-ttu-id="d273b-107">Überprüfen Sie, ob eine vorhergehende `#If` oder `#ElseIf` nicht `#ElseIf` durch einen dazwischen liegenden bedingten Kompilierungs Block oder ein falsch platziertes von diesem getrennt wurde `#End If` .</span><span class="sxs-lookup"><span data-stu-id="d273b-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2. <span data-ttu-id="d273b-108">Wenn dem `#ElseIf` eine-Direktive vorangestellt ist `#Else` , entfernen Sie entweder das, `#Else` oder ändern Sie es in ein `#ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="d273b-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3. <span data-ttu-id="d273b-109">Falls der Code ansonsten in Ordnung ist, fügen Sie am Anfang des Blocks für die bedingte Kompilierung eine `#If` -Direktive hinzu.</span><span class="sxs-lookup"><span data-stu-id="d273b-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d273b-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d273b-110">See also</span></span>

- [<span data-ttu-id="d273b-111">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="d273b-111">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
