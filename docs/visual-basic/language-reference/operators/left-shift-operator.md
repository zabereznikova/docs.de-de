---
title: <<-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 75c16c27dc919ba365cbe3c28c61a1e46496b0ae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824285"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="df91f-102">\<\< -Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df91f-102">\<\< Operator (Visual Basic)</span></span>
<span data-ttu-id="df91f-103">Führt eine arithmetische linksverschiebung in einem Bitmuster aus.</span><span class="sxs-lookup"><span data-stu-id="df91f-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df91f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df91f-104">Syntax</span></span>  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="df91f-105">Teile</span><span class="sxs-lookup"><span data-stu-id="df91f-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="df91f-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="df91f-106">Required.</span></span> <span data-ttu-id="df91f-107">Ganzzahliger numerischer Wert.</span><span class="sxs-lookup"><span data-stu-id="df91f-107">Integral numeric value.</span></span> <span data-ttu-id="df91f-108">Das Ergebnis der Verschiebung des Bitmusters.</span><span class="sxs-lookup"><span data-stu-id="df91f-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="df91f-109">Der Datentyp ist identisch mit der `pattern`.</span><span class="sxs-lookup"><span data-stu-id="df91f-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="df91f-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="df91f-110">Required.</span></span> <span data-ttu-id="df91f-111">Ein ganzzahliger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="df91f-111">Integral numeric expression.</span></span> <span data-ttu-id="df91f-112">Das Bitmuster verschoben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="df91f-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="df91f-113">Der Datentyp muss ein ganzzahliger Typ sein (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).</span><span class="sxs-lookup"><span data-stu-id="df91f-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="df91f-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="df91f-114">Required.</span></span> <span data-ttu-id="df91f-115">Numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="df91f-115">Numeric expression.</span></span> <span data-ttu-id="df91f-116">Die Anzahl der Bits, um das Bitmuster verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="df91f-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="df91f-117">Der Datentyp muss `Integer` oder zu verbreitern `Integer`.</span><span class="sxs-lookup"><span data-stu-id="df91f-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df91f-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df91f-118">Remarks</span></span>  
 <span data-ttu-id="df91f-119">Arithmetische Verschiebungen sind nicht zirkuläre, was bedeutet die Bits verschoben aus einem Ende des Resultsets nicht am anderen Ende wieder eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="df91f-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="df91f-120">In eine arithmetische Verschiebung nach links die Bits, die außerhalb des Gültigkeitsbereichs für den Ergebnisdatentyp verschoben werden verworfen, und die Bitpositionen auf der rechten Seite werden auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="df91f-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="df91f-121">Um zu verhindern, dass eine Verschiebung um mehr Bits, die als Ergebnis werden kann, maskiert Visual Basic den Wert der `amount` mit einer Größenmaske, die den Datentyp der entspricht `pattern`.</span><span class="sxs-lookup"><span data-stu-id="df91f-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="df91f-122">Das binäre AND der folgenden Werte wird für den Betrag der Verschiebung verwendet.</span><span class="sxs-lookup"><span data-stu-id="df91f-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="df91f-123">Die Größenmasken lauten wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="df91f-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="df91f-124">Datentyp `pattern`</span><span class="sxs-lookup"><span data-stu-id="df91f-124">Data type of `pattern`</span></span>|<span data-ttu-id="df91f-125">Size-Maske (dezimal)</span><span class="sxs-lookup"><span data-stu-id="df91f-125">Size mask (decimal)</span></span>|<span data-ttu-id="df91f-126">Size-Maske (hexadezimal)</span><span class="sxs-lookup"><span data-stu-id="df91f-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="df91f-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="df91f-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="df91f-128">7</span><span class="sxs-lookup"><span data-stu-id="df91f-128">7</span></span>|<span data-ttu-id="df91f-129">&H00000007</span><span class="sxs-lookup"><span data-stu-id="df91f-129">&H00000007</span></span>|  
|<span data-ttu-id="df91f-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="df91f-130">`Short`, `UShort`</span></span>|<span data-ttu-id="df91f-131">15</span><span class="sxs-lookup"><span data-stu-id="df91f-131">15</span></span>|<span data-ttu-id="df91f-132">&AMP; H0000000F</span><span class="sxs-lookup"><span data-stu-id="df91f-132">&H0000000F</span></span>|  
|<span data-ttu-id="df91f-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="df91f-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="df91f-134">31</span><span class="sxs-lookup"><span data-stu-id="df91f-134">31</span></span>|<span data-ttu-id="df91f-135">&AMP; H0000001F</span><span class="sxs-lookup"><span data-stu-id="df91f-135">&H0000001F</span></span>|  
|<span data-ttu-id="df91f-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="df91f-136">`Long`, `ULong`</span></span>|<span data-ttu-id="df91f-137">63</span><span class="sxs-lookup"><span data-stu-id="df91f-137">63</span></span>|<span data-ttu-id="df91f-138">&AMP; H0000003F</span><span class="sxs-lookup"><span data-stu-id="df91f-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="df91f-139">Wenn `amount` NULL ist, den Wert der `result` ist identisch mit dem Wert des `pattern`.</span><span class="sxs-lookup"><span data-stu-id="df91f-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="df91f-140">Wenn `amount` ist negativ, dabei handelt es sich als ein Wert ohne Vorzeichen mit der entsprechenden Größe maskiert.</span><span class="sxs-lookup"><span data-stu-id="df91f-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="df91f-141">Arithmetische Schichten generieren keine Stapelüberlauf-Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="df91f-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df91f-142">Die `<<` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="df91f-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="df91f-143">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="df91f-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="df91f-144">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="df91f-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="df91f-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df91f-145">Example</span></span>  
 <span data-ttu-id="df91f-146">Im folgenden Beispiel wird die `<<` Operator, um die Durchführung von Berechnungen nach links verschiebt für ganzzahlige Werte.</span><span class="sxs-lookup"><span data-stu-id="df91f-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="df91f-147">Das Ergebnis hat immer den gleichen Datentyp wie der Ausdruck, der verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="df91f-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 <span data-ttu-id="df91f-148">Die Ergebnisse des vorherigen Beispiels sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="df91f-148">The results of the previous example are as follows:</span></span>  
  
-   <span data-ttu-id="df91f-149">`result1` ist Sie 192 (0000 0000 1100 0000).</span><span class="sxs-lookup"><span data-stu-id="df91f-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
-   <span data-ttu-id="df91f-150">`result2` 3072 (1100-0000-0000 0000) ist.</span><span class="sxs-lookup"><span data-stu-id="df91f-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
-   <span data-ttu-id="df91f-151">`result3` ist-32768 (1000-0000-0000-0000).</span><span class="sxs-lookup"><span data-stu-id="df91f-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
-   <span data-ttu-id="df91f-152">`result4` ist 384 (0000 0001 1000 0000).</span><span class="sxs-lookup"><span data-stu-id="df91f-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
-   <span data-ttu-id="df91f-153">`result5` ist 0 (15 Stellen links verschoben).</span><span class="sxs-lookup"><span data-stu-id="df91f-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="df91f-154">Der Betrag der Verschiebung für `result4` wird berechnet als 17 und 15, die gleich 1 ist.</span><span class="sxs-lookup"><span data-stu-id="df91f-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df91f-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df91f-155">See also</span></span>

- [<span data-ttu-id="df91f-156">Bitverschiebungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="df91f-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="df91f-157">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="df91f-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="df91f-158"><<=-Operator</span><span class="sxs-lookup"><span data-stu-id="df91f-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [<span data-ttu-id="df91f-159">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df91f-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="df91f-160">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="df91f-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="df91f-161">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df91f-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
