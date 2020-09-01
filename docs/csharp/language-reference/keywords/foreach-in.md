---
description: foreach, in (C#-Referenz)
title: foreach-Anweisung in C#
ms.date: 07/22/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 2ed89fa52b2d3d369d668bf79ab32eaf7be18a8a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142075"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="2846e-103">foreach, in (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2846e-103">foreach, in (C# reference)</span></span>

<span data-ttu-id="2846e-104">Die Anweisung `foreach` führt eine Anweisung oder einen Block von Anweisungen für jedes Element in einer Instanz des Typs aus, der die Schnittstellen <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert. Dies wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2846e-104">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

<span data-ttu-id="2846e-105">Die Anweisung `foreach` ist nicht auf diese Typen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="2846e-105">The `foreach` statement isn't limited to those types.</span></span> <span data-ttu-id="2846e-106">Sie können sie mit einer Instanz eines beliebigen Typs verwenden, der die folgenden Bedingungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="2846e-106">You can use it with an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="2846e-107">Ein Typ weist die öffentliche parameterlose Methode `GetEnumerator` auf, deren Rückgabetyp entweder eine Klasse, eine Struktur oder ein Schnittstellentyp ist.</span><span class="sxs-lookup"><span data-stu-id="2846e-107">a type has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="2846e-108">Der Rückgabetyp der Methode `GetEnumerator` weist die öffentliche Eigenschaft `Current` und die öffentliche parameterlose Methode `MoveNext` auf, deren Rückgabetyp <xref:System.Boolean> ist.</span><span class="sxs-lookup"><span data-stu-id="2846e-108">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="2846e-109">Im folgenden Beispiel wird die Anweisung `foreach` mit einer Instanz des Typs <xref:System.Span%601?displayProperty=nameWithType> verwendet, der keine Schnittstellen implementiert:</span><span class="sxs-lookup"><span data-stu-id="2846e-109">The following example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

<span data-ttu-id="2846e-110">Ab C# 7.3 können Sie die Iterationsvariable mit den Modifizierern `ref` oder `ref readonly` deklarieren, wenn die Eigenschaft `Current` des Enumerators einen [Verweisrückgabewert](ref.md#reference-return-values) (`ref T`, wobei `T` dem Typ des Sammlungselements entspricht) zurückgibt. Dies wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2846e-110">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of a collection element), you can declare an iteration variable with the `ref` or `ref readonly` modifier, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

<span data-ttu-id="2846e-111">Ab C# 8.0 können Sie die Anweisung `await foreach` verwenden, um einen asynchronen Datenstrom zu verarbeiten, also den Sammlungstyp, der die Schnittstelle <xref:System.Collections.Generic.IAsyncEnumerable%601> implementiert.</span><span class="sxs-lookup"><span data-stu-id="2846e-111">Beginning with C# 8.0, you can use the `await foreach` statement to consume an asynchronous stream of data, that is, the collection type that implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="2846e-112">Jede Iteration der Schleife kann unterbrochen werden, während das nächste Element asynchron abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2846e-112">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="2846e-113">Im folgenden Beispiel wird veranschaulicht, wie Sie die Anweisung `await foreach` verwenden:</span><span class="sxs-lookup"><span data-stu-id="2846e-113">The following example shows how to use the `await foreach` statement:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

<span data-ttu-id="2846e-114">Standardmäßig werden Streamelemente im erfassten Kontext verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="2846e-114">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="2846e-115">Wenn Sie die Erfassung des Kontexts deaktivieren möchten, verwenden Sie die Erweiterungsmethode <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2846e-115">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="2846e-116">Weitere Informationen über Synchronisierungskontexte und die Erfassung des aktuellen Kontexts finden Sie im Artikel [Verwenden des aufgabenbasierten asynchronen Musters](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="2846e-116">For more information about synchronization contexts and capturing the current context, see [Consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span> <span data-ttu-id="2846e-117">Weitere Informationen finden Sie im Abschnitt [Asynchrone Datenströme](../../whats-new/csharp-8.md#asynchronous-streams) des Artikels [Neues in C# 8.0](../../whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="2846e-117">For more information about asynchronous streams, see the [Asynchronous streams](../../whats-new/csharp-8.md#asynchronous-streams) section of the [What's new in C# 8.0](../../whats-new/csharp-8.md) article.</span></span>

<span data-ttu-id="2846e-118">Sie können die Schleife an jedem Punkt im `foreach`-Anweisungsblock mit der Anweisung [break](break.md) unterbrechen oder mit der Anweisung [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="2846e-118">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="2846e-119">Sie können eine `foreach`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.</span><span class="sxs-lookup"><span data-stu-id="2846e-119">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="2846e-120">Wenn die `foreach`-Anweisung auf `null` angewendet wird, wird <xref:System.NullReferenceException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="2846e-120">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="2846e-121">Falls die Quellsammlung der `foreach`-Anweisung leer ist, wird der Text der `foreach`-Schleife nicht ausgeführt und übersprungen.</span><span class="sxs-lookup"><span data-stu-id="2846e-121">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="type-of-an-iteration-variable"></a><span data-ttu-id="2846e-122">Typ einer Iterationsvariablen</span><span class="sxs-lookup"><span data-stu-id="2846e-122">Type of an iteration variable</span></span>

<span data-ttu-id="2846e-123">Sie können das Schlüsselwort `var` verwenden, damit der Compiler den Typ einer Iterationsvariablen in der Anweisung `foreach` ableiten kann. Dies wird im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2846e-123">You can use the `var` keyword to let the compiler infer the type of an iteration variable in the `foreach` statement, as the following code shows:</span></span>

```csharp
foreach (var item in collection) { }
```

<span data-ttu-id="2846e-124">Sie können auch wie im folgenden Code explizit den Typ einer Iterationsvariablen angeben:</span><span class="sxs-lookup"><span data-stu-id="2846e-124">You can also explicitly specify the type of an iteration variable, as the following code shows:</span></span>

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

<span data-ttu-id="2846e-125">Im obigen Formular muss der Typ `T` eines Sammlungselements implizit oder explizit in Typ `V` einer Iterationsvariablen konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="2846e-125">In the preceding form, type `T` of a collection element must be implicitly or explicitly convertible to type `V` of an iteration variable.</span></span> <span data-ttu-id="2846e-126">Wenn eine explizite Konvertierung von `T` in `V` zur Laufzeit fehlschlägt, löst die Anweisung `foreach` eine <xref:System.InvalidCastException> aus.</span><span class="sxs-lookup"><span data-stu-id="2846e-126">If an explicit conversion from `T` to `V` fails at run time, the `foreach` statement throws an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="2846e-127">Wenn `T` z. B. ein nicht versiegelter Klassentyp ist, kann `V` ein beliebiger Schnittstellentyp sein – sogar der Typ, den `T` nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="2846e-127">For example, if `T` is a non-sealed class type, `V` can be any interface type, even the one that `T` doesn't implement.</span></span> <span data-ttu-id="2846e-128">Zur Laufzeit kann der Typ eines Sammlungselements der Typ sein, der von `T` abgeleitet wird und `V` implementiert.</span><span class="sxs-lookup"><span data-stu-id="2846e-128">At run time, the type of a collection element may be the one that derives from `T` and actually implements `V`.</span></span> <span data-ttu-id="2846e-129">Wenn dies nicht der Fall ist, wird eine <xref:System.InvalidCastException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="2846e-129">If that's not the case, an <xref:System.InvalidCastException> is thrown.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2846e-130">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2846e-130">C# language specification</span></span>

<span data-ttu-id="2846e-131">Weitere Informationen finden Sie im Abschnitt [Die foreach-Anweisung](~/_csharplang/spec/statements.md#the-foreach-statement) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="2846e-131">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2846e-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2846e-132">See also</span></span>

- [<span data-ttu-id="2846e-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2846e-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="2846e-134">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2846e-134">C# keywords</span></span>](index.md)
- [<span data-ttu-id="2846e-135">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="2846e-135">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="2846e-136">for-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2846e-136">for statement</span></span>](for.md)
