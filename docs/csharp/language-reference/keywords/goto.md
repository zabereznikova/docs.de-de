---
title: goto (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- goto_CSharpKeyword
- goto
dev_langs:
- CSharp
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
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
ms.openlocfilehash: cd298809ab883f425f3bb88239f2951ab98cc03e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="goto-c-reference"></a><span data-ttu-id="143e6-102">goto (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="143e6-102">goto (C# Reference)</span></span>
<span data-ttu-id="143e6-103">Die `goto`-Anweisung überträgt die Programmsteuerung direkt an eine Anweisung mit Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="143e6-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>  
  
 <span data-ttu-id="143e6-104">`goto` wird häufig dazu verwendet, eine bestimmte Parameterbezeichnung oder die Standardbezeichnung in einer `switch`-Anweisung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="143e6-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>  
  
 <span data-ttu-id="143e6-105">Mit der `goto`-Anweisung können Sie auch tief geschachtelte Schleifen verlassen.</span><span class="sxs-lookup"><span data-stu-id="143e6-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>  
  
## <a name="example"></a><span data-ttu-id="143e6-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="143e6-106">Example</span></span>  
 <span data-ttu-id="143e6-107">Im folgenden Beispiel wird die Verwendung von `goto` in einer [switch](../../../csharp/language-reference/keywords/switch.md)-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="143e6-107">The following example demonstrates using `goto` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 <span data-ttu-id="143e6-108">[!code-cs[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="143e6-108">[!code-cs[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="143e6-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="143e6-109">Example</span></span>  
 <span data-ttu-id="143e6-110">Im folgenden Beispiel wird die Verwendung von `goto` zum Verlassen geschachtelter Schleifen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="143e6-110">The following example demonstrates using `goto` to break out from nested loops.</span></span>  
  
 <span data-ttu-id="143e6-111">[!code-cs[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="143e6-111">[!code-cs[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="143e6-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="143e6-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="143e6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="143e6-113">See Also</span></span>  
 <span data-ttu-id="143e6-114">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="143e6-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="143e6-115">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="143e6-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="143e6-116">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="143e6-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="143e6-117">[goto-Anweisung](/cpp/cpp/goto-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="143e6-117">[goto Statement](/cpp/cpp/goto-statement-cpp) </span></span>  
 [<span data-ttu-id="143e6-118">Sprunganweisungen</span><span class="sxs-lookup"><span data-stu-id="143e6-118">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)

