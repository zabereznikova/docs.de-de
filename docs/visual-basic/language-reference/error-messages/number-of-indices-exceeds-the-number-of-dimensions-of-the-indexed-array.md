---
title: Die Indexanzahl ist größer als die Anzahl der Dimensionen des indizierten Arrays.
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: 9a191ff7ec3ad6a607e6509cc143c359f64f21ea
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159910"
---
# <a name="bc30106-number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a><span data-ttu-id="23390-102">BC30106: die Anzahl der Indizes überschreitet die Anzahl der Dimensionen des indizierten Arrays.</span><span class="sxs-lookup"><span data-stu-id="23390-102">BC30106: Number of indices exceeds the number of dimensions of the indexed array</span></span>

<span data-ttu-id="23390-103">Die Indexanzahl, die für den Zugriff auf ein Arrayelement verwendet wird, muss mit dem Rang des Arrays identisch sein, d. h. die Anzahl der für das Array deklarierten Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="23390-103">The number of indices used to access an array element must be exactly the same as the rank of the array, that is, the number of dimensions declared for it.</span></span>

 <span data-ttu-id="23390-104">**Fehler-ID:** BC30106</span><span class="sxs-lookup"><span data-stu-id="23390-104">**Error ID:** BC30106</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="23390-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="23390-105">To correct this error</span></span>

- <span data-ttu-id="23390-106">Entfernen Sie die Indizes aus dem Array Verweis, bis die Gesamtzahl der abonniert dem Rang des Arrays gleicht.</span><span class="sxs-lookup"><span data-stu-id="23390-106">Remove subscripts from the array reference until the total number of subscripts equals the rank of the array.</span></span> <span data-ttu-id="23390-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="23390-107">For example:</span></span>

    ```vb
    Dim gameBoard(3, 3) As String

    ' Incorrect code. The array has two dimensions.
    gameBoard(1, 1, 1) = "X"
    gameBoard(2, 1, 1) = "O"

    ' Correct code.
    gameBoard(0, 0) = "X"
    gameBoard(1, 0) = "O"
    ```

## <a name="see-also"></a><span data-ttu-id="23390-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23390-108">See also</span></span>

- [<span data-ttu-id="23390-109">Arrays</span><span class="sxs-lookup"><span data-stu-id="23390-109">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
