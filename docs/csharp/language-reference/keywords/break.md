---
description: break-Anweisung – C#-Referenz
title: break-Anweisung – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 7fd05889f684f7a2282de8222e1195898dead5b9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134743"
---
# <a name="break-c-reference"></a><span data-ttu-id="b2e04-103">break (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b2e04-103">break (C# Reference)</span></span>

<span data-ttu-id="b2e04-104">Die `break`-Anweisung beendet die Ausführung der nächsten einschließenden Schleife oder [switch](./switch.md)-Anweisung, in der sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b2e04-104">The `break` statement terminates the closest enclosing loop or [switch](./switch.md) statement in which it appears.</span></span> <span data-ttu-id="b2e04-105">Das Steuerelement wird an die Anweisung übergeben, die auf die beendete Anweisung folgt, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b2e04-105">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="b2e04-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2e04-106">Example</span></span>

<span data-ttu-id="b2e04-107">In diesem Beispiel enthält die Bedingungsanweisung einen Indikator, der normalerweise zum Zählen von 1 bis 100 verwendet wird. Allerdings beendet die `break`-Anweisung die Schleife nach 4 Durchgängen.</span><span class="sxs-lookup"><span data-stu-id="b2e04-107">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="b2e04-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2e04-108">Example</span></span>

<span data-ttu-id="b2e04-109">In diesem Beispiel wird die Verwendung von `break` in einer [switch](./switch.md)-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b2e04-109">This example demonstrates the use of `break` in a [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="b2e04-110">Bei Eingabe von `4` sähe die Ausgabe wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b2e04-110">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a><span data-ttu-id="b2e04-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2e04-111">Example</span></span>

<span data-ttu-id="b2e04-112">In diesem Beispiel wird die `break`-Anweisung verwendet, um aus einer inneren geschachtelten Schleife auszubrechen und die Steuerung an die äußere Schleife zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b2e04-112">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span> <span data-ttu-id="b2e04-113">Die Steuerung wird _nur_ auf der nächsthöheren Ebene in den geschachtelten Schleifen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b2e04-113">Control is _only_ returned one level up in the nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="b2e04-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2e04-114">Example</span></span>

<span data-ttu-id="b2e04-115">In diesem Beispiel wird die `break`-Anweisung nur verwendet, um während jeder Iteration der Schleife aus dem aktuellen Branch auszubrechen.</span><span class="sxs-lookup"><span data-stu-id="b2e04-115">In this example, the `break` statement is only used to break out of the current branch during each iteration of the loop.</span></span> <span data-ttu-id="b2e04-116">Die-Schleife selbst ist nicht von den Instanzen von `break` betroffen, die zur geschachtelten [switch](./switch.md)-Anweisung gehören.</span><span class="sxs-lookup"><span data-stu-id="b2e04-116">The loop itself is unaffected by the instances of `break` that belong to the nested [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="b2e04-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b2e04-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b2e04-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2e04-118">See also</span></span>

- [<span data-ttu-id="b2e04-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b2e04-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b2e04-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b2e04-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b2e04-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b2e04-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="b2e04-122">switch</span><span class="sxs-lookup"><span data-stu-id="b2e04-122">switch</span></span>](./switch.md)
