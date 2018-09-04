---
title: '&#39;ReDim&#39; können nur die Dimension ganz rechts ändern'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 94e0fe81f7e750a67943b68f2db700e3a7831da1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502585"
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="4e4c9-102">&#39;ReDim&#39; können nur die Dimension ganz rechts ändern</span><span class="sxs-lookup"><span data-stu-id="4e4c9-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="4e4c9-103">Eine `ReDim` -Anweisung hat versucht, mithilfe des `Preserve` -Schlüsselworts eine Dimension eines Arrays zu ändern, die nicht die letzte Dimension ist.</span><span class="sxs-lookup"><span data-stu-id="4e4c9-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="4e4c9-104">Bei Verwendung von `Preserve`können Sie nur die Größe der letzten Dimension eines Arrays ändern.</span><span class="sxs-lookup"><span data-stu-id="4e4c9-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="4e4c9-105">Für alle anderen Dimensionen müssen Sie die gleiche Größe wie für das vorhandene Array angeben.</span><span class="sxs-lookup"><span data-stu-id="4e4c9-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4e4c9-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4e4c9-106">To correct this error</span></span>  
  
-   <span data-ttu-id="4e4c9-107">Entfernen Sie das `Preserve` -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="4e4c9-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e4c9-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e4c9-108">See Also</span></span>  
 [<span data-ttu-id="4e4c9-109">Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4e4c9-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="4e4c9-110">Arraydimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4e4c9-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="4e4c9-111">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4e4c9-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="4e4c9-112">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4e4c9-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="4e4c9-113">Beibehalten – löschen</span><span class="sxs-lookup"><span data-stu-id="4e4c9-113">Preserve - delete</span></span>](https://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
