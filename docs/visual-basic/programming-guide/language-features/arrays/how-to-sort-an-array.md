---
title: 'Vorgehensweise: Sortieren eines Arrays in Visual Basic'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 680f488a98d6e7e31b3d077843514fd12f75481c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586441"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="14493-102">Vorgehensweise: Sortieren eines Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14493-102">How to: Sort An Array in Visual Basic</span></span>
<span data-ttu-id="14493-103">In diesem Beispiel deklariert einen Array von `String` Objekte, die mit dem Namen `zooAnimals`, füllt es und sortiert es anschließend alphabetisch.</span><span class="sxs-lookup"><span data-stu-id="14493-103">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14493-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14493-104">Example</span></span>  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="14493-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="14493-105">Compiling the Code</span></span>  
 <span data-ttu-id="14493-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="14493-106">This example requires:</span></span>  
  
- <span data-ttu-id="14493-107">Der Zugriff auf die <xref:System> Namespace.</span><span class="sxs-lookup"><span data-stu-id="14493-107">Access to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="14493-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="14493-108">Robust Programming</span></span>  
 <span data-ttu-id="14493-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="14493-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="14493-110">Array ist leer (<xref:System.ArgumentNullException> Klasse)</span><span class="sxs-lookup"><span data-stu-id="14493-110">Array is empty (<xref:System.ArgumentNullException> class)</span></span>  
  
- <span data-ttu-id="14493-111">Array ist mehrdimensional (<xref:System.RankException> Klasse)</span><span class="sxs-lookup"><span data-stu-id="14493-111">Array is multidimensional (<xref:System.RankException> class)</span></span>  
  
- <span data-ttu-id="14493-112">Ein oder mehrere Elemente des Arrays implementiert nicht die <xref:System.IComparable> Schnittstelle (<xref:System.InvalidOperationException> Klasse)</span><span class="sxs-lookup"><span data-stu-id="14493-112">One or more elements of the array do not implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14493-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14493-113">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="14493-114">Arrays</span><span class="sxs-lookup"><span data-stu-id="14493-114">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="14493-115">Problembehandlung bei Arrays</span><span class="sxs-lookup"><span data-stu-id="14493-115">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="14493-116">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="14493-116">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="14493-117">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="14493-117">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
