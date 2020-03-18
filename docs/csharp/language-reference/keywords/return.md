---
title: return-Anweisung – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 116bad7a1f9f61311d287c575b52547d63c9e1c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713130"
---
# <a name="return-c-reference"></a><span data-ttu-id="6ba52-102">return (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6ba52-102">return (C# Reference)</span></span>

<span data-ttu-id="6ba52-103">Die Anweisung `return` beendet die Ausführung der Methode, in der sie angezeigt wird, und gibt das Steuerelement an die aufrufende Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="6ba52-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="6ba52-104">Zudem kann ein optionaler Wert zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6ba52-104">It can also return an optional value.</span></span> <span data-ttu-id="6ba52-105">Wenn es sich bei der Methode um einen `void`-Typ handelt, kann die Anweisung `return` ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="6ba52-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="6ba52-106">Wenn sich die „return“-Anweisung in einem `try`-Block befindet, wird der `finally`-Block, falls vorhanden, ausgeführt bevor das Steuerelement an die aufrufende Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6ba52-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="6ba52-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ba52-107">Example</span></span>

 <span data-ttu-id="6ba52-108">Im folgenden Beispiel gibt die Methode `CalculateArea()` die lokale Variable `area` als `double`-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="6ba52-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a `double` value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="6ba52-109">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="6ba52-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="6ba52-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ba52-110">See also</span></span>

- [<span data-ttu-id="6ba52-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6ba52-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6ba52-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6ba52-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6ba52-113">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6ba52-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6ba52-114">return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6ba52-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
