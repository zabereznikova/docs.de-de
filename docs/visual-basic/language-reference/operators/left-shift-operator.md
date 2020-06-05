---
title: <<-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 1128b32a739e7dbf3893dcd19b37247cd4643c85
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370634"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="d256f-102">\<\<Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d256f-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="d256f-103">Führt eine arithmetische linke Verschiebung in einem Bitmuster aus.</span><span class="sxs-lookup"><span data-stu-id="d256f-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d256f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d256f-104">Syntax</span></span>  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="d256f-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="d256f-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="d256f-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d256f-106">Required.</span></span> <span data-ttu-id="d256f-107">Ganzzahliger numerischer Wert.</span><span class="sxs-lookup"><span data-stu-id="d256f-107">Integral numeric value.</span></span> <span data-ttu-id="d256f-108">Das Ergebnis der Verschiebung des Bitmusters.</span><span class="sxs-lookup"><span data-stu-id="d256f-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="d256f-109">Der Datentyp entspricht dem von `pattern`.</span><span class="sxs-lookup"><span data-stu-id="d256f-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="d256f-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d256f-110">Required.</span></span> <span data-ttu-id="d256f-111">Ein ganzzahliger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="d256f-111">Integral numeric expression.</span></span> <span data-ttu-id="d256f-112">Das zu verschiebende Bitmuster.</span><span class="sxs-lookup"><span data-stu-id="d256f-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="d256f-113">Der Datentyp muss ein ganzzahliger Typ (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` oder `ULong`) sein.</span><span class="sxs-lookup"><span data-stu-id="d256f-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="d256f-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d256f-114">Required.</span></span> <span data-ttu-id="d256f-115">Ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="d256f-115">Numeric expression.</span></span> <span data-ttu-id="d256f-116">Die Anzahl der Bits, um die das Bitmuster verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="d256f-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="d256f-117">Der Datentyp muss `Integer` sein oder zu `Integer` erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="d256f-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d256f-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d256f-118">Remarks</span></span>  
 <span data-ttu-id="d256f-119">Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d256f-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="d256f-120">In einer arithmetischen linken Schicht werden die Bits, die nach dem Bereich des Ergebnis Datentyps verschoben werden, verworfen, und die auf der rechten Seite frei gewordenen Bitpositionen werden auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d256f-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="d256f-121">Um eine Verschiebung um mehr Bits zu verhindern, als das Ergebnis enthalten kann, Visual Basic den Wert von `amount` mit einer Größen Maske, die dem Datentyp von entspricht `pattern` .</span><span class="sxs-lookup"><span data-stu-id="d256f-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="d256f-122">Die Binärdatei und diese Werte werden für die UMSCHALT Menge verwendet.</span><span class="sxs-lookup"><span data-stu-id="d256f-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="d256f-123">Die Größen Masken lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d256f-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="d256f-124">Datentyp von`pattern`</span><span class="sxs-lookup"><span data-stu-id="d256f-124">Data type of `pattern`</span></span>|<span data-ttu-id="d256f-125">Größen Maske (dezimal)</span><span class="sxs-lookup"><span data-stu-id="d256f-125">Size mask (decimal)</span></span>|<span data-ttu-id="d256f-126">Größen Maske (hexadezimal)</span><span class="sxs-lookup"><span data-stu-id="d256f-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="d256f-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="d256f-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="d256f-128">7</span><span class="sxs-lookup"><span data-stu-id="d256f-128">7</span></span>|<span data-ttu-id="d256f-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="d256f-129">&H00000007</span></span>|  
|<span data-ttu-id="d256f-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="d256f-130">`Short`, `UShort`</span></span>|<span data-ttu-id="d256f-131">15</span><span class="sxs-lookup"><span data-stu-id="d256f-131">15</span></span>|<span data-ttu-id="d256f-132">&H0000000F</span><span class="sxs-lookup"><span data-stu-id="d256f-132">&H0000000F</span></span>|  
|<span data-ttu-id="d256f-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="d256f-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="d256f-134">31</span><span class="sxs-lookup"><span data-stu-id="d256f-134">31</span></span>|<span data-ttu-id="d256f-135">&H0000001F</span><span class="sxs-lookup"><span data-stu-id="d256f-135">&H0000001F</span></span>|  
|<span data-ttu-id="d256f-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="d256f-136">`Long`, `ULong`</span></span>|<span data-ttu-id="d256f-137">63</span><span class="sxs-lookup"><span data-stu-id="d256f-137">63</span></span>|<span data-ttu-id="d256f-138">&H0000003F</span><span class="sxs-lookup"><span data-stu-id="d256f-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="d256f-139">Wenn `amount` 0 (null) ist, ist der Wert von `result` mit dem Wert von identisch `pattern` .</span><span class="sxs-lookup"><span data-stu-id="d256f-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="d256f-140">Wenn `amount` negativ ist, wird es als nicht signierter Wert angenommen und mit der entsprechenden Größen Maske maskiert.</span><span class="sxs-lookup"><span data-stu-id="d256f-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="d256f-141">Arithmetische Verschiebungen generieren niemals Überlauf Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="d256f-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d256f-142">Der `<<` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="d256f-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d256f-143">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="d256f-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="d256f-144">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d256f-144">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d256f-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d256f-145">Example</span></span>  
 <span data-ttu-id="d256f-146">Im folgenden Beispiel wird der- `<<` Operator verwendet, um die arithmetischen linken Verschiebungen für ganzzahlige Werte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d256f-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="d256f-147">Das Ergebnis weist immer den gleichen Datentyp wie der zu Verschiebe Ausdruck auf.</span><span class="sxs-lookup"><span data-stu-id="d256f-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="d256f-148">Die Ergebnisse des vorherigen Beispiels lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d256f-148">The results of the previous example are as follows:</span></span>  
  
- <span data-ttu-id="d256f-149">`result1`ist 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="d256f-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
- <span data-ttu-id="d256f-150">`result2`ist 3072 (0000 1100 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="d256f-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
- <span data-ttu-id="d256f-151">`result3`ist-32768 (1000 0000 0000 0000).</span><span class="sxs-lookup"><span data-stu-id="d256f-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
- <span data-ttu-id="d256f-152">`result4`ist 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="d256f-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
- <span data-ttu-id="d256f-153">`result5`ist 0 (von 15 Stellen nach links verschoben).</span><span class="sxs-lookup"><span data-stu-id="d256f-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="d256f-154">Die UMSCHALT Menge für `result4` wird als 17 und 15 berechnet, was dem Wert 1 entspricht.</span><span class="sxs-lookup"><span data-stu-id="d256f-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d256f-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d256f-155">See also</span></span>

- [<span data-ttu-id="d256f-156">Bitschiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="d256f-156">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="d256f-157">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="d256f-157">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="d256f-158"><<=-Operator</span><span class="sxs-lookup"><span data-stu-id="d256f-158"><<= Operator</span></span>](left-shift-assignment-operator.md)
- [<span data-ttu-id="d256f-159">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d256f-159">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="d256f-160">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="d256f-160">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="d256f-161">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d256f-161">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
