---
title: '&#39;ReDim&#39; die Anzahl von Dimensionen kann nicht geändert werden.'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: bfd4096141833b85a2126340ef549e1e1d1f8e3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39redim39-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="7a880-102">&#39;ReDim&#39; die Anzahl von Dimensionen kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7a880-102">&#39;ReDim&#39; cannot change the number of dimensions</span></span>
<span data-ttu-id="7a880-103">Ein Vorgang versucht über die `ReDim` -Anweisung, den Rang (Anzahl von Dimensionen) eines Arrays zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7a880-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="7a880-104">`ReDim` kann die Größe einer oder mehrerer Dimensionen eines Arrays ändern, das bereits formal deklariert wurde, kann aber nicht den Rang eines Arrays ändern.</span><span class="sxs-lookup"><span data-stu-id="7a880-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a880-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7a880-105">To correct this error</span></span>  
  
-   <span data-ttu-id="7a880-106">Vergewissern Sie sich, dass Sie den Rang des Arrays und nicht die Größen seiner Dimensionen ändern möchten, und verwenden Sie, sofern möglich, `Dim` , um ein neues Array mit dem gewünschten Rang zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="7a880-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a880-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a880-107">See Also</span></span>  
 [<span data-ttu-id="7a880-108">Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a880-108">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="7a880-109">Arraydimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a880-109">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="7a880-110">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7a880-110">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="7a880-111">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7a880-111">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
