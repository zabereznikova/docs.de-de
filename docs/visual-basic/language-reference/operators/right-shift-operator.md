---
title: '>> Operator (Visual Basic)'
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
ms.openlocfilehash: 337d651e831dc2ab132056f6e9a1f2b5300bf7f8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701329"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="123f6-102">> > Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="123f6-102">>> Operator (Visual Basic)</span></span>
<span data-ttu-id="123f6-103">Führt eine arithmetische Rechtsverschiebung in einem Bitmuster aus.</span><span class="sxs-lookup"><span data-stu-id="123f6-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="123f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="123f6-104">Syntax</span></span>  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="123f6-105">Teile</span><span class="sxs-lookup"><span data-stu-id="123f6-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="123f6-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="123f6-106">Required.</span></span> <span data-ttu-id="123f6-107">Ganzzahliger numerischer Wert.</span><span class="sxs-lookup"><span data-stu-id="123f6-107">Integral numeric value.</span></span> <span data-ttu-id="123f6-108">Das Ergebnis der Verschiebung des Bitmusters.</span><span class="sxs-lookup"><span data-stu-id="123f6-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="123f6-109">Der-Datentyp ist mit dem von `pattern`identisch.</span><span class="sxs-lookup"><span data-stu-id="123f6-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="123f6-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="123f6-110">Required.</span></span> <span data-ttu-id="123f6-111">Ganzzahliger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="123f6-111">Integral numeric expression.</span></span> <span data-ttu-id="123f6-112">Das Bitmuster, das verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="123f6-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="123f6-113">Der Datentyp muss ein ganzzahliger Typ`SByte`( `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`) sein.</span><span class="sxs-lookup"><span data-stu-id="123f6-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="123f6-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="123f6-114">Required.</span></span> <span data-ttu-id="123f6-115">Numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="123f6-115">Numeric expression.</span></span> <span data-ttu-id="123f6-116">Die Anzahl der Bits, um die das Bitmuster verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="123f6-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="123f6-117">Der Datentyp muss oder `Integer` `Integer`erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="123f6-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="123f6-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="123f6-118">Remarks</span></span>  
 <span data-ttu-id="123f6-119">Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="123f6-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="123f6-120">In einer arithmetischen rechten Schicht werden die Bits, die über die bitmost-Bitposition hinaus verschoben werden, verworfen, und das äußteste äußteste Bit (Vorzeichen) wird an die auf der linken Seite freigegebenen Bitpositionen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="123f6-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="123f6-121">Dies bedeutet Folgendes: Wenn `pattern` einen negativen Wert aufweist, werden die frei gewordenen Positionen auf 1 festgelegt. Andernfalls werden Sie auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="123f6-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="123f6-122">Beachten Sie, dass die Datentypen `Byte`, `UShort`, `UInteger` und `ULong` nicht signiert sind, sodass kein Signier Bit vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="123f6-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="123f6-123">Wenn `pattern` einen beliebigen Typ ohne Vorzeichen aufweist, werden die frei gewordenen Positionen immer auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="123f6-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="123f6-124">Um zu verhindern, dass mehr Bits verschoben werden, als das Ergebnis aufnehmen kann, Visual Basic den Wert `amount` mit einer Größen Maske, die dem Datentyp von `pattern` entspricht, maskiert.</span><span class="sxs-lookup"><span data-stu-id="123f6-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="123f6-125">Die Binärdatei und diese Werte werden für die UMSCHALT Menge verwendet.</span><span class="sxs-lookup"><span data-stu-id="123f6-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="123f6-126">Die Größen Masken lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="123f6-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="123f6-127">Datentyp von `pattern`</span><span class="sxs-lookup"><span data-stu-id="123f6-127">Data type of `pattern`</span></span>|<span data-ttu-id="123f6-128">Größen Maske (dezimal)</span><span class="sxs-lookup"><span data-stu-id="123f6-128">Size mask (decimal)</span></span>|<span data-ttu-id="123f6-129">Größen Maske (hexadezimal)</span><span class="sxs-lookup"><span data-stu-id="123f6-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="123f6-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="123f6-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="123f6-131">7</span><span class="sxs-lookup"><span data-stu-id="123f6-131">7</span></span>|<span data-ttu-id="123f6-132">& H00000007</span><span class="sxs-lookup"><span data-stu-id="123f6-132">&H00000007</span></span>|  
|<span data-ttu-id="123f6-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="123f6-133">`Short`, `UShort`</span></span>|<span data-ttu-id="123f6-134">15</span><span class="sxs-lookup"><span data-stu-id="123f6-134">15</span></span>|<span data-ttu-id="123f6-135">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="123f6-135">&H0000000F</span></span>|  
|<span data-ttu-id="123f6-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="123f6-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="123f6-137">31</span><span class="sxs-lookup"><span data-stu-id="123f6-137">31</span></span>|<span data-ttu-id="123f6-138">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="123f6-138">&H0000001F</span></span>|  
|<span data-ttu-id="123f6-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="123f6-139">`Long`, `ULong`</span></span>|<span data-ttu-id="123f6-140">63</span><span class="sxs-lookup"><span data-stu-id="123f6-140">63</span></span>|<span data-ttu-id="123f6-141">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="123f6-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="123f6-142">Wenn `amount` 0 (null) ist, ist der Wert von `result` mit dem Wert von `pattern` identisch.</span><span class="sxs-lookup"><span data-stu-id="123f6-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="123f6-143">Wenn `amount` negativ ist, wird es als nicht signierter Wert angenommen und mit der entsprechenden Größen Maske maskiert.</span><span class="sxs-lookup"><span data-stu-id="123f6-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="123f6-144">Arithmetische Verschiebungen generieren niemals Überlauf Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="123f6-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="123f6-145">Überladen</span><span class="sxs-lookup"><span data-stu-id="123f6-145">Overloading</span></span>  
 <span data-ttu-id="123f6-146">Der `>>`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="123f6-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="123f6-147">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="123f6-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="123f6-148">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="123f6-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="123f6-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="123f6-149">Example</span></span>  
 <span data-ttu-id="123f6-150">Im folgenden Beispiel wird der `>>`-Operator verwendet, um arithmetische Rechte Verschiebungen für ganzzahlige Werte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="123f6-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="123f6-151">Das Ergebnis weist immer den gleichen Datentyp wie der zu Verschiebe Ausdruck auf.</span><span class="sxs-lookup"><span data-stu-id="123f6-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="123f6-152">Die Ergebnisse des vorherigen Beispiels lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="123f6-152">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="123f6-153">`result1` ist 2560 (0000 1010 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="123f6-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="123f6-154">`result2` ist 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="123f6-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="123f6-155">`result3` ist 2 (0000 0000 0000 0010).</span><span class="sxs-lookup"><span data-stu-id="123f6-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="123f6-156">`result4` ist 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="123f6-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="123f6-157">`result5` ist 0 (verschoben von 15 Stellen nach rechts).</span><span class="sxs-lookup"><span data-stu-id="123f6-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="123f6-158">Der Verschiebungs Betrag für `result4` wird als 18 und 15 berechnet, was dem Wert 2 entspricht.</span><span class="sxs-lookup"><span data-stu-id="123f6-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="123f6-159">Das folgende Beispiel zeigt arithmetische Verschiebungen bei einem negativen Wert.</span><span class="sxs-lookup"><span data-stu-id="123f6-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="123f6-160">Die Ergebnisse des vorherigen Beispiels lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="123f6-160">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="123f6-161">`negresult1` ist-512 (1111 1110 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="123f6-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="123f6-162">`negresult2` ist-1 (das Signier Bit wird weitergegeben).</span><span class="sxs-lookup"><span data-stu-id="123f6-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123f6-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="123f6-163">See also</span></span>

- [<span data-ttu-id="123f6-164">Bitverschiebungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="123f6-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="123f6-165">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="123f6-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="123f6-166">>>=-Operator</span><span class="sxs-lookup"><span data-stu-id="123f6-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [<span data-ttu-id="123f6-167">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="123f6-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="123f6-168">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="123f6-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="123f6-169">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="123f6-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
