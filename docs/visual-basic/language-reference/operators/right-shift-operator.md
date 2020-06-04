---
title: '>> Operator'
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
ms.openlocfilehash: 10b07da22b8b43d6a966fa7c334ac6a0ef4b430d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406365"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="7d3d8-102">>> -Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d3d8-102">>> Operator (Visual Basic)</span></span>
<span data-ttu-id="7d3d8-103">Führt eine arithmetische Rechtsverschiebung in einem Bitmuster aus.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d3d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d3d8-104">Syntax</span></span>  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="7d3d8-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="7d3d8-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7d3d8-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-106">Required.</span></span> <span data-ttu-id="7d3d8-107">Ganzzahliger numerischer Wert.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-107">Integral numeric value.</span></span> <span data-ttu-id="7d3d8-108">Das Ergebnis der Verschiebung des Bitmusters.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="7d3d8-109">Der Datentyp entspricht dem von `pattern`.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="7d3d8-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-110">Required.</span></span> <span data-ttu-id="7d3d8-111">Ein ganzzahliger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-111">Integral numeric expression.</span></span> <span data-ttu-id="7d3d8-112">Das zu verschiebende Bitmuster.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="7d3d8-113">Der Datentyp muss ein ganzzahliger Typ (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` oder `ULong`) sein.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="7d3d8-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-114">Required.</span></span> <span data-ttu-id="7d3d8-115">Ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-115">Numeric expression.</span></span> <span data-ttu-id="7d3d8-116">Die Anzahl der Bits, um die das Bitmuster verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="7d3d8-117">Der Datentyp muss `Integer` sein oder zu `Integer` erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d3d8-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7d3d8-118">Remarks</span></span>  
 <span data-ttu-id="7d3d8-119">Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="7d3d8-120">In einer arithmetischen rechten Schicht werden die Bits, die über die bitmost-Bitposition hinaus verschoben werden, verworfen, und das äußteste äußteste Bit (Vorzeichen) wird an die auf der linken Seite freigegebenen Bitpositionen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="7d3d8-121">Dies bedeutet, dass bei `pattern` einem negativen Wert die frei gewordenen Positionen auf 1 festgelegt werden. andernfalls werden Sie auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="7d3d8-122">Beachten Sie, dass die Datentypen,, `Byte` `UShort` `UInteger` und `ULong` nicht signiert sind, sodass kein Signier Bit vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="7d3d8-123">Wenn `pattern` vom Typ "Ganzzahl ohne Vorzeichen" ist, werden die frei gewordenen Positionen immer auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="7d3d8-124">Um zu verhindern, dass mehr Bits verschoben werden, als das Ergebnis enthalten kann, wird Visual Basic den Wert von `amount` mit einer Größen Maske maskiert, die dem Datentyp von entspricht `pattern` .</span><span class="sxs-lookup"><span data-stu-id="7d3d8-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="7d3d8-125">Die Binärdatei und diese Werte werden für die UMSCHALT Menge verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="7d3d8-126">Die Größen Masken lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7d3d8-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="7d3d8-127">Datentyp von`pattern`</span><span class="sxs-lookup"><span data-stu-id="7d3d8-127">Data type of `pattern`</span></span>|<span data-ttu-id="7d3d8-128">Größen Maske (dezimal)</span><span class="sxs-lookup"><span data-stu-id="7d3d8-128">Size mask (decimal)</span></span>|<span data-ttu-id="7d3d8-129">Größen Maske (hexadezimal)</span><span class="sxs-lookup"><span data-stu-id="7d3d8-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="7d3d8-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="7d3d8-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="7d3d8-131">7</span><span class="sxs-lookup"><span data-stu-id="7d3d8-131">7</span></span>|<span data-ttu-id="7d3d8-132">&H00000007</span><span class="sxs-lookup"><span data-stu-id="7d3d8-132">&H00000007</span></span>|  
|<span data-ttu-id="7d3d8-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="7d3d8-133">`Short`, `UShort`</span></span>|<span data-ttu-id="7d3d8-134">15</span><span class="sxs-lookup"><span data-stu-id="7d3d8-134">15</span></span>|<span data-ttu-id="7d3d8-135">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="7d3d8-135">&H0000000F</span></span>|  
|<span data-ttu-id="7d3d8-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="7d3d8-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="7d3d8-137">31</span><span class="sxs-lookup"><span data-stu-id="7d3d8-137">31</span></span>|<span data-ttu-id="7d3d8-138">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="7d3d8-138">&H0000001F</span></span>|  
|<span data-ttu-id="7d3d8-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="7d3d8-139">`Long`, `ULong`</span></span>|<span data-ttu-id="7d3d8-140">63</span><span class="sxs-lookup"><span data-stu-id="7d3d8-140">63</span></span>|<span data-ttu-id="7d3d8-141">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="7d3d8-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="7d3d8-142">Wenn `amount` 0 (null) ist, ist der Wert von `result` mit dem Wert von identisch `pattern` .</span><span class="sxs-lookup"><span data-stu-id="7d3d8-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="7d3d8-143">Wenn `amount` negativ ist, wird es als nicht signierter Wert angenommen und mit der entsprechenden Größen Maske maskiert.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="7d3d8-144">Arithmetische Verschiebungen generieren niemals Überlauf Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7d3d8-145">Überladen</span><span class="sxs-lookup"><span data-stu-id="7d3d8-145">Overloading</span></span>  
 <span data-ttu-id="7d3d8-146">Der `>>` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7d3d8-147">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7d3d8-148">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7d3d8-148">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d3d8-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d3d8-149">Example</span></span>  
 <span data-ttu-id="7d3d8-150">Im folgenden Beispiel wird der- `>>` Operator verwendet, um arithmetische Rechte Verschiebungen für ganzzahlige Werte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="7d3d8-151">Das Ergebnis weist immer den gleichen Datentyp wie der zu Verschiebe Ausdruck auf.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 <span data-ttu-id="7d3d8-152">Die Ergebnisse des vorherigen Beispiels lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7d3d8-152">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="7d3d8-153">`result1`ist 2560 (0000 1010 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="7d3d8-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
- <span data-ttu-id="7d3d8-154">`result2`ist 160 (0000 0000 1010 0000).</span><span class="sxs-lookup"><span data-stu-id="7d3d8-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
- <span data-ttu-id="7d3d8-155">`result3`ist 2 (0000 0000 0000 0010).</span><span class="sxs-lookup"><span data-stu-id="7d3d8-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
- <span data-ttu-id="7d3d8-156">`result4`ist 640 (0000 0010 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="7d3d8-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
- <span data-ttu-id="7d3d8-157">`result5`ist 0 (in 15 Stellen nach rechts verschoben).</span><span class="sxs-lookup"><span data-stu-id="7d3d8-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="7d3d8-158">Die UMSCHALT Menge für `result4` wird als 18 und 15 berechnet, was dem Wert 2 entspricht.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="7d3d8-159">Das folgende Beispiel zeigt arithmetische Verschiebungen bei einem negativen Wert.</span><span class="sxs-lookup"><span data-stu-id="7d3d8-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 <span data-ttu-id="7d3d8-160">Die Ergebnisse des vorherigen Beispiels lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7d3d8-160">The results of the preceding example are as follows:</span></span>  
  
- <span data-ttu-id="7d3d8-161">`negresult1`ist-512 (1111 1110 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="7d3d8-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
- <span data-ttu-id="7d3d8-162">`negresult2`ist-1 (das Signier Bit wird weitergegeben).</span><span class="sxs-lookup"><span data-stu-id="7d3d8-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d3d8-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d3d8-163">See also</span></span>

- [<span data-ttu-id="7d3d8-164">Bitschiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="7d3d8-164">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="7d3d8-165">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="7d3d8-165">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="7d3d8-166">>>=-Operator</span><span class="sxs-lookup"><span data-stu-id="7d3d8-166">>>= Operator</span></span>](right-shift-assignment-operator.md)
- [<span data-ttu-id="7d3d8-167">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d3d8-167">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="7d3d8-168">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="7d3d8-168">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="7d3d8-169">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d3d8-169">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
