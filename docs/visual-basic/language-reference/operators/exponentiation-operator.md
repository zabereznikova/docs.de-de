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
ms.openlocfilehash: 8cdfbec917608211e19c39eb37bd12dbc7c4d33f
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592212"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="79b36-102">^-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79b36-102">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="79b36-103">Potenziert eine Zahl mit einer anderen Zahl.</span><span class="sxs-lookup"><span data-stu-id="79b36-103">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="79b36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="79b36-104">Syntax</span></span>

```vb
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="79b36-105">Teile</span><span class="sxs-lookup"><span data-stu-id="79b36-105">Parts</span></span>

`number`\
<span data-ttu-id="79b36-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="79b36-106">Required.</span></span> <span data-ttu-id="79b36-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="79b36-107">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="79b36-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="79b36-108">Required.</span></span> <span data-ttu-id="79b36-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="79b36-109">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="79b36-110">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="79b36-110">Result</span></span>

<span data-ttu-id="79b36-111">Das Ergebnis ist, dass `number` `exponent`, immer als `Double`-Wert ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="79b36-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="79b36-112">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="79b36-112">Supported Types</span></span>

<span data-ttu-id="79b36-113">`Double`. installiert haben.</span><span class="sxs-lookup"><span data-stu-id="79b36-113">`Double`.</span></span> <span data-ttu-id="79b36-114">Operanden eines beliebigen Typs werden in `Double` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="79b36-114">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="79b36-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79b36-115">Remarks</span></span>

<span data-ttu-id="79b36-116">Visual Basic führt immer eine exponentiell im [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)aus.</span><span class="sxs-lookup"><span data-stu-id="79b36-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>

<span data-ttu-id="79b36-117">Der Wert von `exponent` kann eine Bruch Zahl, eine negative oder beides sein.</span><span class="sxs-lookup"><span data-stu-id="79b36-117">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="79b36-118">Wenn mehr als eine exponentiell in einem einzelnen Ausdruck ausgeführt wird, wird der `^`-Operator ausgewertet, da er von links nach rechts gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="79b36-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="79b36-119">Der `^`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="79b36-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="79b36-120">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="79b36-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="79b36-121">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="79b36-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="79b36-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79b36-122">Example</span></span>

<span data-ttu-id="79b36-123">Im folgenden Beispiel wird der `^`-Operator verwendet, um eine Zahl zur Potenz eines Exponenten zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="79b36-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="79b36-124">Das Ergebnis ist der erste Operand, der für die zweite Potenz ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="79b36-124">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="79b36-125">Das vorangehende Beispiel erzeugt die folgenden Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="79b36-125">The preceding example produces the following results:</span></span>

<span data-ttu-id="79b36-126">`exp1` ist auf 4 (2 Quadrat) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="79b36-126">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="79b36-127">`exp2` ist auf 19683 (3 (3) und dann auf diesen Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="79b36-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="79b36-128">`exp3` ist auf-125 (-5-CUB) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="79b36-128">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="79b36-129">`exp4` ist auf 625 (-5 bis zum vierten Strom) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="79b36-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="79b36-130">`exp5` ist auf 2 (Cube-Stamm von 8) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="79b36-130">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="79b36-131">`exp6` ist auf 0,5 (1,0 dividiert durch den Cube-Stamm von 8) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="79b36-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="79b36-132">Beachten Sie die Wichtigkeit der Klammern in den Ausdrücken im vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="79b36-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="79b36-133">Aufgrund der *Operator Rangfolge*führt Visual Basic normalerweise den `^`-Operator vor allen anderen aus, auch den unären `–`-Operator.</span><span class="sxs-lookup"><span data-stu-id="79b36-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="79b36-134">Wenn `exp4` und `exp6` ohne Klammern berechnet wurden, haben Sie die folgenden Ergebnisse erzeugt:</span><span class="sxs-lookup"><span data-stu-id="79b36-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="79b36-135">`exp4 = -5 ^ 4` wird als – (5 bis zum vierten Leistungswert) berechnet, was zu-625 führen würde.</span><span class="sxs-lookup"><span data-stu-id="79b36-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="79b36-136">`exp6 = 8 ^ -1.0 / 3.0` wird wie folgt berechnet: (8 bis – 1 Power oder 0,125) dividiert durch 3,0, was zu 0.041666666666666666666666666666667 führen würde.</span><span class="sxs-lookup"><span data-stu-id="79b36-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="79b36-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79b36-137">See also</span></span>

- [<span data-ttu-id="79b36-138">^=-Operator</span><span class="sxs-lookup"><span data-stu-id="79b36-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="79b36-139">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="79b36-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="79b36-140">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79b36-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="79b36-141">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="79b36-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="79b36-142">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79b36-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
