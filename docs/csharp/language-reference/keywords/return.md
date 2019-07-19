---
title: return-Anweisung – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: a845ce257bf7f0cf0e64d6815b2278f6cec946e7
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661614"
---
# <a name="return-c-reference"></a><span data-ttu-id="c2723-102">return (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c2723-102">return (C# Reference)</span></span>

<span data-ttu-id="c2723-103">Die Anweisung `return` beendet die Ausführung der Methode, in der sie angezeigt wird, und gibt das Steuerelement an die aufrufende Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="c2723-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="c2723-104">Zudem kann ein optionaler Wert zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c2723-104">It can also return an optional value.</span></span> <span data-ttu-id="c2723-105">Wenn es sich bei der Methode um einen `void`-Typ handelt, kann die Anweisung `return` ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="c2723-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="c2723-106">Wenn sich die „return“-Anweisung in einem `try`-Block befindet, wird der `finally`-Block, falls vorhanden, ausgeführt bevor das Steuerelement an die aufrufende Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c2723-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="c2723-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2723-107">Example</span></span>

 <span data-ttu-id="c2723-108">Im folgenden Beispiel gibt die Methode `CalculateArea()` die lokale Variable `area` als `double`-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c2723-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a `double` value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="c2723-109">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c2723-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c2723-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2723-110">See also</span></span>

- [<span data-ttu-id="c2723-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c2723-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c2723-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c2723-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c2723-113">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c2723-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c2723-114">return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c2723-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
