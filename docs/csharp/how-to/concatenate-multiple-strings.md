---
title: 'Vorgehensweise: Verketten mehrerer Zeichenfolgen (C#-Handbuch)'
description: Es gibt mehrere Möglichkeiten zum Verketten von Zeichenfolgen in C#. Lernen Sie die Optionen und Gründe für verschiedene Auswahlmöglichkeiten kennen.
ms.date: 02/20/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 785c54b6f9a22ae9cbf131918c51e75b8535b7a6
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2018
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a><span data-ttu-id="f41e5-104">Vorgehensweise: Verketten mehrerer Zeichenfolgen (C#-Handbuch)</span><span class="sxs-lookup"><span data-stu-id="f41e5-104">How to: Concatenate Multiple Strings (C# Guide)</span></span>

<span data-ttu-id="f41e5-105">*Verkettung* ist der Prozess, eine Zeichenfolge ans Ende einer anderen Zeichenfolge anzufügen.</span><span class="sxs-lookup"><span data-stu-id="f41e5-105">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="f41e5-106">Sie können Zeichenfolgen mithilfe des `+`-Operators verketten.</span><span class="sxs-lookup"><span data-stu-id="f41e5-106">You concatenate strings by using the `+` operator.</span></span> <span data-ttu-id="f41e5-107">Bei Zeichenfolgenliteralen und Zeichenfolgenkonstanten erfolgt die Verkettung beim Kompilieren. Es erfolgt keine Verkettung zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="f41e5-107">For string literals and string constants, concatenation occurs at compile time; no run-time concatenation occurs.</span></span> <span data-ttu-id="f41e5-108">Bei Zeichenfolgenvariablen erfolgt die Verkettung nur zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="f41e5-108">For string variables, concatenation occurs only at run time.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="f41e5-109">Im folgenden Beispiel wird die Verkettung genutzt, um ein langes Zeichenfolgenliteral in kleinere Zeichenfolgen aufzuteilen, wodurch die Lesbarkeit im Quellcode verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="f41e5-109">The following example uses concatenation to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="f41e5-110">Diese Teile werden zur Kompilierzeit in eine einzelne Zeichenfolge verkettet.</span><span class="sxs-lookup"><span data-stu-id="f41e5-110">These parts are concatenated into a single string at compile time.</span></span> <span data-ttu-id="f41e5-111">Es entstehen unabhängig von der Anzahl an Zeichenfolgen keine Leistungseinbußen zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="f41e5-111">There is no run-time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp-interactive[Combining strings at compile time](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#1)]  
  

<span data-ttu-id="f41e5-112">Zum Verketten von Zeichenfolgenvariablen können Sie die Operatoren `+` und `+=`, die [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) oder die Methoden <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> oder <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="f41e5-112">To concatenate string variables, you can use the `+` or `+=` operators, [string interpolation](../language-reference/tokens/interpolated.md) or the <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="f41e5-113">Der Operator `+` ist einfach zu verwenden und gut für intuitiv verständlichen Code geeignet.</span><span class="sxs-lookup"><span data-stu-id="f41e5-113">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="f41e5-114">Auch wenn Sie mehrere `+`-Operatoren in einer Anweisung verwenden, wird der Inhalt der Zeichenfolge nur einmal kopiert.</span><span class="sxs-lookup"><span data-stu-id="f41e5-114">Even if you use several `+` operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="f41e5-115">Der folgende Code zeigt Beispiele für die Verwendung der Operatoren `+` und `+=` zum Verketten von Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="f41e5-115">The following code shows examples of using the `+` and `+=` operators to concatenate strings:</span></span>

[!code-csharp-interactive[combining strings using +](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#2)]  

<span data-ttu-id="f41e5-116">In einigen Ausdrücken ist es einfacher, Zeichenfolgen mithilfe der Zeichenfolgeninterpolation zu verketten, wie in folgendem Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="f41e5-116">In some expressions, it's easier to concatenate strings using string interpolation, as the following code shows:</span></span>
  
[!code-csharp-interactive[building strings using string interpolation](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#3)]  
  
> [!NOTE]
>  <span data-ttu-id="f41e5-117">Bei der Zeichenfolgenverkettung behandelt der C#-Compiler eine NULL-Zeichenfolge wie eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f41e5-117">In string concatenation operations, the C# compiler treats a null string the same as an empty string.</span></span>

<span data-ttu-id="f41e5-118">Eine andere Methoden zum Verketten von Zeichenfolgen ist <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f41e5-118">Other method to concatenate strings is <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f41e5-119">Diese Methode funktioniert gut, wenn Sie eine Zeichenfolge mit einer kleinen Anzahl von Zeichenfolgenkomponenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="f41e5-119">This method works well when you are building a string from a small number of component strings.</span></span>

<span data-ttu-id="f41e5-120">In anderen Fällen kann es passieren, dass Sie Zeichenfolgen in einer Schleife kombinieren, bei der Sie nicht wissen, wie viele Quellzeichenfolgen Sie kombinieren, und die tatsächliche Anzahl an Quellzeichenfolgen kann in solchen Fällen sehr groß sein.</span><span class="sxs-lookup"><span data-stu-id="f41e5-120">In other cases you may be combining strings in a loop, where you don't know how many source strings you are combining, and the actual number of source strings may be quite large.</span></span> <span data-ttu-id="f41e5-121">Für solche Szenarios wurde die Klasse <xref:System.Text.StringBuilder> entwickelt.</span><span class="sxs-lookup"><span data-stu-id="f41e5-121">The <xref:System.Text.StringBuilder> class was designed for these scenarios.</span></span> <span data-ttu-id="f41e5-122">Im folgenden Code werden Zeichenfolgen mit der Methode <xref:System.Text.StringBuilder.Append%2A> der Klasse <xref:System.Text.StringBuilder> verkettet.</span><span class="sxs-lookup"><span data-stu-id="f41e5-122">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span>  
  
[!code-csharp-interactive[string concatenation using string builder](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#4)]  

<span data-ttu-id="f41e5-123">Erfahren Sie mehr über die [Gründe für das Verketten von Zeichenfolgen oder die `StringBuilder`-Klasse](xref:System.Text.StringBuilder#StringAndSB)</span><span class="sxs-lookup"><span data-stu-id="f41e5-123">You can read more about the [reasons to choose string concatenation or the `StringBuilder` class](xref:System.Text.StringBuilder#StringAndSB)</span></span>

<span data-ttu-id="f41e5-124">Eine weitere Option zum Verketten von Zeichenfolgen aus einer Sammlung ist die Verwendung der Methode <xref:System.String.Concat%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f41e5-124">Another option to join strings from a collection is to use <xref:System.String.Concat%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f41e5-125">Verwenden Sie die <xref:System.String.Join%2A?displayProperty=nameWithType>-Methode, wenn Quellzeichenfolgen durch ein Trennzeichen getrennt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f41e5-125">Use <xref:System.String.Join%2A?displayProperty=nameWithType> method if source strings should be separated by a delimeter.</span></span> <span data-ttu-id="f41e5-126">Der folgenden Code kombiniert ein Array aus Wörtern mithilfe beider Methoden:</span><span class="sxs-lookup"><span data-stu-id="f41e5-126">The following code combines an array of words using both methods:</span></span>

[!code-csharp-interactive[concatenation of string collection](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#5)]

<span data-ttu-id="f41e5-127">Die letzte Option zum Verketten von Zeichenfolgen aus einer Sammlung ist die Verwendung von [LINQ](../programming-guide/concepts/linq/index.md) und der Methode <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f41e5-127">At last, you can use [LINQ](../programming-guide/concepts/linq/index.md) and the <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> method to join strings from a collection.</span></span> <span data-ttu-id="f41e5-128">Diese Methode kombiniert die Quellzeichenfolgen mithilfe eines Lambdaausdrucks.</span><span class="sxs-lookup"><span data-stu-id="f41e5-128">This method combines the source strings using a lambda expression.</span></span> <span data-ttu-id="f41e5-129">Der Lambdaausdruck fügt jede Zeichenfolge der vorhandenen Akkumulation zu.</span><span class="sxs-lookup"><span data-stu-id="f41e5-129">The lambda expression does the work to add each string to the existing accumulation.</span></span> <span data-ttu-id="f41e5-130">Im folgenden Beispiel wird ein Array von Worten kombiniert, indem zwischen jedem Wort im Array Leerzeichen hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="f41e5-130">The following example combines an array of words by adding a space between each word in the array:</span></span>

[!code-csharp-interactive[string concatenation using LINQ expressions](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#6)]  

<span data-ttu-id="f41e5-131">Sie können diese Beispiele ausprobieren, indem Sie sich den Code in unserem [GitHub-Repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings) ansehen.</span><span class="sxs-lookup"><span data-stu-id="f41e5-131">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="f41e5-132">Alternativ dazu können Sie die Beispiele [als ZIP-Datei](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f41e5-132">Or you can download the samples [as a zip file](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="f41e5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f41e5-133">See Also</span></span>  
 <xref:System.String>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="f41e5-134">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f41e5-134">C# Programming Guide</span></span>](../programming-guide/index.md)  
 [<span data-ttu-id="f41e5-135">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f41e5-135">Strings</span></span>](../programming-guide/strings/index.md)
