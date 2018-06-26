---
title: do (C#-Referenz)
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: b918b378623a239803fb4e0a65fcf82fd677b21f
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34566084"
---
# <a name="do-c-reference"></a><span data-ttu-id="30d80-102">do (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="30d80-102">do (C# Reference)</span></span>

<span data-ttu-id="30d80-103">Die Anweisung `do` führt eine Anweisung oder einen Anweisungsblock aus, während ein angegebener boolescher Ausdruck `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="30d80-103">The `do` statement executes a statement or a block of statements while a specified boolean expression evaluates to `true`.</span></span> <span data-ttu-id="30d80-104">Da der Ausdruck nach jeder Ausführung der Schleife ausgewertet wird, wird eine `do-while`-Schleife mindestens einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="30d80-104">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="30d80-105">Dies unterscheidet sich von der [while](while.md)-Schleife, die entweder nie oder mehrmals ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="30d80-105">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="30d80-106">Sie können zu jedem Zeitpunkt im Anweisungsblock `do` aus der Schleife ausbrechen, indem Sie die Anweisung [break](break.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="30d80-106">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="30d80-107">Sie können mithilfe der [continue](continue.md)-Anweisung direkt die Auswertung des `while`-Ausdrucks ausführen.</span><span class="sxs-lookup"><span data-stu-id="30d80-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="30d80-108">Wenn der Ausdruck `true` ergibt, wird die Ausführung bei der ersten Anweisung in der Schleife fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="30d80-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="30d80-109">Andernfalls wird die Ausführung mit der ersten Anweisung nach der Schleife ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="30d80-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="30d80-110">Sie können eine `do-while`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.</span><span class="sxs-lookup"><span data-stu-id="30d80-110">You also can exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="30d80-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30d80-111">Example</span></span>

<span data-ttu-id="30d80-112">Im folgenden Beispiel wird die Verwendung der `do`-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="30d80-112">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="30d80-113">Klicken Sie auf **Run** (Ausführen), um den Beispielcode auszuführen.</span><span class="sxs-lookup"><span data-stu-id="30d80-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="30d80-114">Danach können Sie Änderungen am Code vornehmen und ihn erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="30d80-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="30d80-115">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="30d80-115">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="30d80-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30d80-116">See also</span></span>

 [<span data-ttu-id="30d80-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="30d80-117">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="30d80-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="30d80-118">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="30d80-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="30d80-119">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="30d80-120">do-while-Anweisung (C++)</span><span class="sxs-lookup"><span data-stu-id="30d80-120">do-while Statement (C++)</span></span>](/cpp/cpp/do-while-statement-cpp)  
 [<span data-ttu-id="30d80-121">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="30d80-121">Iteration Statements</span></span>](iteration-statements.md)  
 [<span data-ttu-id="30d80-122">while-Anweisung</span><span class="sxs-lookup"><span data-stu-id="30d80-122">while statement</span></span>](while.md)  
