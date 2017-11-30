---
title: 'Gewusst wie: Zuweisen eines Arrays zu einem anderen Array (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0dd2d678bbfdeaa6b12b5b5a4f69d0fbca8c1944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="ef67c-102">Gewusst wie: Zuweisen eines Arrays zu einem anderen Array (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef67c-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>
<span data-ttu-id="ef67c-103">Da Arrays Objekte sind, können Sie sie in zuweisungsanweisungen wie andere Objekttypen.</span><span class="sxs-lookup"><span data-stu-id="ef67c-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="ef67c-104">Eine Arrayvariable enthält einen Zeiger auf die Daten enthalten sind, die die Elemente des Arrays und die Informationen Rang und die Länge und eine Zuordnung kopiert nur this-Zeiger.</span><span class="sxs-lookup"><span data-stu-id="ef67c-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>  
  
### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="ef67c-105">Zuweisen eines Arrays in ein anderes array</span><span class="sxs-lookup"><span data-stu-id="ef67c-105">To assign one array to another array</span></span>  
  
1.  <span data-ttu-id="ef67c-106">Stellen Sie sicher, dass die beiden Arrays den gleichen Rang (Anzahl der Dimensionen) und kompatible Datentypen haben.</span><span class="sxs-lookup"><span data-stu-id="ef67c-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>  
  
2.  <span data-ttu-id="ef67c-107">Verwenden Sie eine standardmäßige zuweisungsanweisung Zielarray Quellarray zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ef67c-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="ef67c-108">Führen Sie nicht entweder Arrayname mit Klammern.</span><span class="sxs-lookup"><span data-stu-id="ef67c-108">Do not follow either array name with parentheses.</span></span>  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 <span data-ttu-id="ef67c-109">Wenn Sie ein Array in einen anderen zuweisen, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="ef67c-109">When you assign one array to another, the following rules apply:</span></span>  
  
-   <span data-ttu-id="ef67c-110">**Gleicher Rang.**</span><span class="sxs-lookup"><span data-stu-id="ef67c-110">**Equal Ranks.**</span></span> <span data-ttu-id="ef67c-111">Der Rang (Anzahl der Dimensionen) des Zielarrays muss das Quellarray identisch sein.</span><span class="sxs-lookup"><span data-stu-id="ef67c-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>  
  
     <span data-ttu-id="ef67c-112">Bereitgestellten den Rang der zwei Arrays gleich sind, müssen die Dimensionen nicht identisch sein.</span><span class="sxs-lookup"><span data-stu-id="ef67c-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="ef67c-113">Die Anzahl der Elemente in einer bestimmten Dimension kann bei der Zuordnung ändern.</span><span class="sxs-lookup"><span data-stu-id="ef67c-113">The number of elements in a given dimension can change during assignment.</span></span>  
  
-   <span data-ttu-id="ef67c-114">**Elementtypen.**</span><span class="sxs-lookup"><span data-stu-id="ef67c-114">**Element Types.**</span></span> <span data-ttu-id="ef67c-115">Entweder beide Arrays müssen *Verweistyp* Elemente oder beide Arrays müssen *Werttyp* Elemente.</span><span class="sxs-lookup"><span data-stu-id="ef67c-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="ef67c-116">Weitere Informationen finden Sie unter [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="ef67c-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
    -   <span data-ttu-id="ef67c-117">Wenn beide Arrays Wertelemente-Typ haben, müssen die Element-Datentypen dem genau übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ef67c-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="ef67c-118">Die einzige Ausnahme hierbei ist, dass Sie ein Array von zuweisen können `Enum` Elemente in ein Array des Basistyps dieses `Enum`.</span><span class="sxs-lookup"><span data-stu-id="ef67c-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>  
  
    -   <span data-ttu-id="ef67c-119">Wenn beide Arrays Referenztyp Elemente verfügen, muss die Datenquellen-Elementtyp der Ziel-Elementtyp abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ef67c-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="ef67c-120">Wenn dies der Fall ist, haben die beiden Arrays den gleichen vererbungsbeziehung als ihre Elemente.</span><span class="sxs-lookup"><span data-stu-id="ef67c-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="ef67c-121">Hierbei spricht *Array-Kovarianz*.</span><span class="sxs-lookup"><span data-stu-id="ef67c-121">This is called *array covariance*.</span></span>  
  
 <span data-ttu-id="ef67c-122">Der Compiler meldet einen Fehler, wenn die oben genannten Regeln, z. B. verletzt werden die Datentypen nicht kompatibel sind oder die Ränge ungleich sind.</span><span class="sxs-lookup"><span data-stu-id="ef67c-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="ef67c-123">Sie können die Fehlerbehandlung in den Code, um sicherzustellen, dass die Arrays kompatibel sind, bevor Sie versuchen, eine Zuordnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ef67c-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="ef67c-124">Sie können auch die [TryCast-Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) Schlüsselwort, wenn Sie, um zu vermeiden, dass eine Ausnahme ausgelöst möchten.</span><span class="sxs-lookup"><span data-stu-id="ef67c-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef67c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef67c-125">See Also</span></span>  
 [<span data-ttu-id="ef67c-126">Arrays</span><span class="sxs-lookup"><span data-stu-id="ef67c-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="ef67c-127">Problembehandlung bei Arrays</span><span class="sxs-lookup"><span data-stu-id="ef67c-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [<span data-ttu-id="ef67c-128">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ef67c-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="ef67c-129">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="ef67c-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
