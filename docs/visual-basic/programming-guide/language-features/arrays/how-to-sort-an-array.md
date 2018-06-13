---
title: 'Gewusst wie: Sortieren eines Arrays in Visual Basic'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: a067c40e1dd0e881516cbc7769cb9afb879d1b9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646297"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="89591-102">Gewusst wie: Sortieren eines Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89591-102">How to: Sort An Array in Visual Basic</span></span>
<span data-ttu-id="89591-103">Dieses Beispiel deklariert ein Array von `String` Objekte, die mit dem Namen `zooAnimals`aufgefüllt und dann alphabetisch sortiert.</span><span class="sxs-lookup"><span data-stu-id="89591-103">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89591-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89591-104">Example</span></span>  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="89591-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="89591-105">Compiling the Code</span></span>  
 <span data-ttu-id="89591-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="89591-106">This example requires:</span></span>  
  
-   <span data-ttu-id="89591-107">Zugriff auf "mscorlib.dll" und die <xref:System> Namespace.</span><span class="sxs-lookup"><span data-stu-id="89591-107">Access to Mscorlib.dll and the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="89591-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="89591-108">Robust Programming</span></span>  
 <span data-ttu-id="89591-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="89591-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="89591-110">Array ist leer (<xref:System.ArgumentNullException> Klasse)</span><span class="sxs-lookup"><span data-stu-id="89591-110">Array is empty (<xref:System.ArgumentNullException> class)</span></span>  
  
-   <span data-ttu-id="89591-111">Array ist mehrdimensional (<xref:System.RankException> Klasse)</span><span class="sxs-lookup"><span data-stu-id="89591-111">Array is multidimensional (<xref:System.RankException> class)</span></span>  
  
-   <span data-ttu-id="89591-112">Implementiert ein oder mehrere Elemente des Arrays nicht die <xref:System.IComparable> Schnittstelle (<xref:System.InvalidOperationException> Klasse)</span><span class="sxs-lookup"><span data-stu-id="89591-112">One or more elements of the array do not implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89591-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89591-113">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="89591-114">Arrays</span><span class="sxs-lookup"><span data-stu-id="89591-114">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="89591-115">Problembehandlung bei Arrays</span><span class="sxs-lookup"><span data-stu-id="89591-115">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [<span data-ttu-id="89591-116">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="89591-116">Collections</span></span>](../../concepts/collections.md)  
 [<span data-ttu-id="89591-117">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="89591-117">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
