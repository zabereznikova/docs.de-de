---
title: ReDim kann die Anzahl der Dimensionen nicht ändern.
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 8d80af7682f27b403e0f463fdbebbcac71f18b01
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077370"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="85bdb-102">ReDim kann die Anzahl der Dimensionen nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="85bdb-102">'ReDim' cannot change the number of dimensions</span></span>

<span data-ttu-id="85bdb-103">Ein Vorgang versucht über die `ReDim` -Anweisung, den Rang (Anzahl von Dimensionen) eines Arrays zu ändern.</span><span class="sxs-lookup"><span data-stu-id="85bdb-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="85bdb-104">`ReDim` kann die Größe einer oder mehrerer Dimensionen eines Arrays ändern, das bereits formal deklariert wurde, kann aber nicht den Rang eines Arrays ändern.</span><span class="sxs-lookup"><span data-stu-id="85bdb-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="85bdb-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="85bdb-105">To correct this error</span></span>  
  
- <span data-ttu-id="85bdb-106">Vergewissern Sie sich, dass Sie den Rang des Arrays und nicht die Größen seiner Dimensionen ändern möchten, und verwenden Sie, sofern möglich, `Dim` , um ein neues Array mit dem gewünschten Rang zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="85bdb-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85bdb-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85bdb-107">See also</span></span>

- [<span data-ttu-id="85bdb-108">Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85bdb-108">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="85bdb-109">Array Dimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85bdb-109">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="85bdb-110">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="85bdb-110">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="85bdb-111">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="85bdb-111">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)
