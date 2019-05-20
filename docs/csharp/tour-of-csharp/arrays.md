---
title: C#-Arrays – Überblick über C#
description: Arrays sind der grundlegendste Auflistungstyp in der Sprache C#.
ms.date: 08/10/2016
ms.assetid: a440704c-9e88-4c75-97dd-bfe30ca0fb97
ms.openlocfilehash: 56a053ac8525d4c6c34592d6092f3f162cb04247
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634607"
---
# <a name="arrays"></a><span data-ttu-id="9c651-103">Arrays</span><span class="sxs-lookup"><span data-stu-id="9c651-103">Arrays</span></span>

<span data-ttu-id="9c651-104">Ein ***Array*** ist eine Datenstruktur, die eine Anzahl von Variablen enthält, auf die über berechnete Indizes zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="9c651-104">An ***array*** is a data structure that contains a number of variables that are accessed through computed indices.</span></span> <span data-ttu-id="9c651-105">Die im Array enthaltenen Variablen, auch ***Elemente*** des Arrays genannt, weisen alle denselben Typ auf. Dieser Typ wird als ***Elementtyp*** des Arrays bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9c651-105">The variables contained in an array, also called the ***elements*** of the array, are all of the same type, and this type is called the ***element type*** of the array.</span></span>

<span data-ttu-id="9c651-106">Arraytypen sind Verweistypen, und die Deklaration einer Arrayvariablen reserviert Speicher für einen Verweis auf eine Arrayinstanz.</span><span class="sxs-lookup"><span data-stu-id="9c651-106">Array types are reference types, and the declaration of an array variable simply sets aside space for a reference to an array instance.</span></span> <span data-ttu-id="9c651-107">Die tatsächlichen Arrayinstanzen werden unter Verwendung des new-Operators zur Laufzeit dynamisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="9c651-107">Actual array instances are created dynamically at runtime using the new operator.</span></span> <span data-ttu-id="9c651-108">Der new-Vorgang legt die ***Länge*** der neuen Arrayinstanz fest, die dann für die Lebensdauer der Instanz beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="9c651-108">The new operation specifies the ***length*** of the new array instance, which is then fixed for the lifetime of the instance.</span></span> <span data-ttu-id="9c651-109">Die Indizes der Arrayelemente reichen von `0` bis `Length - 1`.</span><span class="sxs-lookup"><span data-stu-id="9c651-109">The indices of the elements of an array range from `0` to `Length - 1`.</span></span> <span data-ttu-id="9c651-110">Der `new`-Operator initialisiert die Elemente eines Arrays automatisch mit ihren Standardwerten. Dieser lautet z.B. für alle numerischen Typen 0 und für alle Verweistypen `null`.</span><span class="sxs-lookup"><span data-stu-id="9c651-110">The `new` operator automatically initializes the elements of an array to their default value, which, for example, is zero for all numeric types and `null` for all reference types.</span></span>

<span data-ttu-id="9c651-111">Im folgenden Beispiel wird ein Array aus `int`-Elementen erstellt. Anschließend wird das Array initialisiert und die Inhalte des Arrays werden gedruckt.</span><span class="sxs-lookup"><span data-stu-id="9c651-111">The following example creates an array of `int` elements, initializes the array, and prints out the contents of the array.</span></span>

[!code-csharp[ArraySample](../../../samples/snippets/csharp/tour/arrays/Program.cs#L3-L18)]

<span data-ttu-id="9c651-112">Mit diesem Beispiel wird ein ***eindimensionales Array*** erstellt und verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c651-112">This example creates and operates on a ***single-dimensional array***.</span></span> <span data-ttu-id="9c651-113">C# unterstützt auch ***mehrdimensionale Arrays***.</span><span class="sxs-lookup"><span data-stu-id="9c651-113">C# also supports ***multi-dimensional arrays***.</span></span> <span data-ttu-id="9c651-114">Die Anzahl von Dimensionen eines Arraytyps, auch als ***Rang*** des Arraytyps bezeichnet, ist 1 plus die Anzahl von Kommas, die innerhalb der eckigen Klammern des Arraytyps angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9c651-114">The number of dimensions of an array type, also known as the ***rank*** of the array type, is one plus the number of commas written between the square brackets of the array type.</span></span> <span data-ttu-id="9c651-115">Mit dem folgenden Beispiel wird respektive ein eindimensionales, ein zweidimensionales und ein dreidimensionales Array erstellt.</span><span class="sxs-lookup"><span data-stu-id="9c651-115">The following example allocates a single-dimensional, a two-dimensional, and a three-dimensional array, respectively.</span></span>

[!code-csharp[ArrayRank](../../../samples/snippets/csharp/tour/arrays/Program.cs#L24-L26)]

<span data-ttu-id="9c651-116">Das `a1`-Array enthält 10 Elemente, das `a2`-Array umfasst 50 (10 × 5) Elemente, und das `a3`-Array enthält 100 (10 × 5 × 2) Elemente.</span><span class="sxs-lookup"><span data-stu-id="9c651-116">The `a1` array contains 10 elements, the `a2` array contains 50 (10 × 5) elements, and the `a3` array contains 100 (10 × 5 × 2) elements.</span></span>
<span data-ttu-id="9c651-117">Ein Array kann einen beliebigen Elementtyp verwenden, einschließlich eines Arraytyps. </span><span class="sxs-lookup"><span data-stu-id="9c651-117">The element type of an array can be any type, including an array type.</span></span> <span data-ttu-id="9c651-118">Ein Array mit Elementen eines Arraytyps wird auch als ***verzweigtes Array*** bezeichnet, weil die Länge der Elementarrays nicht identisch sein muss.</span><span class="sxs-lookup"><span data-stu-id="9c651-118">An array with elements of an array type is sometimes called a ***jagged array*** because the lengths of the element arrays do not all have to be the same.</span></span> <span data-ttu-id="9c651-119">Im folgenden Beispiel wird ein Array aus `int`-Arrays zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="9c651-119">The following example allocates an array of arrays of `int`:</span></span>

[!code-csharp[ArrayAllocation](../../../samples/snippets/csharp/tour/arrays/Program.cs#L31-L34)]

<span data-ttu-id="9c651-120">In der ersten Zeile wird ein Array mit drei Elementen erstellt, das jeweils den Typ `int[]` und einen Anfangswert von `null` aufweist.</span><span class="sxs-lookup"><span data-stu-id="9c651-120">The first line creates an array with three elements, each of type `int[]` and each with an initial value of `null`.</span></span> <span data-ttu-id="9c651-121">In den folgenden Zeilen werden die drei Elemente mit Verweisen auf einzelne Arrayinstanzen unterschiedlicher Länge initialisiert.</span><span class="sxs-lookup"><span data-stu-id="9c651-121">The subsequent lines then initialize the three elements with references to individual array instances of varying lengths.</span></span>

<span data-ttu-id="9c651-122">Der new-Operator erlaubt es, die Anfangswerte der Arrayelemente unter Verwendung eines ***Arrayinitialisierers*** anzugeben, bei dem es sich um eine Liste von Ausdrücken zwischen den Trennzeichen `{` und `}` handelt.</span><span class="sxs-lookup"><span data-stu-id="9c651-122">The new operator permits the initial values of the array elements to be specified using an ***array initializer***, which is a list of expressions written between the delimiters `{` and `}`.</span></span> <span data-ttu-id="9c651-123">Mit dem folgenden Beispiel wird ein `int[]` mit drei Elementen zugewiesen und initialisiert.</span><span class="sxs-lookup"><span data-stu-id="9c651-123">The following example allocates and initializes an `int[]` with three elements.</span></span>

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L39-L39)]

<span data-ttu-id="9c651-124">Beachten Sie, dass die Länge des Arrays aus der Anzahl von Ausdrücken zwischen { und } abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="9c651-124">Note that the length of the array is inferred from the number of expressions between { and }.</span></span> <span data-ttu-id="9c651-125">Deklarationen lokaler Variablen und Felder können weiter verkürzt werden, sodass der Arraytyp nicht erneut aufgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="9c651-125">Local variable and field declarations can be shortened further such that the array type does not have to be restated.</span></span>

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L44-L44)]

<span data-ttu-id="9c651-126">Die zwei vorherigen Beispiele entsprechen dem folgenden:</span><span class="sxs-lookup"><span data-stu-id="9c651-126">Both of the previous examples are equivalent to the following:</span></span>

[!code-csharp[ArrayAssignment](../../../samples/snippets/csharp/tour/arrays/Program.cs#L49-L53)]

>[!div class="step-by-step"]
><span data-ttu-id="9c651-127">[Zurück](structs.md)
>[Weiter](interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="9c651-127">[Previous](structs.md)
[Next](interfaces.md)</span></span>
