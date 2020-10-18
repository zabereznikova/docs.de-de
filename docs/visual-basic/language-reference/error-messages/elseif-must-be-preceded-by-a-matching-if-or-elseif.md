---
title: "\"#ElseIf\" muss ein entsprechendes \"#If\" oder \"#ElseIf\" voranstehen."
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 142c142afe0d9be0ecd4d8a0340f0f1957b20470
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162777"
---
# <a name="bc30014-elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="bd6c7-102">BC30014: ' #ElseIf ' muss ein entsprechendes ' #If ' oder ' #ElseIf ' vorangestellt sein.</span><span class="sxs-lookup"><span data-stu-id="bd6c7-102">BC30014: '#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>

<span data-ttu-id="bd6c7-103">`#ElseIf` ist eine Direktive für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="bd6c7-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="bd6c7-104">Einer- `#ElseIf` Klausel muss eine entsprechende-oder-Klausel vorangestellt sein `#If` `#ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="bd6c7-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>

 <span data-ttu-id="bd6c7-105">**Fehler-ID:** BC30014</span><span class="sxs-lookup"><span data-stu-id="bd6c7-105">**Error ID:** BC30014</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="bd6c7-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="bd6c7-106">To correct this error</span></span>

1. <span data-ttu-id="bd6c7-107">Überprüfen Sie, ob eine vorhergehende `#If` oder `#ElseIf` nicht `#ElseIf` durch einen dazwischen liegenden bedingten Kompilierungs Block oder ein falsch platziertes von diesem getrennt wurde `#End If` .</span><span class="sxs-lookup"><span data-stu-id="bd6c7-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>

2. <span data-ttu-id="bd6c7-108">Wenn dem `#ElseIf` eine-Direktive vorangestellt ist `#Else` , entfernen Sie entweder das, `#Else` oder ändern Sie es in ein `#ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="bd6c7-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>

3. <span data-ttu-id="bd6c7-109">Falls der Code ansonsten in Ordnung ist, fügen Sie am Anfang des Blocks für die bedingte Kompilierung eine `#If` -Direktive hinzu.</span><span class="sxs-lookup"><span data-stu-id="bd6c7-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd6c7-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd6c7-110">See also</span></span>

- [<span data-ttu-id="bd6c7-111">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="bd6c7-111">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
