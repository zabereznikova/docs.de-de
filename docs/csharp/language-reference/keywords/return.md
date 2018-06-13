---
title: return (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 29d2b8e28ae6240b9d06b82695efe1736404c5cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266109"
---
# <a name="return-c-reference"></a><span data-ttu-id="6d196-102">return (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6d196-102">return (C# Reference)</span></span>
<span data-ttu-id="6d196-103">Die Anweisung `return` beendet die Ausführung der Methode, in der sie angezeigt wird, und gibt das Steuerelement an die aufrufende Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="6d196-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="6d196-104">Zudem kann ein optionaler Wert zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6d196-104">It can also return an optional value.</span></span> <span data-ttu-id="6d196-105">Wenn es sich bei der Methode um einen `void`-Typ handelt, kann die Anweisung `return` ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="6d196-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="6d196-106">Wenn sich die „return“-Anweisung in einem `try`-Block befindet, wird der `finally`-Block, falls vorhanden, ausgeführt bevor das Steuerelement an die aufrufende Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6d196-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d196-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d196-107">Example</span></span>  
 <span data-ttu-id="6d196-108">Im folgenden Beispiel gibt die Methode `CalculateArea()` die lokale Variable `area` als [double](../../../csharp/language-reference/keywords/double.md)-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="6d196-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6d196-109">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="6d196-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6d196-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d196-110">See Also</span></span>  
 [<span data-ttu-id="6d196-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6d196-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6d196-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6d196-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6d196-113">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6d196-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6d196-114">return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6d196-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)  
 [<span data-ttu-id="6d196-115">Sprunganweisungen</span><span class="sxs-lookup"><span data-stu-id="6d196-115">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
