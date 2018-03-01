---
title: "Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic)."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adff10d4ae61e45402df64ebaa3baf146371ff9e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="d94aa-102">Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d94aa-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="d94aa-103">Dieser Fehler hat die folgenden möglichen Ursachen:</span><span class="sxs-lookup"><span data-stu-id="d94aa-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="d94aa-104">Mithilfe von `ReDim` so ändern Sie die Anzahl der Elemente eines Arrays mit fester Größe.</span><span class="sxs-lookup"><span data-stu-id="d94aa-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="d94aa-105">Neudimensionierung auf Modulebene dynamisches Array, in dem ein Element als Argument an eine Prozedur wurde übergeben.</span><span class="sxs-lookup"><span data-stu-id="d94aa-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="d94aa-106">Wenn ein Element übergeben wird, wird das Array gesperrt, um zu verhindern, dass Freigeben von Speicher für die Verweisparameter innerhalb der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d94aa-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="d94aa-107">Bei dem Versuch, einen Wert zuzuweisen eine `Variant` Variable, die ein Array ist, enthält aber die `Variant` ist derzeit gesperrt.</span><span class="sxs-lookup"><span data-stu-id="d94aa-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d94aa-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d94aa-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="d94aa-109">Stellen Sie das ursprüngliche Array dynamische statt mit festen `ReDim` (wenn das Array in einer Prozedur deklariert ist), oder deklarieren Sie es ohne Angabe der Anzahl von Elementen (wenn das Array auf Modulebene deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="d94aa-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2.  <span data-ttu-id="d94aa-110">Bestimmen Sie, ob Sie tatsächlich das Element zu übergeben, da es in allen Prozeduren im Modul angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d94aa-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3.  <span data-ttu-id="d94aa-111">Bestimmen, welche Sperren ist der `Variant` und beheben sie das Problem.</span><span class="sxs-lookup"><span data-stu-id="d94aa-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d94aa-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d94aa-112">See Also</span></span>  
 [<span data-ttu-id="d94aa-113">Arrays</span><span class="sxs-lookup"><span data-stu-id="d94aa-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
