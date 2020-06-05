---
title: Generische Prozeduren
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
ms.openlocfilehash: 2efc0410b9d4bb663e1ff19d5a5456d7ff2c99bd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394064"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="4a719-102">Generische Prozeduren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a719-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="4a719-103">Eine *generische Prozedur*, auch als *generische Methode*bezeichnet, ist eine Prozedur, die mit mindestens einem Typparameter definiert wird.</span><span class="sxs-lookup"><span data-stu-id="4a719-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="4a719-104">Dadurch kann der aufrufenden Code die Datentypen bei jedem Aufruf der Prozedur an Ihre Anforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="4a719-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="4a719-105">Eine Prozedur ist nicht generisch, weil Sie lediglich in einer generischen Klasse oder einer generischen Struktur definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4a719-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="4a719-106">Um generisch zu sein, muss die Prozedur zusätzlich zu den normalen Parametern, die Sie annehmen kann, mindestens einen Typparameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="4a719-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="4a719-107">Eine generische Klasse oder Struktur kann nicht generische Prozeduren enthalten, und eine nicht generische Klasse, Struktur oder ein Modul kann generische Prozeduren enthalten.</span><span class="sxs-lookup"><span data-stu-id="4a719-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="4a719-108">Eine generische Prozedur kann die Typparameter in der normalen Parameterliste in Ihrem Rückgabetyp verwenden, wenn Sie über eine verfügt, und in Ihrem Prozedur Code.</span><span class="sxs-lookup"><span data-stu-id="4a719-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="4a719-109">Typableitung</span><span class="sxs-lookup"><span data-stu-id="4a719-109">Type Inference</span></span>  
 <span data-ttu-id="4a719-110">Sie können eine generische Prozedur ohne Angabe von Typargumenten aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4a719-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="4a719-111">Wenn Sie diese Methode auf diese Weise aufzurufen, versucht der Compiler, die entsprechenden Datentypen zu bestimmen, die an die Typargumente der Prozedur übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="4a719-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="4a719-112">Dies wird als *Typrückschluss*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4a719-112">This is called *type inference*.</span></span> <span data-ttu-id="4a719-113">Der folgende Code zeigt einen-Befehl, in dem der Compiler ausleitet, dass der Typ `String` an den Typparameter übergeben werden soll `t` .</span><span class="sxs-lookup"><span data-stu-id="4a719-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 <span data-ttu-id="4a719-114">Wenn der Compiler die Typargumente aus dem Kontext des Aufrufes nicht ableiten kann, meldet er einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="4a719-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="4a719-115">Eine mögliche Ursache für diesen Fehler ist ein Array Rang Konflikt.</span><span class="sxs-lookup"><span data-stu-id="4a719-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="4a719-116">Angenommen, Sie definieren einen normalen Parameter als Array eines Typparameters.</span><span class="sxs-lookup"><span data-stu-id="4a719-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="4a719-117">Wenn Sie die generische Prozedur zum Bereitstellen eines Arrays mit einem anderen Rang (Anzahl von Dimensionen) aufzurufen, bewirkt der Konflikt, dass der Typrückschluss fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="4a719-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="4a719-118">Der folgende Code zeigt einen-Befehl, bei dem ein zweidimensionales Array an eine Prozedur mit einem eindimensionalen Array übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="4a719-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="4a719-119">Sie können den Typrückschluss nur aufrufen, indem Sie alle Typargumente weglassen.</span><span class="sxs-lookup"><span data-stu-id="4a719-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="4a719-120">Wenn Sie ein Typargument angeben, müssen Sie alle angeben.</span><span class="sxs-lookup"><span data-stu-id="4a719-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="4a719-121">Der Typrückschluss wird nur für generische Prozeduren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4a719-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="4a719-122">Sie können den Typrückschluss nicht für generische Klassen, Strukturen, Schnittstellen oder Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4a719-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a719-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4a719-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="4a719-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a719-124">Description</span></span>  
 <span data-ttu-id="4a719-125">Im folgenden Beispiel wird eine generische `Function` Prozedur definiert, um ein bestimmtes Element in einem Array zu finden.</span><span class="sxs-lookup"><span data-stu-id="4a719-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="4a719-126">Er definiert einen Typparameter und verwendet ihn, um die beiden Parameter in der Parameterliste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a719-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4a719-127">Code</span><span class="sxs-lookup"><span data-stu-id="4a719-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a><span data-ttu-id="4a719-128">Kommentare</span><span class="sxs-lookup"><span data-stu-id="4a719-128">Comments</span></span>  
 <span data-ttu-id="4a719-129">Das vorherige Beispiel erfordert die Möglichkeit, mit `searchValue` jedem Element von zu vergleichen `searchArray` .</span><span class="sxs-lookup"><span data-stu-id="4a719-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="4a719-130">Um diese Möglichkeit zu gewährleisten, schränkt Sie den Typparameter ein, `T` um die- <xref:System.IComparable%601> Schnittstelle zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="4a719-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="4a719-131">Der Code verwendet die- <xref:System.IComparable%601.CompareTo%2A> Methode anstelle des- `=` Operators, da es keine Garantie gibt, dass ein für angegebenes Typargument `T` den-Operator unterstützt `=` .</span><span class="sxs-lookup"><span data-stu-id="4a719-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="4a719-132">Sie können die `findElement` Prozedur mit dem folgenden Code testen.</span><span class="sxs-lookup"><span data-stu-id="4a719-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 <span data-ttu-id="4a719-133">Der vorherige Aufruf von `MsgBox` zeigt "0", "1" und "-1" an.</span><span class="sxs-lookup"><span data-stu-id="4a719-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a719-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a719-134">See also</span></span>

- [<span data-ttu-id="4a719-135">Generische Typen in Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a719-135">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="4a719-136">Vorgehensweise: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann</span><span class="sxs-lookup"><span data-stu-id="4a719-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="4a719-137">Vorgehensweise: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="4a719-137">How to: Use a Generic Class</span></span>](how-to-use-a-generic-class.md)
- [<span data-ttu-id="4a719-138">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="4a719-138">Procedures</span></span>](../procedures/index.md)
- [<span data-ttu-id="4a719-139">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4a719-139">Procedure Parameters and Arguments</span></span>](../procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4a719-140">Type List</span><span class="sxs-lookup"><span data-stu-id="4a719-140">Type List</span></span>](../../../language-reference/statements/type-list.md)
- [<span data-ttu-id="4a719-141">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="4a719-141">Parameter List</span></span>](../../../language-reference/statements/parameter-list.md)
