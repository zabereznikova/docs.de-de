---
title: Arrays
description: 'Erfahren Sie, wie Sie Arrays in der Programmiersprache F # erstellen und verwenden.'
ms.date: 08/13/2020
ms.openlocfilehash: 96b0d7eaf10d5afcd9a647681d5c2ef2d2fba335
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739750"
---
# <a name="arrays"></a><span data-ttu-id="daaa9-103">Arrays</span><span class="sxs-lookup"><span data-stu-id="daaa9-103">Arrays</span></span>

<span data-ttu-id="daaa9-104">Arrays sind nullbasierte, änderbare Sequenzen fester Größe von aufeinander folgenden Datenelementen, die alle den gleichen Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-104">Arrays are fixed-size, zero-based, mutable collections of consecutive data elements that are all of the same type.</span></span>

## <a name="create-arrays"></a><span data-ttu-id="daaa9-105">Erstellen von Arrays</span><span class="sxs-lookup"><span data-stu-id="daaa9-105">Create arrays</span></span>

<span data-ttu-id="daaa9-106">Sie können Arrays auf verschiedene Arten erstellen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-106">You can create arrays in several ways.</span></span> <span data-ttu-id="daaa9-107">Sie können ein kleines Array erstellen, indem Sie aufeinander folgende Werte zwischen `[|` und `|]` und durch Semikolons getrennt auflisten, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-107">You can create a small array by listing consecutive values between `[|` and `|]` and separated by semicolons, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet1.fs)]

<span data-ttu-id="daaa9-108">Sie können auch jedes Element in einer eigenen Zeile anordnen. In diesem Fall ist das Semikolontrennzeichen optional.</span><span class="sxs-lookup"><span data-stu-id="daaa9-108">You can also put each element on a separate line, in which case the semicolon separator is optional.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet2.fs)]

<span data-ttu-id="daaa9-109">Der Typ der Arrayelemente wird von den verwendeten Literalen abgeleitet, und er muss konsistent sein.</span><span class="sxs-lookup"><span data-stu-id="daaa9-109">The type of the array elements is inferred from the literals used and must be consistent.</span></span> <span data-ttu-id="daaa9-110">Somit verursacht der folgende Code einen Fehler, da 1.0 ein Gleitkommawert ist und 2 und 3 ganze Zahlen sind.</span><span class="sxs-lookup"><span data-stu-id="daaa9-110">The following code causes an error because 1.0 is a float and 2 and 3 are integers.</span></span>

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

<span data-ttu-id="daaa9-111">Sie können Arrays mithilfe von Sequenzausdrücken erstellen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-111">You can also use sequence expressions to create arrays.</span></span> <span data-ttu-id="daaa9-112">Im folgenden Beispiel wird ein Array aus den Quadraten von ganzen Zahlen zwischen 1 und 10 erstellt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-112">Following is an example that creates an array of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet3.fs)]

<span data-ttu-id="daaa9-113">Verwenden Sie `Array.zeroCreate`, um ein Array zu erstellen, dessen sämtliche Elemente mit 0 (null) initialisiert sind.</span><span class="sxs-lookup"><span data-stu-id="daaa9-113">To create an array in which all the elements are initialized to zero, use `Array.zeroCreate`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="access-elements"></a><span data-ttu-id="daaa9-114">Zugriffs Elemente</span><span class="sxs-lookup"><span data-stu-id="daaa9-114">Access elements</span></span>

<span data-ttu-id="daaa9-115">Sie können auf Array Elemente zugreifen, indem Sie einen Punkt Operator ( `.` ) und eckige Klammern ( `[` und `]` ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-115">You can access array elements by using a dot operator (`.`) and brackets (`[` and `]`).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet5.fs)]

<span data-ttu-id="daaa9-116">Array Indizes beginnen bei 0.</span><span class="sxs-lookup"><span data-stu-id="daaa9-116">Array indexes start at 0.</span></span>

<span data-ttu-id="daaa9-117">Der Zugriff auf Arrayelemente kann auch mit Slicenotation erfolgen, die es Ihnen ermöglicht, einen Teilbereich des Arrays anzugeben.</span><span class="sxs-lookup"><span data-stu-id="daaa9-117">You can also access array elements by using slice notation, which enables you to specify a subrange of the array.</span></span> <span data-ttu-id="daaa9-118">Im Folgenden erhalten Sie Beispiele für Slicenotation.</span><span class="sxs-lookup"><span data-stu-id="daaa9-118">Examples of slice notation follow.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet51.fs)]

<span data-ttu-id="daaa9-119">Bei Verwendung von Slicenotation wird eine neue Kopie des Arrays erstellt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-119">When slice notation is used, a new copy of the array is created.</span></span>

## <a name="array-types-and-modules"></a><span data-ttu-id="daaa9-120">Array Typen und-Module</span><span class="sxs-lookup"><span data-stu-id="daaa9-120">Array types and modules</span></span>

<span data-ttu-id="daaa9-121">Alle F#-Arrays sind vom .NET Framework-Typ <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="daaa9-121">The type of all F# arrays is the .NET Framework type <xref:System.Array?displayProperty=nameWithType>.</span></span> <span data-ttu-id="daaa9-122">Daher unterstützen F#-Arrays alle in <xref:System.Array?displayProperty=nameWithType> verfügbaren Funktionen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-122">Therefore, F# arrays support all the functionality available in <xref:System.Array?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="daaa9-123">Das [ `Array` Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html) unterstützt Vorgänge für eindimensionale Arrays.</span><span class="sxs-lookup"><span data-stu-id="daaa9-123">The [`Array` module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html) supports operations on one-dimensional arrays.</span></span> <span data-ttu-id="daaa9-124">Die Module `Array2D`, `Array3D` und `Array4D` enthalten Funktionen, die Operationen für Arrays mit zwei, drei bzw. vier Dimensionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-124">The modules `Array2D`, `Array3D`, and `Array4D` contain functions that support operations on arrays of two, three, and four dimensions, respectively.</span></span> <span data-ttu-id="daaa9-125">Mit <xref:System.Array?displayProperty=nameWithType> können Sie Arrays mit einem Rang größer vier erstellen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-125">You can create arrays of rank greater than four by using <xref:System.Array?displayProperty=nameWithType>.</span></span>

### <a name="simple-functions"></a><span data-ttu-id="daaa9-126">Einfache Funktionen</span><span class="sxs-lookup"><span data-stu-id="daaa9-126">Simple functions</span></span>

<span data-ttu-id="daaa9-127">[`Array.get`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#get) Ruft ein Element ab.</span><span class="sxs-lookup"><span data-stu-id="daaa9-127">[`Array.get`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#get) gets an element.</span></span> <span data-ttu-id="daaa9-128">[`Array.length`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#length) Gibt die Länge eines Arrays an.</span><span class="sxs-lookup"><span data-stu-id="daaa9-128">[`Array.length`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#length) gives the length of an array.</span></span> <span data-ttu-id="daaa9-129">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) legt ein Element auf einen angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="daaa9-129">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) sets an element to a specified value.</span></span> <span data-ttu-id="daaa9-130">Im folgenden Codebeispiel wird die Verwendung dieser Funktionen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="daaa9-130">The following code example illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

<span data-ttu-id="daaa9-131">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-131">The output is as follows.</span></span>

```console
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a><span data-ttu-id="daaa9-132">Funktionen zum Erstellen von Arrays</span><span class="sxs-lookup"><span data-stu-id="daaa9-132">Functions that create arrays</span></span>

<span data-ttu-id="daaa9-133">Mehrere Funktionen erstellen Arrays, ohne ein vorhandenes Array zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="daaa9-133">Several functions create arrays without requiring an existing array.</span></span> <span data-ttu-id="daaa9-134">[`Array.empty`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#empty) erstellt ein neues Array, das keine-Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="daaa9-134">[`Array.empty`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#empty) creates a new array that does not contain any elements.</span></span> <span data-ttu-id="daaa9-135">[`Array.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#create) erstellt ein Array mit einer angegebenen Größe und legt alle Elemente auf bereitgestellte Werte fest.</span><span class="sxs-lookup"><span data-stu-id="daaa9-135">[`Array.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#create) creates an array of a specified size and sets all the elements to provided values.</span></span> <span data-ttu-id="daaa9-136">[`Array.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#init) erstellt ein Array, wobei eine Dimension und eine Funktion zum Generieren der Elemente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-136">[`Array.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#init) creates an array, given a dimension and a function to generate the elements.</span></span> <span data-ttu-id="daaa9-137">[`Array.zeroCreate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate) erstellt ein Array, in dem alle Elemente mit dem Nullwert für den Typ des Arrays initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-137">[`Array.zeroCreate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate) creates an array in which all the elements are initialized to the zero value for the array's type.</span></span> <span data-ttu-id="daaa9-138">Dieser Code demonstriert die Funktionen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-138">The following code demonstrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

<span data-ttu-id="daaa9-139">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-139">The output is as follows.</span></span>

```console
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

<span data-ttu-id="daaa9-140">[`Array.copy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#copy) erstellt ein neues Array, das Elemente enthält, die aus einem vorhandenen Array kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-140">[`Array.copy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#copy) creates a new array that contains elements that are copied from an existing array.</span></span> <span data-ttu-id="daaa9-141">Beachten Sie, dass die Kopie eine flache Kopie ist, d. h., wenn der Elementtyp ein Verweistyp ist, wird nur der Verweis, nicht das zugrunde liegende Objekt kopiert.</span><span class="sxs-lookup"><span data-stu-id="daaa9-141">Note that the copy is a shallow copy, which means that if the element type is a reference type, only the reference is copied, not the underlying object.</span></span> <span data-ttu-id="daaa9-142">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="daaa9-142">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

<span data-ttu-id="daaa9-143">Der obige Code gibt Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="daaa9-143">The output of the preceding code is as follows:</span></span>

```console
[|Test1; Test2; |]
[|; Test2; |]
```

<span data-ttu-id="daaa9-144">Die Zeichenfolge `Test1` wird nur im ersten Array angezeigt, da der Vorgang der Erstellung eines neuen Elements, den Verweis in `firstArray` überschreibt, aber sich nicht auf den ursprünglichen Verweis auf eine leere Zeichenfolge auswirkt, die immer noch im `secondArray` vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="daaa9-144">The string `Test1` appears only in the first array because the operation of creating a new element overwrites the reference in `firstArray` but does not affect the original reference to an empty string that is still present in `secondArray`.</span></span> <span data-ttu-id="daaa9-145">Die Zeichenfolge `Test2` wird in beiden Arrays angezeigt, da sich die `Insert`-Operation für den <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Typ auf das zugrundeliegende <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Objekt auswirkt, auf das in beiden Arrays verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="daaa9-145">The string `Test2` appears in both arrays because the `Insert` operation on the <xref:System.Text.StringBuilder?displayProperty=nameWithType> type affects the underlying <xref:System.Text.StringBuilder?displayProperty=nameWithType> object, which is referenced in both arrays.</span></span>

<span data-ttu-id="daaa9-146">[`Array.sub`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sub) generiert ein neues Array aus einem Teilbereich eines Arrays.</span><span class="sxs-lookup"><span data-stu-id="daaa9-146">[`Array.sub`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sub) generates a new array from a subrange of an array.</span></span> <span data-ttu-id="daaa9-147">Sie geben den Teilbereich an, indem Sie den Startindex und die Länge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-147">You specify the subrange by providing the starting index and the length.</span></span> <span data-ttu-id="daaa9-148">Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.sub`.</span><span class="sxs-lookup"><span data-stu-id="daaa9-148">The following code demonstrates the use of `Array.sub`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

<span data-ttu-id="daaa9-149">Die Ausgabe zeigt an, dass das Unterfeld bei Element "5" beginnt und 10 Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="daaa9-149">The output shows that the subarray starts at element 5 and contains 10 elements.</span></span>

```console
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

<span data-ttu-id="daaa9-150">[`Array.append`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#append) erstellt ein neues Array, indem zwei vorhandene Arrays kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-150">[`Array.append`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#append) creates a new array by combining two existing arrays.</span></span>

<span data-ttu-id="daaa9-151">Der folgende Code veranschaulicht **Array. Append**.</span><span class="sxs-lookup"><span data-stu-id="daaa9-151">The following code demonstrates **Array.append**.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

<span data-ttu-id="daaa9-152">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-152">The output of the preceding code is as follows.</span></span>

```console
[|1; 2; 3; 4; 5; 6|]
```

<span data-ttu-id="daaa9-153">[`Array.choose`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#choose) wählt Elemente eines Arrays aus, die in ein neues Array eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-153">[`Array.choose`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#choose) selects elements of an array to include in a new array.</span></span> <span data-ttu-id="daaa9-154">Der folgende Code stellt `Array.choose` dar.</span><span class="sxs-lookup"><span data-stu-id="daaa9-154">The following code demonstrates `Array.choose`.</span></span> <span data-ttu-id="daaa9-155">Beachten Sie, dass der Elementtyp des Arrays nicht zum Typ des Werts passen muss, der im Optionstyp zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="daaa9-155">Note that the element type of the array does not have to match the type of the value returned in the option type.</span></span> <span data-ttu-id="daaa9-156">In diesem Beispiel ist der Elementtyp `int`, und die Option ist das Ergebnis einer Polynomfunktion (`elem*elem - 1`) als Gleitkommazahl.</span><span class="sxs-lookup"><span data-stu-id="daaa9-156">In this example, the element type is `int` and the option is the result of a polynomial function, `elem*elem - 1`, as a floating point number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

<span data-ttu-id="daaa9-157">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-157">The output of the preceding code is as follows.</span></span>

```console
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

<span data-ttu-id="daaa9-158">[`Array.collect`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#collect) führt eine angegebene Funktion für jedes Array Element eines vorhandenen Arrays aus und sammelt dann die von der Funktion generierten Elemente und kombiniert Sie in einem neuen Array.</span><span class="sxs-lookup"><span data-stu-id="daaa9-158">[`Array.collect`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#collect) runs a specified function on each array element of an existing array and then collects the elements generated by the function and combines them into a new array.</span></span> <span data-ttu-id="daaa9-159">Der folgende Code stellt `Array.collect` dar.</span><span class="sxs-lookup"><span data-stu-id="daaa9-159">The following code demonstrates `Array.collect`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

<span data-ttu-id="daaa9-160">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-160">The output of the preceding code is as follows.</span></span>

```console
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

<span data-ttu-id="daaa9-161">[`Array.concat`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#concat) nimmt eine Sequenz von Arrays an und kombiniert Sie zu einem einzelnen Array.</span><span class="sxs-lookup"><span data-stu-id="daaa9-161">[`Array.concat`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#concat) takes a sequence of arrays and combines them into a single array.</span></span> <span data-ttu-id="daaa9-162">Der folgende Code stellt `Array.concat` dar.</span><span class="sxs-lookup"><span data-stu-id="daaa9-162">The following code demonstrates `Array.concat`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

<span data-ttu-id="daaa9-163">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-163">The output of the preceding code is as follows.</span></span>

```console
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

<span data-ttu-id="daaa9-164">[`Array.filter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#filter) nimmt eine boolesche Bedingungs Funktion an und generiert ein neues Array, das nur die Elemente aus dem Eingabe Array enthält, für die die Bedingung true ist.</span><span class="sxs-lookup"><span data-stu-id="daaa9-164">[`Array.filter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#filter) takes a Boolean condition function and generates a new array that contains only those elements from the input array for which the condition is true.</span></span> <span data-ttu-id="daaa9-165">Der folgende Code stellt `Array.filter` dar.</span><span class="sxs-lookup"><span data-stu-id="daaa9-165">The following code demonstrates `Array.filter`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

<span data-ttu-id="daaa9-166">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-166">The output of the preceding code is as follows.</span></span>

```console
[|2; 4; 6; 8; 10|]
```

<span data-ttu-id="daaa9-167">[`Array.rev`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#rev) generiert ein neues Array, indem die Reihenfolge eines vorhandenen Arrays umgekehrt wird.</span><span class="sxs-lookup"><span data-stu-id="daaa9-167">[`Array.rev`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#rev) generates a new array by reversing the order of an existing array.</span></span> <span data-ttu-id="daaa9-168">Der folgende Code stellt `Array.rev` dar.</span><span class="sxs-lookup"><span data-stu-id="daaa9-168">The following code demonstrates `Array.rev`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet18.fs)]

<span data-ttu-id="daaa9-169">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-169">The output of the preceding code is as follows.</span></span>

```console
"Hello world!"
```

<span data-ttu-id="daaa9-170">Sie können Funktionen im Array Modul, die Arrays transformieren, mit dem Pipeline Operator () problemlos kombinieren `|>` , wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-170">You can easily combine functions in the array module that transform arrays by using the pipeline operator (`|>`), as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet19.fs)]

<span data-ttu-id="daaa9-171">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="daaa9-171">The output is</span></span>

```console
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a><span data-ttu-id="daaa9-172">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="daaa9-172">Multidimensional arrays</span></span>

<span data-ttu-id="daaa9-173">Ein mehrdimensionales Array kann erstellt werden, jedoch gibt es keine Syntax zum Schreiben eines mehrdimensionalen Arrayliterals.</span><span class="sxs-lookup"><span data-stu-id="daaa9-173">A multidimensional array can be created, but there is no syntax for writing a multidimensional array literal.</span></span> <span data-ttu-id="daaa9-174">Verwenden Sie den-Operator [`array2D`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html) , um ein Array aus einer Sequenz von Sequenzen von Array Elementen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-174">Use the operator [`array2D`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html) to create an array from a sequence of sequences of array elements.</span></span> <span data-ttu-id="daaa9-175">Die Sequenzen können Array- oder Listenliterale sein.</span><span class="sxs-lookup"><span data-stu-id="daaa9-175">The sequences can be array or list literals.</span></span> <span data-ttu-id="daaa9-176">Im folgenden Code wird z. B. ein zweidimensionales Array erstellt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-176">For example, the following code creates a two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

<span data-ttu-id="daaa9-177">Sie können auch die-Funktion verwenden, [`Array2D.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#init) um Arrays von zwei Dimensionen zu initialisieren, und ähnliche Funktionen sind für Arrays mit drei und vier Dimensionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="daaa9-177">You can also use the function [`Array2D.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#init) to initialize arrays of two dimensions, and similar functions are available for arrays of three and four dimensions.</span></span> <span data-ttu-id="daaa9-178">Diese Funktionen nehmen eine Funktion, die zum Erstellen der Elemente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="daaa9-178">These functions take a function that is used to create the elements.</span></span> <span data-ttu-id="daaa9-179">Zum Erstellen eines zweidimensionalen Arrays, das Elemente enthält, die auf einen Anfangswert festgelegt sind, anstatt eine Funktion anzugeben, verwenden Sie die- [`Array2D.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#create) Funktion, die auch für Arrays mit bis zu vier Dimensionen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="daaa9-179">To create a two-dimensional array that contains elements set to an initial value instead of specifying a function, use the [`Array2D.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#create) function, which is also available for arrays up to four dimensions.</span></span> <span data-ttu-id="daaa9-180">Im folgenden Codebeispiel wird die Erstellung eines Arrays von Arrays mit den gewünschten Elementen veranschaulicht, und dann wird mit `Array2D.init` das gewünschte zweidimensionale Array generiert.</span><span class="sxs-lookup"><span data-stu-id="daaa9-180">The following code example first shows how to create an array of arrays that contain the desired elements, and then uses `Array2D.init` to generate the desired two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

<span data-ttu-id="daaa9-181">Arrayindizierung und das Aufteilen von Syntax in Slices werden für Arrays bis zu Rang 4 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-181">Array indexing and slicing syntax is supported for arrays up to rank 4.</span></span> <span data-ttu-id="daaa9-182">Wenn Sie einen Index in mehreren Dimensionen angeben, verwenden Sie Kommas, um die Indizes zu trennen, wie im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="daaa9-182">When you specify an index in multiple dimensions, you use commas to separate the indexes, as illustrated in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

<span data-ttu-id="daaa9-183">Der Typ eines zweidimensionalen Arrays wird als `<type>[,]` (z. B.,`int[,]`, `double[,]`) geschrieben, und der Typ eines dreidimensionalen Arrays wird als `<type>[,,]` usw. für Arrays mit mehr Dimensionen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="daaa9-183">The type of a two-dimensional array is written out as `<type>[,]` (for example, `int[,]`, `double[,]`), and the type of a three-dimensional array is written as `<type>[,,]`, and so on for arrays of higher dimensions.</span></span>

<span data-ttu-id="daaa9-184">Nur eine Teilmenge der Funktionen für eindimensionale Arrays ist auch für mehrdimensionale Arrays verfügbar.</span><span class="sxs-lookup"><span data-stu-id="daaa9-184">Only a subset of the functions available for one-dimensional arrays is also available for multidimensional arrays.</span></span>

### <a name="array-slicing-and-multidimensional-arrays"></a><span data-ttu-id="daaa9-185">Array-aufteilen und mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="daaa9-185">Array slicing and multidimensional arrays</span></span>

<span data-ttu-id="daaa9-186">In einem zweidimensionalen Array (eine Matrix) können Sie eine untergeordnete Matrix extrahieren, indem Sie Bereiche angeben und ein Platzhalter `*` Zeichen () verwenden, um ganze Zeilen oder Spalten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="daaa9-186">In a two-dimensional array (a matrix), you can extract a sub-matrix by specifying ranges and using a wildcard (`*`) character to specify whole rows or columns.</span></span>

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

<span data-ttu-id="daaa9-187">Sie können ein mehrdimensionales Array in unter Elemente derselben oder einer niedrigeren Dimension zerlegen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-187">You can decompose a multidimensional array into subarrays of the same or lower dimension.</span></span> <span data-ttu-id="daaa9-188">Beispielsweise können Sie einen Vektor aus einer Matrix abrufen, indem Sie eine einzelne Zeile oder eine Spalte angeben.</span><span class="sxs-lookup"><span data-stu-id="daaa9-188">For example, you can obtain a vector from a matrix by specifying a single row or column.</span></span>

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

<span data-ttu-id="daaa9-189">Sie können diese segmentierende Syntax für Typen verwenden, die die Elementzugriffsoperatoren und die überladenen `GetSlice`-Methoden implementieren.</span><span class="sxs-lookup"><span data-stu-id="daaa9-189">You can use this slicing syntax for types that implement the element access operators and overloaded `GetSlice` methods.</span></span> <span data-ttu-id="daaa9-190">Beispielsweise erstellt der folgende Code einen Matrixtyp, der das F# 2D-Array umschließt, eine Elementeigenschaft implementiert, um Unterstützung für die Arrayindizierung bereitzustellen, und drei Versionen von `GetSlice` implementiert.</span><span class="sxs-lookup"><span data-stu-id="daaa9-190">For example, the following code creates a Matrix type that wraps the F# 2D array, implements an Item property to provide support for array indexing, and implements three versions of `GetSlice`.</span></span> <span data-ttu-id="daaa9-191">Wenn Sie diesen Code als Vorlage für Ihre Matrixtypen verwenden können, können Sie alle in diesem Abschnitt beschriebenen Segmentierungsvorgänge verwenden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-191">If you can use this code as a template for your matrix types, you can use all the slicing operations that this section describes.</span></span>

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn $"{submatrix}"

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn $"{firstCol}"
```

### <a name="boolean-functions-on-arrays"></a><span data-ttu-id="daaa9-192">Boolesche Funktionen für Arrays</span><span class="sxs-lookup"><span data-stu-id="daaa9-192">Boolean functions on arrays</span></span>

<span data-ttu-id="daaa9-193">Die Funktionen [`Array.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists) und [`Array.exists2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists2) Testelemente in jeweils einem oder zwei Arrays.</span><span class="sxs-lookup"><span data-stu-id="daaa9-193">The functions [`Array.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists) and [`Array.exists2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists2) test elements in either one or two arrays, respectively.</span></span> <span data-ttu-id="daaa9-194">Diese Funktionen akzeptieren eine Testfunktion und geben `true` zurück, wenn die Bedingung von einem Element (oder Elementpaaren für `Array.exists2`) erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="daaa9-194">These functions take a test function and return `true` if there is an element (or element pair for `Array.exists2`) that satisfies the condition.</span></span>

<span data-ttu-id="daaa9-195">Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.exists` und `Array.exists2`.</span><span class="sxs-lookup"><span data-stu-id="daaa9-195">The following code demonstrates the use of `Array.exists` and `Array.exists2`.</span></span> <span data-ttu-id="daaa9-196">In diesen Beispielen werden neue Funktionen durch das Übernehmen von nur einem der Argumente, in diesen Fällen das Funktionsargument, erstellt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-196">In these examples, new functions are created by applying only one of the arguments, in these cases, the function argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

<span data-ttu-id="daaa9-197">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-197">The output of the preceding code is as follows.</span></span>

```console
true
false
false
true
```

<span data-ttu-id="daaa9-198">Ebenso testet die-Funktion [`Array.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall) ein Array, um zu bestimmen, ob jedes Element eine boolesche Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-198">Similarly, the function [`Array.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall) tests an array to determine whether every element satisfies a Boolean condition.</span></span> <span data-ttu-id="daaa9-199">Die Variation [`Array.forall2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall2) führt dasselbe aus, indem eine boolesche Funktion verwendet wird, die Elemente von zwei Arrays gleicher Länge einbezieht.</span><span class="sxs-lookup"><span data-stu-id="daaa9-199">The variation [`Array.forall2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall2) does the same thing by using a Boolean function that involves elements of two arrays of equal length.</span></span> <span data-ttu-id="daaa9-200">Im folgenden Code wird die Verwendung dieser Funktionen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="daaa9-200">The following code illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

<span data-ttu-id="daaa9-201">Die Ausgabe dieser Beispiele lautet folgendermaßen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-201">The output for these examples is as follows.</span></span>

```console
false
true
true
false
```

### <a name="search-arrays"></a><span data-ttu-id="daaa9-202">Arrays suchen</span><span class="sxs-lookup"><span data-stu-id="daaa9-202">Search arrays</span></span>

<span data-ttu-id="daaa9-203">[`Array.find`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#find) nimmt eine boolesche Funktion an und gibt das erste Element zurück, für das die Funktion zurückgibt `true` , oder löst eine aus, <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> Wenn kein Element gefunden wird, das die Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-203">[`Array.find`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#find) takes a Boolean function and returns the first element for which the function returns `true`, or raises a <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> if no element that satisfies the condition is found.</span></span> <span data-ttu-id="daaa9-204">[`Array.findIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#findIndex) ist wie `Array.find` , mit der Ausnahme, dass Sie den Index des-Elements anstelle des-Elements selbst zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-204">[`Array.findIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#findIndex) is like `Array.find`, except that it returns the index of the element instead of the element itself.</span></span>

<span data-ttu-id="daaa9-205">Der folgende Code sucht mithilfe von `Array.find` und `Array.findIndex` eine Zahl, die sowohl ein perfektes Quadrat als auch perfekter Cube ist.</span><span class="sxs-lookup"><span data-stu-id="daaa9-205">The following code uses `Array.find` and `Array.findIndex` to locate a number that is both a perfect square and perfect cube.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

<span data-ttu-id="daaa9-206">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-206">The output is as follows.</span></span>

```console
The first element that is both a square and a cube is 64 and its index is 62.
```

<span data-ttu-id="daaa9-207">[`Array.tryFind`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFind) ist wie `Array.find` , mit der Ausnahme, dass das Ergebnis ein Optionstyp ist, und gibt zurück, `None` Wenn kein Element gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="daaa9-207">[`Array.tryFind`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFind) is like `Array.find`, except that its result is an option type, and it returns `None` if no element is found.</span></span> <span data-ttu-id="daaa9-208">`Array.tryFind` sollte statt `Array.find` verwendet werden, wenn nicht bekannt ist, ob ein entsprechendes Element im Array vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="daaa9-208">`Array.tryFind` should be used instead of `Array.find` when you do not know whether a matching element is in the array.</span></span> <span data-ttu-id="daaa9-209">Ebenso verhält [`Array.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFindIndex) sich wie, `Array.findIndex` mit der Ausnahme, dass der Optionstyp der Rückgabewert ist.</span><span class="sxs-lookup"><span data-stu-id="daaa9-209">Similarly, [`Array.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFindIndex) is like `Array.findIndex` except that the option type is the return value.</span></span> <span data-ttu-id="daaa9-210">Wenn kein Element gefunden wird, lautet die Option `None`.</span><span class="sxs-lookup"><span data-stu-id="daaa9-210">If no element is found, the option is `None`.</span></span>

<span data-ttu-id="daaa9-211">Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.tryFind`.</span><span class="sxs-lookup"><span data-stu-id="daaa9-211">The following code demonstrates the use of `Array.tryFind`.</span></span> <span data-ttu-id="daaa9-212">Dieser Code hängt vom vorherigen Code ab.</span><span class="sxs-lookup"><span data-stu-id="daaa9-212">This code depends on the previous code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

<span data-ttu-id="daaa9-213">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-213">The output is as follows.</span></span>

```console
Found an element: 1
Found an element: 729
Failed to find a matching element.
```

<span data-ttu-id="daaa9-214">Verwenden [`Array.tryPick`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryPick) Sie, wenn Sie ein Element zusätzlich zu dessen Suche transformieren müssen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-214">Use [`Array.tryPick`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryPick) when you need to transform an element in addition to finding it.</span></span> <span data-ttu-id="daaa9-215">Das Ergebnis ist das erste Element, für das die Funktion das transformierte Element als Optionswert zurückgibt, oder `None`, wenn kein solches Element gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="daaa9-215">The result is the first element for which the function returns the transformed element as an option value, or `None` if no such element is found.</span></span>

<span data-ttu-id="daaa9-216">Im folgenden Code wird die Verwendung von `Array.tryPick` veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="daaa9-216">The following code shows the use of `Array.tryPick`.</span></span> <span data-ttu-id="daaa9-217">In diesem Fall werden statt eines Lambdaausdrucks mehrere lokale Hilfsfunktionen definiert, um den Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-217">In this case, instead of a lambda expression, several local helper functions are defined to simplify the code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet27.fs)]

<span data-ttu-id="daaa9-218">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-218">The output is as follows.</span></span>

```console
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
Did not find an element that is both a perfect square and a perfect cube.
```

### <a name="perform-computations-on-arrays"></a><span data-ttu-id="daaa9-219">Ausführen von Berechnungen für Arrays</span><span class="sxs-lookup"><span data-stu-id="daaa9-219">Perform computations on arrays</span></span>

<span data-ttu-id="daaa9-220">Die- [`Array.average`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#average) Funktion gibt den Durchschnitt der einzelnen Elemente in einem Array zurück.</span><span class="sxs-lookup"><span data-stu-id="daaa9-220">The [`Array.average`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#average) function returns the average of each element in an array.</span></span> <span data-ttu-id="daaa9-221">Sie ist auf Elementtypen beschränkt, die die exakte Division durch eine ganze Zahl unterstützen, wozu Gleitkommatypen aber keine ganzzahligen Typen gehören.</span><span class="sxs-lookup"><span data-stu-id="daaa9-221">It is limited to element types that support exact division by an integer, which includes floating point types but not integral types.</span></span> <span data-ttu-id="daaa9-222">Die- [`Array.averageBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#averageBy) Funktion gibt den Durchschnitt der Ergebnisse zurück, die durch den Aufruf einer Funktion für jedes Element verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="daaa9-222">The [`Array.averageBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#averageBy) function returns the average of the results of calling a function on each element.</span></span> <span data-ttu-id="daaa9-223">Für ein Array eines ganzzahligen Typs können Sie `Array.averageBy` verwenden und für die Berechnung die Funktion jedes Element in einen Gleitkommatyp konvertieren lassen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-223">For an array of integral type, you can use `Array.averageBy` and have the function convert each element to a floating point type for the computation.</span></span>

<span data-ttu-id="daaa9-224">Verwenden [`Array.max`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#max) [`Array.min`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#min) Sie oder, um das maximale oder minimale Element zu erhalten, wenn der Elementtyp es unterstützt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-224">Use [`Array.max`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#max) or [`Array.min`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#min) to get the maximum or minimum element, if the element type supports it.</span></span> <span data-ttu-id="daaa9-225">Ebenso wie [`Array.maxBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#maxBy) und [`Array.minBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#minBy) ermöglichen, dass eine Funktion zuerst ausgeführt wird, vielleicht zum Transformieren in einen Typ, der den Vergleich unterstützt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-225">Similarly, [`Array.maxBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#maxBy) and [`Array.minBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#minBy) allow a function to be executed first, perhaps to transform to a type that supports comparison.</span></span>

<span data-ttu-id="daaa9-226">[`Array.sum`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sum) Fügt die Elemente eines Arrays hinzu und [`Array.sumBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sumBy) Ruft für jedes Element eine Funktion auf und addiert die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="daaa9-226">[`Array.sum`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sum) adds the elements of an array, and [`Array.sumBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sumBy) calls a function on each element and adds the results together.</span></span>

<span data-ttu-id="daaa9-227">Verwenden Sie, um eine Funktion für jedes Element in einem Array auszuführen, ohne die Rückgabewerte zu speichern [`Array.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter) .</span><span class="sxs-lookup"><span data-stu-id="daaa9-227">To execute a function on each element in an array without storing the return values, use [`Array.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter).</span></span> <span data-ttu-id="daaa9-228">Verwenden Sie für eine Funktion mit zwei Arrays gleicher Länge [`Array.iter2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter2) .</span><span class="sxs-lookup"><span data-stu-id="daaa9-228">For a function involving two arrays of equal length, use [`Array.iter2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter2).</span></span> <span data-ttu-id="daaa9-229">Wenn Sie auch ein Array der Ergebnisse der Funktion beibehalten müssen, verwenden Sie [`Array.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map) oder [`Array.map2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map2) , das jeweils zwei Arrays verwendet.</span><span class="sxs-lookup"><span data-stu-id="daaa9-229">If you also need to keep an array of the results of the function, use [`Array.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map) or [`Array.map2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map2), which operates on two arrays at a time.</span></span>

<span data-ttu-id="daaa9-230">Die Variationen [`Array.iteri`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri) und [`Array.iteri2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri2) ermöglichen, dass der Index des Elements an der Berechnung beteiligt ist. das gleiche gilt für [`Array.mapi`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi) und [`Array.mapi2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi2) .</span><span class="sxs-lookup"><span data-stu-id="daaa9-230">The variations [`Array.iteri`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri) and [`Array.iteri2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri2) allow the index of the element to be involved in the computation; the same is true for [`Array.mapi`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi) and [`Array.mapi2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi2).</span></span>

<span data-ttu-id="daaa9-231">Die Funktionen [`Array.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold) , [`Array.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack) , [`Array.reduce`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduce) , [`Array.reduceBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduceBack) , [`Array.scan`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scan) und [`Array.scanBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scanBack) führen Algorithmen aus, die alle Elemente eines Arrays einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-231">The functions [`Array.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold), [`Array.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack), [`Array.reduce`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduce), [`Array.reduceBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduceBack), [`Array.scan`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scan), and [`Array.scanBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scanBack) execute algorithms that involve all the elements of an array.</span></span> <span data-ttu-id="daaa9-232">Ebenso werden die Variationen [`Array.fold2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold2) und [`Array.foldBack2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack2) Berechnungen für zwei Arrays durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-232">Similarly, the variations [`Array.fold2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold2) and [`Array.foldBack2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack2) perform computations on two arrays.</span></span>

<span data-ttu-id="daaa9-233">Diese Funktionen zum Ausführen von Berechnungen entsprechen den Funktionen desselben Namens im [Listen Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span><span class="sxs-lookup"><span data-stu-id="daaa9-233">These functions for performing computations correspond to the functions of the same name in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span> <span data-ttu-id="daaa9-234">Verwendungs Beispiele finden Sie unter [Listen](lists.md).</span><span class="sxs-lookup"><span data-stu-id="daaa9-234">For usage examples, see [Lists](lists.md).</span></span>

### <a name="modify-arrays"></a><span data-ttu-id="daaa9-235">Arrays ändern</span><span class="sxs-lookup"><span data-stu-id="daaa9-235">Modify arrays</span></span>

<span data-ttu-id="daaa9-236">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) legt ein Element auf einen angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="daaa9-236">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) sets an element to a specified value.</span></span> <span data-ttu-id="daaa9-237">[`Array.fill`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fill) legt einen Bereich von Elementen in einem Array auf einen angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="daaa9-237">[`Array.fill`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fill) sets a range of elements in an array to a specified value.</span></span> <span data-ttu-id="daaa9-238">Das folgende Codebeispiel enthält ein Beispiel für `Array.fill`.</span><span class="sxs-lookup"><span data-stu-id="daaa9-238">The following code provides an example of `Array.fill`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

<span data-ttu-id="daaa9-239">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-239">The output is as follows.</span></span>

```console
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

<span data-ttu-id="daaa9-240">Sie können verwenden [`Array.blit`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#blit) , um einen unter Abschnitt eines Arrays in ein anderes Array zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="daaa9-240">You can use [`Array.blit`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#blit) to copy a subsection of one array to another array.</span></span>

### <a name="convert-to-and-from-other-types"></a><span data-ttu-id="daaa9-241">Konvertieren in und aus anderen Typen</span><span class="sxs-lookup"><span data-stu-id="daaa9-241">Convert to and from other types</span></span>

<span data-ttu-id="daaa9-242">[`Array.ofList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofList) erstellt ein Array aus einer Liste.</span><span class="sxs-lookup"><span data-stu-id="daaa9-242">[`Array.ofList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofList) creates an array from a list.</span></span> <span data-ttu-id="daaa9-243">[`Array.ofSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofSeq) erstellt ein Array aus einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="daaa9-243">[`Array.ofSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofSeq) creates an array from a sequence.</span></span> <span data-ttu-id="daaa9-244">[`Array.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toList) und [`Array.toSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toSeq) Konvertieren in diese anderen Auflistungs Typen aus dem Arraytyp.</span><span class="sxs-lookup"><span data-stu-id="daaa9-244">[`Array.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toList) and [`Array.toSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toSeq) convert to these other collection types from the array type.</span></span>

### <a name="sort-arrays"></a><span data-ttu-id="daaa9-245">Arrays sortieren</span><span class="sxs-lookup"><span data-stu-id="daaa9-245">Sort arrays</span></span>

<span data-ttu-id="daaa9-246">Verwenden [`Array.sort`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sort) Sie, um ein Array mithilfe der generischen Vergleichsfunktion zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="daaa9-246">Use [`Array.sort`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sort) to sort an array by using the generic comparison function.</span></span> <span data-ttu-id="daaa9-247">Verwenden [`Array.sortBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortBy) Sie, um eine Funktion anzugeben, die einen Wert generiert, der als *Schlüssel* bezeichnet wird, um mithilfe der generischen Vergleichsfunktion für den Schlüssel zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="daaa9-247">Use [`Array.sortBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortBy) to specify a function that generates a value, referred to as a *key*, to sort by using the generic comparison function on the key.</span></span> <span data-ttu-id="daaa9-248">Verwenden [`Array.sortWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortWith) Sie, wenn Sie eine benutzerdefinierte Vergleichsfunktion bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="daaa9-248">Use [`Array.sortWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortWith) if you want to provide a custom comparison function.</span></span> <span data-ttu-id="daaa9-249">`Array.sort`, `Array.sortBy` und `Array.sortWith` geben das sortierte Array als neues Array zurück.</span><span class="sxs-lookup"><span data-stu-id="daaa9-249">`Array.sort`, `Array.sortBy`, and `Array.sortWith` all return the sorted array as a new array.</span></span> <span data-ttu-id="daaa9-250">Die Variationen [`Array.sortInPlace`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlace) , [`Array.sortInPlaceBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceBy) und [`Array.sortInPlaceWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceWith) ändern das vorhandene Array, anstatt ein neues Array zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="daaa9-250">The variations [`Array.sortInPlace`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlace), [`Array.sortInPlaceBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceBy), and [`Array.sortInPlaceWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceWith) modify the existing array instead of returning a new one.</span></span>

### <a name="arrays-and-tuples"></a><span data-ttu-id="daaa9-251">Arrays und Tupel</span><span class="sxs-lookup"><span data-stu-id="daaa9-251">Arrays and tuples</span></span>

<span data-ttu-id="daaa9-252">Die Funktionen [`Array.zip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip) und [`Array.unzip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip) konvertieren Arrays von tupelpaaren in Tupel von Arrays und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="daaa9-252">The functions [`Array.zip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip) and [`Array.unzip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip) convert arrays of tuple pairs to tuples of arrays and vice versa.</span></span> <span data-ttu-id="daaa9-253">[`Array.zip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip3) und [`Array.unzip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip3) sind ähnlich, mit dem Unterschied, dass Sie mit Tupeln von drei Elementen oder Tupeln von drei Arrays funktionieren.</span><span class="sxs-lookup"><span data-stu-id="daaa9-253">[`Array.zip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip3) and [`Array.unzip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip3) are similar except that they work with tuples of three elements or tuples of three arrays.</span></span>

## <a name="parallel-computations-on-arrays"></a><span data-ttu-id="daaa9-254">Parallele Berechnungen von Arrays</span><span class="sxs-lookup"><span data-stu-id="daaa9-254">Parallel computations on arrays</span></span>

<span data-ttu-id="daaa9-255">Das-Modul [`Array.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule-parallel.html) enthält Funktionen zum Ausführen paralleler Berechnungen für Arrays.</span><span class="sxs-lookup"><span data-stu-id="daaa9-255">The module [`Array.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule-parallel.html) contains functions for performing parallel computations on arrays.</span></span> <span data-ttu-id="daaa9-256">Dieses Modul ist in Anwendungen nicht verfügbar, die auf Versionen vor Version 4 von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="daaa9-256">This module is not available in applications that target versions of the .NET Framework prior to version 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="daaa9-257">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="daaa9-257">See also</span></span>

- [<span data-ttu-id="daaa9-258">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="daaa9-258">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="daaa9-259">F#-Typen</span><span class="sxs-lookup"><span data-stu-id="daaa9-259">F# Types</span></span>](fsharp-types.md)
