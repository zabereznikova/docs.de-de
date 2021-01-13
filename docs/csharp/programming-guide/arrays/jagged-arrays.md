---
title: Verzweigte Arrays – C#-Programmierhandbuch
description: Ein Jagged Array in C# ist ein Array, dessen Elemente Arrays verschiedener Größe sind. Hier erfahren Sie, wie Sie Jagged Arrays deklarieren, initialisieren und auf sie zugreifen.
ms.date: 12/18/2020
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 6d4fb939fb6594c7644a80eb688ea852ddf8a5c5
ms.sourcegitcommit: c3093e9d106d8ca87cc86eef1f2ae4ecfb392118
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2020
ms.locfileid: "97737280"
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="600c4-104">Verzweigte Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="600c4-104">Jagged Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="600c4-105">Ein Jagged Array ist ein Array, dessen Elemente Arrays möglicherweise verschiedener Größe sind.</span><span class="sxs-lookup"><span data-stu-id="600c4-105">A jagged array is an array whose elements are arrays, possibly of different sizes.</span></span> <span data-ttu-id="600c4-106">Ein verzweigtes Array wird auch „Array aus Arrays“ genannt.</span><span class="sxs-lookup"><span data-stu-id="600c4-106">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="600c4-107">Die folgenden Beispiele zeigen, wie Sie verzweigte Arrays deklarieren, initialisieren und auf sie zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="600c4-107">The following examples show how to declare, initialize, and access jagged arrays.</span></span>

 <span data-ttu-id="600c4-108">Die folgende Deklaration veranschaulicht ein eindimensionales Array mit drei Elementen, von denen jedes wiederum ein eindimensionales Array aus ganzen Zahlen darstellt:</span><span class="sxs-lookup"><span data-stu-id="600c4-108">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>

 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]

 <span data-ttu-id="600c4-109">Vor der Verwendung von `jaggedArray` müssen seine Elemente initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="600c4-109">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="600c4-110">Sie können die Elemente folgendermaßen initialisieren:</span><span class="sxs-lookup"><span data-stu-id="600c4-110">You can initialize the elements like this:</span></span>

 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]

 <span data-ttu-id="600c4-111">Jedes Element ist ein eindimensionales Array aus ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="600c4-111">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="600c4-112">Das erste Element ist ein Array aus 5 ganzen Zahlen, das zweite aus 4 und das dritte aus 2.</span><span class="sxs-lookup"><span data-stu-id="600c4-112">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>

 <span data-ttu-id="600c4-113">Sie können auch Initialisierer verwenden, um die Arrayelemente mit Werten zu füllen. In diesem Fall wird die Arraygröße nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="600c4-113">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="600c4-114">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="600c4-114">For example:</span></span>

 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]

 <span data-ttu-id="600c4-115">Sie können das Array auch nach der Deklaration folgendermaßen initialisieren:</span><span class="sxs-lookup"><span data-stu-id="600c4-115">You can also initialize the array upon declaration like this:</span></span>

 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]

 <span data-ttu-id="600c4-116">Sie können folgende Kurzformen verwenden.</span><span class="sxs-lookup"><span data-stu-id="600c4-116">You can use the following shorthand form.</span></span> <span data-ttu-id="600c4-117">Beachten Sie, dass der Operator `new` bei der Initialisierung der Elemente nicht ausgelassen werden kann, da es für die Elemente keine Standardinitialisierung gibt:</span><span class="sxs-lookup"><span data-stu-id="600c4-117">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>

 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]

 <span data-ttu-id="600c4-118">Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="600c4-118">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>

 <span data-ttu-id="600c4-119">In den folgenden Beispielen wird veranschaulicht, wie Sie auf einzelne Arrayelemente zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="600c4-119">You can access individual array elements like these examples:</span></span>

 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]

 <span data-ttu-id="600c4-120">Es ist möglich, Jagged Arrays und mehrdimensionale Arrays zu mischen.</span><span class="sxs-lookup"><span data-stu-id="600c4-120">It's possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="600c4-121">Das folgende Beispiel zeigt die Deklaration und Initialisierung eines eindimensionalen verzweigten Arrays, das drei zweidimensionale Arrayelemente unterschiedlicher Größe enthält.</span><span class="sxs-lookup"><span data-stu-id="600c4-121">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="600c4-122">Weitere Informationen finden Sie unter [Mehrdimensionale Arrays](./multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="600c4-122">For more information, see [Multidimensional Arrays](./multidimensional-arrays.md).</span></span>

 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]

 <span data-ttu-id="600c4-123">Im folgenden Beispiel wird dargestellt, wie Sie auf einzelne Elemente zugreifen können. Der Wert des Elements `[1,0]` des ersten Arrays (Wert `5`) wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="600c4-123">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>

 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]

 <span data-ttu-id="600c4-124">Die Methode `Length` gibt die Anzahl der Arrays zurück, die im verzweigten Array enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="600c4-124">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="600c4-125">Wenn Sie beispielsweise das vorherige Array deklariert haben, dann gibt die folgende Zeile:</span><span class="sxs-lookup"><span data-stu-id="600c4-125">For example, assuming you have declared the previous array, this line:</span></span>

 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]

 <span data-ttu-id="600c4-126">den Wert 3 zurück.</span><span class="sxs-lookup"><span data-stu-id="600c4-126">returns a value of 3.</span></span>

## <a name="example"></a><span data-ttu-id="600c4-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="600c4-127">Example</span></span>

 <span data-ttu-id="600c4-128">In diesem Beispiel wird ein Array erstellt, dessen Elemente wiederum selbst Arrays sind.</span><span class="sxs-lookup"><span data-stu-id="600c4-128">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="600c4-129">Jedes Arrayelement hat eine unterschiedliche Größe.</span><span class="sxs-lookup"><span data-stu-id="600c4-129">Each one of the array elements has a different size.</span></span>

 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]

## <a name="see-also"></a><span data-ttu-id="600c4-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="600c4-130">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="600c4-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="600c4-131">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="600c4-132">Arrays</span><span class="sxs-lookup"><span data-stu-id="600c4-132">Arrays</span></span>](./index.md)
- [<span data-ttu-id="600c4-133">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="600c4-133">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="600c4-134">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="600c4-134">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
