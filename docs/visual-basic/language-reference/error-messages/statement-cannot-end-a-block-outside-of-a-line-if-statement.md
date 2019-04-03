---
title: Eine Anweisung kann keinen Block außerhalb einer "If"-Zeilenanweisung beenden.
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 85573099ec0a3f8a23c17bdf384c4c105f9157df
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825793"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="2f4d3-102">Eine Anweisung kann keinen Block außerhalb einer "If"-Zeilenanweisung beenden.</span><span class="sxs-lookup"><span data-stu-id="2f4d3-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="2f4d3-103">Einem einzeiligen `If` -Anweisung enthält mehrere Anweisungen, getrennt durch Doppelpunkte (:), von denen eine `End` -Anweisung für einen Kontrollblock außerhalb der einzeiligen `If`.</span><span class="sxs-lookup"><span data-stu-id="2f4d3-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="2f4d3-104">Einzeilige `If` Anweisungen verwenden Sie nicht die `End If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2f4d3-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="2f4d3-105">**Fehler-ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="2f4d3-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2f4d3-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="2f4d3-106">To correct this error</span></span>  
  
-   <span data-ttu-id="2f4d3-107">Verschieben der einzeilige `If` Anweisung außerhalb der Kontrollblock mit der `End If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2f4d3-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f4d3-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f4d3-108">See also</span></span>

- [<span data-ttu-id="2f4d3-109">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2f4d3-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
