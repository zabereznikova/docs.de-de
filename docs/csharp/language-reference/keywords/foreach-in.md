---
title: foreach, in (C#-Referenz)
ms.date: 10/11/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d5601682d53a01ff07aba7e416aa81ded4c03e4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="2ec1d-102">foreach, in (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2ec1d-102">foreach, in (C# Reference)</span></span>
<span data-ttu-id="2ec1d-103">Mit der `foreach`-Anweisung wird eine Gruppe von eingebetteten Anweisungen für jedes Element in einem Array oder einer Objektauflistung wiederholt, das die Schnittstelle <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-103">The `foreach` statement repeats a group of embedded statements for each element in an array or an object collection that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="2ec1d-104">Die `foreach`-Anweisung wird verwendet, um die Auflistung zu durchlaufen und dadurch die gewünschten Informationen zu erhalten. Setzen Sie sie nicht ein, um der Auflistung Elemente hinzuzufügen oder aus ihr zu entfernen, um unvorhersehbare Nebeneffekte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-104">The `foreach` statement is used to iterate through the collection to get the information that you want, but can not be used to add or remove items from the source collection to avoid unpredictable side effects.</span></span> <span data-ttu-id="2ec1d-105">Wenn Sie Elemente zu der Quellauflistung hinzufügen oder daraus entfernen müssen, verwenden Sie eine [for](for.md)-Schleife.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-105">If you need to add or remove items from the source collection, use a [for](for.md) loop.</span></span>
  
 <span data-ttu-id="2ec1d-106">Die Ausführung der eingebetteten Anweisungen wird für jedes Element in dem Array oder der Auflistung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-106">The embedded statements continue to execute for each element in the array or collection.</span></span> <span data-ttu-id="2ec1d-107">Nachdem die Iteration alle Elemente in der Auflistung durchlaufen hat, wird die Steuerung an die nächste Anweisung, die auf den `foreach`-Block folgt, übergeben.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-107">After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the `foreach` block.</span></span>
  
 <span data-ttu-id="2ec1d-108">Sie können die Schleife an jedem Punkt im `foreach`-Block mit dem Schlüsselwort [break](break.md) unterbrechen oder mit dem Schlüsselwort [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-108">At any point within the `foreach` block, you can break out of the loop by using the [break](break.md) keyword, or step to the next iteration in the loop by using the [continue](continue.md) keyword.</span></span>

 <span data-ttu-id="2ec1d-109">Eine `foreach`-Schleife kann durch die Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-109">A `foreach` loop can also be exited by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

 <span data-ttu-id="2ec1d-110">Weitere Informationen zum `foreach`-Schlüsselwort und zu Codebeispielen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="2ec1d-110">For more information about the `foreach` keyword and code samples, see the following topics:</span></span>  

 [<span data-ttu-id="2ec1d-111">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="2ec1d-111">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [<span data-ttu-id="2ec1d-112">Gewusst wie: Zugreifen auf Sammlungsklassen mit foreach</span><span class="sxs-lookup"><span data-stu-id="2ec1d-112">How to: Access a Collection Class with foreach</span></span>](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a><span data-ttu-id="2ec1d-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ec1d-113">Example</span></span>
 <span data-ttu-id="2ec1d-114">Der folgende Code zeigt drei Beispiele.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-114">The following code shows three examples.</span></span>

> [!TIP]
> <span data-ttu-id="2ec1d-115">Sie können ändern, in den Beispielen Experimentieren mit der Syntax, und wiederholen verschiedene Verwendungen, die eher mit Ihrem Anwendungsfall vergleichbar sind.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-115">You can modify the examples to experiment with the syntax and try different usages that are more similar to your use case.</span></span> <span data-ttu-id="2ec1d-116">Drücken Sie "Ausführen", um den Code auszuführen, und bearbeiten, und drücken Sie "führen Sie" erneut aus.</span><span class="sxs-lookup"><span data-stu-id="2ec1d-116">Press "Run" to run the code, then edit and press "Run" again.</span></span>

-   <span data-ttu-id="2ec1d-117">eine typische `foreach`-Schleife, die den Inhalt eines Arrays von Ganzzahlen anzeigt</span><span class="sxs-lookup"><span data-stu-id="2ec1d-117">a typical `foreach` loop that displays the contents of an array of integers</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   <span data-ttu-id="2ec1d-118">eine [for](../../../csharp/language-reference/keywords/for.md)-Schleife, die die gleiche Aufgabe ausführt</span><span class="sxs-lookup"><span data-stu-id="2ec1d-118">a [for](../../../csharp/language-reference/keywords/for.md) loop that does the same thing</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   <span data-ttu-id="2ec1d-119">eine `foreach`-Schleife, die die Anzahl von Elementen im Array enthält</span><span class="sxs-lookup"><span data-stu-id="2ec1d-119">a `foreach` loop that maintains a count of the number of elements in the array</span></span>

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a><span data-ttu-id="2ec1d-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="2ec1d-120">C# Language Specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2ec1d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ec1d-121">See Also</span></span>  

[<span data-ttu-id="2ec1d-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2ec1d-122">C# Reference</span></span>](../index.md)

[<span data-ttu-id="2ec1d-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2ec1d-123">C# Programming Guide</span></span>](../../programming-guide/index.md)

[<span data-ttu-id="2ec1d-124">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2ec1d-124">C# Keywords</span></span>](index.md)

[<span data-ttu-id="2ec1d-125">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="2ec1d-125">Iteration Statements</span></span>](iteration-statements.md)

[<span data-ttu-id="2ec1d-126">for</span><span class="sxs-lookup"><span data-stu-id="2ec1d-126">for</span></span>](for.md)
