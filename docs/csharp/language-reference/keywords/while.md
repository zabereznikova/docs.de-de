---
title: while (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
dev_langs:
- CSharp
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
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
ms.openlocfilehash: ed531c83dba02b38576bf8354b1ff92f075048bc
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="while-c-reference"></a><span data-ttu-id="d5425-102">while (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d5425-102">while (C# Reference)</span></span>
<span data-ttu-id="d5425-103">Die `while`-Anweisung führt eine Anweisung oder einen Anweisungsblock aus, bis ein bestimmter Ausdruck `false` ergibt.</span><span class="sxs-lookup"><span data-stu-id="d5425-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5425-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5425-104">Example</span></span>  
 <span data-ttu-id="d5425-105">[!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d5425-105">[!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5425-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5425-106">Example</span></span>  
 <span data-ttu-id="d5425-107">[!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d5425-107">[!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5425-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5425-108">Example</span></span>  
 <span data-ttu-id="d5425-109">Da der `while`-Ausdruck vor jeder Ausführung der Schleife getestet wird, wird eine `while`-Schleife entweder nie oder mehrmals ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d5425-109">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="d5425-110">Dies unterscheidet sich von der [do](../../../csharp/language-reference/keywords/do.md)-Schleife, die ein oder mehrmals ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d5425-110">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="d5425-111">Eine `while`-Schleife kann beendet werden, wenn eine [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) oder [throw](../../../csharp/language-reference/keywords/throw.md)-Anweisung die Steuerung außerhalb der Schleife überträgt.</span><span class="sxs-lookup"><span data-stu-id="d5425-111">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="d5425-112">Verwenden Sie die [continue](../../../csharp/language-reference/keywords/continue.md)-Anweisung, um die Steuerung an die nächste Iteration zu übertragen, ohne die Schleife zu beenden.</span><span class="sxs-lookup"><span data-stu-id="d5425-112">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="d5425-113">Beachten Sie den Unterschied in der Ausgabe in den drei vorherigen Beispielen. Der Unterschied ist abhängig davon, wo `int n` inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="d5425-113">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="d5425-114">Im Beispiel unten wird keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="d5425-114">In the example below no output is generated.</span></span>  
  
 <span data-ttu-id="d5425-115">[!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d5425-115">[!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d5425-116">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d5425-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5425-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5425-117">See Also</span></span>  
 <span data-ttu-id="d5425-118">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5425-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d5425-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5425-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d5425-120">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5425-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d5425-121">[while-Anweisung (C++)](/cpp/cpp/while-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="d5425-121">[while Statement (C++)](/cpp/cpp/while-statement-cpp) </span></span>  
 [<span data-ttu-id="d5425-122">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="d5425-122">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

