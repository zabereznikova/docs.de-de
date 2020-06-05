---
title: Eine Anweisung kann keinen Block außerhalb einer "If"-Zeilenanweisung beenden.
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 3fe3faaa3637446bb6ab443ba1d6e1d1004b4d48
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400317"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="f431f-102">Eine Anweisung kann keinen Block außerhalb einer "If"-Zeilenanweisung beenden.</span><span class="sxs-lookup"><span data-stu-id="f431f-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="f431f-103">Eine einzeilige `If` Anweisung enthält mehrere durch Doppelpunkte getrennte Anweisungen (:), von denen eine eine- `End` Anweisung für einen Kontroll Block außerhalb der einzeiligen ist `If` .</span><span class="sxs-lookup"><span data-stu-id="f431f-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="f431f-104">Einzeilige `If` Anweisungen verwenden nicht die- `End If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f431f-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="f431f-105">**Fehler-ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="f431f-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f431f-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f431f-106">To correct this error</span></span>  
  
- <span data-ttu-id="f431f-107">Verschieben Sie die einzeilige `If` Anweisung außerhalb des Kontroll Blocks, der die- `End If` Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="f431f-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f431f-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f431f-108">See also</span></span>

- [<span data-ttu-id="f431f-109">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f431f-109">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
