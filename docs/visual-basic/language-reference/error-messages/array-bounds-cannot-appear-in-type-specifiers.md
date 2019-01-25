---
title: Arraygrenzen können nicht in Typbezeichnern stehen.
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: f31aea5a98233c8f262a77ba5c99eea389bc33ee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715438"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="caea3-102">Arraygrenzen können nicht in Typbezeichnern stehen.</span><span class="sxs-lookup"><span data-stu-id="caea3-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="caea3-103">Array-Größe können nicht als Teil eines Datenspezifizierers Typ deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="caea3-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="caea3-104">**Fehler-ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="caea3-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="caea3-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="caea3-105">To correct this error</span></span>  
  
-   <span data-ttu-id="caea3-106">Geben Sie die Größe des Arrays unmittelbar nach dem Variablennamen, anstatt die Größe des Arrays nach dem Typ, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="caea3-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="caea3-107">Definieren Sie ein Array, und initialisieren Sie es mit der gewünschten Anzahl von Elementen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="caea3-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="caea3-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="caea3-108">See also</span></span>
- [<span data-ttu-id="caea3-109">Arrays</span><span class="sxs-lookup"><span data-stu-id="caea3-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
