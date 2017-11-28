---
title: 'Gewusst wie: Verketten von mehreren Zeichenfolgen (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca240523e2483289e11433fd58d9630a31721b33
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a><span data-ttu-id="84c67-102">Gewusst wie: Verketten von mehreren Zeichenfolgen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="84c67-102">How to: Concatenate Multiple Strings (C# Programming Guide)</span></span>
<span data-ttu-id="84c67-103">*Verkettung* ist der Prozess, eine Zeichenfolge ans Ende einer anderen Zeichenfolge anzufügen.</span><span class="sxs-lookup"><span data-stu-id="84c67-103">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="84c67-104">Wenn Sie Zeichenfolgenliterale oder –konstanten mit dem Operator `+` verketten, erstellt der Compiler eine einzelne Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="84c67-104">When you concatenate string literals or string constants by using the `+` operator, the compiler creates a single string.</span></span> <span data-ttu-id="84c67-105">Es tritt keine Laufzeitverkettung auf.</span><span class="sxs-lookup"><span data-stu-id="84c67-105">No run time concatenation occurs.</span></span> <span data-ttu-id="84c67-106">Zeichenfolgenvariablen können jedoch nur zur Laufzeit verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="84c67-106">However, string variables can be concatenated only at run time.</span></span> <span data-ttu-id="84c67-107">In diesem Fall sollten Sie die Leistungsauswirkungen der verschiedenen Ansätze kennen.</span><span class="sxs-lookup"><span data-stu-id="84c67-107">In this case, you should understand the performance implications of the various approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84c67-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="84c67-108">Example</span></span>  
 <span data-ttu-id="84c67-109">Im folgenden Beispiel wird dargestellt, wie ein langes Zeichenfolgenliteral in kleinere Zeichenfolgen aufgeteilt werden kann, um die Lesbarkeit im Quellcode zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="84c67-109">The following example shows how to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="84c67-110">Diese Teile werden zur Kompilierzeit in eine einzelne Zeichenfolge verkettet.</span><span class="sxs-lookup"><span data-stu-id="84c67-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="84c67-111">Es entstehen unabhängig von der Anzahl an Zeichenfolgen keine Laufzeitleistungseinbußen.</span><span class="sxs-lookup"><span data-stu-id="84c67-111">There is no run time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="84c67-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="84c67-112">Example</span></span>  
 <span data-ttu-id="84c67-113">Um Zeichenfolgenvariablen zu verketten, können Sie den Operator `+` bzw. `+=` oder die Methode <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType>, oder <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="84c67-113">To concatenate string variables, you can use the `+` or `+=` operators, or the <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="84c67-114">Der Operator `+` ist einfach zu verwenden und gut für intuitiv verständlichen Code geeignet.</span><span class="sxs-lookup"><span data-stu-id="84c67-114">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="84c67-115">Auch wenn Sie mehrere +-Operatoren in einer Anweisung verwenden, wird der Inhalt der Zeichenfolge nur einmal kopiert.</span><span class="sxs-lookup"><span data-stu-id="84c67-115">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="84c67-116">Wenn Sie diesen Vorgang jedoch mehrfach wiederholen, z.B. in einer Schleife, kann dies Effizienzprobleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="84c67-116">But if you repeat this operation multiple times, for example in a loop, it might cause efficiency problems.</span></span> <span data-ttu-id="84c67-117">Beachten Sie beispielsweise folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="84c67-117">For example, note the following code:</span></span>  
  
 [!code-csharp[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="84c67-118">Bei der Zeichenfolgenverkettung behandelt der C#-Compiler eine NULL-Zeichenfolge wie eine leere Zeichenfolge, konvertiert jedoch nicht den Wert der ursprünglichen NULL-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="84c67-118">In string concatenation operations, the C# compiler treats a null string the same as an empty string, but it does not convert the value of the original null string.</span></span>  
  
 <span data-ttu-id="84c67-119">Falls Sie keine große Anzahl an Zeichenfolgen (z.B. in einer Schleife) verketten, fallen die Leistungseinbußen dieses Codes wahrscheinlich nicht ins Gewicht.</span><span class="sxs-lookup"><span data-stu-id="84c67-119">If you are not concatenating large numbers of strings (for example, in a loop), the performance cost of this code is probably not significant.</span></span> <span data-ttu-id="84c67-120">Dasselbe gilt für die Methoden <xref:System.String.Concat%2A?displayProperty=nameWithType> und <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="84c67-120">The same is true for the <xref:System.String.Concat%2A?displayProperty=nameWithType> and <xref:System.String.Format%2A?displayProperty=nameWithType> methods.</span></span>  
  
 <span data-ttu-id="84c67-121">Wenn jedoch die Leistung eine wichtige Rolle spielt, sollten Sie immer die Klasse <xref:System.Text.StringBuilder> zum Verketten von Zeichenfolgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="84c67-121">However, when performance is important, you should always use the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span> <span data-ttu-id="84c67-122">Im folgenden Code werden mit der Methode <xref:System.Text.StringBuilder.Append%2A> der Klasse <xref:System.Text.StringBuilder> Zeichenfolgen ohne den Verkettungseffekt des Operators `+` miteinander verkettet.</span><span class="sxs-lookup"><span data-stu-id="84c67-122">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings without the chaining effect of the `+` operator.</span></span>  
  
 [!code-csharp[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="84c67-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84c67-123">See Also</span></span>  
 <xref:System.String>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="84c67-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="84c67-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="84c67-125">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="84c67-125">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
