---
title: Arrays (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
caps.latest.revision: 33
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1035caae15b64d1311305cfe4c1f1a74c80ed19a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="518f5-102">Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="518f5-102">Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="518f5-103">Sie können mehrere Variablen des gleichen Typs in einer Arraydatenstruktur speichern.</span><span class="sxs-lookup"><span data-stu-id="518f5-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="518f5-104">Ein Array wird deklariert, indem der Typ seiner Elemente angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="518f5-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="518f5-105">In den folgenden Beispielen werden ein eindimensionales, ein mehrdimensionales und ein verzweigtes Array erstellt:</span><span class="sxs-lookup"><span data-stu-id="518f5-105">The following examples create single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 <span data-ttu-id="518f5-106">[!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="518f5-106">[!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]</span></span>  
  
## <a name="array-overview"></a><span data-ttu-id="518f5-107">Übersicht über Arrays</span><span class="sxs-lookup"><span data-stu-id="518f5-107">Array Overview</span></span>  
 <span data-ttu-id="518f5-108">Ein Array verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="518f5-108">An array has the following properties:</span></span>  
  
-   <span data-ttu-id="518f5-109">Ein Array kann [eindimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [mehrdimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) oder [verzweigt](../../../csharp/programming-guide/arrays/jagged-arrays.md) sein.</span><span class="sxs-lookup"><span data-stu-id="518f5-109">An array can be [Single-Dimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [Multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) or [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span></span>  
  
-   <span data-ttu-id="518f5-110">Die Anzahl der Dimensionen und die Länge der einzelnen Dimensionen werden festgelegt, wenn die Arrayinstanz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="518f5-110">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="518f5-111">Diese Werte können während der Lebensdauer der Instanz nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="518f5-111">These values can't be changed during the lifetime of the instance.</span></span>  
  
-   <span data-ttu-id="518f5-112">Numerische Arrayelemente sind standardmäßig auf 0 (null) festgelegt, Verweiselemente auf NULL.</span><span class="sxs-lookup"><span data-stu-id="518f5-112">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
-   <span data-ttu-id="518f5-113">Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="518f5-113">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
-   <span data-ttu-id="518f5-114">Arrays sind nullbasiert: Der Index eines Arrays mit `n` Elementen beginnt bei `0` und endet bei `n-1`.</span><span class="sxs-lookup"><span data-stu-id="518f5-114">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
-   <span data-ttu-id="518f5-115">Arrayelemente können einen beliebigen Typ aufweisen, z. B. auch einen Arraytyp.</span><span class="sxs-lookup"><span data-stu-id="518f5-115">Array elements can be of any type, including an array type.</span></span>  
  
-   <span data-ttu-id="518f5-116">Arraytypen sind [Referenztypen](../../../csharp/language-reference/keywords/reference-types.md), die vom abstrakten Basistyp <xref:System.Array> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="518f5-116">Array types are [reference types](../../../csharp/language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="518f5-117">Da dieser Typ <xref:System.Collections.IEnumerable> und <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie die [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Iteration für alle Arrays in C# verwenden.</span><span class="sxs-lookup"><span data-stu-id="518f5-117">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="518f5-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="518f5-118">Related Sections</span></span>  
  
-   [<span data-ttu-id="518f5-119">Arrays als Objekte</span><span class="sxs-lookup"><span data-stu-id="518f5-119">Arrays as Objects</span></span>](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [<span data-ttu-id="518f5-120">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="518f5-120">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [<span data-ttu-id="518f5-121">Übergeben von Arrays als Argumente</span><span class="sxs-lookup"><span data-stu-id="518f5-121">Passing Arrays as Arguments</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [<span data-ttu-id="518f5-122">Übergeben von Arrays mithilfe von "ref" und "out"</span><span class="sxs-lookup"><span data-stu-id="518f5-122">Passing Arrays Using ref and out</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
  
## <a name="c-language-specification"></a><span data-ttu-id="518f5-123">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="518f5-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="518f5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="518f5-124">See Also</span></span>  
 <span data-ttu-id="518f5-125">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="518f5-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="518f5-126">[Collections](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  (Sammlungen)</span><span class="sxs-lookup"><span data-stu-id="518f5-126">[Collections](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) </span></span>  
 [<span data-ttu-id="518f5-127">Array-Auflistungstyp</span><span class="sxs-lookup"><span data-stu-id="518f5-127">Array Collection Type</span></span>](http://msdn.microsoft.com/en-us/8a9964de-8941-47b1-a3cf-a01bc88db9e8)

