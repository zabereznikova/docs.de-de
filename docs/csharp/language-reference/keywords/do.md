---
title: do – C#-Referenz
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: d75dd816278a876fa05d133e5eb189d606300a5c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401926"
---
# <a name="do-c-reference"></a><span data-ttu-id="ed803-102">do (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ed803-102">do (C# Reference)</span></span>

<span data-ttu-id="ed803-103">Die Anweisung `do` führt eine Anweisung oder einen Anweisungsblock aus, während ein angegebener boolescher Ausdruck `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="ed803-103">The `do` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="ed803-104">Da der Ausdruck nach jeder Ausführung der Schleife ausgewertet wird, wird eine `do-while`-Schleife mindestens einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed803-104">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="ed803-105">Dies unterscheidet sich von der [while](while.md)-Schleife, die entweder nie oder mehrmals ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ed803-105">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="ed803-106">Sie können zu jedem Zeitpunkt im Anweisungsblock `do` aus der Schleife ausbrechen, indem Sie die Anweisung [break](break.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed803-106">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="ed803-107">Sie können mithilfe der [continue](continue.md)-Anweisung direkt die Auswertung des `while`-Ausdrucks ausführen.</span><span class="sxs-lookup"><span data-stu-id="ed803-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="ed803-108">Wenn der Ausdruck `true` ergibt, wird die Ausführung bei der ersten Anweisung in der Schleife fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ed803-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="ed803-109">Andernfalls wird die Ausführung mit der ersten Anweisung nach der Schleife ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed803-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="ed803-110">Sie können eine `do-while`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.</span><span class="sxs-lookup"><span data-stu-id="ed803-110">You can also exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="ed803-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed803-111">Example</span></span>

<span data-ttu-id="ed803-112">Im folgenden Beispiel wird die Verwendung der `do`-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ed803-112">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="ed803-113">Klicken Sie auf **Run** (Ausführen), um den Beispielcode auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ed803-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="ed803-114">Danach können Sie Änderungen am Code vornehmen und ihn erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="ed803-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](snippets/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="ed803-115">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ed803-115">C# language specification</span></span>

<span data-ttu-id="ed803-116">Weitere Informationen finden Sie im Abschnitt [Die do-Anweisung](~/_csharplang/spec/statements.md#the-do-statement) der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="ed803-116">For more information, see [The do statement](~/_csharplang/spec/statements.md#the-do-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed803-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed803-117">See also</span></span>

- [<span data-ttu-id="ed803-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ed803-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ed803-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ed803-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ed803-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ed803-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ed803-121">while-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ed803-121">while statement</span></span>](while.md)
