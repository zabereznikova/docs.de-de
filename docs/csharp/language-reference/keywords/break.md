---
title: break-Anweisung – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 77d18d12cd0fabb26906a5b58dc3939da6214a29
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602247"
---
# <a name="break-c-reference"></a><span data-ttu-id="5c12d-102">break (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5c12d-102">break (C# Reference)</span></span>

<span data-ttu-id="5c12d-103">Die `break`-Anweisung beendet die Ausführung der nächsten einschließenden Schleife oder [switch](./switch.md)-Anweisung, in der sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5c12d-103">The `break` statement terminates the closest enclosing loop or [switch](./switch.md) statement in which it appears.</span></span> <span data-ttu-id="5c12d-104">Das Steuerelement wird an die Anweisung übergeben, die auf die beendete Anweisung folgt, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5c12d-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="5c12d-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c12d-105">Example</span></span>

<span data-ttu-id="5c12d-106">In diesem Beispiel enthält die Bedingungsanweisung einen Indikator, der normalerweise zum Zählen von 1 bis 100 verwendet wird. Allerdings beendet die `break`-Anweisung die Schleife nach 4 Durchgängen.</span><span class="sxs-lookup"><span data-stu-id="5c12d-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="5c12d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c12d-107">Example</span></span>

<span data-ttu-id="5c12d-108">In diesem Beispiel wird die `break`-Anweisung verwendet, um aus einer inneren geschachtelten Schleife auszubrechen und die Steuerung an die äußere Schleife zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="5c12d-108">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="5c12d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c12d-109">Example</span></span>

<span data-ttu-id="5c12d-110">In diesem Beispiel wird die Verwendung von `break` in einer [switch](./switch.md)-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5c12d-110">This example demonstrates the use of `break` in a [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="5c12d-111">Bei Eingabe von `4` sähe die Ausgabe wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5c12d-111">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a><span data-ttu-id="5c12d-112">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="5c12d-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5c12d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c12d-113">See also</span></span>

- [<span data-ttu-id="5c12d-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5c12d-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5c12d-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5c12d-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5c12d-116">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5c12d-116">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="5c12d-117">switch</span><span class="sxs-lookup"><span data-stu-id="5c12d-117">switch</span></span>](./switch.md)
