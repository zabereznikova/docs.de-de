---
title: '>> -Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: 870460d78eb2e627de2984c79571fd5172672b55
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64629108"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="995f1-102">>>-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="995f1-102">>> Operator (Visual Basic)</span></span>
<span data-ttu-id="995f1-103">Führt eine arithmetische rechtsverschiebung in einem Bitmuster aus.</span><span class="sxs-lookup"><span data-stu-id="995f1-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="995f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="995f1-104">Syntax</span></span>  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="995f1-105">Teile</span><span class="sxs-lookup"><span data-stu-id="995f1-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="995f1-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="995f1-106">Required.</span></span> <span data-ttu-id="995f1-107">Ganzzahliger numerischer Wert.</span><span class="sxs-lookup"><span data-stu-id="995f1-107">Integral numeric value.</span></span> <span data-ttu-id="995f1-108">Das Ergebnis der Verschiebung des Bitmusters.</span><span class="sxs-lookup"><span data-stu-id="995f1-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="995f1-109">Der Datentyp ist identisch mit der `pattern`.</span><span class="sxs-lookup"><span data-stu-id="995f1-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="995f1-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="995f1-110">Required.</span></span> <span data-ttu-id="995f1-111">Ein ganzzahliger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="995f1-111">Integral numeric expression.</span></span> <span data-ttu-id="995f1-112">Das Bitmuster verschoben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="995f1-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="995f1-113">Der Datentyp muss ein ganzzahliger Typ sein (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).</span><span class="sxs-lookup"><span data-stu-id="995f1-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="995f1-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="995f1-114">Required.</span></span> <span data-ttu-id="995f1-115">Numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="995f1-115">Numeric expression.</span></span> <span data-ttu-id="995f1-116">Die Anzahl der Bits, um das Bitmuster verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="995f1-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="995f1-117">Der Datentyp muss `Integer` oder zu verbreitern `Integer`.</span><span class="sxs-lookup"><span data-stu-id="995f1-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="995f1-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="995f1-118">Remarks</span></span>  
 <span data-ttu-id="995f1-119">Arithmetische Verschiebungen sind nicht zirkuläre, was bedeutet die Bits verschoben aus einem Ende des Resultsets nicht am anderen Ende wieder eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="995f1-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="995f1-120">In eine arithmetische Verschiebung nach rechts die Bits, die hinter der äußere rechte Bit stellt Position verschoben werden verworfen und das Bit ganz links (Anmeldung) wird in der Bitpositionen, die auf der linken Seite weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="995f1-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="995f1-121">Dies bedeutet, dass bei `pattern` hat einen negativen Wert an, die frei werdenden Positionen auf 1 gesetzt werden; andernfalls werden sie auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="995f1-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="995f1-122">Beachten Sie, dass die Datentypen `Byte`, `UShort`, `UInteger`, und `ULong` ohne Vorzeichen sind, es gibt also keine Vorzeichenbit weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="995f1-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="995f1-123">Wenn `pattern` ist ein vorzeichenloser Typ, werden die frei werdenden Stellen immer 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="995f1-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="995f1-124">Um zu verhindern, verschieben, um mehr Bits, die als Ergebnis werden kann, maskiert Visual Basic den Wert der `amount` mit einer Größenmaske, die in den Datentyp der entsprechenden `pattern`.</span><span class="sxs-lookup"><span data-stu-id="995f1-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="995f1-125">Das binäre AND der folgenden Werte wird für den Betrag der Verschiebung verwendet.</span><span class="sxs-lookup"><span data-stu-id="995f1-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="995f1-126">Die Größenmasken lauten wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="995f1-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="995f1-127">Datentyp `pattern`</span><span class="sxs-lookup"><span data-stu-id="995f1-127">Data type of `pattern`</span></span>|<span data-ttu-id="995f1-128">Size-Maske (dezimal)</span><span class="sxs-lookup"><span data-stu-id="995f1-128">Size mask (decimal)</span></span>|<span data-ttu-id="995f1-129">Size-Maske (hexadezimal)</span><span class="sxs-lookup"><span data-stu-id="995f1-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="995f1-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="995f1-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="995f1-131">7</span><span class="sxs-lookup"><span data-stu-id="995f1-131">7</span></span>|<span data-ttu-id="995f1-132">&H00000007</span><span class="sxs-lookup"><span data-stu-id="995f1-132">&H00000007</span></span>|  
|<span data-ttu-id="995f1-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="995f1-133">`Short`, `UShort`</span></span>|<span data-ttu-id="995f1-134">15</span><span class="sxs-lookup"><span data-stu-id="995f1-134">15</span></span>|<span data-ttu-id="995f1-135">&AMP; H0000000F</span><span class="sxs-lookup"><span data-stu-id="995f1-135">&H0000000F</span></span>|  
|<span data-ttu-id="995f1-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="995f1-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="995f1-137">31</span><span class="sxs-lookup"><span data-stu-id="995f1-137">31</span></span>|<span data-ttu-id="995f1-138">&AMP; H0000001F</span><span class="sxs-lookup"><span data-stu-id="995f1-138">&H0000001F</span></span>|  
|<span data-ttu-id="995f1-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="995f1-139">`Long`, `ULong`</span></span>|<span data-ttu-id="995f1-140">63</span><span class="sxs-lookup"><span data-stu-id="995f1-140">63</span></span>|<span data-ttu-id="995f1-141">&AMP; H0000003F</span><span class="sxs-lookup"><span data-stu-id="995f1-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="995f1-142">Wenn `amount` NULL ist, den Wert der `result` ist identisch mit dem Wert des `pattern`.</span><span class="sxs-lookup"><span data-stu-id="995f1-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="995f1-143">Wenn `amount` ist negativ, dabei handelt es sich als ein Wert ohne Vorzeichen mit der entsprechenden Größe maskiert.</span><span class="sxs-lookup"><span data-stu-id="995f1-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="995f1-144">Arithmetische Schichten generieren keine Stapelüberlauf-Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="995f1-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="995f1-145">Überladen</span><span class="sxs-lookup"><span data-stu-id="995f1-145">Overloading</span></span>  
 <span data-ttu-id="995f1-146">Die `>>` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="995f1-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="995f1-147">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="995f1-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="995f1-148">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="995f1-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="995f1-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="995f1-149">Example</span></span>  
 <span data-ttu-id="995f1-150">Im folgenden Beispiel wird die `>>` Operator zum Ausführen von arithmetischer rechtsverschiebungen für ganzzahlige Werte.</span><span class="sxs-lookup"><span data-stu-id="995f1-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="995f1-151">Das Ergebnis hat immer den gleichen Datentyp wie der Ausdruck, der verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="995f1-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="995f1-152">Die Ergebnisse des vorherigen Beispiels sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="995f1-152">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="995f1-153">`result1` 2560 (0000 1010-0000-0000) ist.</span><span class="sxs-lookup"><span data-stu-id="995f1-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="995f1-154">`result2` ist 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="995f1-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="995f1-155">`result3` ist 2 (0000-0000-0000-0010).</span><span class="sxs-lookup"><span data-stu-id="995f1-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="995f1-156">`result4` ist 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="995f1-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="995f1-157">`result5` ist 0 (15 Stellen nach rechts verschoben).</span><span class="sxs-lookup"><span data-stu-id="995f1-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="995f1-158">Der Betrag der Verschiebung für `result4` wird berechnet als 18 und 15, die gleich 2 ist.</span><span class="sxs-lookup"><span data-stu-id="995f1-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="995f1-159">Das folgende Beispiel zeigt die arithmetische Schichten auf einen negativen Wert.</span><span class="sxs-lookup"><span data-stu-id="995f1-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="995f1-160">Die Ergebnisse des vorherigen Beispiels sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="995f1-160">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="995f1-161">`negresult1` ist-512 (1111 1110 0000-0000).</span><span class="sxs-lookup"><span data-stu-id="995f1-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="995f1-162">`negresult2` ist-1 (das signierte Bit wird weitergegeben).</span><span class="sxs-lookup"><span data-stu-id="995f1-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="995f1-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="995f1-163">See also</span></span>

- [<span data-ttu-id="995f1-164">Bitverschiebungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="995f1-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="995f1-165">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="995f1-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="995f1-166">>>=-Operator</span><span class="sxs-lookup"><span data-stu-id="995f1-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [<span data-ttu-id="995f1-167">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="995f1-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="995f1-168">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="995f1-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="995f1-169">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="995f1-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
