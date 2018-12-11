---
title: Arrays (F#)
description: Informationen Sie zum Erstellen und Verwenden von Arrays in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: 0f72718988ee401631c53b74f02948030e83aac1
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129973"
---
# <a name="arrays"></a><span data-ttu-id="50dcd-103">Arrays</span><span class="sxs-lookup"><span data-stu-id="50dcd-103">Arrays</span></span>

> [!NOTE]
> <span data-ttu-id="50dcd-104">Mit dem API-Referenz-Link gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="50dcd-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="50dcd-105">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="50dcd-106">Arrays sind nullbasierte, änderbare Sequenzen fester Größe von aufeinander folgenden Datenelementen, die alle den gleichen Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-106">Arrays are fixed-size, zero-based, mutable collections of consecutive data elements that are all of the same type.</span></span>

## <a name="creating-arrays"></a><span data-ttu-id="50dcd-107">Erstellen von Arrays</span><span class="sxs-lookup"><span data-stu-id="50dcd-107">Creating Arrays</span></span>

<span data-ttu-id="50dcd-108">Sie können Arrays auf verschiedene Arten erstellen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-108">You can create arrays in several ways.</span></span> <span data-ttu-id="50dcd-109">Sie können ein kleines Array erstellen, indem Sie aufeinanderfolgende Werte zwischen auflisten `[|` und `|]` und durch Semikolons getrennt werden, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-109">You can create a small array by listing consecutive values between `[|` and `|]` and separated by semicolons, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet1.fs)]

<span data-ttu-id="50dcd-110">Sie können auch jedes Element in einer eigenen Zeile anordnen. In diesem Fall ist das Semikolontrennzeichen optional.</span><span class="sxs-lookup"><span data-stu-id="50dcd-110">You can also put each element on a separate line, in which case the semicolon separator is optional.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet2.fs)]

<span data-ttu-id="50dcd-111">Der Typ der Arrayelemente wird von den verwendeten Literalen abgeleitet, und er muss konsistent sein.</span><span class="sxs-lookup"><span data-stu-id="50dcd-111">The type of the array elements is inferred from the literals used and must be consistent.</span></span> <span data-ttu-id="50dcd-112">Somit verursacht der folgende Code einen Fehler, da 1.0 ein Gleitkommawert ist und 2 und 3 ganze Zahlen sind.</span><span class="sxs-lookup"><span data-stu-id="50dcd-112">The following code causes an error because 1.0 is a float and 2 and 3 are integers.</span></span>

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

<span data-ttu-id="50dcd-113">Sie können Arrays mithilfe von Sequenzausdrücken erstellen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-113">You can also use sequence expressions to create arrays.</span></span> <span data-ttu-id="50dcd-114">Im folgenden Beispiel wird ein Array aus den Quadraten von ganzen Zahlen zwischen 1 und 10 erstellt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-114">Following is an example that creates an array of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet3.fs)]

<span data-ttu-id="50dcd-115">Verwenden Sie `Array.zeroCreate`, um ein Array zu erstellen, dessen sämtliche Elemente mit 0 (null) initialisiert sind.</span><span class="sxs-lookup"><span data-stu-id="50dcd-115">To create an array in which all the elements are initialized to zero, use `Array.zeroCreate`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="accessing-elements"></a><span data-ttu-id="50dcd-116">Zugreifen auf Elemente</span><span class="sxs-lookup"><span data-stu-id="50dcd-116">Accessing Elements</span></span>

<span data-ttu-id="50dcd-117">Sie können Elemente des Arrays zugreifen, mit dem Punktoperator (`.`) und eckige Klammern (`[` und `]`).</span><span class="sxs-lookup"><span data-stu-id="50dcd-117">You can access array elements by using a dot operator (`.`) and brackets (`[` and `]`).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet5.fs)]

<span data-ttu-id="50dcd-118">Arrayindizes beginnen bei 0.</span><span class="sxs-lookup"><span data-stu-id="50dcd-118">Array indexes start at 0.</span></span>

<span data-ttu-id="50dcd-119">Der Zugriff auf Arrayelemente kann auch mit Slicenotation erfolgen, die es Ihnen ermöglicht, einen Teilbereich des Arrays anzugeben.</span><span class="sxs-lookup"><span data-stu-id="50dcd-119">You can also access array elements by using slice notation, which enables you to specify a subrange of the array.</span></span> <span data-ttu-id="50dcd-120">Im Folgenden erhalten Sie Beispiele für Slicenotation.</span><span class="sxs-lookup"><span data-stu-id="50dcd-120">Examples of slice notation follow.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet51.fs)]

<span data-ttu-id="50dcd-121">Bei Verwendung von Slicenotation wird eine neue Kopie des Arrays erstellt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-121">When slice notation is used, a new copy of the array is created.</span></span>

## <a name="array-types-and-modules"></a><span data-ttu-id="50dcd-122">Arraytypen und Module</span><span class="sxs-lookup"><span data-stu-id="50dcd-122">Array Types and Modules</span></span>

<span data-ttu-id="50dcd-123">Alle F#-Arrays sind vom .NET Framework-Typ <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50dcd-123">The type of all F# arrays is the .NET Framework type <xref:System.Array?displayProperty=nameWithType>.</span></span> <span data-ttu-id="50dcd-124">Daher unterstützen F#-Arrays alle in <xref:System.Array?displayProperty=nameWithType> verfügbaren Funktionen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-124">Therefore, F# arrays support all the functionality available in <xref:System.Array?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="50dcd-125">Das Bibliotheksmodul [ `Microsoft.FSharp.Collections.Array` ](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) Operationen auf eindimensionalen Arrays unterstützt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-125">The library module [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) supports operations on one-dimensional arrays.</span></span> <span data-ttu-id="50dcd-126">Die Module `Array2D`, `Array3D` und `Array4D` enthalten Funktionen, die Operationen für Arrays mit zwei, drei bzw. vier Dimensionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-126">The modules `Array2D`, `Array3D`, and `Array4D` contain functions that support operations on arrays of two, three, and four dimensions, respectively.</span></span> <span data-ttu-id="50dcd-127">Mit <xref:System.Array?displayProperty=nameWithType> können Sie Arrays mit einem Rang größer vier erstellen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-127">You can create arrays of rank greater than four by using <xref:System.Array?displayProperty=nameWithType>.</span></span>

### <a name="simple-functions"></a><span data-ttu-id="50dcd-128">Einfache Funktionen</span><span class="sxs-lookup"><span data-stu-id="50dcd-128">Simple Functions</span></span>

<span data-ttu-id="50dcd-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) Ruft ein Element ab.</span><span class="sxs-lookup"><span data-stu-id="50dcd-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) gets an element.</span></span> <span data-ttu-id="50dcd-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) Gibt die Länge eines Arrays.</span><span class="sxs-lookup"><span data-stu-id="50dcd-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) gives the length of an array.</span></span> <span data-ttu-id="50dcd-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) Legt ein Element mit einem angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="50dcd-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="50dcd-132">Im folgenden Codebeispiel wird die Verwendung dieser Funktionen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="50dcd-132">The following code example illustrates the use of these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet9.fs)]

<span data-ttu-id="50dcd-133">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-133">The output is as follows.</span></span>

```
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a><span data-ttu-id="50dcd-134">Funktionen, die Arrays generieren</span><span class="sxs-lookup"><span data-stu-id="50dcd-134">Functions That Create Arrays</span></span>

<span data-ttu-id="50dcd-135">Mehrere Funktionen erstellen Arrays, ohne ein vorhandenes Array zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="50dcd-135">Several functions create arrays without requiring an existing array.</span></span> <span data-ttu-id="50dcd-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) erstellt ein neues Array, das keine Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="50dcd-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) creates a new array that does not contain any elements.</span></span> <span data-ttu-id="50dcd-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) erstellt ein Array mit einer angegebenen Größe aus, und legt alle Elemente mit angegebenen Werten.</span><span class="sxs-lookup"><span data-stu-id="50dcd-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) creates an array of a specified size and sets all the elements to provided values.</span></span> <span data-ttu-id="50dcd-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) erstellt ein Array unter Verwendung einer Dimensionen und eine Funktion, die die Elemente zu generieren.</span><span class="sxs-lookup"><span data-stu-id="50dcd-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) creates an array, given a dimension and a function to generate the elements.</span></span> <span data-ttu-id="50dcd-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) erstellt ein Array, in dem alle Elemente auf den Wert für den Typ des Arrays initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="50dcd-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) creates an array in which all the elements are initialized to the zero value for the array's type.</span></span> <span data-ttu-id="50dcd-140">Dieser Code demonstriert die Funktionen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-140">The following code demonstrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet91.fs)]

<span data-ttu-id="50dcd-141">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-141">The output is as follows.</span></span>

```
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

<span data-ttu-id="50dcd-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) erstellt ein neues Array, das Elemente enthält, die aus einem vorhandenen Array kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="50dcd-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) creates a new array that contains elements that are copied from an existing array.</span></span> <span data-ttu-id="50dcd-143">Beachten Sie, dass die Kopie eine flache Kopie ist, d. h., wenn der Elementtyp ein Verweistyp ist, wird nur der Verweis, nicht das zugrunde liegende Objekt kopiert.</span><span class="sxs-lookup"><span data-stu-id="50dcd-143">Note that the copy is a shallow copy, which means that if the element type is a reference type, only the reference is copied, not the underlying object.</span></span> <span data-ttu-id="50dcd-144">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="50dcd-144">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet11.fs)]

<span data-ttu-id="50dcd-145">Der obige Code gibt Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="50dcd-145">The output of the preceding code is as follows:</span></span>

```
[|Test1; Test2; |]
[|; Test2; |]
```

<span data-ttu-id="50dcd-146">Die Zeichenfolge `Test1` wird nur im ersten Array angezeigt, da der Vorgang der Erstellung eines neuen Elements, den Verweis in `firstArray` überschreibt, aber sich nicht auf den ursprünglichen Verweis auf eine leere Zeichenfolge auswirkt, die immer noch im `secondArray` vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="50dcd-146">The string `Test1` appears only in the first array because the operation of creating a new element overwrites the reference in `firstArray` but does not affect the original reference to an empty string that is still present in `secondArray`.</span></span> <span data-ttu-id="50dcd-147">Die Zeichenfolge `Test2` wird in beiden Arrays angezeigt, da sich die `Insert`-Operation für den <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Typ auf das zugrundeliegende <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Objekt auswirkt, auf das in beiden Arrays verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="50dcd-147">The string `Test2` appears in both arrays because the `Insert` operation on the <xref:System.Text.StringBuilder?displayProperty=nameWithType> type affects the underlying <xref:System.Text.StringBuilder?displayProperty=nameWithType> object, which is referenced in both arrays.</span></span>

<span data-ttu-id="50dcd-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) generiert ein neues Array aus einem Teilbereich eines Arrays an.</span><span class="sxs-lookup"><span data-stu-id="50dcd-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) generates a new array from a subrange of an array.</span></span> <span data-ttu-id="50dcd-149">Sie geben den Teilbereich an, indem Sie den Startindex und die Länge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-149">You specify the subrange by providing the starting index and the length.</span></span> <span data-ttu-id="50dcd-150">Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.sub`.</span><span class="sxs-lookup"><span data-stu-id="50dcd-150">The following code demonstrates the use of `Array.sub`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet12.fs)]

<span data-ttu-id="50dcd-151">Die Ausgabe zeigt an, dass das Unterfeld bei Element "5" beginnt und 10 Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="50dcd-151">The output shows that the subarray starts at element 5 and contains 10 elements.</span></span>

```
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```
<span data-ttu-id="50dcd-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) ein neues Array erstellt, indem zwei vorhandene Arrays kombiniert.</span><span class="sxs-lookup"><span data-stu-id="50dcd-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) creates a new array by combining two existing arrays.</span></span>

<span data-ttu-id="50dcd-153">Der folgende Code veranschaulicht **Array.append**.</span><span class="sxs-lookup"><span data-stu-id="50dcd-153">The following code demonstrates **Array.append**.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet13.fs)]

<span data-ttu-id="50dcd-154">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="50dcd-154">The output of the preceding code is as follows.</span></span>

```
[|1; 2; 3; 4; 5; 6|]
```

<span data-ttu-id="50dcd-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) Wählt Elemente eines Arrays in ein neues Array eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) selects elements of an array to include in a new array.</span></span> <span data-ttu-id="50dcd-156">Der folgende Code stellt `Array.choose` dar.</span><span class="sxs-lookup"><span data-stu-id="50dcd-156">The following code demonstrates `Array.choose`.</span></span> <span data-ttu-id="50dcd-157">Beachten Sie, dass der Elementtyp des Arrays nicht zum Typ des Werts passen muss, der im Optionstyp zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="50dcd-157">Note that the element type of the array does not have to match the type of the value returned in the option type.</span></span> <span data-ttu-id="50dcd-158">In diesem Beispiel ist der Elementtyp `int`, und die Option ist das Ergebnis einer Polynomfunktion (`elem*elem - 1`) als Gleitkommazahl.</span><span class="sxs-lookup"><span data-stu-id="50dcd-158">In this example, the element type is `int` and the option is the result of a polynomial function, `elem*elem - 1`, as a floating point number.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet14.fs)]

<span data-ttu-id="50dcd-159">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="50dcd-159">The output of the preceding code is as follows.</span></span>

```
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

<span data-ttu-id="50dcd-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) führt eine angegebene Funktion für jedes Arrayelement eines vorhandenen Arrays und erfasst die von der Funktion generierten Elemente und kombiniert diese Elemente in ein neues Array.</span><span class="sxs-lookup"><span data-stu-id="50dcd-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) runs a specified function on each array element of an existing array and then collects the elements generated by the function and combines them into a new array.</span></span> <span data-ttu-id="50dcd-161">Der folgende Code stellt `Array.collect` dar.</span><span class="sxs-lookup"><span data-stu-id="50dcd-161">The following code demonstrates `Array.collect`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet15.fs)]

<span data-ttu-id="50dcd-162">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="50dcd-162">The output of the preceding code is as follows.</span></span>

```
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

<span data-ttu-id="50dcd-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) nimmt eine Sequenz von Arrays und kombiniert diese Elemente in ein einzelnes Array.</span><span class="sxs-lookup"><span data-stu-id="50dcd-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) takes a sequence of arrays and combines them into a single array.</span></span> <span data-ttu-id="50dcd-164">Der folgende Code stellt `Array.concat` dar.</span><span class="sxs-lookup"><span data-stu-id="50dcd-164">The following code demonstrates `Array.concat`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet16.fs)]

<span data-ttu-id="50dcd-165">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="50dcd-165">The output of the preceding code is as follows.</span></span>

```
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

<span data-ttu-id="50dcd-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) nimmt eine boolesche Bedingungsfunktion und generiert ein neues Array, das nur die Elemente des Eingabearrays enthält, für die die Bedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="50dcd-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) takes a Boolean condition function and generates a new array that contains only those elements from the input array for which the condition is true.</span></span> <span data-ttu-id="50dcd-167">Der folgende Code stellt `Array.filter` dar.</span><span class="sxs-lookup"><span data-stu-id="50dcd-167">The following code demonstrates `Array.filter`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet17.fs)]

<span data-ttu-id="50dcd-168">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="50dcd-168">The output of the preceding code is as follows.</span></span>

```
[|2; 4; 6; 8; 10|]
```

<span data-ttu-id="50dcd-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) generiert ein neues Array durch Umkehren der Reihenfolge eines vorhandenen Arrays an.</span><span class="sxs-lookup"><span data-stu-id="50dcd-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) generates a new array by reversing the order of an existing array.</span></span> <span data-ttu-id="50dcd-170">Der folgende Code stellt `Array.rev` dar.</span><span class="sxs-lookup"><span data-stu-id="50dcd-170">The following code demonstrates `Array.rev`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet18.fs)]  

<span data-ttu-id="50dcd-171">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="50dcd-171">The output of the preceding code is as follows.</span></span>

```
"Hello world!"
```

<span data-ttu-id="50dcd-172">Sie können problemlos Funktionen im Arraymodul, die Arrays zu transformieren, indem Sie mit dem Pipeline-Operator kombinieren (`|>`), wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-172">You can easily combine functions in the array module that transform arrays by using the pipeline operator (`|>`), as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet19.fs)]

<span data-ttu-id="50dcd-173">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="50dcd-173">The output is</span></span>

```
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a><span data-ttu-id="50dcd-174">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="50dcd-174">Multidimensional Arrays</span></span>

<span data-ttu-id="50dcd-175">Ein mehrdimensionales Array kann erstellt werden, jedoch gibt es keine Syntax zum Schreiben eines mehrdimensionalen Arrayliterals.</span><span class="sxs-lookup"><span data-stu-id="50dcd-175">A multidimensional array can be created, but there is no syntax for writing a multidimensional array literal.</span></span> <span data-ttu-id="50dcd-176">Verwenden Sie den Operator [ `array2D` ](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) um ein Array aus einer Sequenz von Sequenzen von Arrayelementen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-176">Use the operator [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) to create an array from a sequence of sequences of array elements.</span></span> <span data-ttu-id="50dcd-177">Die Sequenzen können Array- oder Listenliterale sein.</span><span class="sxs-lookup"><span data-stu-id="50dcd-177">The sequences can be array or list literals.</span></span> <span data-ttu-id="50dcd-178">Im folgenden Code wird z. B. ein zweidimensionales Array erstellt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-178">For example, the following code creates a two-dimensional array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet20.fs)]

<span data-ttu-id="50dcd-179">Sie können auch die Funktion [ `Array2D.init` ](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) zum Initialisieren von Arrays mit zwei Dimensionen und ähnliche Funktionen für Arrays mit drei und vier Dimensionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="50dcd-179">You can also use the function [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) to initialize arrays of two dimensions, and similar functions are available for arrays of three and four dimensions.</span></span> <span data-ttu-id="50dcd-180">Diese Funktionen nehmen eine Funktion, die zum Erstellen der Elemente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="50dcd-180">These functions take a function that is used to create the elements.</span></span> <span data-ttu-id="50dcd-181">Verwenden Sie zum Erstellen eines zweidimensionalen Arrays, die Elemente, die festlegen, die auf einen Anfangswert anstelle einer Funktion enthält die [ `Array2D.create` ](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) arrays mit bis zu vier Dimensionen-Funktion, die auch für verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="50dcd-181">To create a two-dimensional array that contains elements set to an initial value instead of specifying a function, use the [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) function, which is also available for arrays up to four dimensions.</span></span> <span data-ttu-id="50dcd-182">Im folgenden Codebeispiel wird die Erstellung eines Arrays von Arrays mit den gewünschten Elementen veranschaulicht, und dann wird mit `Array2D.init` das gewünschte zweidimensionale Array generiert.</span><span class="sxs-lookup"><span data-stu-id="50dcd-182">The following code example first shows how to create an array of arrays that contain the desired elements, and then uses `Array2D.init` to generate the desired two-dimensional array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet21.fs)]

<span data-ttu-id="50dcd-183">Arrayindizierung und das Aufteilen von Syntax in Slices werden für Arrays bis zu Rang 4 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-183">Array indexing and slicing syntax is supported for arrays up to rank 4.</span></span> <span data-ttu-id="50dcd-184">Wenn Sie einen Index in mehreren Dimensionen angeben, verwenden Sie Kommas zum Trennen die Indizes, wie im folgenden Codebeispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-184">When you specify an index in multiple dimensions, you use commas to separate the indexes, as illustrated in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet22.fs)]

<span data-ttu-id="50dcd-185">Der Typ eines zweidimensionalen Arrays wird als `<type>[,]` (z. B.,`int[,]`, `double[,]`) geschrieben, und der Typ eines dreidimensionalen Arrays wird als `<type>[,,]` usw. für Arrays mit mehr Dimensionen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="50dcd-185">The type of a two-dimensional array is written out as `<type>[,]` (for example, `int[,]`, `double[,]`), and the type of a three-dimensional array is written as `<type>[,,]`, and so on for arrays of higher dimensions.</span></span>

<span data-ttu-id="50dcd-186">Nur eine Teilmenge der Funktionen für eindimensionale Arrays ist auch für mehrdimensionale Arrays verfügbar.</span><span class="sxs-lookup"><span data-stu-id="50dcd-186">Only a subset of the functions available for one-dimensional arrays is also available for multidimensional arrays.</span></span> <span data-ttu-id="50dcd-187">Weitere Informationen finden Sie unter [ `Collections.Array Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [ `Collections.Array2D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [ `Collections.Array3D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), und [ `Collections.Array4D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="50dcd-187">For more information, see [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), and [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span></span>

### <a name="array-slicing-and-multidimensional-arrays"></a><span data-ttu-id="50dcd-188">Arraysegmentierung und mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="50dcd-188">Array Slicing and Multidimensional Arrays</span></span>

<span data-ttu-id="50dcd-189">In einem zweidimensionalen Array (eine Matrix), können Sie eine Sub-Matrix extrahieren, indem Sie Bereiche angeben und Verwenden eines Platzhalters (`*`) Zeichen, ganze Zeilen oder Spalten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="50dcd-189">In a two-dimensional array (a matrix), you can extract a sub-matrix by specifying ranges and using a wildcard (`*`) character to specify whole rows or columns.</span></span>

```fsharp
/ Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

<span data-ttu-id="50dcd-190">Ab F# 3.1 können Sie ein mehrdimensionales Array in Unterarrays derselben oder einer niedrigeren Dimension zerlegen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-190">As of F# 3.1, you can decompose a multidimensional array into subarrays of the same or lower dimension.</span></span> <span data-ttu-id="50dcd-191">Beispielsweise können Sie einen Vektor aus einer Matrix abrufen, indem Sie eine einzelne Zeile oder eine Spalte angeben.</span><span class="sxs-lookup"><span data-stu-id="50dcd-191">For example, you can obtain a vector from a matrix by specifying a single row or column.</span></span>

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

<span data-ttu-id="50dcd-192">Sie können diese segmentierende Syntax für Typen verwenden, die die Elementzugriffsoperatoren und die überladenen `GetSlice`-Methoden implementieren.</span><span class="sxs-lookup"><span data-stu-id="50dcd-192">You can use this slicing syntax for types that implement the element access operators and overloaded `GetSlice` methods.</span></span> <span data-ttu-id="50dcd-193">Beispielsweise erstellt der folgende Code einen Matrixtyp, der das F# 2D-Array umschließt, eine Elementeigenschaft implementiert, um Unterstützung für die Arrayindizierung bereitzustellen, und drei Versionen von `GetSlice` implementiert.</span><span class="sxs-lookup"><span data-stu-id="50dcd-193">For example, the following code creates a Matrix type that wraps the F# 2D array, implements an Item property to provide support for array indexing, and implements three versions of `GetSlice`.</span></span> <span data-ttu-id="50dcd-194">Wenn Sie diesen Code als Vorlage für Ihre Matrixtypen verwenden können, können Sie alle in diesem Abschnitt beschriebenen Segmentierungsvorgänge verwenden.</span><span class="sxs-lookup"><span data-stu-id="50dcd-194">If you can use this code as a template for your matrix types, you can use all the slicing operations that this section describes.</span></span>

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
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a><span data-ttu-id="50dcd-195">Boolesche Funktionen für Arrays</span><span class="sxs-lookup"><span data-stu-id="50dcd-195">Boolean Functions on Arrays</span></span>

<span data-ttu-id="50dcd-196">Die Funktionen [ `Array.exists` ](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) und [ `Array.exists2` ](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) bzw. Testen von Elemente in einer oder zwei Arrays.</span><span class="sxs-lookup"><span data-stu-id="50dcd-196">The functions [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) and [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) test elements in either one or two arrays, respectively.</span></span> <span data-ttu-id="50dcd-197">Diese Funktionen akzeptieren eine Testfunktion und geben `true` zurück, wenn die Bedingung von einem Element (oder Elementpaaren für `Array.exists2`) erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="50dcd-197">These functions take a test function and return `true` if there is an element (or element pair for `Array.exists2`) that satisfies the condition.</span></span>

<span data-ttu-id="50dcd-198">Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.exists` und `Array.exists2`.</span><span class="sxs-lookup"><span data-stu-id="50dcd-198">The following code demonstrates the use of `Array.exists` and `Array.exists2`.</span></span> <span data-ttu-id="50dcd-199">In diesen Beispielen werden neue Funktionen durch das Übernehmen von nur einem der Argumente, in diesen Fällen das Funktionsargument, erstellt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-199">In these examples, new functions are created by applying only one of the arguments, in these cases, the function argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet23.fs)]

<span data-ttu-id="50dcd-200">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="50dcd-200">The output of the preceding code is as follows.</span></span>

```
true
false
false
true
```

<span data-ttu-id="50dcd-201">Auf ähnliche Weise die Funktion [ `Array.forall` ](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) testet ein Array, um zu bestimmen, ob jedes Element eine boolesche Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-201">Similarly, the function [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) tests an array to determine whether every element satisfies a Boolean condition.</span></span> <span data-ttu-id="50dcd-202">Die Variation [ `Array.forall2` ](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) führt die gleiche Aufgabe mithilfe einer booleschen Funktion, die Elemente zweier Arrays gleicher Länge umfasst.</span><span class="sxs-lookup"><span data-stu-id="50dcd-202">The variation [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) does the same thing by using a Boolean function that involves elements of two arrays of equal length.</span></span> <span data-ttu-id="50dcd-203">Im folgenden Code wird die Verwendung dieser Funktionen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="50dcd-203">The following code illustrates the use of these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet24.fs)]

<span data-ttu-id="50dcd-204">Die Ausgabe dieser Beispiele lautet folgendermaßen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-204">The output for these examples is as follows.</span></span>

```
false
true
true
false
```

### <a name="searching-arrays"></a><span data-ttu-id="50dcd-205">Durchsuchen von Arrays</span><span class="sxs-lookup"><span data-stu-id="50dcd-205">Searching Arrays</span></span>

<span data-ttu-id="50dcd-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) nimmt eine boolesche Funktion und gibt das erste Element, das für die die Funktion zurückgibt `true`, oder löst eine <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> , wenn kein Element die Bedingung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="50dcd-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) takes a Boolean function and returns the first element for which the function returns `true`, or raises a <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> if no element that satisfies the condition is found.</span></span> <span data-ttu-id="50dcd-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) entspricht dem `Array.find`, außer dass der Index des Elements statt dem Element selbst zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50dcd-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) is like `Array.find`, except that it returns the index of the element instead of the element itself.</span></span>

<span data-ttu-id="50dcd-208">Der folgende Code sucht mithilfe von `Array.find` und `Array.findIndex` eine Zahl, die sowohl ein perfektes Quadrat als auch perfekter Cube ist.</span><span class="sxs-lookup"><span data-stu-id="50dcd-208">The following code uses `Array.find` and `Array.findIndex` to locate a number that is both a perfect square and perfect cube.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet25.fs)]

<span data-ttu-id="50dcd-209">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-209">The output is as follows.</span></span>

```
The first element that is both a square and a cube is 64 and its index is 62.
```

<span data-ttu-id="50dcd-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) entspricht dem `Array.find`, außer dass das Ergebnis ein Optionstyp ist und es gibt `None` , wenn kein Element gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="50dcd-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) is like `Array.find`, except that its result is an option type, and it returns `None` if no element is found.</span></span> <span data-ttu-id="50dcd-211">`Array.tryFind` sollte statt `Array.find` verwendet werden, wenn nicht bekannt ist, ob ein entsprechendes Element im Array vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="50dcd-211">`Array.tryFind` should be used instead of `Array.find` when you do not know whether a matching element is in the array.</span></span> <span data-ttu-id="50dcd-212">Auf ähnliche Weise [ `Array.tryFindIndex` ](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) ähnelt [ `Array.findIndex` ](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) mit dem Unterschied, dass der Optionstyp der Rückgabewert ist.</span><span class="sxs-lookup"><span data-stu-id="50dcd-212">Similarly, [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) is like [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) except that the option type is the return value.</span></span> <span data-ttu-id="50dcd-213">Wenn kein Element gefunden wird, lautet die Option `None`.</span><span class="sxs-lookup"><span data-stu-id="50dcd-213">If no element is found, the option is `None`.</span></span>

<span data-ttu-id="50dcd-214">Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.tryFind`.</span><span class="sxs-lookup"><span data-stu-id="50dcd-214">The following code demonstrates the use of `Array.tryFind`.</span></span> <span data-ttu-id="50dcd-215">Dieser Code hängt vom vorherigen Code ab.</span><span class="sxs-lookup"><span data-stu-id="50dcd-215">This code depends on the previous code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet26.fs)]

<span data-ttu-id="50dcd-216">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-216">The output is as follows.</span></span>

```
Found an element: 1
Found an element: 729
```

<span data-ttu-id="50dcd-217">Verwendung [ `Array.tryPick` ](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) Wenn Sie ein Element zusätzlich zu suchen, sie transformieren müssen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-217">Use [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) when you need to transform an element in addition to finding it.</span></span> <span data-ttu-id="50dcd-218">Das Ergebnis ist das erste Element, für das die Funktion das transformierte Element als Optionswert zurückgibt, oder `None`, wenn kein solches Element gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="50dcd-218">The result is the first element for which the function returns the transformed element as an option value, or `None` if no such element is found.</span></span>

<span data-ttu-id="50dcd-219">Im folgenden Code wird die Verwendung von `Array.tryPick` veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="50dcd-219">The following code shows the use of `Array.tryPick`.</span></span> <span data-ttu-id="50dcd-220">In diesem Fall werden statt eines Lambdaausdrucks mehrere lokale Hilfsfunktionen definiert, um den Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-220">In this case, instead of a lambda expression, several local helper functions are defined to simplify the code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet27.fs)]

<span data-ttu-id="50dcd-221">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-221">The output is as follows.</span></span>

```
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
```

### <a name="performing-computations-on-arrays"></a><span data-ttu-id="50dcd-222">Ausführen von Berechnungen für Arrays</span><span class="sxs-lookup"><span data-stu-id="50dcd-222">Performing Computations on Arrays</span></span>

<span data-ttu-id="50dcd-223">Die [ `Array.average` ](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) Funktion gibt den Durchschnitt jedes Elements in einem Array zurück.</span><span class="sxs-lookup"><span data-stu-id="50dcd-223">The [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) function returns the average of each element in an array.</span></span> <span data-ttu-id="50dcd-224">Sie ist auf Elementtypen beschränkt, die die exakte Division durch eine ganze Zahl unterstützen, wozu Gleitkommatypen aber keine ganzzahligen Typen gehören.</span><span class="sxs-lookup"><span data-stu-id="50dcd-224">It is limited to element types that support exact division by an integer, which includes floating point types but not integral types.</span></span> <span data-ttu-id="50dcd-225">Die [ `Array.averageBy` ](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) Funktion gibt den Durchschnitt der Ergebnisse des Aufrufs einer Funktion auf jedes Element zurück.</span><span class="sxs-lookup"><span data-stu-id="50dcd-225">The [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) function returns the average of the results of calling a function on each element.</span></span> <span data-ttu-id="50dcd-226">Für ein Array eines ganzzahligen Typs können Sie `Array.averageBy` verwenden und für die Berechnung die Funktion jedes Element in einen Gleitkommatyp konvertieren lassen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-226">For an array of integral type, you can use `Array.averageBy` and have the function convert each element to a floating point type for the computation.</span></span>

<span data-ttu-id="50dcd-227">Verwendung [ `Array.max` ](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) oder [ `Array.min` ](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) um die maximale oder minimale Element abzurufen, wenn der Elementtyp dies unterstützt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-227">Use [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) or [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) to get the maximum or minimum element, if the element type supports it.</span></span> <span data-ttu-id="50dcd-228">Auf ähnliche Weise [ `Array.maxBy` ](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) und [ `Array.minBy` ](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) ermöglichen einer Funktion, die zuerst ausgeführt werden, ggf. zur Transformation eines Typs, der Vergleich unterstützt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-228">Similarly, [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) and [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) allow a function to be executed first, perhaps to transform to a type that supports comparison.</span></span>

<span data-ttu-id="50dcd-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) Fügt die Elemente eines Arrays hinzu und [ `Array.sumBy` ](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) Ruft eine Funktion für jedes Element und fügt die Ergebnisse zusammen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) adds the elements of an array, and [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) calls a function on each element and adds the results together.</span></span>

<span data-ttu-id="50dcd-230">Verwenden Sie zum Ausführen einer Funktion auf jedes Element in einem Array ohne zu speichern die Rückgabewerte [ `Array.iter` ](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span><span class="sxs-lookup"><span data-stu-id="50dcd-230">To execute a function on each element in an array without storing the return values, use [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span></span> <span data-ttu-id="50dcd-231">Verwenden Sie für eine Funktion mit zwei Arrays gleicher Länge [ `Array.iter2` ](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span><span class="sxs-lookup"><span data-stu-id="50dcd-231">For a function involving two arrays of equal length, use [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span></span> <span data-ttu-id="50dcd-232">Wenn Sie auch ein Array mit den Ergebnissen der Funktion behalten müssen, verwenden Sie [ `Array.map` ](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) oder [ `Array.map2` ](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), die zwei Arrays zu einem Zeitpunkt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="50dcd-232">If you also need to keep an array of the results of the function, use [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) or [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), which operates on two arrays at a time.</span></span>

<span data-ttu-id="50dcd-233">Die Varianten [ `Array.iteri` ](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) und [ `Array.iteri2` ](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) ermöglichen dem Index des Elements, der Berechnung beteiligt sein; das gleiche gilt für [ `Array.mapi` ](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) und [ `Array.mapi2` ](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span><span class="sxs-lookup"><span data-stu-id="50dcd-233">The variations [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) and [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) allow the index of the element to be involved in the computation; the same is true for [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) and [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span></span>

<span data-ttu-id="50dcd-234">Die Funktionen [ `Array.fold` ](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [ `Array.foldBack` ](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [ `Array.reduce` ](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [ `Array.reduceBack` ](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [ `Array.scan` ](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), und [ `Array.scanBack` ](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) führen Algorithmen aus, die alle Elemente eines Arrays einschließen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-234">The functions [`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), and [`Array.scanBack`](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) execute algorithms that involve all the elements of an array.</span></span> <span data-ttu-id="50dcd-235">Auf ähnliche Weise die Variationen [ `Array.fold2` ](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) und [ `Array.foldBack2` ](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) führen Berechnungen für zwei Arrays.</span><span class="sxs-lookup"><span data-stu-id="50dcd-235">Similarly, the variations [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) and [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) perform computations on two arrays.</span></span>

<span data-ttu-id="50dcd-236">Diese Funktionen zum Ausführen von Berechnungen entsprechen den Funktionen, mit dem gleichen Namen in der [listenmodul](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="50dcd-236">These functions for performing computations correspond to the functions of the same name in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="50dcd-237">Verwendungsbeispiele finden Sie unter [listet](lists.md).</span><span class="sxs-lookup"><span data-stu-id="50dcd-237">For usage examples, see [Lists](lists.md).</span></span>

### <a name="modifying-arrays"></a><span data-ttu-id="50dcd-238">Ändern von Arrays</span><span class="sxs-lookup"><span data-stu-id="50dcd-238">Modifying Arrays</span></span>

<span data-ttu-id="50dcd-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) Legt ein Element mit einem angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="50dcd-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="50dcd-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) Legt einen Bereich von Elementen in einem Array mit einem angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="50dcd-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) sets a range of elements in an array to a specified value.</span></span> <span data-ttu-id="50dcd-241">Das folgende Codebeispiel enthält ein Beispiel für `Array.fill`.</span><span class="sxs-lookup"><span data-stu-id="50dcd-241">The following code provides an example of `Array.fill`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet28.fs)]

<span data-ttu-id="50dcd-242">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="50dcd-242">The output is as follows.</span></span>

```
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

<span data-ttu-id="50dcd-243">Sie können [ `Array.blit` ](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) einen Unterabschnitt eines Arrays in ein anderes Array kopieren.</span><span class="sxs-lookup"><span data-stu-id="50dcd-243">You can use [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) to copy a subsection of one array to another array.</span></span>

### <a name="converting-to-and-from-other-types"></a><span data-ttu-id="50dcd-244">Konvertieren von Typen</span><span class="sxs-lookup"><span data-stu-id="50dcd-244">Converting to and from Other Types</span></span>

<span data-ttu-id="50dcd-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) erstellt ein Array aus einer Liste an.</span><span class="sxs-lookup"><span data-stu-id="50dcd-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) creates an array from a list.</span></span> <span data-ttu-id="50dcd-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) erstellt ein Array aus einer Sequenz an.</span><span class="sxs-lookup"><span data-stu-id="50dcd-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) creates an array from a sequence.</span></span> <span data-ttu-id="50dcd-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) und [ `Array.toSeq` ](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) konvertieren vom Arraytyp in diese anderen Auflistungstypen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) and [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) convert to these other collection types from the array type.</span></span>

### <a name="sorting-arrays"></a><span data-ttu-id="50dcd-248">Sortieren von Arrays</span><span class="sxs-lookup"><span data-stu-id="50dcd-248">Sorting Arrays</span></span>

<span data-ttu-id="50dcd-249">Verwendung [ `Array.sort` ](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) , mithilfe der generischen Vergleichsfunktion ein Array zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="50dcd-249">Use [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) to sort an array by using the generic comparison function.</span></span> <span data-ttu-id="50dcd-250">Verwenden [ `Array.sortBy` ](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) an, die einen Wert generiert eine Funktion als bezeichnet ein *Schlüssel*, sortieren, indem Sie die generische Vergleichsfunktion auf den Schlüssel verwenden.</span><span class="sxs-lookup"><span data-stu-id="50dcd-250">Use [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) to specify a function that generates a value, referred to as a *key*, to sort by using the generic comparison function on the key.</span></span> <span data-ttu-id="50dcd-251">Verwendung [ `Array.sortWith` ](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) , wenn Sie eine benutzerdefinierte Vergleichsfunktion bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="50dcd-251">Use [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) if you want to provide a custom comparison function.</span></span> <span data-ttu-id="50dcd-252">`Array.sort`, `Array.sortBy` und `Array.sortWith` geben das sortierte Array als neues Array zurück.</span><span class="sxs-lookup"><span data-stu-id="50dcd-252">`Array.sort`, `Array.sortBy`, and `Array.sortWith` all return the sorted array as a new array.</span></span> <span data-ttu-id="50dcd-253">Die Varianten [ `Array.sortInPlace` ](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [ `Array.sortInPlaceBy` ](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), und [ `Array.sortInPlaceWith` ](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) anstatt eine neue Ressourcengruppe des vorhandenen Arrays zu ändern.</span><span class="sxs-lookup"><span data-stu-id="50dcd-253">The variations [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), and [`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modify the existing array instead of returning a new one.</span></span>

### <a name="arrays-and-tuples"></a><span data-ttu-id="50dcd-254">Arrays und Tupel</span><span class="sxs-lookup"><span data-stu-id="50dcd-254">Arrays and Tuples</span></span>

<span data-ttu-id="50dcd-255">Die Funktionen [ `Array.zip` ](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) und [ `Array.unzip` ](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) Arrays von Tupelpaaren in Tupel von Arrays und umgekehrt zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="50dcd-255">The functions [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) and [`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convert arrays of tuple pairs to tuples of arrays and vice versa.</span></span> <span data-ttu-id="50dcd-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) und [ `Array.unzip3` ](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) sind ähnlich, außer dass sie mit Tupeln von drei Elementen oder Tupeln von drei Arrays arbeiten.</span><span class="sxs-lookup"><span data-stu-id="50dcd-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) and [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) are similar except that they work with tuples of three elements or tuples of three arrays.</span></span>

## <a name="parallel-computations-on-arrays"></a><span data-ttu-id="50dcd-257">Parallele Berechnungen auf Arrays</span><span class="sxs-lookup"><span data-stu-id="50dcd-257">Parallel Computations on Arrays</span></span>

<span data-ttu-id="50dcd-258">Das Modul [ `Array.Parallel` ](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) enthält Funktionen zum Ausführen paralleler Berechnungen für Arrays.</span><span class="sxs-lookup"><span data-stu-id="50dcd-258">The module [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contains functions for performing parallel computations on arrays.</span></span> <span data-ttu-id="50dcd-259">Dieses Modul ist in Anwendungen nicht verfügbar, die auf Versionen vor Version 4 von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="50dcd-259">This module is not available in applications that target versions of the .NET Framework prior to version 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="50dcd-260">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50dcd-260">See also</span></span>

- [<span data-ttu-id="50dcd-261">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="50dcd-261">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="50dcd-262">F#; Typen</span><span class="sxs-lookup"><span data-stu-id="50dcd-262">F#; Types</span></span>](fsharp-types.md)
