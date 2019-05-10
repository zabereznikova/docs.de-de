---
title: Arraygrenzen können nicht in Typbezeichnern stehen.
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 50e1cd0e41da467a9e816c8e5d64d09a36923d65
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665745"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="301af-102">Arraygrenzen können nicht in Typbezeichnern stehen.</span><span class="sxs-lookup"><span data-stu-id="301af-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="301af-103">Array-Größe können nicht als Teil eines Datenspezifizierers Typ deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="301af-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="301af-104">**Fehler-ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="301af-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="301af-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="301af-105">To correct this error</span></span>  
  
- <span data-ttu-id="301af-106">Geben Sie die Größe des Arrays unmittelbar nach dem Variablennamen, anstatt die Größe des Arrays nach dem Typ, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="301af-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
- <span data-ttu-id="301af-107">Definieren Sie ein Array, und initialisieren Sie es mit der gewünschten Anzahl von Elementen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="301af-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="301af-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="301af-108">See also</span></span>

- [<span data-ttu-id="301af-109">Arrays</span><span class="sxs-lookup"><span data-stu-id="301af-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
