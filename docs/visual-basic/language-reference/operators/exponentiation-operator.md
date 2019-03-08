---
title: ^-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 54de9c91d4e166b8ca1733952dfa9c98ebf11ffe
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674093"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="88598-102">^-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88598-102">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="88598-103">Potenziert eine Zahl potenziert mit einer anderen Zahl.</span><span class="sxs-lookup"><span data-stu-id="88598-103">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="88598-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="88598-104">Syntax</span></span>

```
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="88598-105">Teile</span><span class="sxs-lookup"><span data-stu-id="88598-105">Parts</span></span>

`number`\
<span data-ttu-id="88598-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="88598-106">Required.</span></span> <span data-ttu-id="88598-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="88598-107">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="88598-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="88598-108">Required.</span></span> <span data-ttu-id="88598-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="88598-109">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="88598-110">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="88598-110">Result</span></span>

<span data-ttu-id="88598-111">Das Ergebnis ist `number` potenziert mit der `exponent`, immer als ein `Double` Wert.</span><span class="sxs-lookup"><span data-stu-id="88598-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="88598-112">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="88598-112">Supported Types</span></span>

<span data-ttu-id="88598-113">`Double`.</span><span class="sxs-lookup"><span data-stu-id="88598-113">`Double`.</span></span> <span data-ttu-id="88598-114">Die Operanden eines anderen Typs werden in konvertiert `Double`.</span><span class="sxs-lookup"><span data-stu-id="88598-114">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="88598-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="88598-115">Remarks</span></span>

<span data-ttu-id="88598-116">Visual Basic führt immer die Potenzierung der [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="88598-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>

<span data-ttu-id="88598-117">Der Wert des `exponent` möglich Bruch, negativ oder beides.</span><span class="sxs-lookup"><span data-stu-id="88598-117">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="88598-118">Wenn mehr als eine Potenzierung, in einem einzelnen Ausdruck ausgeführt wird, der `^` Operator wird ausgewertet, wie sie von links nach rechts gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="88598-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="88598-119">Die `^` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="88598-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="88598-120">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="88598-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="88598-121">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="88598-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="88598-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="88598-122">Example</span></span>

<span data-ttu-id="88598-123">Im folgenden Beispiel wird die `^` Operator, um eine Zahl potenziert mit einem Exponenten zu erheben.</span><span class="sxs-lookup"><span data-stu-id="88598-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="88598-124">Das Ergebnis ist der erste Operand des zweiten hoch.</span><span class="sxs-lookup"><span data-stu-id="88598-124">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="88598-125">Im obige Beispiel ergibt sich Folgendes:</span><span class="sxs-lookup"><span data-stu-id="88598-125">The preceding example produces the following results:</span></span>

<span data-ttu-id="88598-126">`exp1` ist auf 4 (2-squared) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="88598-126">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="88598-127">`exp2` wird auf 19683 (3 cubed, klicken Sie dann diesen Wert Kubik) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="88598-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="88598-128">`exp3` wird auf-125 (-5 Kubik) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="88598-128">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="88598-129">`exp4` wird auf 625 (4 -5) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="88598-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="88598-130">`exp5` ist auf 2 (Kubikwurzel von 8) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="88598-130">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="88598-131">`exp6` ist auf 0,5 (1.0, geteilt durch die Kubikwurzel von 8) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="88598-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="88598-132">Beachten Sie die Wichtigkeit der runden Klammern in der die Ausdrücke im vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="88598-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="88598-133">Aufgrund der *Operatorrangfolge*, Visual Basic normalerweise führt die `^` Operator vor allen anderen auch den unären `–` Operator.</span><span class="sxs-lookup"><span data-stu-id="88598-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="88598-134">Wenn `exp4` und `exp6` berechnet worden ohne Klammern, sie würden die folgenden Ergebnisse erzeugt haben:</span><span class="sxs-lookup"><span data-stu-id="88598-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="88598-135">`exp4 = -5 ^ 4` wird berechnet als: (5 4), was-625 ergeben würde.</span><span class="sxs-lookup"><span data-stu-id="88598-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="88598-136">`exp6 = 8 ^ -1.0 / 3.0` wird berechnet als (8 die – 1 oder 0,125) geteilt durch 3.0, das 0,041666666666666666666666666666667 führen würde.</span><span class="sxs-lookup"><span data-stu-id="88598-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="88598-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88598-137">See also</span></span>

- [<span data-ttu-id="88598-138">^=-Operator</span><span class="sxs-lookup"><span data-stu-id="88598-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="88598-139">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="88598-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="88598-140">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88598-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="88598-141">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="88598-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="88598-142">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="88598-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
