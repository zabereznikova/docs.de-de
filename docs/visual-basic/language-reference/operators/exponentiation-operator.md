---
title: ^-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e7159f289b687055c7d75cc8da58d6f76607a83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e6464-102">^-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6464-102">^ Operator (Visual Basic)</span></span>
<span data-ttu-id="e6464-103">Potenziert eine Zahl zur Potenz einer anderen Zahl.</span><span class="sxs-lookup"><span data-stu-id="e6464-103">Raises a number to the power of another number.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6464-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6464-104">Syntax</span></span>  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a><span data-ttu-id="e6464-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e6464-105">Parts</span></span>  
 `number`  
 <span data-ttu-id="e6464-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e6464-106">Required.</span></span> <span data-ttu-id="e6464-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e6464-107">Any numeric expression.</span></span>  
  
 `exponent`  
 <span data-ttu-id="e6464-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e6464-108">Required.</span></span> <span data-ttu-id="e6464-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e6464-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="e6464-110">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="e6464-110">Result</span></span>  
 <span data-ttu-id="e6464-111">Das Ergebnis ist `number` potenziert mit der `exponent`, immer als eine `Double` Wert.</span><span class="sxs-lookup"><span data-stu-id="e6464-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="e6464-112">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="e6464-112">Supported Types</span></span>  
 <span data-ttu-id="e6464-113">`Double`.</span><span class="sxs-lookup"><span data-stu-id="e6464-113">`Double`.</span></span> <span data-ttu-id="e6464-114">Die Operanden eines anderen Typs konvertiert werden `Double`.</span><span class="sxs-lookup"><span data-stu-id="e6464-114">Operands of any different type are converted to `Double`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6464-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6464-115">Remarks</span></span>  
 <span data-ttu-id="e6464-116">Visual Basic führt immer Potenzierung der [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="e6464-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>  
  
 <span data-ttu-id="e6464-117">Der Wert des `exponent` kann Bruch, negativ oder beides.</span><span class="sxs-lookup"><span data-stu-id="e6464-117">The value of `exponent` can be fractional, negative, or both.</span></span>  
  
 <span data-ttu-id="e6464-118">Wenn mehr als eine Potenzierung in einem einzelnen Ausdruck erfolgt die `^` Operators ausgewertet wird, wie sie von links nach rechts entdeckt wird.</span><span class="sxs-lookup"><span data-stu-id="e6464-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6464-119">Die `^` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="e6464-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e6464-120">Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="e6464-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e6464-121">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e6464-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6464-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6464-122">Example</span></span>  
 <span data-ttu-id="e6464-123">Im folgenden Beispiel wird die `^` Operator, um eine Zahl und einen Exponenten auslösen.</span><span class="sxs-lookup"><span data-stu-id="e6464-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="e6464-124">Das Ergebnis ist der erste Operand potenziert mit der zweiten.</span><span class="sxs-lookup"><span data-stu-id="e6464-124">The result is the first operand raised to the power of the second.</span></span>  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 <span data-ttu-id="e6464-125">Das obige Beispiel ergibt sich Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="e6464-125">The preceding example produces the following results:</span></span>  
  
 <span data-ttu-id="e6464-126">`exp1`4 (2 Quadrat) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e6464-126">`exp1` is set to 4 (2 squared).</span></span>  
  
 <span data-ttu-id="e6464-127">`exp2`wird auf 19683 (3 Kubik, klicken Sie dann diesen Wert Kubik) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e6464-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>  
  
 <span data-ttu-id="e6464-128">`exp3`wird auf-125 (-5 Kubik) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e6464-128">`exp3` is set to -125 (-5 cubed).</span></span>  
  
 <span data-ttu-id="e6464-129">`exp4`wird auf 625 (-5 4) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e6464-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>  
  
 <span data-ttu-id="e6464-130">`exp5`wird auf 2 (Kubikwurzel von 8) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e6464-130">`exp5` is set to 2 (cube root of 8).</span></span>  
  
 <span data-ttu-id="e6464-131">`exp6`ist auf 0,5 (1.0, dividiert durch die Kubikwurzel von 8) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e6464-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>  
  
 <span data-ttu-id="e6464-132">Beachten Sie die Wichtigkeit der Klammern der Ausdrücke im vorangehenden Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="e6464-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="e6464-133">Aufgrund der *Operatorrangfolge*, Visual Basic normalerweise führt die `^` Operator vor allen anderen auch den unären `–` Operator.</span><span class="sxs-lookup"><span data-stu-id="e6464-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="e6464-134">Wenn `exp4` und `exp6` berechnet worden ohne Klammern sie hätte die folgenden Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="e6464-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>  
  
 <span data-ttu-id="e6464-135">`exp4 = -5 ^ 4`würde als – 5 mit dem vierten Exponenten, berechnet der-625 würde.</span><span class="sxs-lookup"><span data-stu-id="e6464-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>  
  
 <span data-ttu-id="e6464-136">`exp6 = 8 ^ -1.0 / 3.0`würde als (8, um die Leistungsfähigkeit von – 1 oder 0,125) berechnet werden geteilt durch 3.0, was 0,041666666666666666666666666666667 führen würde.</span><span class="sxs-lookup"><span data-stu-id="e6464-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6464-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6464-137">See Also</span></span>  
 [<span data-ttu-id="e6464-138">^=-Operator</span><span class="sxs-lookup"><span data-stu-id="e6464-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [<span data-ttu-id="e6464-139">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="e6464-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="e6464-140">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6464-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="e6464-141">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="e6464-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="e6464-142">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e6464-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
