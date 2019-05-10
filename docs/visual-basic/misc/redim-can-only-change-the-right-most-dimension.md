---
title: „ReDim“ kann nur die Dimension ganz rechts ändern.
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 584370f356180fe8b1710a9e145018be7f2d8a0f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592297"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="54168-102">„ReDim“ kann nur die Dimension ganz rechts ändern.</span><span class="sxs-lookup"><span data-stu-id="54168-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="54168-103">Eine `ReDim` -Anweisung hat versucht, mithilfe des `Preserve` -Schlüsselworts eine Dimension eines Arrays zu ändern, die nicht die letzte Dimension ist.</span><span class="sxs-lookup"><span data-stu-id="54168-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="54168-104">Bei Verwendung von `Preserve`können Sie nur die Größe der letzten Dimension eines Arrays ändern.</span><span class="sxs-lookup"><span data-stu-id="54168-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="54168-105">Für alle anderen Dimensionen müssen Sie die gleiche Größe wie für das vorhandene Array angeben.</span><span class="sxs-lookup"><span data-stu-id="54168-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="54168-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="54168-106">To correct this error</span></span>  
  
- <span data-ttu-id="54168-107">Entfernen Sie das `Preserve` -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="54168-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54168-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54168-108">See also</span></span>

- [<span data-ttu-id="54168-109">Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54168-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="54168-110">Arraydimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="54168-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="54168-111">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="54168-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="54168-112">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="54168-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
