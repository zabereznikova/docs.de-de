---
title: "&#39; ReDim &#39; Die Dimension ganz rechts kann nur geändert werden."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 752e0e54c48b3b348a477787e5e911f1b1777667
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="a1a7a-102">&#39; ReDim &#39; Die Dimension ganz rechts kann nur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a1a7a-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="a1a7a-103">Eine `ReDim` -Anweisung hat versucht, mithilfe des `Preserve` -Schlüsselworts eine Dimension eines Arrays zu ändern, die nicht die letzte Dimension ist.</span><span class="sxs-lookup"><span data-stu-id="a1a7a-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="a1a7a-104">Bei Verwendung von `Preserve`können Sie nur die Größe der letzten Dimension eines Arrays ändern.</span><span class="sxs-lookup"><span data-stu-id="a1a7a-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="a1a7a-105">Für alle anderen Dimensionen müssen Sie die gleiche Größe wie für das vorhandene Array angeben.</span><span class="sxs-lookup"><span data-stu-id="a1a7a-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a1a7a-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a1a7a-106">To correct this error</span></span>  
  
-   <span data-ttu-id="a1a7a-107">Entfernen Sie das `Preserve` -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="a1a7a-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a7a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1a7a-108">See Also</span></span>  
 [<span data-ttu-id="a1a7a-109">Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a1a7a-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="a1a7a-110">Arraydimensionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a1a7a-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="a1a7a-111">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a1a7a-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="a1a7a-112">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a1a7a-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="a1a7a-113">Beibehalten – löschen</span><span class="sxs-lookup"><span data-stu-id="a1a7a-113">Preserve - delete</span></span>](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
