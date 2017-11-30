---
title: "Generische Prozeduren in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e019ca32277f93f798e99e996a3670c8302ba9b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="d1961-102">Generische Prozeduren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1961-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="d1961-103">Ein *generische Prozedur*auch Namens eine *generische Methode*, wird eine Prozedur mit mindestens einem Typparameter definiert.</span><span class="sxs-lookup"><span data-stu-id="d1961-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="d1961-104">Dadurch wird den aufrufenden Code ein, um die Datentypen, die Anforderungen anzupassen, jedes Mal der Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d1961-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="d1961-105">Eine Prozedur ist nicht generisch, einfach durch innerhalb einer generischen Klasse oder eine generische Struktur definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d1961-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="d1961-106">Um generisch sein, muss die Prozedur über mindestens einen Typparameter, zusätzlich zum normalen Parameter dauern dauern kann.</span><span class="sxs-lookup"><span data-stu-id="d1961-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="d1961-107">Modul kann generische Prozeduren enthalten, oder einer generischen Klasse oder Struktur nicht generischen Prozeduren und eine nicht generische Klasse, Struktur, enthalten.</span><span class="sxs-lookup"><span data-stu-id="d1961-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="d1961-108">Eine generische Prozedur können dessen Typparameter angegeben in der normalen Parameterliste, ihren Rückgabetyp, wenn sie ein, und in der Prozedur Code verfügt.</span><span class="sxs-lookup"><span data-stu-id="d1961-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="d1961-109">Typableitung</span><span class="sxs-lookup"><span data-stu-id="d1961-109">Type Inference</span></span>  
 <span data-ttu-id="d1961-110">Sie können eine generische Prozedur aufrufen, ohne Angabe von Typargumenten an.</span><span class="sxs-lookup"><span data-stu-id="d1961-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="d1961-111">Wenn Sie auf diese Weise aufrufen, versucht der Compiler die entsprechenden Datentypen Übergabe an die Prozedur Typargumente bestimmen.</span><span class="sxs-lookup"><span data-stu-id="d1961-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="d1961-112">Hierbei spricht *Typrückschluss*.</span><span class="sxs-lookup"><span data-stu-id="d1961-112">This is called *type inference*.</span></span> <span data-ttu-id="d1961-113">Der folgende Code zeigt einen Aufruf in die leitet der Compiler, dass er Typ übergeben soll `String` an den Typparameter `t`.</span><span class="sxs-lookup"><span data-stu-id="d1961-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 <span data-ttu-id="d1961-114">Wenn der Compiler die Typargumente aus dem Kontext des Aufrufs ableiten kann, meldet er einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="d1961-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="d1961-115">Eine mögliche Ursache für einen derartigen Fehler gibt ein Array-Rank-Konflikt.</span><span class="sxs-lookup"><span data-stu-id="d1961-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="d1961-116">Nehmen Sie beispielsweise an, dass Sie als ein Array eines Typparameters einen normalen Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="d1961-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="d1961-117">Wenn Sie die generische Prozedur aufrufen, führt dazu, dass ein Array eines abweichenden Rang (Anzahl der Dimensionen) angeben, des Konflikts Typrückschluss fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="d1961-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="d1961-118">Der folgende Code zeigt einen Aufruf in dem ein zweidimensionales Array an eine Prozedur übergeben wird, das ein eindimensionales Array erwartet.</span><span class="sxs-lookup"><span data-stu-id="d1961-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 <span data-ttu-id="d1961-119">Typrückschluss kann nur durch das Weglassen der Typargumente aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d1961-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="d1961-120">Wenn Sie ein Typargument angeben, müssen Sie alle angeben.</span><span class="sxs-lookup"><span data-stu-id="d1961-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="d1961-121">Typrückschluss wird nur für generische Prozeduren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d1961-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="d1961-122">Typrückschluss auf generische Klassen, Strukturen, Schnittstellen und Delegaten kann nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d1961-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1961-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d1961-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d1961-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1961-124">Description</span></span>  
 <span data-ttu-id="d1961-125">Das folgende Beispiel definiert einen generischen `Function` Verfahren, um ein bestimmtes Element in einem Array zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="d1961-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="d1961-126">Er definiert einen Typparameter und verwendet, um die beiden Parameter in der Parameterliste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1961-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d1961-127">Code</span><span class="sxs-lookup"><span data-stu-id="d1961-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="d1961-128">Kommentare</span><span class="sxs-lookup"><span data-stu-id="d1961-128">Comments</span></span>  
 <span data-ttu-id="d1961-129">Das obige Beispiel erfordert, dass vergleichen `searchValue` für jedes Element `searchArray`.</span><span class="sxs-lookup"><span data-stu-id="d1961-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="d1961-130">Um dies zu garantieren, wird den Typparameter `T` zum Implementieren der <xref:System.IComparable%601> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d1961-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="d1961-131">Der Code verwendet die <xref:System.IComparable%601.CompareTo%2A> -Methode anstelle der `=` -Operator, da keine Garantie, die ein Type-Argument besteht für angegeben `T` unterstützt die `=` Operator.</span><span class="sxs-lookup"><span data-stu-id="d1961-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="d1961-132">Sie können testen, die `findElement` Prozedur durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="d1961-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 <span data-ttu-id="d1961-133">Die vorangehenden Aufrufe von `MsgBox` "0", "1" und "-1" bzw. anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d1961-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1961-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1961-134">See Also</span></span>  
 [<span data-ttu-id="d1961-135">Generische Typen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1961-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="d1961-136">Gewusst wie: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann</span><span class="sxs-lookup"><span data-stu-id="d1961-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [<span data-ttu-id="d1961-137">Gewusst wie: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="d1961-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="d1961-138">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d1961-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="d1961-139">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="d1961-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="d1961-140">Typliste</span><span class="sxs-lookup"><span data-stu-id="d1961-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="d1961-141">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="d1961-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
