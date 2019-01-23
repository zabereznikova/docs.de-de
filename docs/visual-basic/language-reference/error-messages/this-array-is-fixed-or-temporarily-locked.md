---
title: Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic).
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: f70b984fc493e79d7a83b33236615a3220405786
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516992"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="10b6a-102">Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="10b6a-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="10b6a-103">Dieser Fehler hat die folgenden möglichen Ursachen:</span><span class="sxs-lookup"><span data-stu-id="10b6a-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="10b6a-104">Mithilfe von `ReDim` so ändern Sie die Anzahl der Elemente eines Arrays fester Größe.</span><span class="sxs-lookup"><span data-stu-id="10b6a-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="10b6a-105">Neudimensionierung ein auf Modulebene dynamisches Array, in dem ein Element an eine Prozedur als Argument übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="10b6a-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="10b6a-106">Wenn ein Element übergeben wird, ist das Array gesperrt, um zu verhindern, dass Freigeben von Speicher für der Verweisparameter, in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="10b6a-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="10b6a-107">Es wird versucht, einen Wert zuweisen einer `Variant` Variable, die ein Array ist, enthält aber die `Variant` ist zurzeit gesperrt.</span><span class="sxs-lookup"><span data-stu-id="10b6a-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="10b6a-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="10b6a-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="10b6a-109">Stellen Sie das ursprüngliche Array dynamisch und nicht als deklarieren Sie es mit festen `ReDim` (wenn das Array in einer Prozedur deklariert wird), oder deklarieren es ohne Angabe der Anzahl der Elemente, (wenn das Array auf der Modulebene deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="10b6a-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2.  <span data-ttu-id="10b6a-110">Bestimmen Sie, ob Sie wirklich benötigen, um das Element, zu übergeben, da es in alle Verfahren im Modul angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="10b6a-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3.  <span data-ttu-id="10b6a-111">Bestimmen, was verhindert die `Variant` und beheben sie das Problem.</span><span class="sxs-lookup"><span data-stu-id="10b6a-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10b6a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10b6a-112">See also</span></span>
- [<span data-ttu-id="10b6a-113">Arrays</span><span class="sxs-lookup"><span data-stu-id="10b6a-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
