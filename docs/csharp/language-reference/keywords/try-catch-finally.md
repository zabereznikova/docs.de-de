---
title: try-catch-finally – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 787005ec09a2c5c4f0e5033c83fd6a7ab7875b7e
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422158"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="64892-102">try-catch-finally (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="64892-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="64892-103">Häufige Verwendungen von `catch` und `finally` sind das Abrufen und Verwenden von Ressourcen in einem `try`-Block, das Vorgehen bei außergewöhnlichen Umständen in einem `catch`-Block und das Freisetzen von Ressourcen im `finally`-Block.</span><span class="sxs-lookup"><span data-stu-id="64892-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="64892-104">Weitere Informationen und Beispiele zum erneuten Auslösen von Ausnahmen finden Sie unter [try-catch](try-catch.md) und [Auslösen von Ausnahmen](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="64892-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="64892-105">Weitere Information über den `finally`-Block finden unter [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="64892-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="64892-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64892-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="64892-107">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="64892-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="64892-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64892-108">See also</span></span>

- [<span data-ttu-id="64892-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="64892-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="64892-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="64892-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="64892-111">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="64892-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="64892-112">try-, throw- und catch-Anweisungen (C++)</span><span class="sxs-lookup"><span data-stu-id="64892-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="64892-113">throw</span><span class="sxs-lookup"><span data-stu-id="64892-113">throw</span></span>](throw.md)
- [<span data-ttu-id="64892-114">Vorgehensweise: Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="64892-114">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="64892-115">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="64892-115">using Statement</span></span>](using-statement.md)
