---
title: /-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: 17eb3eddfae3cf7c818514a2fee20f646876a6ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604522"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ae32d-102">/-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae32d-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="ae32d-103">Dividiert zwei Zahlen und gibt ein Gleitkommaergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="ae32d-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae32d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae32d-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="ae32d-105">Teile</span><span class="sxs-lookup"><span data-stu-id="ae32d-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="ae32d-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ae32d-106">Required.</span></span> <span data-ttu-id="ae32d-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ae32d-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="ae32d-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ae32d-108">Required.</span></span> <span data-ttu-id="ae32d-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ae32d-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="ae32d-110">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="ae32d-110">Supported Types</span></span>  
 <span data-ttu-id="ae32d-111">Alle numerischen Typen, einschließlich der Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ae32d-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="ae32d-112">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="ae32d-112">Result</span></span>  
 <span data-ttu-id="ae32d-113">Das Ergebnis ist der vollständige Quotient aus `expression1` geteilt durch `expression2`, einschließlich des Rests.</span><span class="sxs-lookup"><span data-stu-id="ae32d-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="ae32d-114">Die [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den Quotienten ganze Zahl zurück, die im weiteren Verlauf gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ae32d-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae32d-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ae32d-115">Remarks</span></span>  
 <span data-ttu-id="ae32d-116">Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab.</span><span class="sxs-lookup"><span data-stu-id="ae32d-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="ae32d-117">Die folgende Tabelle zeigt, wie der Datentyp des Ergebnisses bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="ae32d-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="ae32d-118">Datentypen der Operanden</span><span class="sxs-lookup"><span data-stu-id="ae32d-118">Operand data types</span></span>|<span data-ttu-id="ae32d-119">Der Ergebnisdatentyp</span><span class="sxs-lookup"><span data-stu-id="ae32d-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="ae32d-120">Beide Ausdrücke sind ganzzahlige Datentypen (["SByte"](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [kurze](../../../visual-basic/language-reference/data-types/short-data-type.md), ["ushort"](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Ganzzahl](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [lange](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="ae32d-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="ae32d-121">Ein Ausdruck ist eine [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) -Datentyp und der andere wird keine [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="ae32d-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="ae32d-122">Ein Ausdruck ist eine [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -Datentyp und der andere wird keine [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) oder ein [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="ae32d-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="ae32d-123">Einer der Ausdrücke ist ein [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) -Datentyp</span><span class="sxs-lookup"><span data-stu-id="ae32d-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="ae32d-124">Bevor Division ausgeführt wird, werden alle ganzzahligen numerischen Ausdrücke auf Erweitert `Double`.</span><span class="sxs-lookup"><span data-stu-id="ae32d-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="ae32d-125">Wenn Sie das Ergebnis in einen ganzzahligen Datentyp zuweisen, versucht Visual Basic konvertieren das Ergebnis von `Double` auf diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="ae32d-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="ae32d-126">Dies kann eine Ausnahme ausgelöst, wenn das Ergebnis nicht in diesem Typ passt.</span><span class="sxs-lookup"><span data-stu-id="ae32d-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="ae32d-127">Insbesondere finden Sie unter "Division durch Null versucht" auf dieser Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="ae32d-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="ae32d-128">Wenn `expression1` oder `expression2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird dies als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="ae32d-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="ae32d-129">Versuchte Division durch 0 (null)</span><span class="sxs-lookup"><span data-stu-id="ae32d-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="ae32d-130">Wenn `expression2` ergibt 0 (null), die `/` Operator weist unterschiedliches Verhaltensweisen für unterschiedliche Operandendatentypen.</span><span class="sxs-lookup"><span data-stu-id="ae32d-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="ae32d-131">Die folgende Tabelle zeigt die möglichen Verhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="ae32d-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="ae32d-132">Datentypen der Operanden</span><span class="sxs-lookup"><span data-stu-id="ae32d-132">Operand data types</span></span>|<span data-ttu-id="ae32d-133">Verhalten Wenn `expression2` 0 (null)</span><span class="sxs-lookup"><span data-stu-id="ae32d-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="ae32d-134">Gleitkomma (`Single` oder `Double`)</span><span class="sxs-lookup"><span data-stu-id="ae32d-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="ae32d-135">Gibt unendlich (<xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity>), oder <xref:System.Double.NaN> (keine Zahl) Wenn `expression1` ist auch 0 (null)</span><span class="sxs-lookup"><span data-stu-id="ae32d-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="ae32d-136">Löst aus <xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="ae32d-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="ae32d-137">Ganzzahltypen (mit oder ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="ae32d-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="ae32d-138">Wechsel zurück in den ganzzahligen Typ löst versucht <xref:System.OverflowException> da Ganzzahltypen nicht akzeptieren können <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, oder <xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="ae32d-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ae32d-139">Die `/` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="ae32d-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ae32d-140">Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="ae32d-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ae32d-141">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ae32d-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae32d-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae32d-142">Example</span></span>  
 <span data-ttu-id="ae32d-143">Dieses Beispiel verwendet die `/` Operator Gleitkommadivision ausführen.</span><span class="sxs-lookup"><span data-stu-id="ae32d-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="ae32d-144">Das Ergebnis ist der Quotient der beiden Operanden.</span><span class="sxs-lookup"><span data-stu-id="ae32d-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 <span data-ttu-id="ae32d-145">Die Ausdrücke im vorangehenden Beispiel Rückgabewerte 2,5 und 3,333333 zurück.</span><span class="sxs-lookup"><span data-stu-id="ae32d-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="ae32d-146">Beachten Sie, dass das Ergebnis immer Gleitkomma (`Double`), auch wenn beide Operanden ganzzahlige Konstanten sind.</span><span class="sxs-lookup"><span data-stu-id="ae32d-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae32d-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae32d-147">See Also</span></span>  
 [<span data-ttu-id="ae32d-148">/ =-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae32d-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="ae32d-149">\-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae32d-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [<span data-ttu-id="ae32d-150">Datentypen von Operatorergebnissen</span><span class="sxs-lookup"><span data-stu-id="ae32d-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)  
 [<span data-ttu-id="ae32d-151">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="ae32d-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="ae32d-152">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae32d-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="ae32d-153">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="ae32d-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="ae32d-154">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae32d-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
