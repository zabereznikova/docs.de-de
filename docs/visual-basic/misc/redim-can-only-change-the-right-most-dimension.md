---
title: '&#39;ReDim&#39; können nur die Dimension ganz rechts ändern'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: efb98df13a7e3e378347b30b6fc00b90030ec194
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="9eab9-102">&#39;ReDim&#39; können nur die Dimension ganz rechts ändern</span><span class="sxs-lookup"><span data-stu-id="9eab9-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="9eab9-103">Eine `ReDim` -Anweisung hat versucht, mithilfe des `Preserve` -Schlüsselworts eine Dimension eines Arrays zu ändern, die nicht die letzte Dimension ist.</span><span class="sxs-lookup"><span data-stu-id="9eab9-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="9eab9-104">Bei Verwendung von `Preserve`können Sie nur die Größe der letzten Dimension eines Arrays ändern.</span><span class="sxs-lookup"><span data-stu-id="9eab9-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="9eab9-105">Für alle anderen Dimensionen müssen Sie die gleiche Größe wie für das vorhandene Array angeben.</span><span class="sxs-lookup"><span data-stu-id="9eab9-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9eab9-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9eab9-106">To correct this error</span></span>  
  
-   <span data-ttu-id="9eab9-107">Entfernen Sie das `Preserve` -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="9eab9-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eab9-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9eab9-108">See Also</span></span>  
 [<span data-ttu-id="9eab9-109">Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9eab9-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="9eab9-110">Arraydimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9eab9-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="9eab9-111">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9eab9-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="9eab9-112">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9eab9-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="9eab9-113">Beibehalten – löschen</span><span class="sxs-lookup"><span data-stu-id="9eab9-113">Preserve - delete</span></span>](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
