---
title: Arrays (F#)
description: Informationen Sie zum Erstellen und Verwenden von Arrays in der Programmiersprache f#.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 61fa9084-abdc-4cf5-8213-91ec1211866b
ms.openlocfilehash: 7c9d8405230f4d765d3afdeaa154ddc598d0d1ec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="arrays"></a><span data-ttu-id="6b609-104">Arrays</span><span class="sxs-lookup"><span data-stu-id="6b609-104">Arrays</span></span>

> [!NOTE]
<span data-ttu-id="6b609-105">Mit dem API-Referenz-Link gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="6b609-105">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="6b609-106">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6b609-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="6b609-107">Arrays sind nullbasierte, änderbare Sequenzen fester Größe von aufeinander folgenden Datenelementen, die alle den gleichen Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6b609-107">Arrays are fixed-size, zero-based, mutable collections of consecutive data elements that are all of the same type.</span></span>

## <a name="creating-arrays"></a><span data-ttu-id="6b609-108">Erstellen von Arrays</span><span class="sxs-lookup"><span data-stu-id="6b609-108">Creating Arrays</span></span>
<span data-ttu-id="6b609-109">Sie können Arrays auf verschiedene Arten erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b609-109">You can create arrays in several ways.</span></span> <span data-ttu-id="6b609-110">Sie können ein kleines Array erstellen, indem Sie aufeinanderfolgende Werte zwischen auflisten `[|` und `|]` und durch Semikolons getrennt, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6b609-110">You can create a small array by listing consecutive values between `[|` and `|]` and separated by semicolons, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet1.fs)]

<span data-ttu-id="6b609-111">Sie können auch jedes Element in einer eigenen Zeile anordnen. In diesem Fall ist das Semikolontrennzeichen optional.</span><span class="sxs-lookup"><span data-stu-id="6b609-111">You can also put each element on a separate line, in which case the semicolon separator is optional.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet2.fs)]

<span data-ttu-id="6b609-112">Der Typ der Arrayelemente wird von den verwendeten Literalen abgeleitet, und er muss konsistent sein.</span><span class="sxs-lookup"><span data-stu-id="6b609-112">The type of the array elements is inferred from the literals used and must be consistent.</span></span> <span data-ttu-id="6b609-113">Somit verursacht der folgende Code einen Fehler, da 1.0 ein Gleitkommawert ist und 2 und 3 ganze Zahlen sind.</span><span class="sxs-lookup"><span data-stu-id="6b609-113">The following code causes an error because 1.0 is a float and 2 and 3 are integers.</span></span>

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

<span data-ttu-id="6b609-114">Sie können Arrays mithilfe von Sequenzausdrücken erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b609-114">You can also use sequence expressions to create arrays.</span></span> <span data-ttu-id="6b609-115">Im folgenden Beispiel wird ein Array aus den Quadraten von ganzen Zahlen zwischen 1 und 10 erstellt.</span><span class="sxs-lookup"><span data-stu-id="6b609-115">Following is an example that creates an array of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet3.fs)]

<span data-ttu-id="6b609-116">Verwenden Sie `Array.zeroCreate`, um ein Array zu erstellen, dessen sämtliche Elemente mit 0 (null) initialisiert sind.</span><span class="sxs-lookup"><span data-stu-id="6b609-116">To create an array in which all the elements are initialized to zero, use `Array.zeroCreate`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet4.fs)]
    
## <a name="accessing-elements"></a><span data-ttu-id="6b609-117">Zugreifen auf Elemente</span><span class="sxs-lookup"><span data-stu-id="6b609-117">Accessing Elements</span></span>

<span data-ttu-id="6b609-118">Sie können Elemente des Arrays zugreifen, mit dem Punktoperator (`.`) und Klammern (`[` und `]`).</span><span class="sxs-lookup"><span data-stu-id="6b609-118">You can access array elements by using a dot operator (`.`) and brackets (`[` and `]`).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet5.fs)]

<span data-ttu-id="6b609-119">Arrayindizes beginnen bei 0.</span><span class="sxs-lookup"><span data-stu-id="6b609-119">Array indexes start at 0.</span></span>

<span data-ttu-id="6b609-120">Der Zugriff auf Arrayelemente kann auch mit Slicenotation erfolgen, die es Ihnen ermöglicht, einen Teilbereich des Arrays anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6b609-120">You can also access array elements by using slice notation, which enables you to specify a subrange of the array.</span></span> <span data-ttu-id="6b609-121">Im Folgenden erhalten Sie Beispiele für Slicenotation.</span><span class="sxs-lookup"><span data-stu-id="6b609-121">Examples of slice notation follow.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet51.fs)]

<span data-ttu-id="6b609-122">Bei Verwendung von Slicenotation wird eine neue Kopie des Arrays erstellt.</span><span class="sxs-lookup"><span data-stu-id="6b609-122">When slice notation is used, a new copy of the array is created.</span></span>


## <a name="array-types-and-modules"></a><span data-ttu-id="6b609-123">Arraytypen und Module</span><span class="sxs-lookup"><span data-stu-id="6b609-123">Array Types and Modules</span></span>
<span data-ttu-id="6b609-124">Alle F#-Arrays sind vom .NET Framework-Typ <xref:System.Array?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6b609-124">The type of all F# arrays is the .NET Framework type <xref:System.Array?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6b609-125">Daher unterstützen F#-Arrays alle in <xref:System.Array?displayProperty=nameWithType> verfügbaren Funktionen.</span><span class="sxs-lookup"><span data-stu-id="6b609-125">Therefore, F# arrays support all the functionality available in <xref:System.Array?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="6b609-126">Das Bibliotheksmodul [ `Microsoft.FSharp.Collections.Array` ](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) unterstützt Operationen auf eindimensionalen Arrays.</span><span class="sxs-lookup"><span data-stu-id="6b609-126">The library module [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) supports operations on one-dimensional arrays.</span></span> <span data-ttu-id="6b609-127">Die Module `Array2D`, `Array3D` und `Array4D` enthalten Funktionen, die Operationen für Arrays mit zwei, drei bzw. vier Dimensionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6b609-127">The modules `Array2D`, `Array3D`, and `Array4D` contain functions that support operations on arrays of two, three, and four dimensions, respectively.</span></span> <span data-ttu-id="6b609-128">Mit <xref:System.Array?displayProperty=nameWithType> können Sie Arrays mit einem Rang größer vier erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b609-128">You can create arrays of rank greater than four by using <xref:System.Array?displayProperty=nameWithType>.</span></span>

### <a name="simple-functions"></a><span data-ttu-id="6b609-129">Einfache Funktionen</span><span class="sxs-lookup"><span data-stu-id="6b609-129">Simple Functions</span></span>
<span data-ttu-id="6b609-130">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc)Ruft ein Element ab.</span><span class="sxs-lookup"><span data-stu-id="6b609-130">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) gets an element.</span></span> <span data-ttu-id="6b609-131">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f)Gibt die Länge eines Arrays.</span><span class="sxs-lookup"><span data-stu-id="6b609-131">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) gives the length of an array.</span></span> <span data-ttu-id="6b609-132">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790)Legt ein Element an einen angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="6b609-132">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="6b609-133">Im folgenden Codebeispiel wird die Verwendung dieser Funktionen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6b609-133">The following code example illustrates the use of these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet9.fs)]

<span data-ttu-id="6b609-134">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="6b609-134">The output is as follows.</span></span>

```
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a><span data-ttu-id="6b609-135">Funktionen, die Arrays generieren</span><span class="sxs-lookup"><span data-stu-id="6b609-135">Functions That Create Arrays</span></span>

<span data-ttu-id="6b609-136">Mehrere Funktionen erstellen Arrays, ohne ein vorhandenes Array zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="6b609-136">Several functions create arrays without requiring an existing array.</span></span> <span data-ttu-id="6b609-137">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32)erstellt ein neues Array, das keine Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="6b609-137">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) creates a new array that does not contain any elements.</span></span> <span data-ttu-id="6b609-138">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be)erstellt ein Array mit einer angegebenen Größe und legt alle Elemente auf bereitgestellte Werte fest.</span><span class="sxs-lookup"><span data-stu-id="6b609-138">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) creates an array of a specified size and sets all the elements to provided values.</span></span> <span data-ttu-id="6b609-139">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665)erstellt ein Array unter Verwendung einer Dimensionen und einer Funktion, um die Elemente zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6b609-139">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) creates an array, given a dimension and a function to generate the elements.</span></span> <span data-ttu-id="6b609-140">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)erstellt ein Array, in dem alle Elemente auf den Wert 0 für den Typ des Arrays initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6b609-140">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) creates an array in which all the elements are initialized to the zero value for the array's type.</span></span> <span data-ttu-id="6b609-141">Dieser Code demonstriert die Funktionen.</span><span class="sxs-lookup"><span data-stu-id="6b609-141">The following code demonstrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet91.fs)]

<span data-ttu-id="6b609-142">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="6b609-142">The output is as follows.</span></span>

```
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

<span data-ttu-id="6b609-143">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f)erstellt ein neues Array, das Elemente enthält, die aus einem vorhandenen Array kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="6b609-143">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) creates a new array that contains elements that are copied from an existing array.</span></span> <span data-ttu-id="6b609-144">Beachten Sie, dass die Kopie eine flache Kopie ist, d. h., wenn der Elementtyp ein Verweistyp ist, wird nur der Verweis, nicht das zugrunde liegende Objekt kopiert.</span><span class="sxs-lookup"><span data-stu-id="6b609-144">Note that the copy is a shallow copy, which means that if the element type is a reference type, only the reference is copied, not the underlying object.</span></span> <span data-ttu-id="6b609-145">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6b609-145">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet11.fs)]

<span data-ttu-id="6b609-146">Der obige Code gibt Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="6b609-146">The output of the preceding code is as follows:</span></span>

```
[|Test1; Test2; |]
[|; Test2; |]
```

<span data-ttu-id="6b609-147">Die Zeichenfolge `Test1` wird nur im ersten Array angezeigt, da der Vorgang der Erstellung eines neuen Elements, den Verweis in `firstArray` überschreibt, aber sich nicht auf den ursprünglichen Verweis auf eine leere Zeichenfolge auswirkt, die immer noch im `secondArray` vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6b609-147">The string `Test1` appears only in the first array because the operation of creating a new element overwrites the reference in `firstArray` but does not affect the original reference to an empty string that is still present in `secondArray`.</span></span> <span data-ttu-id="6b609-148">Die Zeichenfolge `Test2` wird in beiden Arrays angezeigt, da sich die `Insert`-Operation für den <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Typ auf das zugrundeliegende <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Objekt auswirkt, auf das in beiden Arrays verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6b609-148">The string `Test2` appears in both arrays because the `Insert` operation on the <xref:System.Text.StringBuilder?displayProperty=nameWithType> type affects the underlying <xref:System.Text.StringBuilder?displayProperty=nameWithType> object, which is referenced in both arrays.</span></span>

<span data-ttu-id="6b609-149">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d)generiert ein neues Array aus einem Teilbereich eines Arrays.</span><span class="sxs-lookup"><span data-stu-id="6b609-149">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) generates a new array from a subrange of an array.</span></span> <span data-ttu-id="6b609-150">Sie geben den Teilbereich an, indem Sie den Startindex und die Länge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6b609-150">You specify the subrange by providing the starting index and the length.</span></span> <span data-ttu-id="6b609-151">Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.sub`.</span><span class="sxs-lookup"><span data-stu-id="6b609-151">The following code demonstrates the use of `Array.sub`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet12.fs)]

<span data-ttu-id="6b609-152">Die Ausgabe zeigt an, dass das Unterfeld bei Element "5" beginnt und 10 Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="6b609-152">The output shows that the subarray starts at element 5 and contains 10 elements.</span></span>

```
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```
<span data-ttu-id="6b609-153">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911)erstellt ein neues Array von zwei vorhandene Arrays kombiniert.</span><span class="sxs-lookup"><span data-stu-id="6b609-153">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) creates a new array by combining two existing arrays.</span></span>

<span data-ttu-id="6b609-154">Der folgende Code zeigt **Array.append**.</span><span class="sxs-lookup"><span data-stu-id="6b609-154">The following code demonstrates **Array.append**.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet13.fs)]

<span data-ttu-id="6b609-155">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="6b609-155">The output of the preceding code is as follows.</span></span>

```
[|1; 2; 3; 4; 5; 6|]
```

<span data-ttu-id="6b609-156">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09)Wählt Elemente eines Arrays in ein neues Array eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6b609-156">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) selects elements of an array to include in a new array.</span></span> <span data-ttu-id="6b609-157">Der folgende Code stellt `Array.choose` dar.</span><span class="sxs-lookup"><span data-stu-id="6b609-157">The following code demonstrates `Array.choose`.</span></span> <span data-ttu-id="6b609-158">Beachten Sie, dass der Elementtyp des Arrays nicht zum Typ des Werts passen muss, der im Optionstyp zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6b609-158">Note that the element type of the array does not have to match the type of the value returned in the option type.</span></span> <span data-ttu-id="6b609-159">In diesem Beispiel ist der Elementtyp `int`, und die Option ist das Ergebnis einer Polynomfunktion (`elem*elem - 1`) als Gleitkommazahl.</span><span class="sxs-lookup"><span data-stu-id="6b609-159">In this example, the element type is `int` and the option is the result of a polynomial function, `elem*elem - 1`, as a floating point number.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet14.fs)]

<span data-ttu-id="6b609-160">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="6b609-160">The output of the preceding code is as follows.</span></span>

```
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

<span data-ttu-id="6b609-161">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a)führt eine angegebene Funktion auf jedes Arrayelement eines vorhandenen Arrays und sammelt die von der Funktion generierten Elemente und kombiniert sie in ein neues Array.</span><span class="sxs-lookup"><span data-stu-id="6b609-161">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) runs a specified function on each array element of an existing array and then collects the elements generated by the function and combines them into a new array.</span></span> <span data-ttu-id="6b609-162">Der folgende Code stellt `Array.collect` dar.</span><span class="sxs-lookup"><span data-stu-id="6b609-162">The following code demonstrates `Array.collect`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet15.fs)]

<span data-ttu-id="6b609-163">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="6b609-163">The output of the preceding code is as follows.</span></span>

```
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

<span data-ttu-id="6b609-164">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302)verwendet eine Sequenz von Arrays und kombiniert sie zu einem Array.</span><span class="sxs-lookup"><span data-stu-id="6b609-164">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) takes a sequence of arrays and combines them into a single array.</span></span> <span data-ttu-id="6b609-165">Der folgende Code stellt `Array.concat` dar.</span><span class="sxs-lookup"><span data-stu-id="6b609-165">The following code demonstrates `Array.concat`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet16.fs)]

<span data-ttu-id="6b609-166">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="6b609-166">The output of the preceding code is as follows.</span></span>

```
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

<span data-ttu-id="6b609-167">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede)nimmt eine boolesche Bedingungsfunktion und generiert ein neues Array, das nur die Elemente des Eingabearrays enthält, für die die Bedingung "true" ist.</span><span class="sxs-lookup"><span data-stu-id="6b609-167">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) takes a Boolean condition function and generates a new array that contains only those elements from the input array for which the condition is true.</span></span> <span data-ttu-id="6b609-168">Der folgende Code stellt `Array.filter` dar.</span><span class="sxs-lookup"><span data-stu-id="6b609-168">The following code demonstrates `Array.filter`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet17.fs)]

<span data-ttu-id="6b609-169">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="6b609-169">The output of the preceding code is as follows.</span></span>

```
[|2; 4; 6; 8; 10|]
```

<span data-ttu-id="6b609-170">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709)generiert ein neues Array, indem die Reihenfolge eines vorhandenen Arrays umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="6b609-170">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) generates a new array by reversing the order of an existing array.</span></span> <span data-ttu-id="6b609-171">Der folgende Code stellt `Array.rev` dar.</span><span class="sxs-lookup"><span data-stu-id="6b609-171">The following code demonstrates `Array.rev`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet18.fs)]  

<span data-ttu-id="6b609-172">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="6b609-172">The output of the preceding code is as follows.</span></span>

```
"Hello world!"
```

<span data-ttu-id="6b609-173">Funktionen im Arraymodul, die Arrays umwandeln, mithilfe des pipelineoperators können problemlos kombiniert werden (`|>`), wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6b609-173">You can easily combine functions in the array module that transform arrays by using the pipeline operator (`|>`), as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet19.fs)]

<span data-ttu-id="6b609-174">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6b609-174">The output is</span></span>

```
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a><span data-ttu-id="6b609-175">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="6b609-175">Multidimensional Arrays</span></span>

<span data-ttu-id="6b609-176">Ein mehrdimensionales Array kann erstellt werden, jedoch gibt es keine Syntax zum Schreiben eines mehrdimensionalen Arrayliterals.</span><span class="sxs-lookup"><span data-stu-id="6b609-176">A multidimensional array can be created, but there is no syntax for writing a multidimensional array literal.</span></span> <span data-ttu-id="6b609-177">Verwenden Sie den Operator [ `array2D` ](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) um ein Array aus einer Sequenz von Sequenzen von Arrayelementen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b609-177">Use the operator [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) to create an array from a sequence of sequences of array elements.</span></span> <span data-ttu-id="6b609-178">Die Sequenzen können Array- oder Listenliterale sein.</span><span class="sxs-lookup"><span data-stu-id="6b609-178">The sequences can be array or list literals.</span></span> <span data-ttu-id="6b609-179">Im folgenden Code wird z. B. ein zweidimensionales Array erstellt.</span><span class="sxs-lookup"><span data-stu-id="6b609-179">For example, the following code creates a two-dimensional array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet20.fs)]

<span data-ttu-id="6b609-180">Sie können auch mithilfe der Funktion [ `Array2D.init` ](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) zum Initialisieren von Arrays mit zwei Dimensionen und ähnliche Funktionen für Arrays mit drei und vier Dimensionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6b609-180">You can also use the function [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) to initialize arrays of two dimensions, and similar functions are available for arrays of three and four dimensions.</span></span> <span data-ttu-id="6b609-181">Diese Funktionen nehmen eine Funktion, die zum Erstellen der Elemente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6b609-181">These functions take a function that is used to create the elements.</span></span> <span data-ttu-id="6b609-182">Um ein zweidimensionales Array zu erstellen, die auf einen Anfangswert angeben einer funktionsrückgabewerts, statt festgelegt Elemente enthält, verwenden Sie die [ `Array2D.create` ](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) Funktion, die auch für arrays bis zu vier Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="6b609-182">To create a two-dimensional array that contains elements set to an initial value instead of specifying a function, use the [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) function, which is also available for arrays up to four dimensions.</span></span> <span data-ttu-id="6b609-183">Im folgenden Codebeispiel wird die Erstellung eines Arrays von Arrays mit den gewünschten Elementen veranschaulicht, und dann wird mit `Array2D.init` das gewünschte zweidimensionale Array generiert.</span><span class="sxs-lookup"><span data-stu-id="6b609-183">The following code example first shows how to create an array of arrays that contain the desired elements, and then uses `Array2D.init` to generate the desired two-dimensional array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet21.fs)]

<span data-ttu-id="6b609-184">Arrayindizierung und das Aufteilen von Syntax in Slices werden für Arrays bis zu Rang 4 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6b609-184">Array indexing and slicing syntax is supported for arrays up to rank 4.</span></span> <span data-ttu-id="6b609-185">Wenn Sie einen Index in mehreren Dimensionen angeben, verwenden Sie Kommas zum Trennen der Indizes, wie im folgenden Codebeispiel wird veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6b609-185">When you specify an index in multiple dimensions, you use commas to separate the indexes, as illustrated in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet22.fs)]
    
<span data-ttu-id="6b609-186">Der Typ eines zweidimensionalen Arrays wird als `<type>[,]` (z. B.,`int[,]`, `double[,]`) geschrieben, und der Typ eines dreidimensionalen Arrays wird als `<type>[,,]` usw. für Arrays mit mehr Dimensionen geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b609-186">The type of a two-dimensional array is written out as `<type>[,]` (for example, `int[,]`, `double[,]`), and the type of a three-dimensional array is written as `<type>[,,]`, and so on for arrays of higher dimensions.</span></span>

<span data-ttu-id="6b609-187">Nur eine Teilmenge der Funktionen für eindimensionale Arrays ist auch für mehrdimensionale Arrays verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6b609-187">Only a subset of the functions available for one-dimensional arrays is also available for multidimensional arrays.</span></span> <span data-ttu-id="6b609-188">Weitere Informationen finden Sie unter [ `Collections.Array Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [ `Collections.Array2D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [ `Collections.Array3D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), und [ `Collections.Array4D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="6b609-188">For more information, see [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), and [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span></span>

### <a name="array-slicing-and-multidimensional-arrays"></a><span data-ttu-id="6b609-189">Arraysegmentierung und mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="6b609-189">Array Slicing and Multidimensional Arrays</span></span>

<span data-ttu-id="6b609-190">In ein zweidimensionales Array (eine Matrix), können Sie eine Sub-Matrix extrahieren, indem Sie Bereiche angeben und Platzhalter (`*`) Zeichen, ganze Zeilen oder Spalten an.</span><span class="sxs-lookup"><span data-stu-id="6b609-190">In a two-dimensional array (a matrix), you can extract a sub-matrix by specifying ranges and using a wildcard (`*`) character to specify whole rows or columns.</span></span>

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

<span data-ttu-id="6b609-191">Ab F# 3.1 können Sie ein mehrdimensionales Array in Unterarrays derselben oder einer niedrigeren Dimension zerlegen.</span><span class="sxs-lookup"><span data-stu-id="6b609-191">As of F# 3.1, you can decompose a multidimensional array into subarrays of the same or lower dimension.</span></span> <span data-ttu-id="6b609-192">Beispielsweise können Sie einen Vektor aus einer Matrix abrufen, indem Sie eine einzelne Zeile oder eine Spalte angeben.</span><span class="sxs-lookup"><span data-stu-id="6b609-192">For example, you can obtain a vector from a matrix by specifying a single row or column.</span></span>

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

<span data-ttu-id="6b609-193">Sie können diese segmentierende Syntax für Typen verwenden, die die Elementzugriffsoperatoren und die überladenen `GetSlice`-Methoden implementieren.</span><span class="sxs-lookup"><span data-stu-id="6b609-193">You can use this slicing syntax for types that implement the element access operators and overloaded `GetSlice` methods.</span></span> <span data-ttu-id="6b609-194">Beispielsweise erstellt der folgende Code einen Matrixtyp, der das F# 2D-Array umschließt, eine Elementeigenschaft implementiert, um Unterstützung für die Arrayindizierung bereitzustellen, und drei Versionen von `GetSlice` implementiert.</span><span class="sxs-lookup"><span data-stu-id="6b609-194">For example, the following code creates a Matrix type that wraps the F# 2D array, implements an Item property to provide support for array indexing, and implements three versions of `GetSlice`.</span></span> <span data-ttu-id="6b609-195">Wenn Sie diesen Code als Vorlage für Ihre Matrixtypen verwenden können, können Sie alle in diesem Abschnitt beschriebenen Segmentierungsvorgänge verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b609-195">If you can use this code as a template for your matrix types, you can use all the slicing operations that this section describes.</span></span>

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

### <a name="boolean-functions-on-arrays"></a><span data-ttu-id="6b609-196">Boolesche Funktionen für Arrays</span><span class="sxs-lookup"><span data-stu-id="6b609-196">Boolean Functions on Arrays</span></span>

<span data-ttu-id="6b609-197">Die Funktionen [ `Array.exists` ](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) und [ `Array.exists2` ](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) bzw. Testen Elemente in einer oder zwei Arrays.</span><span class="sxs-lookup"><span data-stu-id="6b609-197">The functions [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) and [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) test elements in either one or two arrays, respectively.</span></span> <span data-ttu-id="6b609-198">Diese Funktionen akzeptieren eine Testfunktion und geben `true` zurück, wenn die Bedingung von einem Element (oder Elementpaaren für `Array.exists2`) erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="6b609-198">These functions take a test function and return `true` if there is an element (or element pair for `Array.exists2`) that satisfies the condition.</span></span>

<span data-ttu-id="6b609-199">Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.exists` und `Array.exists2`.</span><span class="sxs-lookup"><span data-stu-id="6b609-199">The following code demonstrates the use of `Array.exists` and `Array.exists2`.</span></span> <span data-ttu-id="6b609-200">In diesen Beispielen werden neue Funktionen durch das Übernehmen von nur einem der Argumente, in diesen Fällen das Funktionsargument, erstellt.</span><span class="sxs-lookup"><span data-stu-id="6b609-200">In these examples, new functions are created by applying only one of the arguments, in these cases, the function argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet23.fs)]

<span data-ttu-id="6b609-201">Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.</span><span class="sxs-lookup"><span data-stu-id="6b609-201">The output of the preceding code is as follows.</span></span>

```
true
false
false
true
```

<span data-ttu-id="6b609-202">Auf ähnliche Weise die Funktion [ `Array.forall` ](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) testet ein Array, um zu bestimmen, ob jedes Element eine boolesche Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="6b609-202">Similarly, the function [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) tests an array to determine whether every element satisfies a Boolean condition.</span></span> <span data-ttu-id="6b609-203">Die Variation [ `Array.forall2` ](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) führt die gleiche Aufgabe mithilfe einer booleschen Funktion, die Elemente zweier Arrays gleicher Länge enthält.</span><span class="sxs-lookup"><span data-stu-id="6b609-203">The variation [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) does the same thing by using a Boolean function that involves elements of two arrays of equal length.</span></span> <span data-ttu-id="6b609-204">Im folgenden Code wird die Verwendung dieser Funktionen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6b609-204">The following code illustrates the use of these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet24.fs)]

<span data-ttu-id="6b609-205">Die Ausgabe dieser Beispiele lautet folgendermaßen.</span><span class="sxs-lookup"><span data-stu-id="6b609-205">The output for these examples is as follows.</span></span>

```
false
true
true
false
```

### <a name="searching-arrays"></a><span data-ttu-id="6b609-206">Durchsuchen von Arrays</span><span class="sxs-lookup"><span data-stu-id="6b609-206">Searching Arrays</span></span>

<span data-ttu-id="6b609-207">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33)nimmt eine boolesche Funktion und gibt das erste Element, für die die Funktion zurückgibt `true`, oder löst eine <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> , wenn kein Element, das die Bedingung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="6b609-207">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) takes a Boolean function and returns the first element for which the function returns `true`, or raises a <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> if no element that satisfies the condition is found.</span></span> <span data-ttu-id="6b609-208">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f)entspricht dem `Array.find`, außer dass der Index des Elements statt dem Element selbst zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6b609-208">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) is like `Array.find`, except that it returns the index of the element instead of the element itself.</span></span>

<span data-ttu-id="6b609-209">Der folgende Code sucht mithilfe von `Array.find` und `Array.findIndex` eine Zahl, die sowohl ein perfektes Quadrat als auch perfekter Cube ist.</span><span class="sxs-lookup"><span data-stu-id="6b609-209">The following code uses `Array.find` and `Array.findIndex` to locate a number that is both a perfect square and perfect cube.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet25.fs)]

<span data-ttu-id="6b609-210">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="6b609-210">The output is as follows.</span></span>

```
The first element that is both a square and a cube is 64 and its index is 62.
```

<span data-ttu-id="6b609-211">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9)entspricht dem `Array.find`, außer dass das Ergebnis ein Optionstyp ist und es gibt `None` , wenn kein Element gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="6b609-211">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) is like `Array.find`, except that its result is an option type, and it returns `None` if no element is found.</span></span> <span data-ttu-id="6b609-212">`Array.tryFind` sollte statt `Array.find` verwendet werden, wenn nicht bekannt ist, ob ein entsprechendes Element im Array vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6b609-212">`Array.tryFind` should be used instead of `Array.find` when you do not know whether a matching element is in the array.</span></span> <span data-ttu-id="6b609-213">Auf ähnliche Weise [ `Array.tryFindIndex` ](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) entspricht [ `Array.findIndex` ](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) mit dem Unterschied, dass der Optionstyp der Rückgabewert ist.</span><span class="sxs-lookup"><span data-stu-id="6b609-213">Similarly, [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) is like [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) except that the option type is the return value.</span></span> <span data-ttu-id="6b609-214">Wenn kein Element gefunden wird, lautet die Option `None`.</span><span class="sxs-lookup"><span data-stu-id="6b609-214">If no element is found, the option is `None`.</span></span>

<span data-ttu-id="6b609-215">Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.tryFind`.</span><span class="sxs-lookup"><span data-stu-id="6b609-215">The following code demonstrates the use of `Array.tryFind`.</span></span> <span data-ttu-id="6b609-216">Dieser Code hängt vom vorherigen Code ab.</span><span class="sxs-lookup"><span data-stu-id="6b609-216">This code depends on the previous code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet26.fs)]

<span data-ttu-id="6b609-217">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="6b609-217">The output is as follows.</span></span>

```
Found an element: 1
Found an element: 729
```

<span data-ttu-id="6b609-218">Verwendung [ `Array.tryPick` ](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) Wenn Sie ein Element zusätzlich zum Auffinden transformieren müssen.</span><span class="sxs-lookup"><span data-stu-id="6b609-218">Use [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) when you need to transform an element in addition to finding it.</span></span> <span data-ttu-id="6b609-219">Das Ergebnis ist das erste Element, für das die Funktion das transformierte Element als Optionswert zurückgibt, oder `None`, wenn kein solches Element gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="6b609-219">The result is the first element for which the function returns the transformed element as an option value, or `None` if no such element is found.</span></span>

<span data-ttu-id="6b609-220">Im folgenden Code wird die Verwendung von `Array.tryPick` veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6b609-220">The following code shows the use of `Array.tryPick`.</span></span> <span data-ttu-id="6b609-221">In diesem Fall werden statt eines Lambdaausdrucks mehrere lokale Hilfsfunktionen definiert, um den Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="6b609-221">In this case, instead of a lambda expression, several local helper functions are defined to simplify the code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet27.fs)]

<span data-ttu-id="6b609-222">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="6b609-222">The output is as follows.</span></span>

```
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
```

### <a name="performing-computations-on-arrays"></a><span data-ttu-id="6b609-223">Ausführen von Berechnungen für Arrays</span><span class="sxs-lookup"><span data-stu-id="6b609-223">Performing Computations on Arrays</span></span>

<span data-ttu-id="6b609-224">Die [ `Array.average` ](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) Funktion gibt den Durchschnitt jedes Elements in einem Array zurück.</span><span class="sxs-lookup"><span data-stu-id="6b609-224">The [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) function returns the average of each element in an array.</span></span> <span data-ttu-id="6b609-225">Sie ist auf Elementtypen beschränkt, die die exakte Division durch eine ganze Zahl unterstützen, wozu Gleitkommatypen aber keine ganzzahligen Typen gehören.</span><span class="sxs-lookup"><span data-stu-id="6b609-225">It is limited to element types that support exact division by an integer, which includes floating point types but not integral types.</span></span> <span data-ttu-id="6b609-226">Die [ `Array.averageBy` ](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) Funktion gibt den Durchschnitt der Ergebnisse des Aufrufs einer Funktion auf jedes Element zurück.</span><span class="sxs-lookup"><span data-stu-id="6b609-226">The [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) function returns the average of the results of calling a function on each element.</span></span> <span data-ttu-id="6b609-227">Für ein Array eines ganzzahligen Typs können Sie `Array.averageBy` verwenden und für die Berechnung die Funktion jedes Element in einen Gleitkommatyp konvertieren lassen.</span><span class="sxs-lookup"><span data-stu-id="6b609-227">For an array of integral type, you can use `Array.averageBy` and have the function convert each element to a floating point type for the computation.</span></span>

<span data-ttu-id="6b609-228">Verwendung [ `Array.max` ](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) oder [ `Array.min` ](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) auf die maximale oder minimale Element abzurufen, wenn der Elementtyp dies unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6b609-228">Use [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) or [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) to get the maximum or minimum element, if the element type supports it.</span></span> <span data-ttu-id="6b609-229">Auf ähnliche Weise [ `Array.maxBy` ](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) und [ `Array.minBy` ](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) ermöglichen einer Funktion, die zuerst ausgeführt werden, ggf. zur Transformation eines Typs, der Vergleich unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6b609-229">Similarly, [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) and [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) allow a function to be executed first, perhaps to transform to a type that supports comparison.</span></span>

<span data-ttu-id="6b609-230">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2)Fügt die Elemente eines Arrays hinzu und [ `Array.sumBy` ](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) Ruft eine Funktion auf jedes Element und fügt die Ergebnisse zusammen.</span><span class="sxs-lookup"><span data-stu-id="6b609-230">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) adds the elements of an array, and [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) calls a function on each element and adds the results together.</span></span>

<span data-ttu-id="6b609-231">Verwenden, um eine Funktion auf jedes Element in einem Array auszuführen, ohne zu speichern die Rückgabewerte [ `Array.iter` ](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span><span class="sxs-lookup"><span data-stu-id="6b609-231">To execute a function on each element in an array without storing the return values, use [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span></span> <span data-ttu-id="6b609-232">Verwenden Sie für eine Funktion mit zwei Arrays gleicher Länge [ `Array.iter2` ](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span><span class="sxs-lookup"><span data-stu-id="6b609-232">For a function involving two arrays of equal length, use [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span></span> <span data-ttu-id="6b609-233">Wenn Sie auch ein Array der Ergebnisse der Funktion beibehalten müssen, verwenden Sie [ `Array.map` ](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) oder [ `Array.map2` ](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), die zu einem Zeitpunkt wirkt auf zwei Arrays.</span><span class="sxs-lookup"><span data-stu-id="6b609-233">If you also need to keep an array of the results of the function, use [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) or [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), which operates on two arrays at a time.</span></span>

<span data-ttu-id="6b609-234">Die Variationen [ `Array.iteri` ](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) und [ `Array.iteri2` ](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) ermöglichen dem Index des Elements, das in die Berechnung einbezogen werden, die dasselbe gilt für [ `Array.mapi` ](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) und [ `Array.mapi2` ](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span><span class="sxs-lookup"><span data-stu-id="6b609-234">The variations [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) and [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) allow the index of the element to be involved in the computation; the same is true for [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) and [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span></span>

<span data-ttu-id="6b609-235">Die Funktionen [ `Array.fold` ](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [ `Array.foldBack` ](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [ `Array.reduce` ](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [ `Array.reduceBack` ](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [ `Array.scan` ](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), und [ `Array.scanBack` ](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) führen Algorithmen aus, die alle Elemente eines Arrays einschließen.</span><span class="sxs-lookup"><span data-stu-id="6b609-235">The functions [`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), and [`Array.scanBack`](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) execute algorithms that involve all the elements of an array.</span></span> <span data-ttu-id="6b609-236">Auf ähnliche Weise, die Variationen [ `Array.fold2` ](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) und [ `Array.foldBack2` ](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) führen Berechnungen für zwei Arrays.</span><span class="sxs-lookup"><span data-stu-id="6b609-236">Similarly, the variations [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) and [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) perform computations on two arrays.</span></span>

<span data-ttu-id="6b609-237">Diese Funktionen zum Ausführen von Berechnungen entsprechen den Funktionen mit dem gleichen Namen in der [listenmodul](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="6b609-237">These functions for performing computations correspond to the functions of the same name in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="6b609-238">Verwendungsbeispiele finden Sie unter [listet](lists.md).</span><span class="sxs-lookup"><span data-stu-id="6b609-238">For usage examples, see [Lists](lists.md).</span></span>

### <a name="modifying-arrays"></a><span data-ttu-id="6b609-239">Ändern von Arrays</span><span class="sxs-lookup"><span data-stu-id="6b609-239">Modifying Arrays</span></span>

<span data-ttu-id="6b609-240">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790)Legt ein Element an einen angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="6b609-240">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="6b609-241">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2)Legt einen Bereich von Elementen in einem Array auf einen angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="6b609-241">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) sets a range of elements in an array to a specified value.</span></span> <span data-ttu-id="6b609-242">Das folgende Codebeispiel enthält ein Beispiel für `Array.fill`.</span><span class="sxs-lookup"><span data-stu-id="6b609-242">The following code provides an example of `Array.fill`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet28.fs)]

<span data-ttu-id="6b609-243">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="6b609-243">The output is as follows.</span></span>

```
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

<span data-ttu-id="6b609-244">Sie können [ `Array.blit` ](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) einen Unterabschnitt eines Arrays in ein anderes Array kopieren.</span><span class="sxs-lookup"><span data-stu-id="6b609-244">You can use [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) to copy a subsection of one array to another array.</span></span>

### <a name="converting-to-and-from-other-types"></a><span data-ttu-id="6b609-245">Konvertieren von Typen</span><span class="sxs-lookup"><span data-stu-id="6b609-245">Converting to and from Other Types</span></span>

<span data-ttu-id="6b609-246">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b)erstellt ein Array aus einer Liste an.</span><span class="sxs-lookup"><span data-stu-id="6b609-246">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) creates an array from a list.</span></span> <span data-ttu-id="6b609-247">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c)erstellt ein Array aus einer Sequenz an.</span><span class="sxs-lookup"><span data-stu-id="6b609-247">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) creates an array from a sequence.</span></span> <span data-ttu-id="6b609-248">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786)und [ `Array.toSeq` ](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) konvertieren vom Arraytyp in diese anderen Auflistungstypen.</span><span class="sxs-lookup"><span data-stu-id="6b609-248">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) and [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) convert to these other collection types from the array type.</span></span>

### <a name="sorting-arrays"></a><span data-ttu-id="6b609-249">Sortieren von Arrays</span><span class="sxs-lookup"><span data-stu-id="6b609-249">Sorting Arrays</span></span>

<span data-ttu-id="6b609-250">Verwendung [ `Array.sort` ](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) , mithilfe der generischen Vergleichsfunktion ein Array zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="6b609-250">Use [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) to sort an array by using the generic comparison function.</span></span> <span data-ttu-id="6b609-251">Verwendung [ `Array.sortBy` ](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) an eine Funktion, die einen Wert generiert bezeichnet als eine *Schlüssel*, um mithilfe der generischen Vergleichsfunktion auf den Schlüssel zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="6b609-251">Use [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) to specify a function that generates a value, referred to as a *key*, to sort by using the generic comparison function on the key.</span></span> <span data-ttu-id="6b609-252">Verwendung [ `Array.sortWith` ](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) , wenn Sie eine benutzerdefinierte Vergleichsfunktion bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="6b609-252">Use [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) if you want to provide a custom comparison function.</span></span> <span data-ttu-id="6b609-253">`Array.sort`, `Array.sortBy` und `Array.sortWith` geben das sortierte Array als neues Array zurück.</span><span class="sxs-lookup"><span data-stu-id="6b609-253">`Array.sort`, `Array.sortBy`, and `Array.sortWith` all return the sorted array as a new array.</span></span> <span data-ttu-id="6b609-254">Die Variationen [ `Array.sortInPlace` ](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [ `Array.sortInPlaceBy` ](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), und [ `Array.sortInPlaceWith` ](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) das vorhandene Array anstatt ein neues Konto zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6b609-254">The variations [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), and [`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modify the existing array instead of returning a new one.</span></span>

### <a name="arrays-and-tuples"></a><span data-ttu-id="6b609-255">Arrays und Tupel</span><span class="sxs-lookup"><span data-stu-id="6b609-255">Arrays and Tuples</span></span>

<span data-ttu-id="6b609-256">Die Funktionen [ `Array.zip` ](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) und [ `Array.unzip` ](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) konvertieren Arrays von Tupelpaaren in Tupel von Arrays und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="6b609-256">The functions [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) and [`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convert arrays of tuple pairs to tuples of arrays and vice versa.</span></span> <span data-ttu-id="6b609-257">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d)und [ `Array.unzip3` ](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) sind ähnlich, außer dass sie mit Tupeln von drei Elementen oder Tupeln von drei Arrays arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6b609-257">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) and [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) are similar except that they work with tuples of three elements or tuples of three arrays.</span></span>

## <a name="parallel-computations-on-arrays"></a><span data-ttu-id="6b609-258">Parallele Berechnungen auf Arrays</span><span class="sxs-lookup"><span data-stu-id="6b609-258">Parallel Computations on Arrays</span></span>

<span data-ttu-id="6b609-259">Das Modul [ `Array.Parallel` ](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) enthält Funktionen zum Ausführen paralleler Berechnungen für Arrays.</span><span class="sxs-lookup"><span data-stu-id="6b609-259">The module [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contains functions for performing parallel computations on arrays.</span></span> <span data-ttu-id="6b609-260">Dieses Modul ist in Anwendungen nicht verfügbar, die auf Versionen vor Version 4 von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="6b609-260">This module is not available in applications that target versions of the .NET Framework prior to version 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b609-261">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b609-261">See Also</span></span>
[<span data-ttu-id="6b609-262">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="6b609-262">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="6b609-263">F#; Typen</span><span class="sxs-lookup"><span data-stu-id="6b609-263">F#; Types</span></span>](fsharp-types.md)
