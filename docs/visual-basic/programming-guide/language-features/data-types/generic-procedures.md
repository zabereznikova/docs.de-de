---
title: Generische Prozeduren in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: 4aed16ce9eb59da54156a0cd5f1594819788521b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818916"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="d4c38-102">Generische Prozeduren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4c38-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="d4c38-103">Ein *generische Prozedur*auch Namens eine *generische Methode*, wird eine Prozedur mit mindestens einem Typparameter definiert.</span><span class="sxs-lookup"><span data-stu-id="d4c38-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="d4c38-104">Dadurch wird den aufrufenden Code auf die Datentypen, die Anforderungen jedes Mal passen sie die Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="d4c38-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="d4c38-105">Eine Prozedur ist nicht generisch, einfach aufgrund der innerhalb einer generischen Klasse oder eine generische Struktur definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d4c38-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="d4c38-106">Um generisch sein, muss die Prozedur mindestens einen Typparameter, zusätzlich zum normalen Parameter ausführen, dauert es möglicherweise.</span><span class="sxs-lookup"><span data-stu-id="d4c38-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="d4c38-107">Module kann generische Prozeduren enthält, oder einer generischen Klasse oder Struktur nicht generischen Prozeduren und eine nicht generische Klasse, Struktur, enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4c38-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="d4c38-108">Eine generische Prozedur können dessen Typparameter in der normalen Parameterliste, ihren Rückgabetyp, wenn sie über ein, und in der Prozedur Code verfügt.</span><span class="sxs-lookup"><span data-stu-id="d4c38-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="d4c38-109">Typableitung</span><span class="sxs-lookup"><span data-stu-id="d4c38-109">Type Inference</span></span>  
 <span data-ttu-id="d4c38-110">Sie können eine generische Prozedur aufrufen, ohne Angabe von Typargumenten überhaupt.</span><span class="sxs-lookup"><span data-stu-id="d4c38-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="d4c38-111">Wenn Sie auf diese Weise aufrufen, versucht der Compiler, um zu bestimmen, die entsprechenden Datentypen Übergabe an die Prozedur Typargumente.</span><span class="sxs-lookup"><span data-stu-id="d4c38-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="d4c38-112">Dies wird als bezeichnet *Typrückschluss*.</span><span class="sxs-lookup"><span data-stu-id="d4c38-112">This is called *type inference*.</span></span> <span data-ttu-id="d4c38-113">Der folgende Code zeigt einen Aufruf in die leitet der Compiler, dass er Typ übergeben soll `String` an den Typparameter `t`.</span><span class="sxs-lookup"><span data-stu-id="d4c38-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 <span data-ttu-id="d4c38-114">Wenn der Compiler die Typargumente aus dem Kontext des Aufrufs nicht ableiten kann, wird ein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="d4c38-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="d4c38-115">Eine mögliche Ursache für einen derartigen Fehler ist ein Array Rank-Konflikt.</span><span class="sxs-lookup"><span data-stu-id="d4c38-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="d4c38-116">Nehmen wir beispielsweise an, dass Sie einen normalen Parameter als Array von einem Typparameter definieren.</span><span class="sxs-lookup"><span data-stu-id="d4c38-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="d4c38-117">Rufen Sie die generische Prozedur bewirkt, dass ein Array von einem abweichenden Rang (Anzahl der Dimensionen) angeben, des Konflikts Typrückschluss fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="d4c38-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="d4c38-118">Der folgende Code zeigt einen Aufruf in das ein zweidimensionales Array an eine Prozedur übergeben wird, das ein eindimensionales Array erwartet.</span><span class="sxs-lookup"><span data-stu-id="d4c38-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="d4c38-119">Sie können den Typrückschluss aufrufen, nur, indem Sie alle Typargumente auslassen.</span><span class="sxs-lookup"><span data-stu-id="d4c38-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="d4c38-120">Wenn Sie ein Typargument angeben, müssen Sie alle angeben.</span><span class="sxs-lookup"><span data-stu-id="d4c38-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="d4c38-121">Typrückschluss ist nur für generische Prozeduren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4c38-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="d4c38-122">Typrückschluss für generische Klassen, Strukturen, Schnittstellen oder Delegaten kann nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d4c38-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4c38-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4c38-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d4c38-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4c38-124">Description</span></span>  
 <span data-ttu-id="d4c38-125">Das folgende Beispiel definiert einen generischen `Function` Verfahren zum Suchen eines bestimmten Elements in einem Array.</span><span class="sxs-lookup"><span data-stu-id="d4c38-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="d4c38-126">Er definiert einen Typparameter und wird verwendet, um die beiden Parameter in der Parameterliste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d4c38-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d4c38-127">Code</span><span class="sxs-lookup"><span data-stu-id="d4c38-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a><span data-ttu-id="d4c38-128">Kommentare</span><span class="sxs-lookup"><span data-stu-id="d4c38-128">Comments</span></span>  
 <span data-ttu-id="d4c38-129">Das obige Beispiel erfordert die Möglichkeit, vergleichen `searchValue` für jedes Element `searchArray`.</span><span class="sxs-lookup"><span data-stu-id="d4c38-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="d4c38-130">Um dies zu garantieren, schränkt sie die Typparameter `T` zum Implementieren der <xref:System.IComparable%601> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d4c38-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="d4c38-131">Der Code verwendet die <xref:System.IComparable%601.CompareTo%2A> -Methode anstelle der `=` -Operator, da keine Garantie, die ein Typargument besteht für angegeben `T` unterstützt die `=` Operator.</span><span class="sxs-lookup"><span data-stu-id="d4c38-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="d4c38-132">Sie können testen, die `findElement` Prozedur durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="d4c38-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 <span data-ttu-id="d4c38-133">Der vorherigen Aufrufe von `MsgBox` anzeigen bzw. "0", "1" und "-1".</span><span class="sxs-lookup"><span data-stu-id="d4c38-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c38-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4c38-134">See also</span></span>

- [<span data-ttu-id="d4c38-135">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4c38-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="d4c38-136">Vorgehensweise: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann</span><span class="sxs-lookup"><span data-stu-id="d4c38-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="d4c38-137">Vorgehensweise: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="d4c38-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="d4c38-138">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d4c38-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="d4c38-139">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="d4c38-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d4c38-140">Typliste</span><span class="sxs-lookup"><span data-stu-id="d4c38-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="d4c38-141">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="d4c38-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
