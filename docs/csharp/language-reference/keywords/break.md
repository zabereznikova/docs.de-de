---
title: break-Anweisung (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 9dc71cce3cc0ca4035df483d2b3a3ab9a3bab9c5
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46695827"
---
# <a name="break-c-reference"></a><span data-ttu-id="53dc3-102">break (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="53dc3-102">break (C# Reference)</span></span>

<span data-ttu-id="53dc3-103">Die `break`-Anweisung beendet die Ausführung der nächsten einschließenden Schleife oder [switch](../../../csharp/language-reference/keywords/switch.md)-Anweisung, in der sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="53dc3-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="53dc3-104">Das Steuerelement wird an die Anweisung übergeben, die auf die beendete Anweisung folgt, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="53dc3-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="53dc3-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53dc3-105">Example</span></span>

<span data-ttu-id="53dc3-106">In diesem Beispiel enthält die Bedingungsanweisung einen Indikator, der normalerweise zum Zählen von 1 bis 100 verwendet wird. Allerdings beendet die `break`-Anweisung die Schleife nach 4 Durchgängen.</span><span class="sxs-lookup"><span data-stu-id="53dc3-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="53dc3-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53dc3-107">Example</span></span>

<span data-ttu-id="53dc3-108">In diesem Beispiel wird die `break`-Anweisung verwendet, um aus einer inneren geschachtelten Schleife auszubrechen und die Steuerung an die äußere Schleife zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="53dc3-108">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="53dc3-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53dc3-109">Example</span></span>

<span data-ttu-id="53dc3-110">In diesem Beispiel wird die Verwendung von `break` in einer [switch](../../../csharp/language-reference/keywords/switch.md)-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="53dc3-110">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="53dc3-111">Bei Eingabe von `4` sähe die Ausgabe wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="53dc3-111">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a><span data-ttu-id="53dc3-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="53dc3-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="53dc3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53dc3-113">See Also</span></span>

- [<span data-ttu-id="53dc3-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="53dc3-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="53dc3-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="53dc3-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="53dc3-116">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="53dc3-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="53dc3-117">switch</span><span class="sxs-lookup"><span data-stu-id="53dc3-117">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)  
- [<span data-ttu-id="53dc3-118">Sprunganweisungen</span><span class="sxs-lookup"><span data-stu-id="53dc3-118">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)  
- [<span data-ttu-id="53dc3-119">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="53dc3-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
