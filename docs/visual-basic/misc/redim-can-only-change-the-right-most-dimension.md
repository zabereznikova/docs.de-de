---
title: „ReDim“ kann nur die Dimension ganz rechts ändern.
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 8e42e0df7b97fb96f468ce37dd4cfc52fad8c596
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358295"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="77677-102">„ReDim“ kann nur die Dimension ganz rechts ändern.</span><span class="sxs-lookup"><span data-stu-id="77677-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="77677-103">Eine `ReDim` -Anweisung hat versucht, mithilfe des `Preserve` -Schlüsselworts eine Dimension eines Arrays zu ändern, die nicht die letzte Dimension ist.</span><span class="sxs-lookup"><span data-stu-id="77677-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="77677-104">Bei Verwendung von `Preserve`können Sie nur die Größe der letzten Dimension eines Arrays ändern.</span><span class="sxs-lookup"><span data-stu-id="77677-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="77677-105">Für alle anderen Dimensionen müssen Sie die gleiche Größe wie für das vorhandene Array angeben.</span><span class="sxs-lookup"><span data-stu-id="77677-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="77677-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="77677-106">To correct this error</span></span>  
  
- <span data-ttu-id="77677-107">Entfernen Sie das `Preserve` -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="77677-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77677-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77677-108">See also</span></span>

- [<span data-ttu-id="77677-109">Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77677-109">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="77677-110">Array Dimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77677-110">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="77677-111">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="77677-111">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="77677-112">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="77677-112">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)
