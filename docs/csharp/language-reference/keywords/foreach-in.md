---
title: foreach, in (C#-Referenz)
ms.date: 05/24/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: b6b7dc0a4d3970ddfbbb6635ccebbbd5b75671e4
ms.sourcegitcommit: 54231aa56fca059e9297888a96fbca1d4cf3746c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2018
ms.locfileid: "34549376"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="8f094-102">foreach, in (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8f094-102">foreach, in (C# Reference)</span></span>

<span data-ttu-id="8f094-103">Die Anweisung `foreach` führt eine Anweisung oder einen Block von Anweisungen für jedes Element in einer Instanz des Typs aus, der die Schnittstelle <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert.</span><span class="sxs-lookup"><span data-stu-id="8f094-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="8f094-104">Die Anweisung `foreach` ist nicht auf diese Typen beschränkt und kann auf eine Instanz eines beliebigen Typs angewendet werden, der die folgenden Bedingungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="8f094-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="8f094-105">Er weist die öffentliche parameterlose Methode `GetEnumerator` auf, deren Rückgabetyp entweder Klasse, Struktur oder Schnittstellentyp ist.</span><span class="sxs-lookup"><span data-stu-id="8f094-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="8f094-106">Der Rückgabetyp der Methode `GetEnumerator` weist die öffentliche Eigenschaft `Current` und die öffentliche parameterlose Methode `MoveNext` auf, deren Rückgabetyp <xref:System.Boolean> ist.</span><span class="sxs-lookup"><span data-stu-id="8f094-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="8f094-107">Sie können die Schleife an jedem Punkt im `foreach`-Anweisungsblock mit dem Schlüsselwort [break](break.md) unterbrechen oder mit dem Schlüsselwort [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="8f094-107">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) keyword, or step to the next iteration in the loop by using the [continue](continue.md) keyword.</span></span> <span data-ttu-id="8f094-108">Sie können eine `foreach`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.</span><span class="sxs-lookup"><span data-stu-id="8f094-108">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="8f094-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8f094-109">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="8f094-110">Das folgende Beispiel zeigt die Syntax der Anweisung `foreach` mit einer Instanz des Typs <xref:System.Collections.Generic.List%601>, der die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> implementiert:</span><span class="sxs-lookup"><span data-stu-id="8f094-110">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="8f094-111">Im nächste Beispiel wird die Anweisung `foreach` mit einer Instanz des Typs <xref:System.Span%601?displayProperty=nameWithType> verwendet, der keine Schnittstellen implementiert:</span><span class="sxs-lookup"><span data-stu-id="8f094-111">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="8f094-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="8f094-112">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8f094-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f094-113">See also</span></span>

[<span data-ttu-id="8f094-114">Die foreach-Anweisung (C#-Spezifikation)</span><span class="sxs-lookup"><span data-stu-id="8f094-114">The foreach statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)  
[<span data-ttu-id="8f094-115">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="8f094-115">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  
[<span data-ttu-id="8f094-116">for</span><span class="sxs-lookup"><span data-stu-id="8f094-116">for</span></span>](for.md)  
[<span data-ttu-id="8f094-117">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="8f094-117">Iteration Statements</span></span>](iteration-statements.md)  
[<span data-ttu-id="8f094-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8f094-118">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="8f094-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="8f094-119">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="8f094-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8f094-120">C# Programming Guide</span></span>](../../programming-guide/index.md)  