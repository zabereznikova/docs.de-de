---
title: Not-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 4e54fdca9123ad5595eb9a8c5e2ac5bc303a8f6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824212"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="36852-102">Not-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36852-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="36852-103">Führt eine logische Negation für einen `Boolean` Ausdruck oder eine bitweise Negation eines numerischen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="36852-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36852-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="36852-104">Syntax</span></span>  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="36852-105">Teile</span><span class="sxs-lookup"><span data-stu-id="36852-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="36852-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="36852-106">Required.</span></span> <span data-ttu-id="36852-107">Alle `Boolean` oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="36852-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="36852-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="36852-108">Required.</span></span> <span data-ttu-id="36852-109">Alle `Boolean` oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="36852-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36852-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36852-110">Remarks</span></span>  
 <span data-ttu-id="36852-111">Für `Boolean` Ausdrücke, in der folgende Tabelle wird veranschaulicht, wie `result` bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="36852-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="36852-112">Wenn `expression` ist</span><span class="sxs-lookup"><span data-stu-id="36852-112">If `expression` is</span></span>|<span data-ttu-id="36852-113">Der Wert des `result` ist</span><span class="sxs-lookup"><span data-stu-id="36852-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="36852-114">Bei numerischen Ausdrücken der `Not` Operator kehrt die Bitwerte ein beliebiger numerischer Ausdruck, und legt das entsprechende Bit in `result` gemäß der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="36852-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="36852-115">Wenn bit `expression` ist</span><span class="sxs-lookup"><span data-stu-id="36852-115">If bit in `expression` is</span></span>|<span data-ttu-id="36852-116">Das entsprechende Bit im `result` ist</span><span class="sxs-lookup"><span data-stu-id="36852-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="36852-117">1</span><span class="sxs-lookup"><span data-stu-id="36852-117">1</span></span>|<span data-ttu-id="36852-118">0</span><span class="sxs-lookup"><span data-stu-id="36852-118">0</span></span>|  
|<span data-ttu-id="36852-119">0</span><span class="sxs-lookup"><span data-stu-id="36852-119">0</span></span>|<span data-ttu-id="36852-120">1</span><span class="sxs-lookup"><span data-stu-id="36852-120">1</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="36852-121">Da die logischen und bitweisen Operatoren auf eine niedrigere Rangfolge als der anderen arithmetischen und relationalen Operatoren haben, sollten alle bitweisen Operationen in Klammern, um die genaue Ausführung sicherzustellen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="36852-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="36852-122">Datentypen</span><span class="sxs-lookup"><span data-stu-id="36852-122">Data Types</span></span>  
 <span data-ttu-id="36852-123">Der Datentyp des Ergebnisses einer booleschen Negation ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="36852-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="36852-124">Der Ergebnistyp für die Daten für die eine bitweise Negation, ist identisch mit der `expression`.</span><span class="sxs-lookup"><span data-stu-id="36852-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="36852-125">Allerdings ist der Ausdruck `Decimal`, das Ergebnis ist `Long`.</span><span class="sxs-lookup"><span data-stu-id="36852-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="36852-126">Überladen</span><span class="sxs-lookup"><span data-stu-id="36852-126">Overloading</span></span>  
 <span data-ttu-id="36852-127">Die `Not` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn der Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="36852-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="36852-128">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="36852-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="36852-129">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="36852-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="36852-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36852-130">Example</span></span>  
 <span data-ttu-id="36852-131">Im folgenden Beispiel wird die `Not` Operator, um die logischen Negation für Ausführen einer `Boolean` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="36852-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="36852-132">Das Ergebnis ist eine `Boolean` Wert, der die Umkehrung des Werts des Ausdrucks darstellt.</span><span class="sxs-lookup"><span data-stu-id="36852-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="36852-133">Im vorherige Beispiel erzeugt die Ergebnisse der `False` und `True`bzw.</span><span class="sxs-lookup"><span data-stu-id="36852-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36852-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36852-134">Example</span></span>  
 <span data-ttu-id="36852-135">Im folgenden Beispiel wird die `Not` Operator, um die logische Negation der einzelnen Bits eines numerischen Ausdrucks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="36852-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="36852-136">Das Bit im Ergebnismuster ist das Gegenteil von das entsprechende Bit im Operandenmuster, einschließlich des Vorzeichenbits fest.</span><span class="sxs-lookup"><span data-stu-id="36852-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="36852-137">Im vorherige Beispiel werden die Ergebnisse der – 11 – 9 und –7, bzw. erzeugt.</span><span class="sxs-lookup"><span data-stu-id="36852-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36852-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36852-138">See also</span></span>

- [<span data-ttu-id="36852-139">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36852-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="36852-140">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36852-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="36852-141">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="36852-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="36852-142">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="36852-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
