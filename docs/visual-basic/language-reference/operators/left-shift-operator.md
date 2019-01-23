---
title: '&lt;&lt; -Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: d39a134390591e3c72887a38e8aacb4631c71d87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539037"
---
# <a name="ltlt-operator-visual-basic"></a><span data-ttu-id="85049-102">&lt;&lt; -Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85049-102">&lt;&lt; Operator (Visual Basic)</span></span>
<span data-ttu-id="85049-103">Führt eine arithmetische linksverschiebung in einem Bitmuster aus.</span><span class="sxs-lookup"><span data-stu-id="85049-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85049-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85049-104">Syntax</span></span>  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="85049-105">Teile</span><span class="sxs-lookup"><span data-stu-id="85049-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="85049-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="85049-106">Required.</span></span> <span data-ttu-id="85049-107">Ganzzahliger numerischer Wert.</span><span class="sxs-lookup"><span data-stu-id="85049-107">Integral numeric value.</span></span> <span data-ttu-id="85049-108">Das Ergebnis der Verschiebung des Bitmusters.</span><span class="sxs-lookup"><span data-stu-id="85049-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="85049-109">Der Datentyp ist identisch mit der `pattern`.</span><span class="sxs-lookup"><span data-stu-id="85049-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="85049-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="85049-110">Required.</span></span> <span data-ttu-id="85049-111">Ein ganzzahliger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="85049-111">Integral numeric expression.</span></span> <span data-ttu-id="85049-112">Das Bitmuster verschoben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="85049-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="85049-113">Der Datentyp muss ein ganzzahliger Typ sein (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).</span><span class="sxs-lookup"><span data-stu-id="85049-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="85049-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="85049-114">Required.</span></span> <span data-ttu-id="85049-115">Numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="85049-115">Numeric expression.</span></span> <span data-ttu-id="85049-116">Die Anzahl der Bits, um das Bitmuster verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="85049-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="85049-117">Der Datentyp muss `Integer` oder zu verbreitern `Integer`.</span><span class="sxs-lookup"><span data-stu-id="85049-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85049-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85049-118">Remarks</span></span>  
 <span data-ttu-id="85049-119">Arithmetische Verschiebungen sind nicht zirkuläre, was bedeutet die Bits verschoben aus einem Ende des Resultsets nicht am anderen Ende wieder eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="85049-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="85049-120">In eine arithmetische Verschiebung nach links die Bits, die außerhalb des Gültigkeitsbereichs für den Ergebnisdatentyp verschoben werden verworfen, und die Bitpositionen auf der rechten Seite werden auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="85049-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="85049-121">Um zu verhindern, dass eine Verschiebung um mehr Bits, die als Ergebnis werden kann, maskiert Visual Basic den Wert der `amount` mit einer Größenmaske, die den Datentyp der entspricht `pattern`.</span><span class="sxs-lookup"><span data-stu-id="85049-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="85049-122">Das binäre AND der folgenden Werte wird für den Betrag der Verschiebung verwendet.</span><span class="sxs-lookup"><span data-stu-id="85049-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="85049-123">Die Größenmasken lauten wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="85049-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="85049-124">Datentyp `pattern`</span><span class="sxs-lookup"><span data-stu-id="85049-124">Data type of `pattern`</span></span>|<span data-ttu-id="85049-125">Size-Maske (dezimal)</span><span class="sxs-lookup"><span data-stu-id="85049-125">Size mask (decimal)</span></span>|<span data-ttu-id="85049-126">Size-Maske (hexadezimal)</span><span class="sxs-lookup"><span data-stu-id="85049-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="85049-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="85049-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="85049-128">7</span><span class="sxs-lookup"><span data-stu-id="85049-128">7</span></span>|<span data-ttu-id="85049-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="85049-129">&H00000007</span></span>|  
|<span data-ttu-id="85049-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="85049-130">`Short`, `UShort`</span></span>|<span data-ttu-id="85049-131">15</span><span class="sxs-lookup"><span data-stu-id="85049-131">15</span></span>|<span data-ttu-id="85049-132">&AMP; H0000000F</span><span class="sxs-lookup"><span data-stu-id="85049-132">&H0000000F</span></span>|  
|<span data-ttu-id="85049-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="85049-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="85049-134">31</span><span class="sxs-lookup"><span data-stu-id="85049-134">31</span></span>|<span data-ttu-id="85049-135">&AMP; H0000001F</span><span class="sxs-lookup"><span data-stu-id="85049-135">&H0000001F</span></span>|  
|<span data-ttu-id="85049-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="85049-136">`Long`, `ULong`</span></span>|<span data-ttu-id="85049-137">63</span><span class="sxs-lookup"><span data-stu-id="85049-137">63</span></span>|<span data-ttu-id="85049-138">&AMP; H0000003F</span><span class="sxs-lookup"><span data-stu-id="85049-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="85049-139">Wenn `amount` NULL ist, den Wert der `result` ist identisch mit dem Wert des `pattern`.</span><span class="sxs-lookup"><span data-stu-id="85049-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="85049-140">Wenn `amount` ist negativ, dabei handelt es sich als ein Wert ohne Vorzeichen mit der entsprechenden Größe maskiert.</span><span class="sxs-lookup"><span data-stu-id="85049-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="85049-141">Arithmetische Schichten generieren keine Stapelüberlauf-Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="85049-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85049-142">Die `<<` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="85049-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="85049-143">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="85049-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="85049-144">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="85049-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85049-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85049-145">Example</span></span>  
 <span data-ttu-id="85049-146">Im folgenden Beispiel wird die `<<` Operator, um die Durchführung von Berechnungen nach links verschiebt für ganzzahlige Werte.</span><span class="sxs-lookup"><span data-stu-id="85049-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="85049-147">Das Ergebnis hat immer den gleichen Datentyp wie der Ausdruck, der verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="85049-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-operator_1.vb)]  
  
 <span data-ttu-id="85049-148">Die Ergebnisse des vorherigen Beispiels sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="85049-148">The results of the previous example are as follows:</span></span>  
  
-   <span data-ttu-id="85049-149">`result1` ist Sie 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="85049-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
-   <span data-ttu-id="85049-150">`result2` 3072 (1100-0000-0000 0000) ist.</span><span class="sxs-lookup"><span data-stu-id="85049-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
-   <span data-ttu-id="85049-151">`result3` ist-32768 (1000-0000-0000-0000).</span><span class="sxs-lookup"><span data-stu-id="85049-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
-   <span data-ttu-id="85049-152">`result4` ist 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="85049-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
-   <span data-ttu-id="85049-153">`result5` ist 0 (15 Stellen links verschoben).</span><span class="sxs-lookup"><span data-stu-id="85049-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="85049-154">Der Betrag der Verschiebung für `result4` wird berechnet als 17 und 15, die gleich 1 ist.</span><span class="sxs-lookup"><span data-stu-id="85049-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85049-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85049-155">See also</span></span>
- [<span data-ttu-id="85049-156">Bitverschiebungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="85049-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="85049-157">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="85049-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="85049-158"><<=-Operator</span><span class="sxs-lookup"><span data-stu-id="85049-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="85049-159">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85049-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="85049-160">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="85049-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="85049-161">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85049-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
