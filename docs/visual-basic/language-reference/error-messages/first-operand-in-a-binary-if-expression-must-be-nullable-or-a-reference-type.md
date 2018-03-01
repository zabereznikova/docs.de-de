---
title: "Der erste Operand in eine Binärdatei &#39; Wenn &#39; Ausdruck muss NULL-Werte zulässt, oder geben Sie ein Verweis"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f66b110c02076120c55a3bff28c3d7614bf8be26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="first-operand-in-a-binary-39if39-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="3b474-102">Der erste Operand in eine Binärdatei &#39; Wenn &#39; Ausdruck muss NULL-Werte zulässt, oder geben Sie ein Verweis</span><span class="sxs-lookup"><span data-stu-id="3b474-102">First operand in a binary &#39;If&#39; expression must be nullable or a reference type</span></span>
<span data-ttu-id="3b474-103">Ein `If` -Ausdruck kann entweder zwei oder drei Argumente übernehmen.</span><span class="sxs-lookup"><span data-stu-id="3b474-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="3b474-104">Wenn Sie nur zwei Argumente senden, sind für das erste Argument muss ein Verweistyp oder ein NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="3b474-104">When you send only two arguments, the first argument must be a reference type or a nullable type.</span></span> <span data-ttu-id="3b474-105">Wenn das erste Argument zu beliebiegen Dokumentbestandteilen außer ergibt `Nothing`, dessen Wert zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3b474-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="3b474-106">Wenn das erste Argument ergibt `Nothing`, das zweite Argument ausgewertet und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b474-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>  
  
 <span data-ttu-id="3b474-107">Der folgende Code enthält z. B. zwei `If` Ausdrücke, eine mit drei Argumenten und einen mit zwei Argumenten.</span><span class="sxs-lookup"><span data-stu-id="3b474-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="3b474-108">Die Ausdrücke berechnen und den gleichen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="3b474-108">The expressions calculate and return the same value.</span></span>  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 <span data-ttu-id="3b474-109">Dieser Fehler wird durch die folgenden Ausdrücke verursacht:</span><span class="sxs-lookup"><span data-stu-id="3b474-109">The following expressions cause this error:</span></span>  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 <span data-ttu-id="3b474-110">**Fehler-ID:** BC33107</span><span class="sxs-lookup"><span data-stu-id="3b474-110">**Error ID:** BC33107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3b474-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="3b474-111">To correct this error</span></span>  
  
-   <span data-ttu-id="3b474-112">Wenn Sie den Code ändern können, damit das erste Argument ein Referenztyp oder ein Verweistyp ist, sollten Sie beim Konvertieren in drei Argumenten `If` Ausdruck oder eine `If...Then...Else` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3b474-112">If you cannot change the code so that the first argument is a nullable type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b474-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b474-113">See Also</span></span>  
 [<span data-ttu-id="3b474-114">If-Operator</span><span class="sxs-lookup"><span data-stu-id="3b474-114">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="3b474-115">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3b474-115">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="3b474-116">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="3b474-116">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
