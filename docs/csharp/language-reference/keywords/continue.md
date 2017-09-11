---
title: continue (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- continue_CSharpKeyword
- continue
dev_langs:
- CSharp
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4a0dcedb32b153c31ec5ed799f66062463307db9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="continue-c-reference"></a><span data-ttu-id="e62eb-102">continue (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e62eb-102">continue (C# Reference)</span></span>
<span data-ttu-id="e62eb-103">Die `continue`-Anweisung übergibt die Steuerung an die nächste Iteration der einschließenden [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) oder [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Anweisung, in der sie angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e62eb-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e62eb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e62eb-104">Example</span></span>  
 <span data-ttu-id="e62eb-105">In diesem Beispiel wird ein Zähler initialisiert, um von 1 bis 10 zu zählen.</span><span class="sxs-lookup"><span data-stu-id="e62eb-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="e62eb-106">Indem die `continue`-Anweisung in Verbindung mit dem `(i < 9)`-Ausdruck verwendet wird, werden die Anweisungen zwischen `continue` und dem Ende des `for`-Rumpfs übersprungen.</span><span class="sxs-lookup"><span data-stu-id="e62eb-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>  
  
 <span data-ttu-id="e62eb-107">[!code-cs[csrefKeywordsJump#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/continue_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e62eb-107">[!code-cs[csrefKeywordsJump#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/continue_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e62eb-108">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="e62eb-108">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e62eb-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e62eb-109">See Also</span></span>  
 <span data-ttu-id="e62eb-110">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e62eb-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e62eb-111">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e62eb-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e62eb-112">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e62eb-112">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e62eb-113">[break-Anweisung](/cpp/cpp/break-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="e62eb-113">[break Statement](/cpp/cpp/break-statement-cpp) </span></span>  
 [<span data-ttu-id="e62eb-114">Sprunganweisungen</span><span class="sxs-lookup"><span data-stu-id="e62eb-114">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)

