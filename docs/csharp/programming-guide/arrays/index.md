---
title: Arrays – C#-Programmierhandbuch
description: Speichern Sie mehrere Variablen des gleichen Typs in einer Arraydatenstruktur in C#. Deklarieren Sie ein Array, indem Sie einen Typ angeben, oder geben Sie ein Objekt an, um beliebige Typen zu speichern.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: e302ff2e4c2488c4899c4eb99a666d2d322119ce
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474734"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="2632d-104">Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2632d-104">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="2632d-105">Sie können mehrere Variablen des gleichen Typs in einer Arraydatenstruktur speichern.</span><span class="sxs-lookup"><span data-stu-id="2632d-105">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="2632d-106">Ein Array wird deklariert, indem der Typ seiner Elemente angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2632d-106">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="2632d-107">Wenn Sie möchten, dass das Array Element jedes Typs speichert, können Sie `object` als dessen Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="2632d-107">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="2632d-108">Im vereinheitlichen Typsystem von C# erben alle Typen, vordefiniert und benutzerdefiniert sowie Verweis- und Werttypen, direkt oder indirekt von <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="2632d-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="2632d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2632d-109">Example</span></span>

<span data-ttu-id="2632d-110">In den folgenden Beispiel wird ein eindimensionales, ein mehrdimensionales und ein verzweigtes Array erstellt:</span><span class="sxs-lookup"><span data-stu-id="2632d-110">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="2632d-111">Übersicht über Arrays</span><span class="sxs-lookup"><span data-stu-id="2632d-111">Array overview</span></span>

<span data-ttu-id="2632d-112">Ein Array verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="2632d-112">An array has the following properties:</span></span>

- <span data-ttu-id="2632d-113">Ein Array kann [eindimensional](single-dimensional-arrays.md), [mehrdimensional](multidimensional-arrays.md) oder [verzweigt](jagged-arrays.md) sein.</span><span class="sxs-lookup"><span data-stu-id="2632d-113">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="2632d-114">Die Anzahl der Dimensionen und die Länge der einzelnen Dimensionen werden festgelegt, wenn die Arrayinstanz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2632d-114">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="2632d-115">Diese Werte können während der Lebensdauer der Instanz nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2632d-115">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="2632d-116">Numerische Arrayelemente sind standardmäßig auf 0 (null) festgelegt, Verweiselemente auf NULL.</span><span class="sxs-lookup"><span data-stu-id="2632d-116">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="2632d-117">Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="2632d-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="2632d-118">Arrays sind nullbasiert: Der Index eines Arrays mit `n` Elementen beginnt bei `0` und endet bei `n-1`.</span><span class="sxs-lookup"><span data-stu-id="2632d-118">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="2632d-119">Arrayelemente können einen beliebigen Typ aufweisen, z. B. auch einen Arraytyp.</span><span class="sxs-lookup"><span data-stu-id="2632d-119">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="2632d-120">Arraytypen sind [Referenztypen](../../language-reference/keywords/reference-types.md), die vom abstrakten Basistyp <xref:System.Array> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2632d-120">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="2632d-121">Da dieser Typ <xref:System.Collections.IEnumerable> und <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die [foreach](../../language-reference/keywords/foreach-in.md)-Iteration für alle Arrays in C# verwenden.</span><span class="sxs-lookup"><span data-stu-id="2632d-121">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="2632d-122">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="2632d-122">Related sections</span></span>

- [<span data-ttu-id="2632d-123">Arrays als Objekte</span><span class="sxs-lookup"><span data-stu-id="2632d-123">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="2632d-124">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="2632d-124">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="2632d-125">Übergeben von Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="2632d-125">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="2632d-126">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2632d-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2632d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2632d-127">See also</span></span>

- [<span data-ttu-id="2632d-128">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2632d-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2632d-129">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="2632d-129">Collections</span></span>](../concepts/collections.md)
