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
ms.openlocfilehash: 74d166dbcf03b868baf464864e4c246f789df9cc
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605875"
---
# <a name="continue-c-reference"></a><span data-ttu-id="bab70-102">continue (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bab70-102">continue (C# Reference)</span></span>

<span data-ttu-id="bab70-103">Die `continue`-Anweisung übergibt die Steuerung an die nächste Iteration der einschließenden [while](./while.md), [do](./do.md), [for](./for.md) oder [foreach](./foreach-in.md)-Anweisung, in der sie angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="bab70-103">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="bab70-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bab70-104">Example</span></span>

<span data-ttu-id="bab70-105">In diesem Beispiel wird ein Zähler initialisiert, um von 1 bis 10 zu zählen.</span><span class="sxs-lookup"><span data-stu-id="bab70-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="bab70-106">Indem die `continue`-Anweisung in Verbindung mit dem `(i < 9)`-Ausdruck verwendet wird, werden die Anweisungen zwischen `continue` und dem Ende des `for`-Rumpfs übersprungen.</span><span class="sxs-lookup"><span data-stu-id="bab70-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="bab70-107">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="bab70-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bab70-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bab70-108">See also</span></span>

- [<span data-ttu-id="bab70-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bab70-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bab70-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bab70-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bab70-111">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bab70-111">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="bab70-112">break-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bab70-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
