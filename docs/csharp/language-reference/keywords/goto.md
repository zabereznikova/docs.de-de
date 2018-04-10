---
title: goto (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aa12a7547cfcd4a2076b5b0a308139f8a823f482
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="goto-c-reference"></a><span data-ttu-id="28342-102">goto (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="28342-102">goto (C# Reference)</span></span>
<span data-ttu-id="28342-103">Die `goto`-Anweisung überträgt die Programmsteuerung direkt an eine Anweisung mit Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="28342-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>  
  
 <span data-ttu-id="28342-104">`goto` wird häufig dazu verwendet, eine bestimmte Parameterbezeichnung oder die Standardbezeichnung in einer `switch`-Anweisung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="28342-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>  
  
 <span data-ttu-id="28342-105">Mit der `goto`-Anweisung können Sie auch tief geschachtelte Schleifen verlassen.</span><span class="sxs-lookup"><span data-stu-id="28342-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28342-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28342-106">Example</span></span>  
 <span data-ttu-id="28342-107">Im folgenden Beispiel wird die Verwendung von `goto` in einer [switch](../../../csharp/language-reference/keywords/switch.md)-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="28342-107">The following example demonstrates using `goto` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="28342-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28342-108">Example</span></span>  
 <span data-ttu-id="28342-109">Im folgenden Beispiel wird die Verwendung von `goto` zum Verlassen geschachtelter Schleifen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="28342-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="28342-110">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="28342-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="28342-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28342-111">See Also</span></span>  
 [<span data-ttu-id="28342-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="28342-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="28342-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="28342-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="28342-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="28342-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="28342-115">Goto-Anweisung</span><span class="sxs-lookup"><span data-stu-id="28342-115">goto Statement</span></span>](/cpp/cpp/goto-statement-cpp)  
 [<span data-ttu-id="28342-116">Sprunganweisungen</span><span class="sxs-lookup"><span data-stu-id="28342-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
