---
title: Effiziente Kombination von Operatoren
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
ms.openlocfilehash: 83ad53e4c75490a75eba0f80a6bf0f078aa4d426
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348993"
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="5e14d-102">Effiziente Kombination von Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e14d-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="5e14d-103">Komplexe Ausdrücke können viele verschiedene Operatoren enthalten.</span><span class="sxs-lookup"><span data-stu-id="5e14d-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="5e14d-104">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5e14d-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="5e14d-105">Das Erstellen komplexer Ausdrücke, wie z. b. der im vorherigen Beispiel, erfordert ein umfassendes Verständnis der Regeln der Operator Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="5e14d-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="5e14d-106">Weitere Informationen finden Sie unter [Operator Rangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="5e14d-106">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="5e14d-107">Klammer Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5e14d-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="5e14d-108">Häufig möchten Sie, dass Vorgänge in einer anderen Reihenfolge ausgeführt werden, die von der Operator Rangfolge bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="5e14d-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="5e14d-109">Betrachten Sie das folgende Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5e14d-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="5e14d-110">Im vorherigen Beispiel wird `z` mit `y`multipliziert und das Ergebnis dann `4`hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5e14d-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="5e14d-111">Wenn Sie jedoch `y` und `4` hinzufügen möchten, bevor Sie das Ergebnis mit `z`multiplizieren, können Sie die normale Operator Rangfolge mithilfe von Klammern überschreiben.</span><span class="sxs-lookup"><span data-stu-id="5e14d-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="5e14d-112">Wenn Sie einen Ausdruck in Klammern einschließen, erzwingen Sie, dass dieser Ausdruck unabhängig von der Operator Rangfolge zuerst ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="5e14d-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="5e14d-113">Um das vorangehende Beispiel zu erzwingen, müssen Sie es wie im folgenden Beispiel neu schreiben.</span><span class="sxs-lookup"><span data-stu-id="5e14d-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="5e14d-114">Im vorangehenden Beispiel werden `y` und `4`hinzugefügt. Anschließend wird diese Summe mit `z`multipliziert.</span><span class="sxs-lookup"><span data-stu-id="5e14d-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="5e14d-115">Eingeklamlierte Klammer Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5e14d-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="5e14d-116">Sie können Ausdrücke in mehreren Ebenen von Klammern schachteln, um die Rangfolge noch weiter zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="5e14d-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="5e14d-117">Die Ausdrücke, die in Klammern am tiefsten geschachtelt sind, werden zuerst ausgewertet, gefolgt von der nächst tiefen geschachtelten, usw. bis zu der am wenigsten tief geschachtelten und schließlich den Ausdrücken außerhalb der Klammern.</span><span class="sxs-lookup"><span data-stu-id="5e14d-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="5e14d-118">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5e14d-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="5e14d-119">Im vorherigen Beispiel wird `z + 2` zuerst ausgewertet, dann die anderen Klammer Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="5e14d-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="5e14d-120">Die exponentiierung, bei der normalerweise eine höhere Rangfolge als Addition oder Multiplikation fest steht, wird in diesem Beispiel zuletzt ausgewertet, da die anderen Ausdrücke in Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5e14d-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e14d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e14d-121">See also</span></span>

- [<span data-ttu-id="5e14d-122">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e14d-122">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="5e14d-123">Vergleichs Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e14d-123">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="5e14d-124">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e14d-124">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="5e14d-125">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e14d-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="5e14d-126">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5e14d-126">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="5e14d-127">Wertvergleiche</span><span class="sxs-lookup"><span data-stu-id="5e14d-127">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="5e14d-128">Gewusst wie: Berechnen von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="5e14d-128">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="5e14d-129">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e14d-129">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
