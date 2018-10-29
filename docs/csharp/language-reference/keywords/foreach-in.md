---
title: foreach-Anweisung in C#
ms.date: 06/29/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 675e6b7fa925fe1822c2fc321d79afd13b5e4c51
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347682"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="04092-102">foreach, in (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="04092-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="04092-103">Die Anweisung `foreach` führt eine Anweisung oder einen Block von Anweisungen für jedes Element in einer Instanz des Typs aus, der die Schnittstelle <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert.</span><span class="sxs-lookup"><span data-stu-id="04092-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="04092-104">Die Anweisung `foreach` ist nicht auf diese Typen beschränkt und kann auf eine Instanz eines beliebigen Typs angewendet werden, der die folgenden Bedingungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="04092-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="04092-105">Er weist die öffentliche parameterlose Methode `GetEnumerator` auf, deren Rückgabetyp entweder Klasse, Struktur oder Schnittstellentyp ist.</span><span class="sxs-lookup"><span data-stu-id="04092-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="04092-106">Der Rückgabetyp der Methode `GetEnumerator` weist die öffentliche Eigenschaft `Current` und die öffentliche parameterlose Methode `MoveNext` auf, deren Rückgabetyp <xref:System.Boolean> ist.</span><span class="sxs-lookup"><span data-stu-id="04092-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="04092-107">Sie können die Schleife an jedem Punkt im `foreach`-Anweisungsblock mit der Anweisung [break](break.md) unterbrechen oder mit der Anweisung [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="04092-107">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="04092-108">Sie können eine `foreach`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.</span><span class="sxs-lookup"><span data-stu-id="04092-108">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="04092-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="04092-109">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="04092-110">Das folgende Beispiel zeigt die Syntax der Anweisung `foreach` mit einer Instanz des Typs <xref:System.Collections.Generic.List%601>, der die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> implementiert:</span><span class="sxs-lookup"><span data-stu-id="04092-110">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="04092-111">Im nächste Beispiel wird die Anweisung `foreach` mit einer Instanz des Typs <xref:System.Span%601?displayProperty=nameWithType> verwendet, der keine Schnittstellen implementiert:</span><span class="sxs-lookup"><span data-stu-id="04092-111">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="04092-112">Ab C# 7.3 können Sie die Iterationsvariable mit den Modifizierern `ref` oder `ref readonly` deklarieren, wenn die `Current`-Eigenschaft des Enumerators einen [Verweisrückgabewert](../../programming-guide/classes-and-structs/ref-returns.md) (`ref T`, wobei `T` dem Typ des Auflistungselements entspricht) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="04092-112">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span> <span data-ttu-id="04092-113">Im folgenden Beispiel wird eine `ref`-Iterationsvariable verwendet, um die Werte der Elemente in einem stackalloc-Array festzulegen.</span><span class="sxs-lookup"><span data-stu-id="04092-113">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="04092-114">Die Version `ref readonly` durchläuft die Auflistung, um alle Werte auszugeben.</span><span class="sxs-lookup"><span data-stu-id="04092-114">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="04092-115">Die `readonly`-Deklaration verwendet eine implizite lokale Variablendeklaration.</span><span class="sxs-lookup"><span data-stu-id="04092-115">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="04092-116">Implizite Variablendeklarationen können wie explizit typisierte Variablendeklarationen mit `ref`- oder `ref readonly`-Deklarationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04092-116">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a><span data-ttu-id="04092-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="04092-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="04092-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04092-118">See also</span></span>

- [<span data-ttu-id="04092-119">Die foreach-Anweisung (C#-Spezifikation)</span><span class="sxs-lookup"><span data-stu-id="04092-119">The foreach statement (C# language specification)</span></span>](~/_csharplang/spec/statements.md#the-foreach-statement)
- [<span data-ttu-id="04092-120">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="04092-120">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="04092-121">for</span><span class="sxs-lookup"><span data-stu-id="04092-121">for</span></span>](for.md)
- [<span data-ttu-id="04092-122">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="04092-122">Iteration Statements</span></span>](iteration-statements.md)
- [<span data-ttu-id="04092-123">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="04092-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="04092-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="04092-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="04092-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="04092-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
