---
title: Verzweigte Arrays – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 56013f0143d5efcb31a476909cb6e92504ff0dbc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705703"
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="0bd70-102">Verzweigte Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0bd70-102">Jagged Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="0bd70-103">Ein verzweigtes Array ist ein Array, dessen Elemente wiederum Arrays sind.</span><span class="sxs-lookup"><span data-stu-id="0bd70-103">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="0bd70-104">Die Elemente eines verzweigten Arrays können eine unterschiedliche Dimension und Größe besitzen.</span><span class="sxs-lookup"><span data-stu-id="0bd70-104">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="0bd70-105">Ein verzweigtes Array wird auch „Array aus Arrays“ genannt.</span><span class="sxs-lookup"><span data-stu-id="0bd70-105">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="0bd70-106">Die folgenden Beispiele zeigen, wie Sie verzweigte Arrays deklarieren, initialisieren und auf sie zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0bd70-106">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="0bd70-107">Die folgende Deklaration veranschaulicht ein eindimensionales Array mit drei Elementen, von denen jedes wiederum ein eindimensionales Array aus ganzen Zahlen darstellt:</span><span class="sxs-lookup"><span data-stu-id="0bd70-107">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]  
  
 <span data-ttu-id="0bd70-108">Vor der Verwendung von `jaggedArray` müssen seine Elemente initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0bd70-108">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="0bd70-109">Sie können die Elemente folgendermaßen initialisieren:</span><span class="sxs-lookup"><span data-stu-id="0bd70-109">You can initialize the elements like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]  
  
 <span data-ttu-id="0bd70-110">Jedes Element ist ein eindimensionales Array aus ganzen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="0bd70-110">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="0bd70-111">Das erste Element ist ein Array aus 5 ganzen Zahlen, das zweite aus 4 und das dritte aus 2.</span><span class="sxs-lookup"><span data-stu-id="0bd70-111">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="0bd70-112">Sie können auch Initialisierer verwenden, um die Arrayelemente mit Werten zu füllen. In diesem Fall wird die Arraygröße nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="0bd70-112">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="0bd70-113">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0bd70-113">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]  
  
 <span data-ttu-id="0bd70-114">Sie können das Array auch nach der Deklaration folgendermaßen initialisieren:</span><span class="sxs-lookup"><span data-stu-id="0bd70-114">You can also initialize the array upon declaration like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]  
  
 <span data-ttu-id="0bd70-115">Sie können folgende Kurzformen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0bd70-115">You can use the following shorthand form.</span></span> <span data-ttu-id="0bd70-116">Beachten Sie, dass der Operator `new` bei der Initialisierung der Elemente nicht ausgelassen werden kann, da es für die Elemente keine Standardinitialisierung gibt:</span><span class="sxs-lookup"><span data-stu-id="0bd70-116">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]  
  
 <span data-ttu-id="0bd70-117">Ein verzweigtes Array ist ein Array von Arrays, und deshalb sind seine Elemente Referenztypen und werden mit `null` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="0bd70-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="0bd70-118">In den folgenden Beispielen wird veranschaulicht, wie Sie auf einzelne Arrayelemente zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="0bd70-118">You can access individual array elements like these examples:</span></span>  
  
 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]  
  
 <span data-ttu-id="0bd70-119">Es ist möglich, verzweigte und mehrdimensionale Arrays zu mischen.</span><span class="sxs-lookup"><span data-stu-id="0bd70-119">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="0bd70-120">Das folgende Beispiel zeigt die Deklaration und Initialisierung eines eindimensionalen verzweigten Arrays, das drei zweidimensionale Arrayelemente unterschiedlicher Größe enthält.</span><span class="sxs-lookup"><span data-stu-id="0bd70-120">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="0bd70-121">Weitere Informationen zu zweidimensionalen Arrays finden Sie unter [Mehrdimensionale Arrays](./multidimensional-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="0bd70-121">For more information about two-dimensional arrays, see [Multidimensional Arrays](./multidimensional-arrays.md).</span></span>  
  
 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]  
  
 <span data-ttu-id="0bd70-122">Im folgenden Beispiel wird dargestellt, wie Sie auf einzelne Elemente zugreifen können. Der Wert des Elements `[1,0]` des ersten Arrays (Wert `5`) wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0bd70-122">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]  
  
 <span data-ttu-id="0bd70-123">Die Methode `Length` gibt die Anzahl der Arrays zurück, die im verzweigten Array enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="0bd70-123">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="0bd70-124">Wenn Sie beispielsweise das vorherige Array deklariert haben, dann gibt die folgende Zeile:</span><span class="sxs-lookup"><span data-stu-id="0bd70-124">For example, assuming you have declared the previous array, this line:</span></span>  
  
 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]  
  
 <span data-ttu-id="0bd70-125">den Wert 3 zurück.</span><span class="sxs-lookup"><span data-stu-id="0bd70-125">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bd70-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0bd70-126">Example</span></span>

 <span data-ttu-id="0bd70-127">In diesem Beispiel wird ein Array erstellt, dessen Elemente wiederum selbst Arrays sind.</span><span class="sxs-lookup"><span data-stu-id="0bd70-127">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="0bd70-128">Jedes Arrayelement hat eine unterschiedliche Größe.</span><span class="sxs-lookup"><span data-stu-id="0bd70-128">Each one of the array elements has a different size.</span></span>  
  
 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]  
  
## <a name="see-also"></a><span data-ttu-id="0bd70-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bd70-129">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="0bd70-130">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0bd70-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0bd70-131">Arrays</span><span class="sxs-lookup"><span data-stu-id="0bd70-131">Arrays</span></span>](./index.md)
- [<span data-ttu-id="0bd70-132">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="0bd70-132">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="0bd70-133">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="0bd70-133">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
