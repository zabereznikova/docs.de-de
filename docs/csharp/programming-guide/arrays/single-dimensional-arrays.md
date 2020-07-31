---
title: Eindimensionale Arrays – C#-Programmierhandbuch
description: Hier erfahren Sie, wie Sie mithilfe des neuen Operators ein eindimensionales Array in C# erstellen, indem Sie den Arrayelementtyp und die Anzahl der Elemente angeben.
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: ada01262d57cbfebc8bfa1a5fee0639a10db5a4b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474591"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="c03a6-103">Eindimensionale Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c03a6-103">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="c03a6-104">Sie erstellen ein eindimensionales Array mit dem Operator [new](../../language-reference/operators/new-operator.md), indem Sie den Arrayelementtyp und die Anzahl der Elemente angeben.</span><span class="sxs-lookup"><span data-stu-id="c03a6-104">You create a single-dimensional array using the [new](../../language-reference/operators/new-operator.md) operator specifying the array element type and the number of elements.</span></span> <span data-ttu-id="c03a6-105">Im folgenden Beispiel wird ein Array aus fünf Integern deklariert:</span><span class="sxs-lookup"><span data-stu-id="c03a6-105">The following example declares an array of five integers:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

<span data-ttu-id="c03a6-106">Dieses Array enthält die Elemente `array[0]` bis `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="c03a6-106">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="c03a6-107">Die Elemente des Arrays werden mit dem Standardwert des Elementtyps initialisiert (`0` für Integer).</span><span class="sxs-lookup"><span data-stu-id="c03a6-107">The elements of the array are initialized to the default value of the element type, `0` for integers.</span></span>

<span data-ttu-id="c03a6-108">Arrays können jeden beliebigen Elementtyp speichern, den Sie angeben. Dies wird im folgenden Beispiel veranschaulicht, in dem ein Array aus Zeichenfolgen deklariert wird:</span><span class="sxs-lookup"><span data-stu-id="c03a6-108">Arrays can store any element type you specify, such as the following example that declares an array of strings:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a><span data-ttu-id="c03a6-109">Arrayinitialisierung</span><span class="sxs-lookup"><span data-stu-id="c03a6-109">Array Initialization</span></span>

<span data-ttu-id="c03a6-110">Sie können die Elemente eines Arrays initialisieren, wenn Sie das Array deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c03a6-110">You can initialize the elements of an array when you declare the array.</span></span> <span data-ttu-id="c03a6-111">Der Spezifizierer für die Länge ist nicht erforderlich, weil dieser von der Anzahl der Elemente in der Initialisierungsliste abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c03a6-111">The length specifier isn't needed because it's inferred by the number of elements in the initialization list.</span></span> <span data-ttu-id="c03a6-112">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c03a6-112">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

<span data-ttu-id="c03a6-113">Im folgenden Code wird eine Deklaration eines Zeichenfolgenarrays veranschaulicht, in dem jedes Arrayelement durch den Namen eines Wochentags initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="c03a6-113">The following code shows a declaration of a string array where each array element is initialized by a name of a day:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
<span data-ttu-id="c03a6-114">Wie im folgenden Code gezeigt, können Sie den `new`-Ausdruck und den Arraytyp bei der Deklaration vermeiden, wenn Sie ein Array initialisieren.</span><span class="sxs-lookup"><span data-stu-id="c03a6-114">You can avoid the `new` expression and the array type when you initialize an array upon declaration, as shown in the following code.</span></span> <span data-ttu-id="c03a6-115">Diese Art von Array wird als [implizit typisiertes Array](implicitly-typed-arrays.md) bezeichnet:</span><span class="sxs-lookup"><span data-stu-id="c03a6-115">This is called an [implicitly typed array](implicitly-typed-arrays.md):</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

<span data-ttu-id="c03a6-116">Sie können eine Arrayvariable deklarieren, ohne sie zu erstellen. Sie müssen jedoch den Operator `new` verwenden, wenn Sie dieser Variable ein neues Array zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c03a6-116">You can declare an array variable without creating it, but you must use the `new` operator when you assign a new array to this variable.</span></span> <span data-ttu-id="c03a6-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c03a6-117">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="c03a6-118">Werttyp- und Verweistyparrays</span><span class="sxs-lookup"><span data-stu-id="c03a6-118">Value Type and Reference Type Arrays</span></span>

<span data-ttu-id="c03a6-119">Betrachten Sie die folgende Arraydeklaration:</span><span class="sxs-lookup"><span data-stu-id="c03a6-119">Consider the following array declaration:</span></span>  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

<span data-ttu-id="c03a6-120">Das Ergebnis dieser Anweisung hängt davon ab, ob `SomeType` ein Werttyp oder ein Verweistyp ist.</span><span class="sxs-lookup"><span data-stu-id="c03a6-120">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="c03a6-121">Wenn es sich um einen Werttyp handelt, erstellt die Anweisung ein Array aus 10 Elementen, die alle den Typ `SomeType` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c03a6-121">If it's a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="c03a6-122">Stellt `SomeType` einen Verweistyp dar, wird durch die Anweisung ein Array aus 10 Elementen erstellt, von denen jedes mit einem NULL-Verweis initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="c03a6-122">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span> <span data-ttu-id="c03a6-123">In beiden Instanzen werden die Elemente mit dem Standardwert für den Elementtyp initialisiert.</span><span class="sxs-lookup"><span data-stu-id="c03a6-123">In both instances, the elements are initialized to the default value for the element type.</span></span> <span data-ttu-id="c03a6-124">Weitere Informationen zu Werttypen und Verweistypen finden Sie unter [Werttypen](../../language-reference/builtin-types/value-types.md) und [Verweistypen](../../language-reference/keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="c03a6-124">For more information about value types and reference types, see [Value types](../../language-reference/builtin-types/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c03a6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c03a6-125">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="c03a6-126">Arrays</span><span class="sxs-lookup"><span data-stu-id="c03a6-126">Arrays</span></span>](./index.md)
- [<span data-ttu-id="c03a6-127">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="c03a6-127">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="c03a6-128">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="c03a6-128">Jagged Arrays</span></span>](./jagged-arrays.md)
