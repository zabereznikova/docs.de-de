---
title: while – C#-Referenz
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: eb9aa2ea8d6b1c96e0be7d377f7c047194b598de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712792"
---
# <a name="while-c-reference"></a><span data-ttu-id="e7ae3-102">while (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e7ae3-102">while (C# Reference)</span></span>

<span data-ttu-id="e7ae3-103">Die Anweisung `while` führt eine Anweisung oder einen Anweisungsblock aus, während ein angegebener boolescher Ausdruck `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="e7ae3-103">The `while` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="e7ae3-104">Da der Ausdruck vor jeder Ausführung der Schleife ausgewertet wird, wird eine `while`-Schleife entweder nie oder mehrmals ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e7ae3-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="e7ae3-105">Dies unterscheidet sich von der [do](do.md)-Schleife, die ein oder mehrmals ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7ae3-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="e7ae3-106">Sie können zu jedem Zeitpunkt im Anweisungsblock `while` aus der Schleife ausbrechen, indem Sie die Anweisung [break](break.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7ae3-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="e7ae3-107">Sie können mithilfe der [continue](continue.md)-Anweisung direkt die Auswertung des `while`-Ausdrucks ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7ae3-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="e7ae3-108">Wenn der Ausdruck `true` ergibt, wird die Ausführung bei der ersten Anweisung in der Schleife fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e7ae3-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="e7ae3-109">Andernfalls wird die Ausführung mit der ersten Anweisung nach der Schleife ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e7ae3-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="e7ae3-110">Sie können eine `while`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.</span><span class="sxs-lookup"><span data-stu-id="e7ae3-110">You also can exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="e7ae3-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7ae3-111">Example</span></span>

<span data-ttu-id="e7ae3-112">Im folgenden Beispiel wird die Verwendung der `while`-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e7ae3-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="e7ae3-113">Klicken Sie auf **Run** (Ausführen), um den Beispielcode auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e7ae3-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="e7ae3-114">Danach können Sie Änderungen am Code vornehmen und ihn erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7ae3-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="e7ae3-115">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e7ae3-115">C# language specification</span></span>

<span data-ttu-id="e7ae3-116">Weitere Informationen finden Sie im Abschnitt [Die while-Anweisung](~/_csharplang/spec/statements.md#the-while-statement) der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="e7ae3-116">For more information, see [The while statement](~/_csharplang/spec/statements.md#the-while-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7ae3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7ae3-117">See also</span></span>

- [<span data-ttu-id="e7ae3-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e7ae3-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e7ae3-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e7ae3-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e7ae3-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e7ae3-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e7ae3-121">do-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e7ae3-121">do statement</span></span>](do.md)
