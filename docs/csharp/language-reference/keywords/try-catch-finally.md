---
title: try-catch-finally – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 5d98f6967595c7c32b23ba5422a8d9ca79f7f54c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713039"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="25643-102">try-catch-finally (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="25643-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="25643-103">Häufige Verwendungen von `catch` und `finally` sind das Abrufen und Verwenden von Ressourcen in einem `try`-Block, das Vorgehen bei außergewöhnlichen Umständen in einem `catch`-Block und das Freisetzen von Ressourcen im `finally`-Block.</span><span class="sxs-lookup"><span data-stu-id="25643-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="25643-104">Weitere Informationen und Beispiele zum erneuten Auslösen von Ausnahmen finden Sie unter [try-catch](try-catch.md) und [Auslösen von Ausnahmen](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="25643-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="25643-105">Weitere Information über den `finally`-Block finden unter [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="25643-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="25643-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25643-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="25643-107">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="25643-107">C# language specification</span></span>

<span data-ttu-id="25643-108">Weitere Informationen finden Sie im Abschnitt [Die Try-Anweisung](~/_csharplang/spec/statements.md#the-try-statement) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="25643-108">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="25643-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25643-109">See also</span></span>

- [<span data-ttu-id="25643-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="25643-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="25643-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="25643-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="25643-112">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25643-112">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="25643-113">try, throw, and catch Statements (C++) (try-, throw- und catch-Anweisungen (C++))</span><span class="sxs-lookup"><span data-stu-id="25643-113">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="25643-114">throw</span><span class="sxs-lookup"><span data-stu-id="25643-114">throw</span></span>](throw.md)
- [<span data-ttu-id="25643-115">Vorgehensweise: Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="25643-115">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="25643-116">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="25643-116">using Statement</span></span>](using-statement.md)
