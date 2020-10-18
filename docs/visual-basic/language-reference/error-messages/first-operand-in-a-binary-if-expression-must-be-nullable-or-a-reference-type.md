---
title: Der erste Operand in einem binären If-Ausdruck muss ein Typ, der NULL-Werte zulässt, oder ein Referenztyp sein
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: bca9b74a68815b4e5a3bb2dc114b9031cdf24099
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162738"
---
# <a name="bc33107-first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="b1c07-102">BC33107: der erste Operand in einem binären If-Ausdruck muss NULL-Werte zulassen oder ein Verweistyp sein.</span><span class="sxs-lookup"><span data-stu-id="b1c07-102">BC33107: First operand in a binary 'If' expression must be nullable or a reference type</span></span>

<span data-ttu-id="b1c07-103">Ein `If` Ausdruck kann entweder zwei oder drei Argumente annehmen.</span><span class="sxs-lookup"><span data-stu-id="b1c07-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="b1c07-104">Wenn Sie nur zwei Argumente senden, muss das erste Argument ein Referenztyp oder ein Werte zulässt-Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="b1c07-104">When you send only two arguments, the first argument must be a reference type or a nullable value type.</span></span> <span data-ttu-id="b1c07-105">Wenn das erste Argument etwas anderes als ausgewertet wird `Nothing` , wird der Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b1c07-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="b1c07-106">Wenn das erste Argument ergibt `Nothing` , wird das zweite Argument ausgewertet und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b1c07-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>

 <span data-ttu-id="b1c07-107">Der folgende Code enthält z. b `If` . zwei Ausdrücke, eine mit drei Argumenten und eine mit zwei Argumenten.</span><span class="sxs-lookup"><span data-stu-id="b1c07-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="b1c07-108">Die Ausdrücke berechnen und geben denselben Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1c07-108">The expressions calculate and return the same value.</span></span>

```vb
' firstChoice is a nullable value type.
Dim firstChoice? As Integer = Nothing
Dim secondChoice As Integer = 1128
' If expression with three arguments.
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))
' If expression with two arguments.
Console.WriteLine(If(firstChoice, secondChoice))
```

 <span data-ttu-id="b1c07-109">Dieser Fehler wird durch die folgenden Ausdrücke verursacht:</span><span class="sxs-lookup"><span data-stu-id="b1c07-109">The following expressions cause this error:</span></span>

```vb
Dim choice1 = 4
Dim choice2 = 5
Dim booleanVar = True

' Not valid.
'Console.WriteLine(If(choice1 < choice2, 1))
' Not valid.
'Console.WriteLine(If(booleanVar, "Test returns True."))
```

 <span data-ttu-id="b1c07-110">**Fehler-ID:** BC33107</span><span class="sxs-lookup"><span data-stu-id="b1c07-110">**Error ID:** BC33107</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b1c07-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b1c07-111">To correct this error</span></span>

- <span data-ttu-id="b1c07-112">Wenn Sie den Code nicht ändern können, sodass das erste Argument ein Werte zulässt-Werttyp oder Verweistyp ist, sollten Sie in Erwägung gezogen werden, einen Ausdruck mit drei Argumenten oder eine- `If` Anweisung zu ändern `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="b1c07-112">If you cannot change the code so that the first argument is a nullable value type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>

```vb
Console.WriteLine(If(choice1 < choice2, 1, 2))
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))
```

## <a name="see-also"></a><span data-ttu-id="b1c07-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1c07-113">See also</span></span>

- [<span data-ttu-id="b1c07-114">If-Operator</span><span class="sxs-lookup"><span data-stu-id="b1c07-114">If Operator</span></span>](../operators/if-operator.md)
- [<span data-ttu-id="b1c07-115">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b1c07-115">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="b1c07-116">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="b1c07-116">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
