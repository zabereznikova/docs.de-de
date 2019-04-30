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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935355"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="6beea-102">Arraygrenzen können nicht in Typbezeichnern stehen.</span><span class="sxs-lookup"><span data-stu-id="6beea-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="6beea-103">Array-Größe können nicht als Teil eines Datenspezifizierers Typ deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="6beea-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="6beea-104">**Fehler-ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="6beea-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6beea-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6beea-105">To correct this error</span></span>  
  
- <span data-ttu-id="6beea-106">Geben Sie die Größe des Arrays unmittelbar nach dem Variablennamen, anstatt die Größe des Arrays nach dem Typ, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6beea-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
- <span data-ttu-id="6beea-107">Definieren Sie ein Array, und initialisieren Sie es mit der gewünschten Anzahl von Elementen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6beea-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6beea-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6beea-108">See also</span></span>

- [<span data-ttu-id="6beea-109">Arrays</span><span class="sxs-lookup"><span data-stu-id="6beea-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
