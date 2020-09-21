---
title: 'Vorgehensweise: Verketten mehrerer Zeichenfolgen (C#-Handbuch)'
description: Es gibt mehrere Möglichkeiten zum Verketten von Zeichenfolgen in C#. Lernen Sie die Optionen und Gründe für verschiedene Auswahlmöglichkeiten kennen.
ms.date: 02/20/2018
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
ms.openlocfilehash: f2aae14deac967a833fb3510acdb32e0971485b5
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537482"
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a><span data-ttu-id="5df7d-104">Vorgehensweise: Verketten mehrerer Zeichenfolgen (C#-Handbuch)</span><span class="sxs-lookup"><span data-stu-id="5df7d-104">How to concatenate multiple strings (C# Guide)</span></span>

<span data-ttu-id="5df7d-105">*Verkettung* ist der Prozess, eine Zeichenfolge ans Ende einer anderen Zeichenfolge anzufügen.</span><span class="sxs-lookup"><span data-stu-id="5df7d-105">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="5df7d-106">Sie können Zeichenfolgen mithilfe des `+`-Operators verketten.</span><span class="sxs-lookup"><span data-stu-id="5df7d-106">You concatenate strings by using the `+` operator.</span></span> <span data-ttu-id="5df7d-107">Bei Zeichenfolgenliteralen und Zeichenfolgenkonstanten erfolgt die Verkettung beim Kompilieren. Es erfolgt keine Verkettung zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="5df7d-107">For string literals and string constants, concatenation occurs at compile time; no run-time concatenation occurs.</span></span> <span data-ttu-id="5df7d-108">Bei Zeichenfolgenvariablen erfolgt die Verkettung nur zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="5df7d-108">For string variables, concatenation occurs only at run time.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="5df7d-109">Im folgenden Beispiel wird die Verkettung genutzt, um ein langes Zeichenfolgenliteral in kleinere Zeichenfolgen aufzuteilen, wodurch die Lesbarkeit im Quellcode verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="5df7d-109">The following example uses concatenation to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="5df7d-110">Diese Teile werden zur Kompilierzeit in eine einzelne Zeichenfolge verkettet.</span><span class="sxs-lookup"><span data-stu-id="5df7d-110">These parts are concatenated into a single string at compile time.</span></span> <span data-ttu-id="5df7d-111">Es entstehen unabhängig von der Anzahl an Zeichenfolgen keine Leistungseinbußen zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="5df7d-111">There is no run-time performance cost regardless of the number of strings involved.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet1":::

<span data-ttu-id="5df7d-112">Zum Verketten von Zeichenfolgenvariablen können Sie die Operatoren `+` und `+=`, die [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) oder die Methoden <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> oder <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="5df7d-112">To concatenate string variables, you can use the `+` or `+=` operators, [string interpolation](../language-reference/tokens/interpolated.md) or the <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="5df7d-113">Der Operator `+` ist einfach zu verwenden und gut für intuitiv verständlichen Code geeignet.</span><span class="sxs-lookup"><span data-stu-id="5df7d-113">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="5df7d-114">Auch wenn Sie mehrere `+`-Operatoren in einer Anweisung verwenden, wird der Inhalt der Zeichenfolge nur einmal kopiert.</span><span class="sxs-lookup"><span data-stu-id="5df7d-114">Even if you use several `+` operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="5df7d-115">Der folgende Code zeigt Beispiele für die Verwendung der Operatoren `+` und `+=` zum Verketten von Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="5df7d-115">The following code shows examples of using the `+` and `+=` operators to concatenate strings:</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet2":::

<span data-ttu-id="5df7d-116">In einigen Ausdrücken ist es einfacher, Zeichenfolgen mithilfe der Zeichenfolgeninterpolation zu verketten, wie in folgendem Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="5df7d-116">In some expressions, it's easier to concatenate strings using string interpolation, as the following code shows:</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet3":::

> [!NOTE]
> <span data-ttu-id="5df7d-117">Bei der Zeichenfolgenverkettung behandelt der C#-Compiler eine NULL-Zeichenfolge wie eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5df7d-117">In string concatenation operations, the C# compiler treats a null string the same as an empty string.</span></span>

<span data-ttu-id="5df7d-118">Eine andere Methoden zum Verketten von Zeichenfolgen ist <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5df7d-118">Other method to concatenate strings is <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5df7d-119">Diese Methode funktioniert gut, wenn Sie eine Zeichenfolge mit einer kleinen Anzahl von Zeichenfolgenkomponenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="5df7d-119">This method works well when you are building a string from a small number of component strings.</span></span>

<span data-ttu-id="5df7d-120">In anderen Fällen kann es passieren, dass Sie Zeichenfolgen in einer Schleife kombinieren, bei der Sie nicht wissen, wie viele Quellzeichenfolgen kombiniert werden, und die tatsächliche Anzahl an Quellzeichenfolgen kann in solchen Fällen sehr groß sein.</span><span class="sxs-lookup"><span data-stu-id="5df7d-120">In other cases, you may be combining strings in a loop where you don't know how many source strings you're combining, and the actual number of source strings may be large.</span></span> <span data-ttu-id="5df7d-121">Für solche Szenarios wurde die Klasse <xref:System.Text.StringBuilder> entwickelt.</span><span class="sxs-lookup"><span data-stu-id="5df7d-121">The <xref:System.Text.StringBuilder> class was designed for these scenarios.</span></span> <span data-ttu-id="5df7d-122">Im folgenden Code werden Zeichenfolgen mit der Methode <xref:System.Text.StringBuilder.Append%2A> der Klasse <xref:System.Text.StringBuilder> verkettet.</span><span class="sxs-lookup"><span data-stu-id="5df7d-122">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet4":::

<span data-ttu-id="5df7d-123">Erfahren Sie mehr über die [Gründe für das Verketten von Zeichenfolgen oder die `StringBuilder`-Klasse](/dotnet/api/system.text.stringbuilder#the-string-and-stringbuilder-types).</span><span class="sxs-lookup"><span data-stu-id="5df7d-123">You can read more about the [reasons to choose string concatenation or the `StringBuilder` class](/dotnet/api/system.text.stringbuilder#the-string-and-stringbuilder-types).</span></span>

<span data-ttu-id="5df7d-124">Eine weitere Option zum Verketten von Zeichenfolgen aus einer Sammlung ist die Verwendung der Methode <xref:System.String.Concat%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5df7d-124">Another option to join strings from a collection is to use <xref:System.String.Concat%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5df7d-125">Verwenden Sie die <xref:System.String.Join%2A?displayProperty=nameWithType>-Methode, wenn Quellzeichenfolgen durch ein Trennzeichen getrennt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5df7d-125">Use <xref:System.String.Join%2A?displayProperty=nameWithType> method if source strings should be separated by a delimiter.</span></span> <span data-ttu-id="5df7d-126">Der folgenden Code kombiniert ein Array aus Wörtern mithilfe beider Methoden:</span><span class="sxs-lookup"><span data-stu-id="5df7d-126">The following code combines an array of words using both methods:</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet5":::

<span data-ttu-id="5df7d-127">Die letzte Option zum Verketten von Zeichenfolgen aus einer Sammlung ist die Verwendung von [LINQ](../programming-guide/concepts/linq/index.md) und der Methode <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5df7d-127">At last, you can use [LINQ](../programming-guide/concepts/linq/index.md) and the <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> method to join strings from a collection.</span></span> <span data-ttu-id="5df7d-128">Diese Methode kombiniert die Quellzeichenfolgen mithilfe eines Lambdaausdrucks.</span><span class="sxs-lookup"><span data-stu-id="5df7d-128">This method combines the source strings using a lambda expression.</span></span> <span data-ttu-id="5df7d-129">Der Lambdaausdruck fügt jede Zeichenfolge der vorhandenen Akkumulation zu.</span><span class="sxs-lookup"><span data-stu-id="5df7d-129">The lambda expression does the work to add each string to the existing accumulation.</span></span> <span data-ttu-id="5df7d-130">Im folgenden Beispiel wird ein Array von Worten kombiniert, indem zwischen jedem Wort im Array Leerzeichen hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="5df7d-130">The following example combines an array of words by adding a space between each word in the array:</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/Concatenate.cs" id="Snippet6":::

## <a name="see-also"></a><span data-ttu-id="5df7d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5df7d-131">See also</span></span>

- <xref:System.String>
- <xref:System.Text.StringBuilder>
- [<span data-ttu-id="5df7d-132">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5df7d-132">C# programming guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="5df7d-133">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="5df7d-133">Strings</span></span>](../programming-guide/strings/index.md)
