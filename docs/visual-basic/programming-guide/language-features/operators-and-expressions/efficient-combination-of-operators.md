---
title: Effiziente Kombination von Operatoren (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b0f1d637bc1757515cf271a8c70d62effab0843
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="d8fb0-102">Effiziente Kombination von Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8fb0-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="d8fb0-103">Komplexe Ausdrücke können viele verschiedene Operatoren enthalten.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="d8fb0-104">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="d8fb0-105">Erstellen von komplexen Ausdrücken wie im vorherigen Beispiel erfordert ein gehendes Verständnis von den Regeln der Operatorrangfolge.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="d8fb0-106">Weitere Informationen finden Sie unter [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="d8fb0-106">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="d8fb0-107">Ausdrücke in Klammern</span><span class="sxs-lookup"><span data-stu-id="d8fb0-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="d8fb0-108">Häufig sollen Operationen in einer anderen Reihenfolge aus, die vom Operatorrangfolge bestimmt den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="d8fb0-109">Betrachten Sie das folgende Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="d8fb0-110">Das obige Beispiel multipliziert `z` von `y`, fügt dann das Ergebnis, das `4`.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="d8fb0-111">Aber wenn Sie hinzufügen möchten `y` und `4` vor dem Multiplizieren des Ergebnisses durch `z`, Sie können normale Operatorrangfolge überschreiben, indem Sie Klammern verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="d8fb0-112">Durch einen Ausdruck in Klammern einschließen, erzwingen Sie, dass dieser Ausdruck unabhängig von der Operatorrangfolge zuerst ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="d8fb0-113">Um das vorangehende Beispiel so führen Sie zuerst das Hinzufügen zu erzwingen, konnte Sie es wie im folgenden Beispiel schreiben.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="d8fb0-114">Das obige Beispiel fügt `y` und `4`, klicken Sie dann diese Summe durch multipliziert `z`.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="d8fb0-115">Geschachtelte Ausdrücke in Klammern</span><span class="sxs-lookup"><span data-stu-id="d8fb0-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="d8fb0-116">Sie können Ausdrücke in mehrere Ebenen von Klammern, um noch weiter Vorrang schachteln.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="d8fb0-117">Die Ausdrücke, die am tiefsten geschachtelte in Klammern werden zuerst ausgewertet, gefolgt von der nächsten am tiefsten geschachtelte, und so weiter, die am wenigsten tief verschachtelte und schließlich die Ausdrücke außerhalb der Klammern.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="d8fb0-118">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="d8fb0-119">Im vorherigen Beispiel `z + 2` wird zuerst ausgewertet, und klicken Sie dann auf die andere Ausdrücke in Klammern.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="d8fb0-120">Potenzierung, die normalerweise Vorrang vor Addition und Multiplikation aufweist, wird zuletzt in diesem Beispiel wird ausgewertet, weil die andere Ausdrücke in Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d8fb0-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8fb0-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8fb0-121">See Also</span></span>  
 [<span data-ttu-id="d8fb0-122">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8fb0-122">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="d8fb0-123">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8fb0-123">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="d8fb0-124">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8fb0-124">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="d8fb0-125">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8fb0-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="d8fb0-126">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="d8fb0-126">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="d8fb0-127">Wertvergleiche</span><span class="sxs-lookup"><span data-stu-id="d8fb0-127">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="d8fb0-128">Gewusst wie: Berechnen von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="d8fb0-128">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [<span data-ttu-id="d8fb0-129">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8fb0-129">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
