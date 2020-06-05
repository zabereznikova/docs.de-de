---
title: Das Array ist fixiert oder vorübergehend gesperrt
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 4a86460104b6c4d9d6791e60f6f377cec0030425
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363032"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="cd9f8-102">Das Array ist fixiert oder vorübergehend gesperrt (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cd9f8-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="cd9f8-103">Dieser Fehler kann folgende Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="cd9f8-103">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="cd9f8-104">Mithilfe `ReDim` von können Sie die Anzahl von Elementen eines Arrays mit fester Größe ändern.</span><span class="sxs-lookup"><span data-stu-id="cd9f8-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
- <span data-ttu-id="cd9f8-105">Neudimensionierung eines dynamischen Arrays auf Modulebene, in dem ein Element als Argument an eine Prozedur weitergegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="cd9f8-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="cd9f8-106">Wenn ein Element übergeben wird, wird das Array gesperrt, um zu verhindern, dass der Speicherplatz für den Verweis Parameter innerhalb der Prozedur aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="cd9f8-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
- <span data-ttu-id="cd9f8-107">Es wird versucht, einer `Variant` Variablen, die ein Array enthält, einen Wert zuzuweisen, aber die `Variant` ist zurzeit gesperrt.</span><span class="sxs-lookup"><span data-stu-id="cd9f8-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cd9f8-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="cd9f8-108">To correct this error</span></span>  
  
1. <span data-ttu-id="cd9f8-109">Legen Sie das ursprüngliche Array dynamisch und nicht fest, indem Sie es mit deklarieren `ReDim` (wenn das Array innerhalb einer Prozedur deklariert ist), oder indem Sie es deklarieren, ohne die Anzahl der Elemente anzugeben (wenn das Array auf Modulebene deklariert ist).</span><span class="sxs-lookup"><span data-stu-id="cd9f8-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="cd9f8-110">Stellen Sie fest, ob das Element wirklich übergeben werden muss, da es in allen Prozeduren im Modul sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="cd9f8-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="cd9f8-111">Legen Sie fest, was gesperrt ist, `Variant` und beheben Sie es.</span><span class="sxs-lookup"><span data-stu-id="cd9f8-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9f8-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd9f8-112">See also</span></span>

- [<span data-ttu-id="cd9f8-113">Arrays</span><span class="sxs-lookup"><span data-stu-id="cd9f8-113">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
