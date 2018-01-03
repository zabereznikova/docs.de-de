---
title: 'Gewusst wie: Sortieren eines Arrays in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f24c0625058dbd960411d5981b4e98e0e9422b99
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="ac80f-102">Gewusst wie: Sortieren eines Arrays in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac80f-102">How to: Sort An Array in Visual Basic</span></span>
<span data-ttu-id="ac80f-103">Dieses Beispiel deklariert ein Array von `String` Objekte, die mit dem Namen `zooAnimals`aufgefüllt und dann alphabetisch sortiert.</span><span class="sxs-lookup"><span data-stu-id="ac80f-103">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac80f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac80f-104">Example</span></span>  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ac80f-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ac80f-105">Compiling the Code</span></span>  
 <span data-ttu-id="ac80f-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ac80f-106">This example requires:</span></span>  
  
-   <span data-ttu-id="ac80f-107">Zugriff auf "mscorlib.dll" und die <xref:System> Namespace.</span><span class="sxs-lookup"><span data-stu-id="ac80f-107">Access to Mscorlib.dll and the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ac80f-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="ac80f-108">Robust Programming</span></span>  
 <span data-ttu-id="ac80f-109">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="ac80f-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="ac80f-110">Array ist leer (<xref:System.ArgumentNullException> Klasse)</span><span class="sxs-lookup"><span data-stu-id="ac80f-110">Array is empty (<xref:System.ArgumentNullException> class)</span></span>  
  
-   <span data-ttu-id="ac80f-111">Array ist mehrdimensional (<xref:System.RankException> Klasse)</span><span class="sxs-lookup"><span data-stu-id="ac80f-111">Array is multidimensional (<xref:System.RankException> class)</span></span>  
  
-   <span data-ttu-id="ac80f-112">Implementiert ein oder mehrere Elemente des Arrays nicht die <xref:System.IComparable> Schnittstelle (<xref:System.InvalidOperationException> Klasse)</span><span class="sxs-lookup"><span data-stu-id="ac80f-112">One or more elements of the array do not implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac80f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac80f-113">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="ac80f-114">Arrays</span><span class="sxs-lookup"><span data-stu-id="ac80f-114">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="ac80f-115">Problembehandlung bei Arrays</span><span class="sxs-lookup"><span data-stu-id="ac80f-115">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [<span data-ttu-id="ac80f-116">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="ac80f-116">Collections</span></span>](../../concepts/collections.md)  
 [<span data-ttu-id="ac80f-117">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ac80f-117">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
