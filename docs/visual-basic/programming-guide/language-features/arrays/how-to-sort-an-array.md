---
title: 'Vorgehensweise: Array in Visual Basic sortieren'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 467d1bcce6bda2feb5a8e59c152cb292d753e79b
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700980"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="45458-102">Gewusst wie: Sortieren eines Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45458-102">How to: sort an array in Visual Basic</span></span>

<span data-ttu-id="45458-103">Dieser Artikel zeigt ein Beispiel für das Sortieren eines Arrays von Zeichen folgen in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="45458-103">This article shows an example of how to sort an array of strings in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="45458-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="45458-104">Example</span></span>

<span data-ttu-id="45458-105">In diesem Beispiel wird ein Array von `String`-Objekten mit dem Namen `zooAnimals` deklariert, aufgefüllt und dann alphabetisch sortiert:</span><span class="sxs-lookup"><span data-stu-id="45458-105">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically:</span></span>
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a><span data-ttu-id="45458-106">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="45458-106">Robust programming</span></span>

<span data-ttu-id="45458-107">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="45458-107">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="45458-108">Das Array ist leer (<xref:System.ArgumentNullException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="45458-108">Array is empty (<xref:System.ArgumentNullException> class).</span></span>
- <span data-ttu-id="45458-109">Array ist mehrdimensional (<xref:System.RankException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="45458-109">Array is multidimensional (<xref:System.RankException> class).</span></span>
- <span data-ttu-id="45458-110">Mindestens ein Element des Arrays implementiert nicht die <xref:System.IComparable>-Schnittstelle (<xref:System.InvalidOperationException>-Klasse).</span><span class="sxs-lookup"><span data-stu-id="45458-110">One or more elements of the array don't implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="45458-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45458-111">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="45458-112">Arrays</span><span class="sxs-lookup"><span data-stu-id="45458-112">Arrays</span></span>](index.md)
- [<span data-ttu-id="45458-113">Problembehandlung bei Arrays</span><span class="sxs-lookup"><span data-stu-id="45458-113">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="45458-114">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="45458-114">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="45458-115">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45458-115">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)
