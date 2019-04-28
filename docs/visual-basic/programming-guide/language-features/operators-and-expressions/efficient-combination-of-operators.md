---
title: Effiziente Kombination von Operatoren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 8f5dd6c56b3e4576b9d798e0e5e10b2996f558dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864652"
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="1ef1f-102">Effiziente Kombination von Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ef1f-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="1ef1f-103">Komplexe Ausdrücke können viele verschiedene Operatoren enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="1ef1f-104">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="1ef1f-105">Erstellen von komplexen Ausdrücken wie im vorherigen Beispiel erfordert ein tiefgreifendes Verständnis der Regeln der Operatorrangfolge.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="1ef1f-106">Weitere Informationen finden Sie unter [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="1ef1f-106">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="1ef1f-107">Ausdrücke in Klammern</span><span class="sxs-lookup"><span data-stu-id="1ef1f-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="1ef1f-108">Häufig möchten Sie die Vorgänge, die weitere Vorgehensweise in einer anderen Reihenfolge aus, die vom Operatorrangfolge bestimmt.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="1ef1f-109">Betrachten Sie das folgende Beispiel.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="1ef1f-110">Im vorherige Beispiel multipliziert `z` von `y`, fügt dann das Ergebnis an `4`.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="1ef1f-111">Aber wenn Sie hinzufügen möchten `y` und `4` vor dem Multiplizieren des Ergebnisses von `z`, Sie können normale Operatorrangfolge überschreiben, indem Sie Klammern verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="1ef1f-112">Einen Ausdruck in Klammern einschließen, erzwingen Sie, dass dieser Ausdruck unabhängig von der Operatorrangfolge zuerst ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="1ef1f-113">Um das vorangehende Beispiel so führen Sie zuerst das Hinzufügen zu erzwingen, können Sie ihn wie im folgenden Beispiel umschreiben.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="1ef1f-114">Im vorherige Beispiel fügt `y` und `4`, klicken Sie dann multipliziert die Summe von `z`.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="1ef1f-115">Geschachtelte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="1ef1f-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="1ef1f-116">Sie können Ausdrücke in mehrere Ebenen von Klammern, um die Rangfolge noch überschrieben schachteln.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="1ef1f-117">Die Ausdrücke, die am tiefsten geschachtelte in Klammern werden zuerst ausgewertet, gefolgt von der nächsten am tiefsten geschachtelt, und so weiter, die am wenigsten tief verschachtelte und schließlich die Ausdrücke außerhalb der Klammern.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="1ef1f-118">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="1ef1f-119">Im vorherigen Beispiel `z + 2` wird zuerst ausgewertet, und klicken Sie dann auf die andere Ausdrücke in Klammern.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="1ef1f-120">Potenzierung, die normalerweise Vorrang vor Addition oder Multiplikation hat, ist in diesem Beispiel zuletzt ausgewertet, da die anderen Ausdrücke in Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef1f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ef1f-121">See also</span></span>

- [<span data-ttu-id="1ef1f-122">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ef1f-122">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="1ef1f-123">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ef1f-123">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="1ef1f-124">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ef1f-124">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="1ef1f-125">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ef1f-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="1ef1f-126">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="1ef1f-126">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="1ef1f-127">Wertvergleiche</span><span class="sxs-lookup"><span data-stu-id="1ef1f-127">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="1ef1f-128">Vorgehensweise: Berechnen von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="1ef1f-128">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="1ef1f-129">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ef1f-129">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
