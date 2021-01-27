---
title: Arrays – C#-Programmierhandbuch
description: Speichern Sie mehrere Variablen des gleichen Typs in einer Arraydatenstruktur in C#. Deklarieren Sie ein Array, indem Sie einen Typ angeben, oder geben Sie ein Objekt an, um beliebige Typen zu speichern.
ms.date: 01/22/2021
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 203d8b86da4e74d8c5397132a0ba68618eedf348
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794769"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="7a7c9-104">Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="7a7c9-104">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="7a7c9-105">Sie können mehrere Variablen des gleichen Typs in einer Arraydatenstruktur speichern.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-105">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="7a7c9-106">Ein Array wird deklariert, indem der Typ seiner Elemente angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-106">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="7a7c9-107">Wenn Sie möchten, dass das Array Element jedes Typs speichert, können Sie `object` als dessen Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-107">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="7a7c9-108">Im vereinheitlichen Typsystem von C# erben alle Typen, vordefiniert und benutzerdefiniert sowie Verweis- und Werttypen, direkt oder indirekt von <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="7a7c9-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a7c9-109">Example</span></span>

<span data-ttu-id="7a7c9-110">In den folgenden Beispiel wird ein eindimensionales, ein mehrdimensionales und ein verzweigtes Array erstellt:</span><span class="sxs-lookup"><span data-stu-id="7a7c9-110">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="7a7c9-111">Übersicht über Arrays</span><span class="sxs-lookup"><span data-stu-id="7a7c9-111">Array overview</span></span>

<span data-ttu-id="7a7c9-112">Ein Array verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="7a7c9-112">An array has the following properties:</span></span>

- <span data-ttu-id="7a7c9-113">Ein Array kann [eindimensional](single-dimensional-arrays.md), [mehrdimensional](multidimensional-arrays.md) oder [verzweigt](jagged-arrays.md) sein.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-113">An array can be [single-dimensional](single-dimensional-arrays.md), [multidimensional](multidimensional-arrays.md) or [jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="7a7c9-114">Die Anzahl der Dimensionen und die Länge der einzelnen Dimensionen werden festgelegt, wenn die Arrayinstanz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-114">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="7a7c9-115">Diese Werte können während der Lebensdauer der Instanz nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-115">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="7a7c9-116">Numerische Arrayelemente sind standardmäßig auf 0 (null) festgelegt, Verweiselemente auf NULL.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-116">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="7a7c9-117">Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="7a7c9-118">Arrays sind nullbasiert: Der Index eines Arrays mit `n` Elementen beginnt bei `0` und endet bei `n-1`.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-118">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="7a7c9-119">Arrayelemente können einen beliebigen Typ aufweisen, z. B. auch einen Arraytyp.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-119">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="7a7c9-120">Arraytypen sind [Referenztypen](../../language-reference/keywords/reference-types.md), die vom abstrakten Basistyp <xref:System.Array> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-120">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="7a7c9-121">Da dieser Typ <xref:System.Collections.IEnumerable> und <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die [foreach](../../language-reference/keywords/foreach-in.md)-Iteration für alle Arrays in C# verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-121">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

### <a name="arrays-as-objects"></a><span data-ttu-id="7a7c9-122">Arrays als Objekte</span><span class="sxs-lookup"><span data-stu-id="7a7c9-122">Arrays as Objects</span></span>

<span data-ttu-id="7a7c9-123">In C# sind Arrays tatsächlich Objekte und nicht nur adressierbare Regionen zusammenhängender Speicher wie in C und C++.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-123">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="7a7c9-124"><xref:System.Array> ist der abstrakte Basistyp aller Typen von Arrays.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-124"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="7a7c9-125">Sie können die Eigenschaften und die anderen Klassenmember verwenden, über die <xref:System.Array> verfügt.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-125">You can use the properties and other class members that <xref:System.Array> has.</span></span> <span data-ttu-id="7a7c9-126">Ein Beispiel dafür ist die Verwendung der <xref:System.Array.Length%2A>-Eigenschaft, um die Länge eines Arrays zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-126">An example of this is using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="7a7c9-127">Der folgende Code weist die Länge des `numbers`-Arrays, die `5` beträgt, einer Variablen mit dem Namen `lengthOfNumbers` zu:</span><span class="sxs-lookup"><span data-stu-id="7a7c9-127">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

<span data-ttu-id="7a7c9-128">Die <xref:System.Array>-Klasse bietet viele weitere nützliche Methoden und Eigenschaften zum Sortieren, Durchsuchen und Kopieren von Arrays.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-128">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span> <span data-ttu-id="7a7c9-129">Im folgenden Beispiel wird die <xref:System.Array.Rank%2A>-Eigenschaft verwendet, um die Anzahl der Dimensionen eines Arrays anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7a7c9-129">The following example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a><span data-ttu-id="7a7c9-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a7c9-130">See also</span></span>

- [<span data-ttu-id="7a7c9-131">Verwenden eindimensionaler Arrays</span><span class="sxs-lookup"><span data-stu-id="7a7c9-131">How to use single-dimensional arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="7a7c9-132">Verwenden mehrdimensionaler Arrays</span><span class="sxs-lookup"><span data-stu-id="7a7c9-132">How to use multi-dimensional arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="7a7c9-133">Verwenden verzweigter Arrays</span><span class="sxs-lookup"><span data-stu-id="7a7c9-133">How to use jagged arrays</span></span>](jagged-arrays.md)
- [<span data-ttu-id="7a7c9-134">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="7a7c9-134">Using foreach with arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="7a7c9-135">Übergeben von Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="7a7c9-135">Passing arrays as arguments</span></span>](passing-arrays-as-arguments.md)
- [<span data-ttu-id="7a7c9-136">Implizit typisierte Arrays</span><span class="sxs-lookup"><span data-stu-id="7a7c9-136">Implicitly typed arrays</span></span>](implicitly-typed-arrays.md)
- [<span data-ttu-id="7a7c9-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7a7c9-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7a7c9-138">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="7a7c9-138">Collections</span></span>](../concepts/collections.md)

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
