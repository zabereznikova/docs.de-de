---
title: Arrays (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 2c3f22cb2a011aea9f0fff9ef49d1fd780d6d832
ms.sourcegitcommit: 7f7664837d35320a0bad3f7e4ecd68d6624633b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/30/2018
ms.locfileid: "52671967"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="84320-102">Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="84320-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="84320-103">Sie können mehrere Variablen des gleichen Typs in einer Arraydatenstruktur speichern.</span><span class="sxs-lookup"><span data-stu-id="84320-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="84320-104">Ein Array wird deklariert, indem der Typ seiner Elemente angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="84320-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="84320-105">In den folgenden Beispielen werden ein eindimensionales, ein mehrdimensionales und ein verzweigtes Array erstellt:</span><span class="sxs-lookup"><span data-stu-id="84320-105">The following examples create single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 [!code-csharp[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## <a name="array-overview"></a><span data-ttu-id="84320-106">Übersicht über Arrays</span><span class="sxs-lookup"><span data-stu-id="84320-106">Array Overview</span></span>

 <span data-ttu-id="84320-107">Ein Array verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="84320-107">An array has the following properties:</span></span>  
  
-   <span data-ttu-id="84320-108">Ein Array kann [eindimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [mehrdimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) oder [verzweigt](../../../csharp/programming-guide/arrays/jagged-arrays.md) sein.</span><span class="sxs-lookup"><span data-stu-id="84320-108">An array can be [Single-Dimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [Multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) or [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span></span>  
  
-   <span data-ttu-id="84320-109">Die Anzahl der Dimensionen und die Länge der einzelnen Dimensionen werden festgelegt, wenn die Arrayinstanz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="84320-109">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="84320-110">Diese Werte können während der Lebensdauer der Instanz nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="84320-110">These values can't be changed during the lifetime of the instance.</span></span>  
  
-   <span data-ttu-id="84320-111">Numerische Arrayelemente sind standardmäßig auf 0 (null) festgelegt, Verweiselemente auf NULL.</span><span class="sxs-lookup"><span data-stu-id="84320-111">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
-   <span data-ttu-id="84320-112">Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="84320-112">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
-   <span data-ttu-id="84320-113">Arrays sind nullbasiert: Der Index eines Arrays mit `n` Elementen beginnt bei `0` und endet bei `n-1`.</span><span class="sxs-lookup"><span data-stu-id="84320-113">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
-   <span data-ttu-id="84320-114">Arrayelemente können einen beliebigen Typ aufweisen, z. B. auch einen Arraytyp.</span><span class="sxs-lookup"><span data-stu-id="84320-114">Array elements can be of any type, including an array type.</span></span>  
  
-   <span data-ttu-id="84320-115">Arraytypen sind [Referenztypen](../../../csharp/language-reference/keywords/reference-types.md), die vom abstrakten Basistyp <xref:System.Array> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="84320-115">Array types are [reference types](../../../csharp/language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="84320-116">Da dieser Typ <xref:System.Collections.IEnumerable> und <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Iteration für alle Arrays in C# verwenden.</span><span class="sxs-lookup"><span data-stu-id="84320-116">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="84320-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="84320-117">Related Sections</span></span>  
  
-   [<span data-ttu-id="84320-118">Arrays als Objekte</span><span class="sxs-lookup"><span data-stu-id="84320-118">Arrays as Objects</span></span>](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [<span data-ttu-id="84320-119">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="84320-119">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [<span data-ttu-id="84320-120">Übergeben von Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="84320-120">Passing Arrays as Arguments</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="84320-121">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="84320-121">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="84320-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84320-122">See Also</span></span>

- [<span data-ttu-id="84320-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="84320-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="84320-124">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="84320-124">Collections</span></span>](../../../csharp/programming-guide/concepts/collections.md)
