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
ms.openlocfilehash: dbe4f4e95c2b99f1be47885e39d51db81ba3a97d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173704"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="b043a-102">foreach, in (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b043a-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="b043a-103">Die Anweisung `foreach` führt eine Anweisung oder einen Block von Anweisungen für jedes Element in einer Instanz des Typs aus, der die Schnittstelle <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert.</span><span class="sxs-lookup"><span data-stu-id="b043a-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="b043a-104">Die Anweisung `foreach` ist nicht auf diese Typen beschränkt und kann auf eine Instanz eines beliebigen Typs angewendet werden, der die folgenden Bedingungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="b043a-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="b043a-105">Er weist die öffentliche parameterlose Methode `GetEnumerator` auf, deren Rückgabetyp entweder Klasse, Struktur oder Schnittstellentyp ist.</span><span class="sxs-lookup"><span data-stu-id="b043a-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="b043a-106">Der Rückgabetyp der Methode `GetEnumerator` weist die öffentliche Eigenschaft `Current` und die öffentliche parameterlose Methode `MoveNext` auf, deren Rückgabetyp <xref:System.Boolean> ist.</span><span class="sxs-lookup"><span data-stu-id="b043a-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="b043a-107">Ab C# 7.3 können Sie die Iterationsvariable mit den Modifizierern `ref` oder `ref readonly` deklarieren, wenn die `Current`-Eigenschaft des Enumerators einen [Verweisrückgabewert](ref.md#reference-return-values) (`ref T`, wobei `T` dem Typ des Auflistungselements entspricht) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b043a-107">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="b043a-108">Ab C# 8.0 kann der `await`-Operator auf die `foreach`-Anweisung angewendet werden, wenn der Auflistungstyp die <xref:System.Collections.Generic.IAsyncEnumerable%601>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="b043a-108">Beginning with C# 8.0, the `await` operator may be applied to the `foreach` statement when the collection type implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="b043a-109">Jede Iteration der Schleife kann unterbrochen werden, während das nächste Element asynchron abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b043a-109">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="b043a-110">Standardmäßig werden Streamelemente im erfassten Kontext verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b043a-110">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="b043a-111">Wenn Sie die Erfassung des Kontexts deaktivieren möchten, verwenden Sie die Erweiterungsmethode <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b043a-111">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="b043a-112">Weitere Informationen über Synchronisierungskontexte und die Erfassung des aktuellen Kontexts finden Sie im Artikel über das [Verwenden des aufgabenbasierten asynchronen Musters](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="b043a-112">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="b043a-113">Sie können die Schleife an jedem Punkt im `foreach`-Anweisungsblock mit der Anweisung [break](break.md) unterbrechen oder mit der Anweisung [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="b043a-113">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="b043a-114">Sie können eine `foreach`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.</span><span class="sxs-lookup"><span data-stu-id="b043a-114">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="b043a-115">Wenn die `foreach`-Anweisung auf `null` angewendet wird, wird <xref:System.NullReferenceException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b043a-115">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="b043a-116">Falls die Quellsammlung der `foreach`-Anweisung leer ist, wird der Text der `foreach`-Schleife nicht ausgeführt und übersprungen.</span><span class="sxs-lookup"><span data-stu-id="b043a-116">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="examples"></a><span data-ttu-id="b043a-117">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b043a-117">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="b043a-118">Das folgende Beispiel zeigt die Syntax der Anweisung `foreach` mit einer Instanz des Typs <xref:System.Collections.Generic.List%601>, der die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> implementiert:</span><span class="sxs-lookup"><span data-stu-id="b043a-118">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="b043a-119">Im nächste Beispiel wird die Anweisung `foreach` mit einer Instanz des Typs <xref:System.Span%601?displayProperty=nameWithType> verwendet, der keine Schnittstellen implementiert:</span><span class="sxs-lookup"><span data-stu-id="b043a-119">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="b043a-120">Im folgenden Beispiel wird eine `ref`-Iterationsvariable verwendet, um die Werte der Elemente in einem stackalloc-Array festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b043a-120">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="b043a-121">Die Version `ref readonly` durchläuft die Auflistung, um alle Werte auszugeben.</span><span class="sxs-lookup"><span data-stu-id="b043a-121">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="b043a-122">Die `readonly`-Deklaration verwendet eine implizite lokale Variablendeklaration.</span><span class="sxs-lookup"><span data-stu-id="b043a-122">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="b043a-123">Implizite Variablendeklarationen können wie explizit typisierte Variablendeklarationen mit `ref`- oder `ref readonly`-Deklarationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b043a-123">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

<span data-ttu-id="b043a-124">Das folgende Beispiel verwendet `await foreach`, um eine Auflistung zu durchlaufen, die jedes Element asynchron generiert:</span><span class="sxs-lookup"><span data-stu-id="b043a-124">The following example uses `await foreach` to iterate a collection that generates each element asynchronously:</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#AwaitForeach)]

## <a name="c-language-specification"></a><span data-ttu-id="b043a-125">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b043a-125">C# language specification</span></span>

<span data-ttu-id="b043a-126">Weitere Informationen finden Sie im Abschnitt [Die foreach-Anweisung](~/_csharplang/spec/statements.md#the-foreach-statement) der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="b043a-126">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="b043a-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b043a-127">See also</span></span>

- [<span data-ttu-id="b043a-128">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b043a-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b043a-129">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b043a-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b043a-130">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b043a-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b043a-131">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="b043a-131">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="b043a-132">for-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b043a-132">for statement</span></span>](for.md)
