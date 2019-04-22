---
title: Der erste Operand in einem binären If-Ausdruck muss ein Typ, der NULL-Werte zulässt, oder ein Referenztyp sein
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 32ff0adca9d35e6b5439ae06be85414924dac2e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838624"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="751a4-102">Der erste Operand in einem binären If-Ausdruck muss ein Typ, der NULL-Werte zulässt, oder ein Referenztyp sein</span><span class="sxs-lookup"><span data-stu-id="751a4-102">First operand in a binary 'If' expression must be nullable or a reference type</span></span>
<span data-ttu-id="751a4-103">Ein `If` Ausdruck kann entweder zwei oder drei Argumente annehmen.</span><span class="sxs-lookup"><span data-stu-id="751a4-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="751a4-104">Wenn Sie nur zwei Argumente senden, muss das erste Argument ein Verweistyp oder einem nullable-Typ sein.</span><span class="sxs-lookup"><span data-stu-id="751a4-104">When you send only two arguments, the first argument must be a reference type or a nullable type.</span></span> <span data-ttu-id="751a4-105">Ergibt das erste Argument auf einen anderen als `Nothing`, dessen Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="751a4-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="751a4-106">Wenn das erste Argument ergibt `Nothing`, das zweite Argument wird ausgewertet und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="751a4-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>  
  
 <span data-ttu-id="751a4-107">Der folgende Code enthält z. B. zwei `If` Ausdrücke, eine mit drei Argumenten und einen mit zwei Argumenten.</span><span class="sxs-lookup"><span data-stu-id="751a4-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="751a4-108">Die Ausdrücke berechnen und den gleichen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="751a4-108">The expressions calculate and return the same value.</span></span>  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 <span data-ttu-id="751a4-109">Dieser Fehler wird durch die folgenden Ausdrücke verursacht:</span><span class="sxs-lookup"><span data-stu-id="751a4-109">The following expressions cause this error:</span></span>  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 <span data-ttu-id="751a4-110">**Fehler-ID:** BC33107</span><span class="sxs-lookup"><span data-stu-id="751a4-110">**Error ID:** BC33107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="751a4-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="751a4-111">To correct this error</span></span>  
  
-   <span data-ttu-id="751a4-112">Wenn Sie den Code, damit das erste Argument ein nullable-Typ oder ein Typ ist nicht mehr ändern können, sollten Sie die Konvertierung in ein drei-Argument `If` Ausdruck oder eine `If...Then...Else` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="751a4-112">If you cannot change the code so that the first argument is a nullable type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a><span data-ttu-id="751a4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="751a4-113">See also</span></span>

- [<span data-ttu-id="751a4-114">If-Operator</span><span class="sxs-lookup"><span data-stu-id="751a4-114">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="751a4-115">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="751a4-115">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="751a4-116">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="751a4-116">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
