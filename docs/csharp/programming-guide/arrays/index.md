---
title: Arrays – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: e31cff94c51c626c4b8f0e08df270c45a9cc1316
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72772100"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="cdabe-102">Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="cdabe-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="cdabe-103">Sie können mehrere Variablen des gleichen Typs in einer Arraydatenstruktur speichern.</span><span class="sxs-lookup"><span data-stu-id="cdabe-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="cdabe-104">Ein Array wird deklariert, indem der Typ seiner Elemente angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cdabe-104">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="cdabe-105">Wenn Sie möchten, dass das Array Element jedes Typs speichert, können Sie `object` als dessen Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="cdabe-105">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="cdabe-106">Im vereinheitlichen Typsystem von C# erben alle Typen, vordefiniert und benutzerdefiniert sowie Verweis- und Werttypen, direkt oder indirekt von <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="cdabe-106">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="cdabe-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cdabe-107">Example</span></span>

<span data-ttu-id="cdabe-108">In den folgenden Beispiel wird ein eindimensionales, ein mehrdimensionales und ein verzweigtes Array erstellt:</span><span class="sxs-lookup"><span data-stu-id="cdabe-108">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="cdabe-109">Übersicht über Arrays</span><span class="sxs-lookup"><span data-stu-id="cdabe-109">Array overview</span></span>

<span data-ttu-id="cdabe-110">Ein Array verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="cdabe-110">An array has the following properties:</span></span>

- <span data-ttu-id="cdabe-111">Ein Array kann [eindimensional](single-dimensional-arrays.md), [mehrdimensional](multidimensional-arrays.md) oder [verzweigt](jagged-arrays.md) sein.</span><span class="sxs-lookup"><span data-stu-id="cdabe-111">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="cdabe-112">Die Anzahl der Dimensionen und die Länge der einzelnen Dimensionen werden festgelegt, wenn die Arrayinstanz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="cdabe-112">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="cdabe-113">Diese Werte können während der Lebensdauer der Instanz nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cdabe-113">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="cdabe-114">Numerische Arrayelemente sind standardmäßig auf 0 (null) festgelegt, Verweiselemente auf NULL.</span><span class="sxs-lookup"><span data-stu-id="cdabe-114">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="cdabe-115">Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="cdabe-115">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="cdabe-116">Arrays sind nullbasiert: Der Index eines Arrays mit `n` Elementen beginnt bei `0` und endet bei `n-1`.</span><span class="sxs-lookup"><span data-stu-id="cdabe-116">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="cdabe-117">Arrayelemente können einen beliebigen Typ aufweisen, z. B. auch einen Arraytyp.</span><span class="sxs-lookup"><span data-stu-id="cdabe-117">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="cdabe-118">Arraytypen sind [Referenztypen](../../language-reference/keywords/reference-types.md), die vom abstrakten Basistyp <xref:System.Array> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="cdabe-118">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="cdabe-119">Da dieser Typ <xref:System.Collections.IEnumerable> und <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die [foreach](../../language-reference/keywords/foreach-in.md)-Iteration für alle Arrays in C# verwenden.</span><span class="sxs-lookup"><span data-stu-id="cdabe-119">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="cdabe-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="cdabe-120">Related sections</span></span>

- [<span data-ttu-id="cdabe-121">Arrays als Objekte</span><span class="sxs-lookup"><span data-stu-id="cdabe-121">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="cdabe-122">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="cdabe-122">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="cdabe-123">Übergeben von Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="cdabe-123">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="cdabe-124">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="cdabe-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="cdabe-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdabe-125">See also</span></span>

- [<span data-ttu-id="cdabe-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cdabe-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cdabe-127">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="cdabe-127">Collections</span></span>](../concepts/collections.md)
