---
description: continue-Anweisung – C#-Referenz
title: continue-Anweisung – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 76578b0ad7e2b969609fbf50df1f9ab7de6e5097
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128438"
---
# <a name="continue-c-reference"></a><span data-ttu-id="9f05f-103">continue (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9f05f-103">continue (C# Reference)</span></span>

<span data-ttu-id="9f05f-104">Die `continue`-Anweisung übergibt die Steuerung an die nächste Iteration der einschließenden [while](./while.md), [do](./do.md), [for](./for.md) oder [foreach](./foreach-in.md)-Anweisung, in der sie angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9f05f-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="9f05f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f05f-105">Example</span></span>

<span data-ttu-id="9f05f-106">In diesem Beispiel wird ein Zähler initialisiert, um von 1 bis 10 zu zählen.</span><span class="sxs-lookup"><span data-stu-id="9f05f-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="9f05f-107">Indem die `continue`-Anweisung in Verbindung mit dem `(i < 9)`-Ausdruck verwendet wird, werden die Anweisungen zwischen `continue` und dem Ende des `for`-Rumpfs übersprungen.</span><span class="sxs-lookup"><span data-stu-id="9f05f-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="9f05f-108">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="9f05f-108">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9f05f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f05f-109">See also</span></span>

- [<span data-ttu-id="9f05f-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9f05f-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9f05f-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9f05f-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9f05f-112">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="9f05f-112">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="9f05f-113">break-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9f05f-113">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
