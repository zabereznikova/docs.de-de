---
title: '&gt;&gt;Operator (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4eb0ed817c95905a679de5026bf6494eb72df078
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="881f5-102">&gt;&gt;Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="881f5-102">&gt;&gt; Operator (Visual Basic)</span></span>
<span data-ttu-id="881f5-103">Führt eine arithmetische rechtsverschiebung in einem Bitmuster aus.</span><span class="sxs-lookup"><span data-stu-id="881f5-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="881f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="881f5-104">Syntax</span></span>  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="881f5-105">Teile</span><span class="sxs-lookup"><span data-stu-id="881f5-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="881f5-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="881f5-106">Required.</span></span> <span data-ttu-id="881f5-107">Ganzzahlige numerische Wert ist.</span><span class="sxs-lookup"><span data-stu-id="881f5-107">Integral numeric value.</span></span> <span data-ttu-id="881f5-108">Das Ergebnis der Verschiebung des Bitmusters.</span><span class="sxs-lookup"><span data-stu-id="881f5-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="881f5-109">Der Datentyp ist dieselbe wie `pattern`.</span><span class="sxs-lookup"><span data-stu-id="881f5-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="881f5-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="881f5-110">Required.</span></span> <span data-ttu-id="881f5-111">Ganzzahlige numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="881f5-111">Integral numeric expression.</span></span> <span data-ttu-id="881f5-112">Das Bitmuster verschoben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="881f5-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="881f5-113">Der Datentyp muss ein ganzzahliger Typ sein (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).</span><span class="sxs-lookup"><span data-stu-id="881f5-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="881f5-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="881f5-114">Required.</span></span> <span data-ttu-id="881f5-115">Numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="881f5-115">Numeric expression.</span></span> <span data-ttu-id="881f5-116">Die Anzahl der zu verschiebenden Bitmusters Bits.</span><span class="sxs-lookup"><span data-stu-id="881f5-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="881f5-117">Der Datentyp muss `Integer` oder erweitert werden, um `Integer`.</span><span class="sxs-lookup"><span data-stu-id="881f5-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="881f5-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="881f5-118">Remarks</span></span>  
 <span data-ttu-id="881f5-119">Arithmetische Schichten sind nicht zirkulär, d. h. die Bits verschobene ein Ende des Resultsets nicht am anderen Ende wieder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="881f5-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="881f5-120">Klicken Sie in eine arithmetische Verschiebung nach rechts die Bits hinter Bit ganz rechts verschoben werden verworfen, und das am weitesten links stehende (Vorzeichenbit) wird in die auf der linken Seite frei gewordene Bitpositionen übertragen.</span><span class="sxs-lookup"><span data-stu-id="881f5-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="881f5-121">Dies bedeutet, dass bei `pattern` hat einen negativen Wert werden die frei werdenden Positionen auf einen festgelegt; andernfalls sind sie auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="881f5-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="881f5-122">Beachten Sie, dass die Datentypen `Byte`, `UShort`, `UInteger`, und `ULong` sind, es gibt also keine Vorzeichenbit weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="881f5-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="881f5-123">Wenn `pattern` weist eine nicht signierte Typ, die frei werdenden Positionen immer auf 0 (null) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="881f5-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="881f5-124">Um zu verhindern, Verschieben von mehr Bits, als das Ergebnis aufnehmen kann, maskiert Visual Basic den Wert der `amount` mit einer Größenmaske, die in den Datentyp der entsprechenden `pattern`.</span><span class="sxs-lookup"><span data-stu-id="881f5-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="881f5-125">Das binäre AND dieser Werte wird für den Betrag der Verschiebung verwendet.</span><span class="sxs-lookup"><span data-stu-id="881f5-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="881f5-126">Die Größenmasken lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="881f5-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="881f5-127">Datentyp`pattern`</span><span class="sxs-lookup"><span data-stu-id="881f5-127">Data type of `pattern`</span></span>|<span data-ttu-id="881f5-128">Größenmaske (dezimal)</span><span class="sxs-lookup"><span data-stu-id="881f5-128">Size mask (decimal)</span></span>|<span data-ttu-id="881f5-129">Größenmaske (hexadezimal)</span><span class="sxs-lookup"><span data-stu-id="881f5-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="881f5-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="881f5-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="881f5-131">7</span><span class="sxs-lookup"><span data-stu-id="881f5-131">7</span></span>|<span data-ttu-id="881f5-132">& H00000007</span><span class="sxs-lookup"><span data-stu-id="881f5-132">&H00000007</span></span>|  
|<span data-ttu-id="881f5-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="881f5-133">`Short`, `UShort`</span></span>|<span data-ttu-id="881f5-134">15</span><span class="sxs-lookup"><span data-stu-id="881f5-134">15</span></span>|<span data-ttu-id="881f5-135">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="881f5-135">&H0000000F</span></span>|  
|<span data-ttu-id="881f5-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="881f5-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="881f5-137">31</span><span class="sxs-lookup"><span data-stu-id="881f5-137">31</span></span>|<span data-ttu-id="881f5-138">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="881f5-138">&H0000001F</span></span>|  
|<span data-ttu-id="881f5-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="881f5-139">`Long`, `ULong`</span></span>|<span data-ttu-id="881f5-140">63</span><span class="sxs-lookup"><span data-stu-id="881f5-140">63</span></span>|<span data-ttu-id="881f5-141">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="881f5-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="881f5-142">Wenn `amount` gleich NULL ist, werden den Wert der `result` ist identisch mit dem Wert des `pattern`.</span><span class="sxs-lookup"><span data-stu-id="881f5-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="881f5-143">Wenn `amount` ist negativ ist, es als Wert ohne Vorzeichen und wird mit der entsprechenden Größe maskiert.</span><span class="sxs-lookup"><span data-stu-id="881f5-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="881f5-144">Arithmetische Schichten generieren nie Stapelüberlauf-Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="881f5-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="881f5-145">Überladen</span><span class="sxs-lookup"><span data-stu-id="881f5-145">Overloading</span></span>  
 <span data-ttu-id="881f5-146">Die `>>` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="881f5-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="881f5-147">Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="881f5-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="881f5-148">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="881f5-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="881f5-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="881f5-149">Example</span></span>  
 <span data-ttu-id="881f5-150">Im folgenden Beispiel wird die `>>` Operator arithmetische rechtsverschiebungen für ganzzahlige Werte ausführen.</span><span class="sxs-lookup"><span data-stu-id="881f5-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="881f5-151">Das Ergebnis hat immer den gleichen Datentyp wie der zu verschiebende Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="881f5-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 <span data-ttu-id="881f5-152">Die Ergebnisse des obigen Beispiels sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="881f5-152">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="881f5-153">`result1`2560 (0000 1010 0000 0000) ist.</span><span class="sxs-lookup"><span data-stu-id="881f5-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
-   <span data-ttu-id="881f5-154">`result2`ist 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="881f5-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
-   <span data-ttu-id="881f5-155">`result3`ist 2 (0000-0000-0000-0010).</span><span class="sxs-lookup"><span data-stu-id="881f5-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
-   <span data-ttu-id="881f5-156">`result4`ist 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="881f5-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
-   <span data-ttu-id="881f5-157">`result5`ist 0 (15 Stellen rechts verschoben).</span><span class="sxs-lookup"><span data-stu-id="881f5-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="881f5-158">Der Betrag der Verschiebung für `result4` wird berechnet als 18 und 15, die gleich 2 ist.</span><span class="sxs-lookup"><span data-stu-id="881f5-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="881f5-159">Das folgende Beispiel zeigt die arithmetische Schichten auf einen negativen Wert.</span><span class="sxs-lookup"><span data-stu-id="881f5-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 <span data-ttu-id="881f5-160">Die Ergebnisse des obigen Beispiels sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="881f5-160">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="881f5-161">`negresult1`ist-512 (1111 1110 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="881f5-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
-   <span data-ttu-id="881f5-162">`negresult2`ist-1 (das Vorzeichenbit wird weitergegeben).</span><span class="sxs-lookup"><span data-stu-id="881f5-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="881f5-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="881f5-163">See Also</span></span>  
 [<span data-ttu-id="881f5-164">Bitverschiebungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="881f5-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="881f5-165">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="881f5-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="881f5-166">>>=-Operator</span><span class="sxs-lookup"><span data-stu-id="881f5-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)  
 [<span data-ttu-id="881f5-167">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="881f5-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="881f5-168">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="881f5-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="881f5-169">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="881f5-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
