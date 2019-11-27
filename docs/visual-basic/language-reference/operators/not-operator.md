---
title: Not-Operator
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
ms.openlocfilehash: 08b091ccf6c50438b5ad9d6c445510112abe7418
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348297"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="b9210-102">Not-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9210-102">Not Operator (Visual Basic)</span></span>
<span data-ttu-id="b9210-103">Führt eine logische Negation für einen `Boolean` Ausdruck oder eine bitweise Negation eines numerischen Ausdrucks aus.</span><span class="sxs-lookup"><span data-stu-id="b9210-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9210-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9210-104">Syntax</span></span>  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b9210-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="b9210-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b9210-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="b9210-106">Required.</span></span> <span data-ttu-id="b9210-107">Eine beliebige `Boolean` oder ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b9210-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="b9210-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="b9210-108">Required.</span></span> <span data-ttu-id="b9210-109">Eine beliebige `Boolean` oder ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b9210-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9210-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9210-110">Remarks</span></span>  
 <span data-ttu-id="b9210-111">In der folgenden Tabelle wird für `Boolean` Ausdrücke veranschaulicht, wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="b9210-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="b9210-112">Wenn `expression` ist</span><span class="sxs-lookup"><span data-stu-id="b9210-112">If `expression` is</span></span>|<span data-ttu-id="b9210-113">Der Wert von `result` ist</span><span class="sxs-lookup"><span data-stu-id="b9210-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="b9210-114">Bei numerischen Ausdrücken kehrt der `Not`-Operator die Bitwerte eines beliebigen numerischen Ausdrucks um und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="b9210-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="b9210-115">Wenn Bit in `expression` ist</span><span class="sxs-lookup"><span data-stu-id="b9210-115">If bit in `expression` is</span></span>|<span data-ttu-id="b9210-116">Das Bit in `result` ist</span><span class="sxs-lookup"><span data-stu-id="b9210-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="b9210-117">1</span><span class="sxs-lookup"><span data-stu-id="b9210-117">1</span></span>|<span data-ttu-id="b9210-118">0</span><span class="sxs-lookup"><span data-stu-id="b9210-118">0</span></span>|  
|<span data-ttu-id="b9210-119">0</span><span class="sxs-lookup"><span data-stu-id="b9210-119">0</span></span>|<span data-ttu-id="b9210-120">1</span><span class="sxs-lookup"><span data-stu-id="b9210-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="b9210-121">Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um eine exakte Ausführung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="b9210-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="b9210-122">Datentypen</span><span class="sxs-lookup"><span data-stu-id="b9210-122">Data Types</span></span>  
 <span data-ttu-id="b9210-123">Bei einer booleschen Negation wird der Datentyp des Ergebnisses `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b9210-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="b9210-124">Bei einer bitweisen Negation ist der Ergebnis Datentyp mit dem des `expression`identisch.</span><span class="sxs-lookup"><span data-stu-id="b9210-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="b9210-125">Wenn Expression jedoch `Decimal`ist, ist das Ergebnis `Long`.</span><span class="sxs-lookup"><span data-stu-id="b9210-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b9210-126">Überladen</span><span class="sxs-lookup"><span data-stu-id="b9210-126">Overloading</span></span>  
 <span data-ttu-id="b9210-127">Der `Not`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="b9210-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="b9210-128">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="b9210-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b9210-129">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b9210-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9210-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9210-130">Example</span></span>  
 <span data-ttu-id="b9210-131">Im folgenden Beispiel wird der `Not`-Operator verwendet, um eine logische Negation für einen `Boolean` Ausdruck auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b9210-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="b9210-132">Das Ergebnis ist ein `Boolean` Wert, der das Gegenteil des Werts des Ausdrucks darstellt.</span><span class="sxs-lookup"><span data-stu-id="b9210-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="b9210-133">Im vorangehenden Beispiel werden die Ergebnisse von `False` bzw. `True`erzeugt.</span><span class="sxs-lookup"><span data-stu-id="b9210-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9210-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9210-134">Example</span></span>  
 <span data-ttu-id="b9210-135">Im folgenden Beispiel wird der `Not`-Operator verwendet, um die logische Negation der einzelnen Bits eines numerischen Ausdrucks auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b9210-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="b9210-136">Das Bit im Ergebnis Muster wird auf das Gegenteil des entsprechenden Bits im Operanden Muster festgelegt, einschließlich des Signier Bits.</span><span class="sxs-lookup"><span data-stu-id="b9210-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="b9210-137">Im vorherigen Beispiel werden die Ergebnisse von – 11, – 9 bzw. – 7 erzeugt.</span><span class="sxs-lookup"><span data-stu-id="b9210-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9210-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9210-138">See also</span></span>

- [<span data-ttu-id="b9210-139">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9210-139">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="b9210-140">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9210-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b9210-141">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="b9210-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b9210-142">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b9210-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
