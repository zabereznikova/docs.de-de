---
title: ReDim kann die Anzahl der Dimensionen nicht ändern.
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: b2404927c2faf30d1d058d2163fd5d67e1a52e1e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358166"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="02e8c-102">ReDim kann die Anzahl der Dimensionen nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="02e8c-102">'ReDim' cannot change the number of dimensions</span></span>
<span data-ttu-id="02e8c-103">Ein Vorgang versucht über die `ReDim` -Anweisung, den Rang (Anzahl von Dimensionen) eines Arrays zu ändern.</span><span class="sxs-lookup"><span data-stu-id="02e8c-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="02e8c-104">`ReDim` kann die Größe einer oder mehrerer Dimensionen eines Arrays ändern, das bereits formal deklariert wurde, kann aber nicht den Rang eines Arrays ändern.</span><span class="sxs-lookup"><span data-stu-id="02e8c-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="02e8c-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="02e8c-105">To correct this error</span></span>  
  
- <span data-ttu-id="02e8c-106">Vergewissern Sie sich, dass Sie den Rang des Arrays und nicht die Größen seiner Dimensionen ändern möchten, und verwenden Sie, sofern möglich, `Dim` , um ein neues Array mit dem gewünschten Rang zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="02e8c-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02e8c-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02e8c-107">See also</span></span>

- [<span data-ttu-id="02e8c-108">Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02e8c-108">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="02e8c-109">Array Dimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02e8c-109">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="02e8c-110">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="02e8c-110">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="02e8c-111">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="02e8c-111">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)
