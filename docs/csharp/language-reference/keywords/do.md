---
title: do (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
dev_langs:
- CSharp
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 58a9361c440bc1b17c5ab929ff7b45ba71ce50a4
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="do-c-reference"></a><span data-ttu-id="ea2e2-102">do (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ea2e2-102">do (C# Reference)</span></span>
<span data-ttu-id="ea2e2-103">Die `do`-Anweisung führt eine Anweisung oder einen Block wiederholt aus, bis ein bestimmter Ausdruck `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="ea2e2-103">The `do` statement executes a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="ea2e2-104">Der Text der Schleife muss in geschweifte Klammern eingeschlossen werden, `{}`, wenn es nicht aus einer einzelnen Anweisung besteht.</span><span class="sxs-lookup"><span data-stu-id="ea2e2-104">The body of the loop must be enclosed in braces, `{}`, unless it consists of a single statement.</span></span> <span data-ttu-id="ea2e2-105">In diesem Fall sind die Klammern optional.</span><span class="sxs-lookup"><span data-stu-id="ea2e2-105">In that case, the braces are optional.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea2e2-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea2e2-106">Example</span></span>  
 <span data-ttu-id="ea2e2-107">Im folgenden Beispiel führen die `do-while`-Schleifenanweisungen solange aus, bis die Variable `x` kleiner als 5 ist.</span><span class="sxs-lookup"><span data-stu-id="ea2e2-107">In the following example, the `do-while` loop statements execute as long as the variable `x` is less than 5.</span></span>  
  
 <span data-ttu-id="ea2e2-108">[!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ea2e2-108">[!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]</span></span>  
  
 <span data-ttu-id="ea2e2-109">Im Gegensatz zur [while](../../../csharp/language-reference/keywords/while.md)-Anweisung wird eine `do-while`-Schleife einmal ausgeführt, bevor der bedingte Ausdruck ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="ea2e2-109">Unlike the [while](../../../csharp/language-reference/keywords/while.md) statement, a `do-while` loop is executed one time before the conditional expression is evaluated.</span></span>  
  
 <span data-ttu-id="ea2e2-110">An jedem Punkt im `do-while`-Block können Sie mithilfe der [break](../../../csharp/language-reference/keywords/break.md)-Anweisung aus der Schleife ausbrechen.</span><span class="sxs-lookup"><span data-stu-id="ea2e2-110">At any point in the `do-while` block, you can break out of the loop using the [break](../../../csharp/language-reference/keywords/break.md) statement.</span></span> <span data-ttu-id="ea2e2-111">Sie können mithilfe der [continue](../../../csharp/language-reference/keywords/continue.md)-Anweisung direkt die `while`-Ausdrucksauswertung der Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="ea2e2-111">You can step directly to the `while` expression evaluation statement by using the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="ea2e2-112">Wenn der `while`-Ausdruck TRUE ergibt, wird die Ausführung bei der ersten Anweisung in der Schleife fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ea2e2-112">If the `while` expression evaluates to true, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="ea2e2-113">Wenn der Ausdruck FALSE ergibt, wird die Ausführung bei der ersten Anweisung nach der `do-while`-Schleife fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ea2e2-113">If the expression evaluates to false, execution continues at the first statement after the `do-while` loop.</span></span>  
  
 <span data-ttu-id="ea2e2-114">Eine `do-while`-Schleife kann durch die Anweisungen [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) oder [throw](../../../csharp/language-reference/keywords/throw.md) beendet werden.</span><span class="sxs-lookup"><span data-stu-id="ea2e2-114">A `do-while` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ea2e2-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ea2e2-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ea2e2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea2e2-116">See Also</span></span>  
 <span data-ttu-id="ea2e2-117">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ea2e2-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ea2e2-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ea2e2-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ea2e2-119">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="ea2e2-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="ea2e2-120">[do-while-Anweisung (C++)](/cpp/cpp/do-while-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="ea2e2-120">[do-while Statement (C++)](/cpp/cpp/do-while-statement-cpp) </span></span>  
 [<span data-ttu-id="ea2e2-121">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="ea2e2-121">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

