---
title: Eindimensionale Arrays (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: c2f26fd74a596ada21eef578e58c9cd8e0305d6c
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48027127"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="2577c-102">Eindimensionale Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2577c-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="2577c-103">Sie können ein eindimensionales Array aus fünf ganzen Zahlen deklarieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2577c-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]  
  
 <span data-ttu-id="2577c-104">Dieses Array enthält die Elemente `array[0]` bis `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="2577c-104">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="2577c-105">Der [neue](../../../csharp/language-reference/keywords/new.md) Operator wird verwendet, um das Array zu erstellen und die Arrayelemente mit ihren Standardwerten zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="2577c-105">The [new](../../../csharp/language-reference/keywords/new.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="2577c-106">In diesem Beispiel werden alle Arrayelemente mit null initialisiert.</span><span class="sxs-lookup"><span data-stu-id="2577c-106">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="2577c-107">Ein Array, das Zeichenfolgenelemente speichert, kann auf die gleiche Weise deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="2577c-107">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="2577c-108">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2577c-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a><span data-ttu-id="2577c-109">Arrayinitialisierung</span><span class="sxs-lookup"><span data-stu-id="2577c-109">Array Initialization</span></span>

 <span data-ttu-id="2577c-110">Arrays können nach der Deklaration initialisiert werden. In diesem Fall ist kein Rangbezeichner erforderlich, da er bereits durch die Anzahl der Elemente in der Initialisierungsliste bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2577c-110">It is possible to initialize an array upon declaration, in which case, the rank specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="2577c-111">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2577c-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]  
  
 <span data-ttu-id="2577c-112">Ein Zeichenfolgenarray kann auf die gleiche Weise initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2577c-112">A string array can be initialized in the same way.</span></span> <span data-ttu-id="2577c-113">Die nachfolgende Deklaration zeigt ein Zeichenfolgenarray, in dem jedes Arrayelement durch den Namen eines Wochentags initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="2577c-113">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
  
 [!code-csharp[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]  
  
 <span data-ttu-id="2577c-114">Beim Initialisieren eines Arrays nach der Deklaration können Sie die folgenden Kurzbefehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="2577c-114">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 [!code-csharp[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]  
  
 <span data-ttu-id="2577c-115">Eine Arrayvariable kann auch ohne Initialisierung deklariert werden. Verwenden Sie hierzu jedoch den Operator `new`, um dieser Variable ein Array zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="2577c-115">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="2577c-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2577c-116">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]  
  
 <span data-ttu-id="2577c-117">In C# 3.0 werden implizit typisierte Arrays eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2577c-117">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="2577c-118">Weitere Informationen finden Sie unter [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="2577c-118">For more information, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="2577c-119">Werttyp- und Verweistyparrays</span><span class="sxs-lookup"><span data-stu-id="2577c-119">Value Type and Reference Type Arrays</span></span>

 <span data-ttu-id="2577c-120">Betrachten Sie die folgende Arraydeklaration:</span><span class="sxs-lookup"><span data-stu-id="2577c-120">Consider the following array declaration:</span></span>  
  
 [!code-csharp[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]  
  
 <span data-ttu-id="2577c-121">Das Ergebnis dieser Anweisung hängt davon ab, ob `SomeType` ein Werttyp oder ein Verweistyp ist.</span><span class="sxs-lookup"><span data-stu-id="2577c-121">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="2577c-122">Bei einem Werttyp wird durch die Anweisung ein Array aus 10 Elementen erstellt, von denen jedes den Typ `SomeType` besitzt.</span><span class="sxs-lookup"><span data-stu-id="2577c-122">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="2577c-123">Stellt `SomeType` einen Verweistyp dar, wird durch die Anweisung ein Array aus 10 Elementen erstellt, von denen jedes mit einem NULL-Verweis initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="2577c-123">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="2577c-124">Weitere Informationen zu Werttypen und Verweistypen finden Sie unter [Typen](../../../csharp/language-reference/keywords/types.md).</span><span class="sxs-lookup"><span data-stu-id="2577c-124">For more information about value types and reference types, see [Types](../../../csharp/language-reference/keywords/types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2577c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2577c-125">See Also</span></span>

- <xref:System.Array>  
- [<span data-ttu-id="2577c-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2577c-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2577c-127">Arrays</span><span class="sxs-lookup"><span data-stu-id="2577c-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="2577c-128">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="2577c-128">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
- [<span data-ttu-id="2577c-129">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="2577c-129">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
