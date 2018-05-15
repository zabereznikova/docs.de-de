---
title: while (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 23c5ca3bb7dc401a894a6c3918fbaec9a9306153
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="while-c-reference"></a><span data-ttu-id="0d2c5-102">while (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0d2c5-102">while (C# Reference)</span></span>
<span data-ttu-id="0d2c5-103">Die `while`-Anweisung führt eine Anweisung oder einen Anweisungsblock aus, bis ein bestimmter Ausdruck `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="0d2c5-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d2c5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d2c5-104">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="0d2c5-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d2c5-105">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="0d2c5-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d2c5-106">Example</span></span>  
 <span data-ttu-id="0d2c5-107">Da der `while`-Ausdruck vor jeder Ausführung der Schleife getestet wird, wird eine `while`-Schleife entweder nie oder mehrmals ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d2c5-107">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="0d2c5-108">Dies unterscheidet sich von der [do](../../../csharp/language-reference/keywords/do.md)-Schleife, die ein oder mehrmals ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0d2c5-108">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="0d2c5-109">Eine `while`-Schleife kann beendet werden, wenn eine [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) oder [throw](../../../csharp/language-reference/keywords/throw.md)-Anweisung die Steuerung außerhalb der Schleife überträgt.</span><span class="sxs-lookup"><span data-stu-id="0d2c5-109">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="0d2c5-110">Verwenden Sie die [continue](../../../csharp/language-reference/keywords/continue.md)-Anweisung, um die Steuerung an die nächste Iteration zu übertragen, ohne die Schleife zu beenden.</span><span class="sxs-lookup"><span data-stu-id="0d2c5-110">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="0d2c5-111">Beachten Sie den Unterschied in der Ausgabe in den drei vorherigen Beispielen. Der Unterschied ist abhängig davon, wo `int n` inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="0d2c5-111">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="0d2c5-112">Im Beispiel unten wird keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="0d2c5-112">In the example below no output is generated.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0d2c5-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="0d2c5-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d2c5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d2c5-114">See Also</span></span>  
 [<span data-ttu-id="0d2c5-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0d2c5-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0d2c5-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0d2c5-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0d2c5-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0d2c5-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0d2c5-118">while-Anweisung (C++)</span><span class="sxs-lookup"><span data-stu-id="0d2c5-118">while Statement (C++)</span></span>](/cpp/cpp/while-statement-cpp)  
 [<span data-ttu-id="0d2c5-119">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="0d2c5-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
