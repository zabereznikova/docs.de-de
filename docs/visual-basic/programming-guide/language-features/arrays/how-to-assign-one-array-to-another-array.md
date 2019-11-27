---
title: 'Gewusst wie: Zuweisen eines Arrays zu einem anderen Array'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: be5337e36c2cc7ad9f9b32182b8575ac66bb4a50
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351892"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="99a00-102">Gewusst wie: Zuweisen eines Arrays zu einem anderen Array (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99a00-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="99a00-103">Da Arrays Objekte sind, können Sie Sie in Zuweisungs Anweisungen wie anderen Objekttypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="99a00-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="99a00-104">Eine Array Variable enthält einen Zeiger auf die Daten, die die Array Elemente und die Rang-und Längen Informationen bilden, und eine Zuweisung kopiert nur diesen Zeiger.</span><span class="sxs-lookup"><span data-stu-id="99a00-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="99a00-105">So weisen Sie ein Array einem anderen Array zu</span><span class="sxs-lookup"><span data-stu-id="99a00-105">To assign one array to another array</span></span>

1. <span data-ttu-id="99a00-106">Stellen Sie sicher, dass die beiden Arrays denselben Rang (Anzahl von Dimensionen) und kompatible Element Datentypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="99a00-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="99a00-107">Verwenden Sie eine Standard Zuweisungsanweisung zum Zuweisen des Quell Arrays zum Zielarray.</span><span class="sxs-lookup"><span data-stu-id="99a00-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="99a00-108">Folgen Sie keinem der Array Namen mit Klammern.</span><span class="sxs-lookup"><span data-stu-id="99a00-108">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="99a00-109">Wenn Sie ein Array einem anderen zuweisen, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="99a00-109">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="99a00-110">**Gleiche Ränge.**</span><span class="sxs-lookup"><span data-stu-id="99a00-110">**Equal Ranks.**</span></span> <span data-ttu-id="99a00-111">Der Rang (Anzahl der Dimensionen) des Zielarrays muss mit dem des Quell Arrays identisch sein.</span><span class="sxs-lookup"><span data-stu-id="99a00-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="99a00-112">Wenn die Ränge der beiden Arrays gleich sind, müssen die Dimensionen nicht gleich sein.</span><span class="sxs-lookup"><span data-stu-id="99a00-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="99a00-113">Die Anzahl von Elementen in einer bestimmten Dimension kann sich während der Zuweisung ändern.</span><span class="sxs-lookup"><span data-stu-id="99a00-113">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="99a00-114">**Element Typen.**</span><span class="sxs-lookup"><span data-stu-id="99a00-114">**Element Types.**</span></span> <span data-ttu-id="99a00-115">Beide Arrays müssen über *Verweistyp* Elemente verfügen, oder beide Arrays müssen *Werttyp* Elemente aufweisen.</span><span class="sxs-lookup"><span data-stu-id="99a00-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="99a00-116">Weitere Informationen finden Sie unter [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="99a00-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="99a00-117">Wenn beide Arrays Werttyp Elemente aufweisen, müssen die Element Datentypen exakt identisch sein.</span><span class="sxs-lookup"><span data-stu-id="99a00-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="99a00-118">Die einzige Ausnahme besteht darin, dass Sie ein Array von `Enum` Elementen einem Array des Basistyps dieses `Enum`zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="99a00-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="99a00-119">Wenn beide Arrays Verweistyp Elemente aufweisen, muss der Quell Elementtyp vom Ziel Elementtyp abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="99a00-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="99a00-120">Wenn dies der Fall ist, haben die beiden Arrays dieselbe Vererbungs Beziehung wie ihre Elemente.</span><span class="sxs-lookup"><span data-stu-id="99a00-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="99a00-121">Dies wird als *Array Kovarianz*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="99a00-121">This is called *array covariance*.</span></span>

<span data-ttu-id="99a00-122">Der Compiler meldet einen Fehler, wenn die oben genannten Regeln verletzt werden, z. b. wenn die Datentypen nicht kompatibel sind oder die Ränge ungleich sind.</span><span class="sxs-lookup"><span data-stu-id="99a00-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="99a00-123">Sie können dem Code Fehlerbehandlung hinzufügen, um sicherzustellen, dass die Arrays kompatibel sind, bevor Sie eine Zuweisung versuchen.</span><span class="sxs-lookup"><span data-stu-id="99a00-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="99a00-124">Sie können auch das [TryCast-Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) Schlüsselwort verwenden, wenn Sie keine Ausnahme auslösen möchten.</span><span class="sxs-lookup"><span data-stu-id="99a00-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="99a00-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99a00-125">See also</span></span>

- [<span data-ttu-id="99a00-126">Arrays</span><span class="sxs-lookup"><span data-stu-id="99a00-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="99a00-127">Problembehandlung bei Arrays</span><span class="sxs-lookup"><span data-stu-id="99a00-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="99a00-128">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="99a00-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="99a00-129">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="99a00-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
