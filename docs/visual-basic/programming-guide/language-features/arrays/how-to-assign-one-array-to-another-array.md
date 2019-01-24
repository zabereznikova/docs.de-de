---
title: 'Vorgehensweise: Zuweisen eines Arrays zu einem anderen Array (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: f2617d270caf5ed4ade68934486fee6afb6c413f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572720"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="12661-102">Vorgehensweise: Zuweisen eines Arrays zu einem anderen Array (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12661-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>
<span data-ttu-id="12661-103">Da Arrays Objekte sind, können Sie sie in zuweisungsanweisungen wie andere Objekttypen.</span><span class="sxs-lookup"><span data-stu-id="12661-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="12661-104">Eine Array-Variable enthält einen Zeiger auf die Daten enthalten sind, die die Elemente des Arrays und die Informationen Rang und die Länge und eine Zuordnung kopiert nur this-Zeiger.</span><span class="sxs-lookup"><span data-stu-id="12661-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>  
  
### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="12661-105">Zuweisen eines Arrays zu einem anderen array</span><span class="sxs-lookup"><span data-stu-id="12661-105">To assign one array to another array</span></span>  
  
1.  <span data-ttu-id="12661-106">Stellen Sie sicher, dass die beiden Arrays den gleichen Rang (Anzahl der Dimensionen) und kompatiblen Elements-Datentypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="12661-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>  
  
2.  <span data-ttu-id="12661-107">Verwenden Sie eine standardmäßige zuweisungsanweisung, um das Quellarray in den Zielarray zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="12661-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="12661-108">Führen Sie nicht entweder Arrayname mit Klammern.</span><span class="sxs-lookup"><span data-stu-id="12661-108">Do not follow either array name with parentheses.</span></span>  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 <span data-ttu-id="12661-109">Wenn Sie ein Array zu einem anderen zuweisen, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="12661-109">When you assign one array to another, the following rules apply:</span></span>  
  
-   <span data-ttu-id="12661-110">**Gleicher Rang.**</span><span class="sxs-lookup"><span data-stu-id="12661-110">**Equal Ranks.**</span></span> <span data-ttu-id="12661-111">Der Rang (Anzahl der Dimensionen) des Zielarrays muss des Quellarrays, identisch sein.</span><span class="sxs-lookup"><span data-stu-id="12661-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>  
  
     <span data-ttu-id="12661-112">Sofern die Ränge von zwei Arrays gleich sind, müssen die Dimensionen nicht gleich sind.</span><span class="sxs-lookup"><span data-stu-id="12661-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="12661-113">Die Anzahl der Elemente in der angegebenen Dimension kann bei der Zuordnung ändern.</span><span class="sxs-lookup"><span data-stu-id="12661-113">The number of elements in a given dimension can change during assignment.</span></span>  
  
-   <span data-ttu-id="12661-114">**Elementtypen.**</span><span class="sxs-lookup"><span data-stu-id="12661-114">**Element Types.**</span></span> <span data-ttu-id="12661-115">Es müssen entweder beide Arrays *Verweistyp* Elemente oder beide Arrays müssen *Werttyp* Elemente.</span><span class="sxs-lookup"><span data-stu-id="12661-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="12661-116">Weitere Informationen finden Sie unter [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="12661-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
    -   <span data-ttu-id="12661-117">Wenn beide Arrays Elementen mit Werttyp haben, müssen die Element-Datentypen genau übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="12661-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="12661-118">Die einzige Ausnahme hierbei ist, dass Sie ein Array von zuweisen können `Enum` Elemente in ein Array des Basistyps dieses `Enum`.</span><span class="sxs-lookup"><span data-stu-id="12661-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>  
  
    -   <span data-ttu-id="12661-119">Wenn beide Arrays Elemente aufweisen, muss der Elementtyp der Datenquelle von der Ziel-Elementtyp abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="12661-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="12661-120">Wenn dies der Fall ist, müssen die beiden Arrays die gleiche vererbungsbeziehung als ihre Elemente.</span><span class="sxs-lookup"><span data-stu-id="12661-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="12661-121">Dies wird als bezeichnet *Array-Kovarianz*.</span><span class="sxs-lookup"><span data-stu-id="12661-121">This is called *array covariance*.</span></span>  
  
 <span data-ttu-id="12661-122">Der Compiler meldet, dass ein Fehler, wenn die oben genannten Regeln, z. B. verletzt werden die Datentypen nicht kompatibel sind oder die Ränge ungleich sind.</span><span class="sxs-lookup"><span data-stu-id="12661-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="12661-123">Sie können die Fehlerbehandlung in Ihrem Code, um sicherzustellen, dass die Arrays kompatibel sind, bevor Sie versuchen, eine Zuordnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="12661-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="12661-124">Sie können auch die [TryCast-Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) Schlüsselwort, wenn Sie das Auslösen einer Ausnahme vermeiden möchten.</span><span class="sxs-lookup"><span data-stu-id="12661-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12661-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12661-125">See also</span></span>
- [<span data-ttu-id="12661-126">Arrays</span><span class="sxs-lookup"><span data-stu-id="12661-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="12661-127">Problembehandlung bei Arrays</span><span class="sxs-lookup"><span data-stu-id="12661-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="12661-128">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="12661-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="12661-129">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="12661-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
