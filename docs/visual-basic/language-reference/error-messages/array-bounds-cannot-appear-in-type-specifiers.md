---
title: Arraygrenzen können nicht in Typbezeichnern stehen.
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 951f710160ae1023671773c21c73946f5ae94c2b
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512762"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="c50a3-102">Arraygrenzen können nicht in Typbezeichnern stehen.</span><span class="sxs-lookup"><span data-stu-id="c50a3-102">Array bounds cannot appear in type specifiers</span></span>

<span data-ttu-id="c50a3-103">Array Größen können nicht als Teil eines Datentyp Spezifizierers deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="c50a3-103">Array sizes cannot be declared as part of a data type specifier.</span></span>

<span data-ttu-id="c50a3-104">**Fehler-ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="c50a3-104">**Error ID:** BC30638</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c50a3-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c50a3-105">To correct this error</span></span>

- <span data-ttu-id="c50a3-106">Geben Sie die Größe des Arrays direkt nach dem Variablennamen an, anstatt die Array Größe nach dem Typ zu platzieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c50a3-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>

  ```vb
  Dim Array(8) As Integer
  ```

- <span data-ttu-id="c50a3-107">Definieren Sie ein Array, und initialisieren Sie es mit der gewünschten Anzahl von Elementen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c50a3-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>

  ```vb
  Dim Array2() As Integer = New Integer(8) {}
  ```

## <a name="see-also"></a><span data-ttu-id="c50a3-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c50a3-108">See also</span></span>

- [<span data-ttu-id="c50a3-109">Arrays</span><span class="sxs-lookup"><span data-stu-id="c50a3-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
