---
title: Arraygrenzen können nicht in Typbezeichnern stehen.
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: f20ed883005641082eb89e2effa5221594910ffe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838780"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="47384-102">Arraygrenzen können nicht in Typbezeichnern stehen.</span><span class="sxs-lookup"><span data-stu-id="47384-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="47384-103">Array-Größe können nicht als Teil eines Datenspezifizierers Typ deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="47384-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="47384-104">**Fehler-ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="47384-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="47384-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="47384-105">To correct this error</span></span>  
  
-   <span data-ttu-id="47384-106">Geben Sie die Größe des Arrays unmittelbar nach dem Variablennamen, anstatt die Größe des Arrays nach dem Typ, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="47384-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="47384-107">Definieren Sie ein Array, und initialisieren Sie es mit der gewünschten Anzahl von Elementen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="47384-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="47384-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47384-108">See also</span></span>

- [<span data-ttu-id="47384-109">Arrays</span><span class="sxs-lookup"><span data-stu-id="47384-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
