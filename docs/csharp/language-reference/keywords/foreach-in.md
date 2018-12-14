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
ms.openlocfilehash: 417a8cefbc9bc7544ae1156992e6e6c549fb828f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128621"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="fabe8-102">foreach, in (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fabe8-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="fabe8-103">Die Anweisung `foreach` führt eine Anweisung oder einen Block von Anweisungen für jedes Element in einer Instanz des Typs aus, der die Schnittstelle <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert.</span><span class="sxs-lookup"><span data-stu-id="fabe8-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="fabe8-104">Die Anweisung `foreach` ist nicht auf diese Typen beschränkt und kann auf eine Instanz eines beliebigen Typs angewendet werden, der die folgenden Bedingungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="fabe8-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="fabe8-105">Er weist die öffentliche parameterlose Methode `GetEnumerator` auf, deren Rückgabetyp entweder Klasse, Struktur oder Schnittstellentyp ist.</span><span class="sxs-lookup"><span data-stu-id="fabe8-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="fabe8-106">Der Rückgabetyp der Methode `GetEnumerator` weist die öffentliche Eigenschaft `Current` und die öffentliche parameterlose Methode `MoveNext` auf, deren Rückgabetyp <xref:System.Boolean> ist.</span><span class="sxs-lookup"><span data-stu-id="fabe8-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="fabe8-107">Ab C# 7.3 können Sie die Iterationsvariable mit den Modifizierern `ref` oder `ref readonly` deklarieren, wenn die `Current`-Eigenschaft des Enumerators einen [Verweisrückgabewert](ref.md#reference-return-values) (`ref T`, wobei `T` dem Typ des Auflistungselements entspricht) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fabe8-107">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="fabe8-108">Sie können die Schleife an jedem Punkt im `foreach`-Anweisungsblock mit der Anweisung [break](break.md) unterbrechen oder mit der Anweisung [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="fabe8-108">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="fabe8-109">Sie können eine `foreach`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.</span><span class="sxs-lookup"><span data-stu-id="fabe8-109">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="fabe8-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fabe8-110">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="fabe8-111">Das folgende Beispiel zeigt die Syntax der Anweisung `foreach` mit einer Instanz des Typs <xref:System.Collections.Generic.List%601>, der die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> implementiert:</span><span class="sxs-lookup"><span data-stu-id="fabe8-111">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="fabe8-112">Im nächste Beispiel wird die Anweisung `foreach` mit einer Instanz des Typs <xref:System.Span%601?displayProperty=nameWithType> verwendet, der keine Schnittstellen implementiert:</span><span class="sxs-lookup"><span data-stu-id="fabe8-112">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="fabe8-113">Im folgenden Beispiel wird eine `ref`-Iterationsvariable verwendet, um die Werte der Elemente in einem stackalloc-Array festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fabe8-113">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="fabe8-114">Die Version `ref readonly` durchläuft die Auflistung, um alle Werte auszugeben.</span><span class="sxs-lookup"><span data-stu-id="fabe8-114">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="fabe8-115">Die `readonly`-Deklaration verwendet eine implizite lokale Variablendeklaration.</span><span class="sxs-lookup"><span data-stu-id="fabe8-115">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="fabe8-116">Implizite Variablendeklarationen können wie explizit typisierte Variablendeklarationen mit `ref`- oder `ref readonly`-Deklarationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fabe8-116">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a><span data-ttu-id="fabe8-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="fabe8-117">C# language specification</span></span>

<span data-ttu-id="fabe8-118">Weitere Informationen finden Sie im Abschnitt [Die foreach-Anweisung](~/_csharplang/spec/statements.md#the-foreach-statement) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="fabe8-118">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fabe8-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fabe8-119">See also</span></span>

- [<span data-ttu-id="fabe8-120">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="fabe8-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fabe8-121">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fabe8-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fabe8-122">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fabe8-122">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fabe8-123">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="fabe8-123">Iteration Statements</span></span>](iteration-statements.md)
- [<span data-ttu-id="fabe8-124">Verwenden von foreach mit Arrays</span><span class="sxs-lookup"><span data-stu-id="fabe8-124">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="fabe8-125">for-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fabe8-125">for statement</span></span>](for.md)
