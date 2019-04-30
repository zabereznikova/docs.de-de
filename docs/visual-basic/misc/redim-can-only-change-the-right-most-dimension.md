---
title: „ReDim“ kann nur die Dimension ganz rechts ändern.
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 86d639e70e85b19a91f89fa4e0cab330af07dccf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61943363"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="c9e20-102">„ReDim“ kann nur die Dimension ganz rechts ändern.</span><span class="sxs-lookup"><span data-stu-id="c9e20-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="c9e20-103">Eine `ReDim` -Anweisung hat versucht, mithilfe des `Preserve` -Schlüsselworts eine Dimension eines Arrays zu ändern, die nicht die letzte Dimension ist.</span><span class="sxs-lookup"><span data-stu-id="c9e20-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="c9e20-104">Bei Verwendung von `Preserve`können Sie nur die Größe der letzten Dimension eines Arrays ändern.</span><span class="sxs-lookup"><span data-stu-id="c9e20-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="c9e20-105">Für alle anderen Dimensionen müssen Sie die gleiche Größe wie für das vorhandene Array angeben.</span><span class="sxs-lookup"><span data-stu-id="c9e20-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c9e20-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c9e20-106">To correct this error</span></span>  
  
- <span data-ttu-id="c9e20-107">Entfernen Sie das `Preserve` -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="c9e20-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e20-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9e20-108">See also</span></span>

- [<span data-ttu-id="c9e20-109">Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9e20-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="c9e20-110">Arraydimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9e20-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="c9e20-111">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c9e20-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="c9e20-112">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c9e20-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
