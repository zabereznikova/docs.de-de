---
title: do (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 5599f079e29fd094c4d6a6a75afba89fb562a166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="do-c-reference"></a><span data-ttu-id="f01b1-102">do (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f01b1-102">do (C# Reference)</span></span>
<span data-ttu-id="f01b1-103">Die `do`-Anweisung führt eine Anweisung oder einen Block wiederholt aus, bis ein bestimmter Ausdruck `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="f01b1-103">The `do` statement executes a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="f01b1-104">Der Text der Schleife muss in geschweifte Klammern eingeschlossen werden, `{}`, wenn es nicht aus einer einzelnen Anweisung besteht.</span><span class="sxs-lookup"><span data-stu-id="f01b1-104">The body of the loop must be enclosed in braces, `{}`, unless it consists of a single statement.</span></span> <span data-ttu-id="f01b1-105">In diesem Fall sind die Klammern optional.</span><span class="sxs-lookup"><span data-stu-id="f01b1-105">In that case, the braces are optional.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f01b1-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f01b1-106">Example</span></span>  
 <span data-ttu-id="f01b1-107">Im folgenden Beispiel führen die `do-while`-Schleifenanweisungen solange aus, bis die Variable `x` kleiner als 5 ist.</span><span class="sxs-lookup"><span data-stu-id="f01b1-107">In the following example, the `do-while` loop statements execute as long as the variable `x` is less than 5.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 <span data-ttu-id="f01b1-108">Im Gegensatz zur [while](../../../csharp/language-reference/keywords/while.md)-Anweisung wird eine `do-while`-Schleife einmal ausgeführt, bevor der bedingte Ausdruck ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="f01b1-108">Unlike the [while](../../../csharp/language-reference/keywords/while.md) statement, a `do-while` loop is executed one time before the conditional expression is evaluated.</span></span>  
  
 <span data-ttu-id="f01b1-109">An jedem Punkt im `do-while`-Block können Sie mithilfe der [break](../../../csharp/language-reference/keywords/break.md)-Anweisung aus der Schleife ausbrechen.</span><span class="sxs-lookup"><span data-stu-id="f01b1-109">At any point in the `do-while` block, you can break out of the loop using the [break](../../../csharp/language-reference/keywords/break.md) statement.</span></span> <span data-ttu-id="f01b1-110">Sie können mithilfe der [continue](../../../csharp/language-reference/keywords/continue.md)-Anweisung direkt die `while`-Ausdrucksauswertung der Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="f01b1-110">You can step directly to the `while` expression evaluation statement by using the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="f01b1-111">Wenn der `while`-Ausdruck TRUE ergibt, wird die Ausführung bei der ersten Anweisung in der Schleife fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f01b1-111">If the `while` expression evaluates to true, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="f01b1-112">Wenn der Ausdruck FALSE ergibt, wird die Ausführung bei der ersten Anweisung nach der `do-while`-Schleife fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f01b1-112">If the expression evaluates to false, execution continues at the first statement after the `do-while` loop.</span></span>  
  
 <span data-ttu-id="f01b1-113">Eine `do-while`-Schleife kann durch die Anweisungen [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) oder [throw](../../../csharp/language-reference/keywords/throw.md) beendet werden.</span><span class="sxs-lookup"><span data-stu-id="f01b1-113">A `do-while` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f01b1-114">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f01b1-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f01b1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f01b1-115">See Also</span></span>  
 [<span data-ttu-id="f01b1-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f01b1-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f01b1-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f01b1-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f01b1-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f01b1-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f01b1-119">do-while-Anweisung (C++)</span><span class="sxs-lookup"><span data-stu-id="f01b1-119">do-while Statement (C++)</span></span>](/cpp/cpp/do-while-statement-cpp)  
 [<span data-ttu-id="f01b1-120">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="f01b1-120">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
