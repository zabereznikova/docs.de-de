---
title: Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic).
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: e912bd202603d9a0f427418708ad584c7d6203e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593563"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="f13e7-102">Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="f13e7-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="f13e7-103">Dieser Fehler hat die folgenden möglichen Ursachen:</span><span class="sxs-lookup"><span data-stu-id="f13e7-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="f13e7-104">Mithilfe von `ReDim` so ändern Sie die Anzahl der Elemente eines Arrays mit fester Größe.</span><span class="sxs-lookup"><span data-stu-id="f13e7-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="f13e7-105">Neudimensionierung auf Modulebene dynamisches Array, in dem ein Element als Argument an eine Prozedur wurde übergeben.</span><span class="sxs-lookup"><span data-stu-id="f13e7-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="f13e7-106">Wenn ein Element übergeben wird, wird das Array gesperrt, um zu verhindern, dass Freigeben von Speicher für die Verweisparameter innerhalb der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="f13e7-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="f13e7-107">Bei dem Versuch, einen Wert zuzuweisen eine `Variant` Variable, die ein Array ist, enthält aber die `Variant` ist derzeit gesperrt.</span><span class="sxs-lookup"><span data-stu-id="f13e7-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f13e7-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f13e7-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="f13e7-109">Stellen Sie das ursprüngliche Array dynamische statt mit festen `ReDim` (wenn das Array in einer Prozedur deklariert ist), oder deklarieren Sie es ohne Angabe der Anzahl von Elementen (wenn das Array auf Modulebene deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="f13e7-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2.  <span data-ttu-id="f13e7-110">Bestimmen Sie, ob Sie tatsächlich das Element zu übergeben, da es in allen Prozeduren im Modul angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f13e7-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3.  <span data-ttu-id="f13e7-111">Bestimmen, welche Sperren ist der `Variant` und beheben sie das Problem.</span><span class="sxs-lookup"><span data-stu-id="f13e7-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f13e7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f13e7-112">See Also</span></span>  
 [<span data-ttu-id="f13e7-113">Arrays</span><span class="sxs-lookup"><span data-stu-id="f13e7-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
