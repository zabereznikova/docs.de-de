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
ms.openlocfilehash: d5fd2f5edf85c3ac2c8f0367b85b37e76e2e856e
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422112"
---
# <a name="continue-c-reference"></a><span data-ttu-id="cb0fb-102">continue (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cb0fb-102">continue (C# Reference)</span></span>

<span data-ttu-id="cb0fb-103">Die `continue`-Anweisung übergibt die Steuerung an die nächste Iteration der einschließenden [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) oder [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Anweisung, in der sie angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="cb0fb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb0fb-104">Example</span></span>

<span data-ttu-id="cb0fb-105">In diesem Beispiel wird ein Zähler initialisiert, um von 1 bis 10 zu zählen.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="cb0fb-106">Indem die `continue`-Anweisung in Verbindung mit dem `(i < 9)`-Ausdruck verwendet wird, werden die Anweisungen zwischen `continue` und dem Ende des `for`-Rumpfs übersprungen.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="cb0fb-107">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="cb0fb-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="cb0fb-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb0fb-108">See also</span></span>

- [<span data-ttu-id="cb0fb-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="cb0fb-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="cb0fb-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cb0fb-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="cb0fb-111">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="cb0fb-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="cb0fb-112">break-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cb0fb-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
