---
title: foreach-Anweisung in C#
ms.date: 05/17/2019
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 9c1521f39dea72b51801a81b13e8a0203956731c
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422800"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="94907-102">foreach, in (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="94907-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="94907-103">Die Anweisung `foreach` führt eine Anweisung oder einen Block von Anweisungen für jedes Element in einer Instanz des Typs aus, der die Schnittstelle <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert.</span><span class="sxs-lookup"><span data-stu-id="94907-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="94907-104">Die Anweisung `foreach` ist nicht auf diese Typen beschränkt und kann auf eine Instanz eines beliebigen Typs angewendet werden, der die folgenden Bedingungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="94907-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="94907-105">Er weist die öffentliche parameterlose Methode `GetEnumerator` auf, deren Rückgabetyp entweder Klasse, Struktur oder Schnittstellentyp ist.</span><span class="sxs-lookup"><span data-stu-id="94907-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="94907-106">Der Rückgabetyp der Methode `GetEnumerator` weist die öffentliche Eigenschaft `Current` und die öffentliche parameterlose Methode `MoveNext` auf, deren Rückgabetyp <xref:System.Boolean> ist.</span><span class="sxs-lookup"><span data-stu-id="94907-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="94907-107">Ab C# 7.3 können Sie die Iterationsvariable mit den Modifizierern `ref` oder `ref readonly` deklarieren, wenn die `Current`-Eigenschaft des Enumerators einen [Verweisrückgabewert](ref.md#reference-return-values) (`ref T`, wobei `T` dem Typ des Auflistungselements entspricht) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="94907-107">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="94907-108">Sie können die Schleife an jedem Punkt im `foreach`-Anweisungsblock mit der Anweisung [break](break.md) unterbrechen oder mit der Anweisung [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="94907-108">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="94907-109">Sie können eine `foreach`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.</span><span class="sxs-lookup"><span data-stu-id="94907-109">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="94907-110">Wenn die `foreach`-Anweisung auf `null` angewendet wird, wird <xref:System.NullReferenceException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="94907-110">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="94907-111">Falls die Quellsammlung der `foreach`-Anweisung leer ist, wird der Text der `foreach`-Schleife nicht ausgeführt und übersprungen.</span><span class="sxs-lookup"><span data-stu-id="94907-111">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop is not executed and skipped.</span></span>

## <a name="examples"></a><span data-ttu-id="94907-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="94907-112">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="94907-113">Das folgende Beispiel zeigt die Syntax der Anweisung `foreach` mit einer Instanz des Typs <xref:System.Collections.Generic.List%601>, der die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> implementiert:</span><span class="sxs-lookup"><span data-stu-id="94907-113">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="94907-114">Im nächste Beispiel wird die Anweisung `foreach` mit einer Instanz des Typs <xref:System.Span%601?displayProperty=nameWithType> verwendet, der keine Schnittstellen implementiert:</span><span class="sxs-lookup"><span data-stu-id="94907-114">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="94907-115">Im folgenden Beispiel wird eine `ref`-Iterationsvariable verwendet, um die Werte der Elemente in einem stackalloc-Array festzulegen.</span><span class="sxs-lookup"><span data-stu-id="94907-115">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="94907-116">Die Version `ref readonly` durchläuft die Auflistung, um alle Werte auszugeben.</span><span class="sxs-lookup"><span data-stu-id="94907-116">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="94907-117">Die `readonly`-Deklaration verwendet eine implizite lokale Variablendeklaration.</span><span class="sxs-lookup"><span data-stu-id="94907-117">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="94907-118">Implizite Variablendeklarationen können wie explizit typisierte Variablendeklarationen mit `ref`- oder `ref readonly`-Deklarationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="94907-118">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a><span data-ttu-id="94907-119">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="94907-119">C# language specification</span></span>

<span data-ttu-id="94907-120">Weitere Informationen finden Sie im Abschnitt [Die foreach-Anweisung](~/_csharplang/spec/statements.md#the-foreach-statement) der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="94907-120">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="94907-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94907-121">See also</span></span>

- [<span data-ttu-id="94907-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="94907-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="94907-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="94907-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="94907-124">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="94907-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="94907-125">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="94907-125">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="94907-126">for-Anweisung</span><span class="sxs-lookup"><span data-stu-id="94907-126">for statement</span></span>](for.md)
