---
title: break (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 0cfe722bfefc1befd8a453f4454b05b3e4a0da76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="break-c-reference"></a><span data-ttu-id="802a1-102">break (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="802a1-102">break (C# Reference)</span></span>
<span data-ttu-id="802a1-103">Die `break`-Anweisung beendet die Ausführung der nächsten einschließenden Schleife oder [switch](../../../csharp/language-reference/keywords/switch.md)-Anweisung, in der sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="802a1-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="802a1-104">Das Steuerelement wird an die Anweisung übergeben, die auf die beendete Anweisung folgt, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="802a1-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>  
  
## <a name="example"></a><span data-ttu-id="802a1-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="802a1-105">Example</span></span>  
 <span data-ttu-id="802a1-106">In diesem Beispiel enthält die Bedingungsanweisung einen Indikator, der normalerweise zum Zählen von 1 bis 100 verwendet wird. Allerdings beendet die `break`-Anweisung die Schleife nach 4 Durchgängen.</span><span class="sxs-lookup"><span data-stu-id="802a1-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="802a1-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="802a1-107">Example</span></span>  
 <span data-ttu-id="802a1-108">In diesem Beispiel wird die `break`-Anweisung verwendet, um aus einer inneren geschachtelten Schleife auszubrechen und die Steuerung an die äußere Schleife zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="802a1-108">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="802a1-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="802a1-109">Example</span></span>  
 <span data-ttu-id="802a1-110">In diesem Beispiel wird die Verwendung von `break` in einer [switch](../../../csharp/language-reference/keywords/switch.md)-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="802a1-110">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_3.cs)]  
  
 <span data-ttu-id="802a1-111">Bei Eingabe von `4` sähe die Ausgabe wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="802a1-111">If you entered `4`, the output would be:</span></span>  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="802a1-112">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="802a1-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="802a1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="802a1-113">See Also</span></span>  
 [<span data-ttu-id="802a1-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="802a1-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="802a1-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="802a1-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="802a1-116">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="802a1-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="802a1-117">switch</span><span class="sxs-lookup"><span data-stu-id="802a1-117">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)  
 [<span data-ttu-id="802a1-118">Sprunganweisungen</span><span class="sxs-lookup"><span data-stu-id="802a1-118">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)  
 [<span data-ttu-id="802a1-119">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="802a1-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
