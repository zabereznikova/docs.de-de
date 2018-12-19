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
ms.openlocfilehash: 3419ad46d5bbe13bb4308ad15b7819d615cdbe86
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244725"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="7062a-102">try-catch-finally (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7062a-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="7062a-103">Häufige Verwendungen von `catch` und `finally` sind das Abrufen und Verwenden von Ressourcen in einem `try`-Block, das Vorgehen bei außergewöhnlichen Umständen in einem `catch`-Block und das Freisetzen von Ressourcen im `finally`-Block.</span><span class="sxs-lookup"><span data-stu-id="7062a-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="7062a-104">Weitere Informationen und Beispiele zum erneuten Auslösen von Ausnahmen finden Sie unter [try-catch](try-catch.md) und [Auslösen von Ausnahmen](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="7062a-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="7062a-105">Weitere Information über den `finally`-Block finden unter [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="7062a-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="7062a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7062a-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="7062a-107">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="7062a-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7062a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7062a-108">See also</span></span>

- [<span data-ttu-id="7062a-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7062a-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7062a-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7062a-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7062a-111">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7062a-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="7062a-112">try-, throw- und catch-Anweisungen (C++)</span><span class="sxs-lookup"><span data-stu-id="7062a-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="7062a-113">Ausnahmebehandlungsanweisungen</span><span class="sxs-lookup"><span data-stu-id="7062a-113">Exception Handling Statements</span></span>](exception-handling-statements.md)
- [<span data-ttu-id="7062a-114">throw</span><span class="sxs-lookup"><span data-stu-id="7062a-114">throw</span></span>](throw.md)
- [<span data-ttu-id="7062a-115">Vorgehensweise: Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7062a-115">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="7062a-116">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7062a-116">using Statement</span></span>](using-statement.md)