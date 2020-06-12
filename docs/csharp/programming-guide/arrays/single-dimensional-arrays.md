---
title: Eindimensionale Arrays – C#-Programmierhandbuch
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: e189253eedc21fa2d51e16407f04b034610bb57b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410243"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="fa20a-102">Eindimensionale Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fa20a-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="fa20a-103">Sie erstellen ein eindimensionales Array mit dem Operator [new](../../language-reference/operators/new-operator.md), indem Sie den Arrayelementtyp und die Anzahl der Elemente angeben.</span><span class="sxs-lookup"><span data-stu-id="fa20a-103">You create a single-dimensional array using the [new](../../language-reference/operators/new-operator.md) operator specifying the array element type and the number of elements.</span></span> <span data-ttu-id="fa20a-104">Im folgenden Beispiel wird ein Array aus fünf Integern deklariert:</span><span class="sxs-lookup"><span data-stu-id="fa20a-104">The following example declares an array of five integers:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

<span data-ttu-id="fa20a-105">Dieses Array enthält die Elemente `array[0]` bis `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="fa20a-105">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="fa20a-106">Die Elemente des Arrays werden mit dem Standardwert des Elementtyps initialisiert (`0` für Integer).</span><span class="sxs-lookup"><span data-stu-id="fa20a-106">The elements of the array are initialized to the default value of the element type, `0` for integers.</span></span>

<span data-ttu-id="fa20a-107">Arrays können jeden beliebigen Elementtyp speichern, den Sie angeben. Dies wird im folgenden Beispiel veranschaulicht, in dem ein Array aus Zeichenfolgen deklariert wird:</span><span class="sxs-lookup"><span data-stu-id="fa20a-107">Arrays can store any element type you specify, such as the following example that declares an array of strings:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a><span data-ttu-id="fa20a-108">Arrayinitialisierung</span><span class="sxs-lookup"><span data-stu-id="fa20a-108">Array Initialization</span></span>

<span data-ttu-id="fa20a-109">Sie können die Elemente eines Arrays initialisieren, wenn Sie das Array deklarieren.</span><span class="sxs-lookup"><span data-stu-id="fa20a-109">You can initialize the elements of an array when you declare the array.</span></span> <span data-ttu-id="fa20a-110">Der Spezifizierer für die Länge ist nicht erforderlich, weil dieser von der Anzahl der Elemente in der Initialisierungsliste abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="fa20a-110">The length specifier isn't needed because it's inferred by the number of elements in the initialization list.</span></span> <span data-ttu-id="fa20a-111">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fa20a-111">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

<span data-ttu-id="fa20a-112">Im folgenden Code wird eine Deklaration eines Zeichenfolgenarrays veranschaulicht, in dem jedes Arrayelement durch den Namen eines Wochentags initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="fa20a-112">The following code shows a declaration of a string array where each array element is initialized by a name of a day:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
<span data-ttu-id="fa20a-113">Wie im folgenden Code gezeigt, können Sie den `new`-Ausdruck und den Arraytyp bei der Deklaration vermeiden, wenn Sie ein Array initialisieren.</span><span class="sxs-lookup"><span data-stu-id="fa20a-113">You can avoid the `new` expression and the array type when you initialize an array upon declaration, as shown in the following code.</span></span> <span data-ttu-id="fa20a-114">Diese Art von Array wird als [implizit typisiertes Array](implicitly-typed-arrays.md) bezeichnet:</span><span class="sxs-lookup"><span data-stu-id="fa20a-114">This is called an [implicitly typed array](implicitly-typed-arrays.md):</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

<span data-ttu-id="fa20a-115">Sie können eine Arrayvariable deklarieren, ohne sie zu erstellen. Sie müssen jedoch den Operator `new` verwenden, wenn Sie dieser Variable ein neues Array zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fa20a-115">You can declare an array variable without creating it, but you must use the `new` operator when you assign a new array to this variable.</span></span> <span data-ttu-id="fa20a-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fa20a-116">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="fa20a-117">Werttyp- und Verweistyparrays</span><span class="sxs-lookup"><span data-stu-id="fa20a-117">Value Type and Reference Type Arrays</span></span>

<span data-ttu-id="fa20a-118">Betrachten Sie die folgende Arraydeklaration:</span><span class="sxs-lookup"><span data-stu-id="fa20a-118">Consider the following array declaration:</span></span>  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

<span data-ttu-id="fa20a-119">Das Ergebnis dieser Anweisung hängt davon ab, ob `SomeType` ein Werttyp oder ein Verweistyp ist.</span><span class="sxs-lookup"><span data-stu-id="fa20a-119">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="fa20a-120">Wenn es sich um einen Werttyp handelt, erstellt die Anweisung ein Array aus 10 Elementen, die alle den Typ `SomeType` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fa20a-120">If it's a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="fa20a-121">Stellt `SomeType` einen Verweistyp dar, wird durch die Anweisung ein Array aus 10 Elementen erstellt, von denen jedes mit einem NULL-Verweis initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="fa20a-121">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span> <span data-ttu-id="fa20a-122">In beiden Instanzen werden die Elemente mit dem Standardwert für den Elementtyp initialisiert.</span><span class="sxs-lookup"><span data-stu-id="fa20a-122">In both instances, the elements are initialized to the default value for the element type.</span></span> <span data-ttu-id="fa20a-123">Weitere Informationen zu Werttypen und Verweistypen finden Sie unter [Werttypen](../../language-reference/builtin-types/value-types.md) und [Verweistypen](../../language-reference/keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="fa20a-123">For more information about value types and reference types, see [Value types](../../language-reference/builtin-types/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fa20a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa20a-124">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="fa20a-125">Arrays</span><span class="sxs-lookup"><span data-stu-id="fa20a-125">Arrays</span></span>](./index.md)
- [<span data-ttu-id="fa20a-126">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="fa20a-126">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="fa20a-127">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="fa20a-127">Jagged Arrays</span></span>](./jagged-arrays.md)
