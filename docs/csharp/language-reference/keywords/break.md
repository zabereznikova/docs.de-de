---
title: break (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- break
- break_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
caps.latest.revision: 21
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
ms.openlocfilehash: 73f6b6a37513b3aed796d811672fa43fa9e1c0b1
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="break-c-reference"></a><span data-ttu-id="284bb-102">break (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="284bb-102">break (C# Reference)</span></span>
<span data-ttu-id="284bb-103">Die `break`-Anweisung beendet die Ausführung der nächsten einschließenden Schleife oder [switch](../../../csharp/language-reference/keywords/switch.md)-Anweisung, in der sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="284bb-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="284bb-104">Das Steuerelement wird an die Anweisung übergeben, die auf die beendete Anweisung folgt, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="284bb-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>  
  
## <a name="example"></a><span data-ttu-id="284bb-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="284bb-105">Example</span></span>  
 <span data-ttu-id="284bb-106">In diesem Beispiel enthält die Bedingungsanweisung einen Indikator, der normalerweise zum Zählen von 1 bis 100 verwendet wird. Allerdings beendet die `break`-Anweisung die Schleife nach 4 Durchgängen.</span><span class="sxs-lookup"><span data-stu-id="284bb-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>  
  
 <span data-ttu-id="284bb-107">[!code-cs[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="284bb-107">[!code-cs[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="284bb-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="284bb-108">Example</span></span>  
 <span data-ttu-id="284bb-109">In diesem Beispiel wird die `break`-Anweisung verwendet, um aus einer inneren geschachtelten Schleife auszubrechen und die Steuerung an die äußere Schleife zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="284bb-109">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>  
  
 <span data-ttu-id="284bb-110">[!code-cs[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="284bb-110">[!code-cs[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="284bb-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="284bb-111">Example</span></span>  
 <span data-ttu-id="284bb-112">In diesem Beispiel wird die Verwendung von `break` in einer [switch](../../../csharp/language-reference/keywords/switch.md)-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="284bb-112">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 <span data-ttu-id="284bb-113">[!code-cs[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="284bb-113">[!code-cs[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_3.cs)]</span></span>  
  
 <span data-ttu-id="284bb-114">Bei Eingabe von `4` sähe die Ausgabe wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="284bb-114">If you entered `4`, the output would be:</span></span>  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="284bb-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="284bb-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="284bb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="284bb-116">See Also</span></span>  
 <span data-ttu-id="284bb-117">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="284bb-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="284bb-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="284bb-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="284bb-119">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="284bb-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="284bb-120">[switch](../../../csharp/language-reference/keywords/switch.md) </span><span class="sxs-lookup"><span data-stu-id="284bb-120">[switch](../../../csharp/language-reference/keywords/switch.md) </span></span>  
 <span data-ttu-id="284bb-121">[Sprunganweisungen](../../../csharp/language-reference/keywords/jump-statements.md) </span><span class="sxs-lookup"><span data-stu-id="284bb-121">[Jump Statements](../../../csharp/language-reference/keywords/jump-statements.md) </span></span>  
 [<span data-ttu-id="284bb-122">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="284bb-122">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

