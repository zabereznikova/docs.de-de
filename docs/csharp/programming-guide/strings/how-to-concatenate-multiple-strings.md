---
title: 'Gewusst wie: Verketten von mehreren Zeichenfolgen (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b191a61258a496115a4d7045046f9b4a2dbee58c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a><span data-ttu-id="14d8e-102">Gewusst wie: Verketten von mehreren Zeichenfolgen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="14d8e-102">How to: Concatenate Multiple Strings (C# Programming Guide)</span></span>
<span data-ttu-id="14d8e-103">*Verkettung* ist der Prozess, eine Zeichenfolge ans Ende einer anderen Zeichenfolge anzufügen.</span><span class="sxs-lookup"><span data-stu-id="14d8e-103">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="14d8e-104">Wenn Sie Zeichenfolgenliterale oder –konstanten mit dem Operator `+` verketten, erstellt der Compiler eine einzelne Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="14d8e-104">When you concatenate string literals or string constants by using the `+` operator, the compiler creates a single string.</span></span> <span data-ttu-id="14d8e-105">Es tritt keine Laufzeitverkettung auf.</span><span class="sxs-lookup"><span data-stu-id="14d8e-105">No run time concatenation occurs.</span></span> <span data-ttu-id="14d8e-106">Zeichenfolgenvariablen können jedoch nur zur Laufzeit verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="14d8e-106">However, string variables can be concatenated only at run time.</span></span> <span data-ttu-id="14d8e-107">In diesem Fall sollten Sie die Leistungsauswirkungen der verschiedenen Ansätze kennen.</span><span class="sxs-lookup"><span data-stu-id="14d8e-107">In this case, you should understand the performance implications of the various approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14d8e-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14d8e-108">Example</span></span>  
 <span data-ttu-id="14d8e-109">Im folgenden Beispiel wird dargestellt, wie ein langes Zeichenfolgenliteral in kleinere Zeichenfolgen aufgeteilt werden kann, um die Lesbarkeit im Quellcode zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="14d8e-109">The following example shows how to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="14d8e-110">Diese Teile werden zur Kompilierzeit in eine einzelne Zeichenfolge verkettet.</span><span class="sxs-lookup"><span data-stu-id="14d8e-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="14d8e-111">Es entstehen unabhängig von der Anzahl an Zeichenfolgen keine Laufzeitleistungseinbußen.</span><span class="sxs-lookup"><span data-stu-id="14d8e-111">There is no run time performance cost regardless of the number of strings involved.</span></span>  
  
 <span data-ttu-id="14d8e-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="14d8e-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="14d8e-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14d8e-113">Example</span></span>  
 <span data-ttu-id="14d8e-114">Um Zeichenfolgenvariablen zu verketten, können Sie den Operator `+` bzw. `+=` oder die Methode <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName>, oder <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName> verwenden.</span><span class="sxs-lookup"><span data-stu-id="14d8e-114">To concatenate string variables, you can use the `+` or `+=` operators, or the <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName> methods.</span></span> <span data-ttu-id="14d8e-115">Der Operator `+` ist einfach zu verwenden und gut für intuitiv verständlichen Code geeignet.</span><span class="sxs-lookup"><span data-stu-id="14d8e-115">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="14d8e-116">Auch wenn Sie mehrere +-Operatoren in einer Anweisung verwenden, wird der Inhalt der Zeichenfolge nur einmal kopiert.</span><span class="sxs-lookup"><span data-stu-id="14d8e-116">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="14d8e-117">Wenn Sie diesen Vorgang jedoch mehrfach wiederholen, z.B. in einer Schleife, kann dies Effizienzprobleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="14d8e-117">But if you repeat this operation multiple times, for example in a loop, it might cause efficiency problems.</span></span> <span data-ttu-id="14d8e-118">Beachten Sie beispielsweise folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="14d8e-118">For example, note the following code:</span></span>  
  
 <span data-ttu-id="14d8e-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="14d8e-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14d8e-120">Bei der Zeichenfolgenverkettung behandelt der C#-Compiler eine NULL-Zeichenfolge wie eine leere Zeichenfolge, konvertiert jedoch nicht den Wert der ursprünglichen NULL-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="14d8e-120">In string concatenation operations, the C# compiler treats a null string the same as an empty string, but it does not convert the value of the original null string.</span></span>  
  
 <span data-ttu-id="14d8e-121">Falls Sie keine große Anzahl an Zeichenfolgen (z.B. in einer Schleife) verketten, fallen die Leistungseinbußen dieses Codes wahrscheinlich nicht ins Gewicht.</span><span class="sxs-lookup"><span data-stu-id="14d8e-121">If you are not concatenating large numbers of strings (for example, in a loop), the performance cost of this code is probably not significant.</span></span> <span data-ttu-id="14d8e-122">Dasselbe gilt für die Methoden <xref:System.String.Concat%2A?displayProperty=fullName> und <xref:System.String.Format%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="14d8e-122">The same is true for the <xref:System.String.Concat%2A?displayProperty=fullName> and <xref:System.String.Format%2A?displayProperty=fullName> methods.</span></span>  
  
 <span data-ttu-id="14d8e-123">Wenn jedoch die Leistung eine wichtige Rolle spielt, sollten Sie immer die Klasse <xref:System.Text.StringBuilder> zum Verketten von Zeichenfolgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="14d8e-123">However, when performance is important, you should always use the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span> <span data-ttu-id="14d8e-124">Im folgenden Code werden mit der Methode <xref:System.Text.StringBuilder.Append%2A> der Klasse <xref:System.Text.StringBuilder> Zeichenfolgen ohne den Verkettungseffekt des Operators `+` miteinander verkettet.</span><span class="sxs-lookup"><span data-stu-id="14d8e-124">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings without the chaining effect of the `+` operator.</span></span>  
  
 <span data-ttu-id="14d8e-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="14d8e-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14d8e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14d8e-126">See Also</span></span>  
 <span data-ttu-id="14d8e-127"><xref:System.String></span><span class="sxs-lookup"><span data-stu-id="14d8e-127"><xref:System.String></span></span>   
 <span data-ttu-id="14d8e-128"><xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="14d8e-128"><xref:System.Text.StringBuilder></span></span>   
 <span data-ttu-id="14d8e-129">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="14d8e-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="14d8e-130">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="14d8e-130">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

