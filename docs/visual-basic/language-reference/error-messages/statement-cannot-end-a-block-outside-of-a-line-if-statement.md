---
title: Anweisung kann nicht beendet einen Block außerhalb einer Zeile &#39;Wenn&#39; Anweisung
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: af3006ddc35dfcaa52a54229881baa48cfb7809a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596683"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a><span data-ttu-id="4d9fe-102">Anweisung kann nicht beendet einen Block außerhalb einer Zeile &#39;Wenn&#39; Anweisung</span><span class="sxs-lookup"><span data-stu-id="4d9fe-102">Statement cannot end a block outside of a line &#39;If&#39; statement</span></span>
<span data-ttu-id="4d9fe-103">Eine einzeilige `If` -Anweisung enthält mehrere Anweisungen, die getrennt durch Doppelpunkte (:)), von denen eine `End` -Anweisung für einen Kontrollblock außerhalb der einzeiligen `If`.</span><span class="sxs-lookup"><span data-stu-id="4d9fe-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="4d9fe-104">Einzeilige `If` Anweisungen verwenden Sie nicht die `End If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4d9fe-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="4d9fe-105">**Fehler-ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="4d9fe-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4d9fe-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4d9fe-106">To correct this error</span></span>  
  
-   <span data-ttu-id="4d9fe-107">Verschieben Sie die einzeilige `If` Anweisung außerhalb der Kontrollblock enthält, die die `End If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4d9fe-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d9fe-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d9fe-108">See Also</span></span>  
 [<span data-ttu-id="4d9fe-109">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4d9fe-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
