---
title: continue-Anweisung – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 0b3baf6eb4843ff67a3d76af06ca86ca9ec2db03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690591"
---
# <a name="continue-c-reference"></a><span data-ttu-id="82607-102">continue (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="82607-102">continue (C# Reference)</span></span>

<span data-ttu-id="82607-103">Die `continue`-Anweisung übergibt die Steuerung an die nächste Iteration der einschließenden [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) oder [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Anweisung, in der sie angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="82607-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="82607-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82607-104">Example</span></span>

<span data-ttu-id="82607-105">In diesem Beispiel wird ein Zähler initialisiert, um von 1 bis 10 zu zählen.</span><span class="sxs-lookup"><span data-stu-id="82607-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="82607-106">Indem die `continue`-Anweisung in Verbindung mit dem `(i < 9)`-Ausdruck verwendet wird, werden die Anweisungen zwischen `continue` und dem Ende des `for`-Rumpfs übersprungen.</span><span class="sxs-lookup"><span data-stu-id="82607-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="82607-107">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="82607-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="82607-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82607-108">See also</span></span>

- [<span data-ttu-id="82607-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="82607-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="82607-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="82607-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="82607-111">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="82607-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="82607-112">break-Anweisung</span><span class="sxs-lookup"><span data-stu-id="82607-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
- [<span data-ttu-id="82607-113">Sprunganweisungen</span><span class="sxs-lookup"><span data-stu-id="82607-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
