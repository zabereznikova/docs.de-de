---
title: Eindimensionale Arrays – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: 07c6061bfc66b1640d0eacca217302feff1a390a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715031"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="f623a-102">Eindimensionale Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f623a-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="f623a-103">Sie können ein eindimensionales Array aus fünf ganzen Zahlen deklarieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f623a-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#4)]  
  
 <span data-ttu-id="f623a-104">Dieses Array enthält die Elemente `array[0]` bis `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="f623a-104">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="f623a-105">Der [neue](../../language-reference/operators/new-operator.md) Operator wird verwendet, um das Array zu erstellen und die Arrayelemente mit ihren Standardwerten zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f623a-105">The [new](../../language-reference/operators/new-operator.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="f623a-106">In diesem Beispiel werden alle Arrayelemente mit null initialisiert.</span><span class="sxs-lookup"><span data-stu-id="f623a-106">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="f623a-107">Ein Array, das Zeichenfolgenelemente speichert, kann auf die gleiche Weise deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="f623a-107">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="f623a-108">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f623a-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#5)]  
  
## <a name="array-initialization"></a><span data-ttu-id="f623a-109">Arrayinitialisierung</span><span class="sxs-lookup"><span data-stu-id="f623a-109">Array Initialization</span></span>

 <span data-ttu-id="f623a-110">Arrays können nach der Deklaration initialisiert werden. In diesem Fall ist kein Längenspezifizierer erforderlich, da er bereits durch die Anzahl der Elemente in der Initialisierungsliste bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f623a-110">It is possible to initialize an array upon declaration, in which case, the length specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="f623a-111">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f623a-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#6)]  
  
 <span data-ttu-id="f623a-112">Ein Zeichenfolgenarray kann auf die gleiche Weise initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f623a-112">A string array can be initialized in the same way.</span></span> <span data-ttu-id="f623a-113">Die nachfolgende Deklaration zeigt ein Zeichenfolgenarray, in dem jedes Arrayelement durch den Namen eines Wochentags initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="f623a-113">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
 
 ```csharp
 string[] weekDays = new string[] { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
 ```
  
 <span data-ttu-id="f623a-114">Beim Initialisieren eines Arrays nach der Deklaration können Sie die folgenden Kurzbefehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="f623a-114">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 [!code-csharp[csProgGuideArrays#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#8)]  
  
 <span data-ttu-id="f623a-115">Eine Arrayvariable kann auch ohne Initialisierung deklariert werden. Verwenden Sie hierzu jedoch den Operator `new`, um dieser Variable ein Array zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f623a-115">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="f623a-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f623a-116">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#9)]  
  
 <span data-ttu-id="f623a-117">In C# 3.0 werden implizit typisierte Arrays eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f623a-117">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="f623a-118">Weitere Informationen finden Sie unter [Implizit typisierte Arrays](./implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="f623a-118">For more information, see [Implicitly Typed Arrays](./implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="f623a-119">Werttyp- und Verweistyparrays</span><span class="sxs-lookup"><span data-stu-id="f623a-119">Value Type and Reference Type Arrays</span></span>

 <span data-ttu-id="f623a-120">Betrachten Sie die folgende Arraydeklaration:</span><span class="sxs-lookup"><span data-stu-id="f623a-120">Consider the following array declaration:</span></span>  
  
 [!code-csharp[csProgGuideArrays#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#10)]  
  
 <span data-ttu-id="f623a-121">Das Ergebnis dieser Anweisung hängt davon ab, ob `SomeType` ein Werttyp oder ein Verweistyp ist.</span><span class="sxs-lookup"><span data-stu-id="f623a-121">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="f623a-122">Bei einem Werttyp wird durch die Anweisung ein Array aus 10 Elementen erstellt, von denen jedes den Typ `SomeType` besitzt.</span><span class="sxs-lookup"><span data-stu-id="f623a-122">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="f623a-123">Stellt `SomeType` einen Verweistyp dar, wird durch die Anweisung ein Array aus 10 Elementen erstellt, von denen jedes mit einem NULL-Verweis initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f623a-123">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
<span data-ttu-id="f623a-124">Weitere Informationen zu Werttypen und Verweistypen finden Sie unter [Werttypen](../../language-reference/keywords/value-types.md) und [Verweistypen](../../language-reference/keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="f623a-124">For more information about value types and reference types, see [Value types](../../language-reference/keywords/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f623a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f623a-125">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="f623a-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f623a-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f623a-127">Arrays</span><span class="sxs-lookup"><span data-stu-id="f623a-127">Arrays</span></span>](./index.md)
- [<span data-ttu-id="f623a-128">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="f623a-128">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="f623a-129">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="f623a-129">Jagged Arrays</span></span>](./jagged-arrays.md)
