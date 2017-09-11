---
title: try-catch-finally (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
dev_langs:
- CSharp
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 05b2e0075aae79f85fba26d64690eefadaa166cd
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="97ab6-102">try-catch-finally (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="97ab6-102">try-catch-finally (C# Reference)</span></span>
<span data-ttu-id="97ab6-103">Häufige Verwendungen von `catch` und `finally` sind das Abrufen und Verwenden von Ressourcen in einem `try`-Block, das Vorgehen bei außergewöhnlichen Umständen in einem `catch`-Block und das Freisetzen von Ressourcen im `finally`-Block.</span><span class="sxs-lookup"><span data-stu-id="97ab6-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>  
  
 <span data-ttu-id="97ab6-104">Weitere Informationen und Beispiele zum erneuten Auslösen von Ausnahmen finden Sie unter [try-catch](../../../csharp/language-reference/keywords/try-catch.md) und [Auslösen von Ausnahmen](https://msdn.microsoft.com/library/xhcbs8fz).</span><span class="sxs-lookup"><span data-stu-id="97ab6-104">For more information and examples on re-throwing exceptions, see [try-catch](../../../csharp/language-reference/keywords/try-catch.md) and [Throwing Exceptions](https://msdn.microsoft.com/library/xhcbs8fz).</span></span> <span data-ttu-id="97ab6-105">Weitere Information über den `finally`-Block finden unter [try-finally](../../../csharp/language-reference/keywords/try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="97ab6-105">For more information about the `finally` block, see [try-finally](../../../csharp/language-reference/keywords/try-finally.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="97ab6-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97ab6-106">Example</span></span>  
 <span data-ttu-id="97ab6-107">[!code-cs[csrefKeywordsExceptions#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch-finally_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="97ab6-107">[!code-cs[csrefKeywordsExceptions#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch-finally_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="97ab6-108">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="97ab6-108">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="97ab6-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97ab6-109">See Also</span></span>  
 <span data-ttu-id="97ab6-110">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="97ab6-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="97ab6-111">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="97ab6-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="97ab6-112">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="97ab6-112">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="97ab6-113">[try-, throw- und catch-Anweisungen (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span><span class="sxs-lookup"><span data-stu-id="97ab6-113">[try, throw, and catch Statements (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span></span>  
 <span data-ttu-id="97ab6-114">[Ausnahmebehandlungsanweisungen](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="97ab6-114">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 <span data-ttu-id="97ab6-115">[throw](../../../csharp/language-reference/keywords/throw.md) </span><span class="sxs-lookup"><span data-stu-id="97ab6-115">[throw](../../../csharp/language-reference/keywords/throw.md) </span></span>  
 <span data-ttu-id="97ab6-116">[Vorgehensweise: Explizites Auslösen von Ausnahmen](https://msdn.microsoft.com/library/xhcbs8fz) </span><span class="sxs-lookup"><span data-stu-id="97ab6-116">[How to: Explicitly Throw Exceptions](https://msdn.microsoft.com/library/xhcbs8fz) </span></span>  
 [<span data-ttu-id="97ab6-117">Using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="97ab6-117">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

