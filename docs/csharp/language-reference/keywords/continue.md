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
ms.openlocfilehash: 6c70934c3b861e1a1433e5c0b95bb32e9d717c53
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877651"
---
# <a name="continue-c-reference"></a><span data-ttu-id="7ac1c-103">continue (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7ac1c-103">continue (C# Reference)</span></span>

<span data-ttu-id="7ac1c-104">Die `continue`-Anweisung übergibt die Steuerung an die nächste Iteration der einschließenden [while](./while.md), [do](./do.md), [for](./for.md) oder [foreach](./foreach-in.md)-Anweisung, in der sie angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="7ac1c-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="7ac1c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ac1c-105">Example</span></span>

<span data-ttu-id="7ac1c-106">In diesem Beispiel wird ein Zähler initialisiert, um von 1 bis 10 zu zählen.</span><span class="sxs-lookup"><span data-stu-id="7ac1c-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="7ac1c-107">Indem die `continue`-Anweisung in Verbindung mit dem `(i < 9)`-Ausdruck verwendet wird, werden die Anweisungen zwischen `continue` und dem Ende des `for`-Teils in Iterationen übersprungen, in denen `i` weniger als 9 beträgt.</span><span class="sxs-lookup"><span data-stu-id="7ac1c-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped in the iterations where `i` is less than 9.</span></span> <span data-ttu-id="7ac1c-108">In den letzten beiden Iterationen der `for`-Schleife, für die i == 9 und i == 10 gilt, wird die `continue`-Anweisung nicht ausgeführt, und der Wert von `i` wird in der Konsole zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7ac1c-108">In the last two iterations of the `for` loop (where i == 9 and i == 10), the `continue` statement is not executed and the value of `i` is printed to the console.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="7ac1c-109">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="7ac1c-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7ac1c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ac1c-110">See also</span></span>

- [<span data-ttu-id="7ac1c-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7ac1c-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7ac1c-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7ac1c-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7ac1c-113">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7ac1c-113">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="7ac1c-114">break-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7ac1c-114">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
