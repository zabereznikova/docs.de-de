---
title: return (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- return_CSharpKeyword
- return
dev_langs:
- CSharp
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: 18
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
ms.openlocfilehash: 596375a1cba8f5ecbad636a6829c1a0599f8c0f4
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="return-c-reference"></a><span data-ttu-id="e877b-102">return (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e877b-102">return (C# Reference)</span></span>
<span data-ttu-id="e877b-103">Die Anweisung `return` beendet die Ausführung der Methode, in der sie angezeigt wird, und gibt das Steuerelement an die aufrufende Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="e877b-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="e877b-104">Zudem kann ein optionaler Wert zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e877b-104">It can also return an optional value.</span></span> <span data-ttu-id="e877b-105">Wenn es sich bei der Methode um einen `void`-Typ handelt, kann die Anweisung `return` ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="e877b-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="e877b-106">Wenn sich die „return“-Anweisung in einem `try`-Block befindet, wird der `finally`-Block, falls vorhanden, ausgeführt bevor das Steuerelement an die aufrufende Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e877b-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e877b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e877b-107">Example</span></span>  
 <span data-ttu-id="e877b-108">Im folgenden Beispiel gibt die Methode `A()` die Variable `Area` als [double](../../../csharp/language-reference/keywords/double.md)-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="e877b-108">In the following example, the method `A()` returns the variable `Area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 <span data-ttu-id="e877b-109">[!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e877b-109">[!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e877b-110">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="e877b-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e877b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e877b-111">See Also</span></span>  
 <span data-ttu-id="e877b-112">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e877b-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e877b-113">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e877b-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e877b-114">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e877b-114">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e877b-115">[return Statement („return“-Anweisung)](/cpp/cpp/return-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="e877b-115">[return Statement](/cpp/cpp/return-statement-cpp) </span></span>  
 [<span data-ttu-id="e877b-116">Sprunganweisungen</span><span class="sxs-lookup"><span data-stu-id="e877b-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)

