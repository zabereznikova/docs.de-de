---
title: '&#39; #ElseIf &#39; muss ein entsprechender &#39; #If &#39;vorangestellt werden; oder &#39; #ElseIf &#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords: BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b3a4e809e1108fcd6e116538a1947057e9548ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a><span data-ttu-id="19094-102">&#39; #ElseIf &#39; muss ein entsprechender &#39; #If &#39;vorangestellt werden; oder &#39; #ElseIf &#39;</span><span class="sxs-lookup"><span data-stu-id="19094-102">&#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39;</span></span>
<span data-ttu-id="19094-103">`#ElseIf`ist eine Direktive für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="19094-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="19094-104">Ein `#ElseIf` Klausel muss ein entsprechender stehen `#If` oder `#ElseIf` Klausel.</span><span class="sxs-lookup"><span data-stu-id="19094-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="19094-105">**Fehler-ID:** BC30014</span><span class="sxs-lookup"><span data-stu-id="19094-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="19094-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="19094-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="19094-107">Überprüfen Sie, ob eine vorangestellte `#If` oder `#ElseIf` nicht von diesem getrennt wurde `#ElseIf` durch einen dazwischen liegenden Block bedingte Kompilierung oder eine falsch platzierte `#End If`.</span><span class="sxs-lookup"><span data-stu-id="19094-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="19094-108">Wenn die `#ElseIf` vorangestellt ist ein `#Else` -Direktive, entfernen Sie entweder die `#Else` oder ändern Sie ihn in ein `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="19094-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="19094-109">Falls der Code ansonsten in Ordnung ist, fügen Sie am Anfang des Blocks für die bedingte Kompilierung eine `#If` -Direktive hinzu.</span><span class="sxs-lookup"><span data-stu-id="19094-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19094-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19094-110">See Also</span></span>  
 [<span data-ttu-id="19094-111">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="19094-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
