---
title: Operator /
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
ms.openlocfilehash: 537d8b0c703b59743f1a7c531448118058707645
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331055"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a6dd2-102">/-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6dd2-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="a6dd2-103">Dividiert zwei Zahlen und gibt ein Gleit Komma Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6dd2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6dd2-104">Syntax</span></span>  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="a6dd2-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="a6dd2-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="a6dd2-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a6dd2-106">Required.</span></span> <span data-ttu-id="a6dd2-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="a6dd2-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a6dd2-108">Required.</span></span> <span data-ttu-id="a6dd2-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="a6dd2-110">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="a6dd2-110">Supported Types</span></span>  
 <span data-ttu-id="a6dd2-111">Alle numerischen Typen, einschließlich der unsignierten und Gleit Komma Typen und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="a6dd2-112">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="a6dd2-112">Result</span></span>  
 <span data-ttu-id="a6dd2-113">Das Ergebnis ist der vollständige Quotienten von `expression1` dividiert durch `expression2`, einschließlich Rest.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="a6dd2-114">Der [Operator \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten zurück, der den Rest löscht.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6dd2-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6dd2-115">Remarks</span></span>  
 <span data-ttu-id="a6dd2-116">Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="a6dd2-117">In der folgenden Tabelle wird gezeigt, wie der Datentyp des Ergebnisses bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="a6dd2-118">Operanden Datentypen</span><span class="sxs-lookup"><span data-stu-id="a6dd2-118">Operand data types</span></span>|<span data-ttu-id="a6dd2-119">Ergebnis Datentyp</span><span class="sxs-lookup"><span data-stu-id="a6dd2-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="a6dd2-120">Beide Ausdrücke sind [ganzzahlige](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)Datentypen ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), UInteger, [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ulong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)).</span><span class="sxs-lookup"><span data-stu-id="a6dd2-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="a6dd2-121">Ein Ausdruck ist ein [einzelner](../../../visual-basic/language-reference/data-types/single-data-type.md) Datentyp, und der andere ist kein [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) .</span><span class="sxs-lookup"><span data-stu-id="a6dd2-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="a6dd2-122">Ein Ausdruck ist ein [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -Datentyp, der andere kein [einzelner](../../../visual-basic/language-reference/data-types/single-data-type.md) oder [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) -Wert.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="a6dd2-123">Jeder Ausdruck ist ein [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="a6dd2-124">Bevor die Division durchgeführt wird, werden alle ganzzahligen numerischen Ausdrücke auf `Double`erweitert.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="a6dd2-125">Wenn Sie das Ergebnis einem ganzzahligen Datentyp zuweisen, versucht Visual Basic, das Ergebnis von `Double` in diesen Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="a6dd2-126">Dadurch kann eine Ausnahme ausgelöst werden, wenn das Ergebnis nicht in diesen Typ passt.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="a6dd2-127">Weitere Informationen finden Sie auf dieser Hilfeseite unter "versuchte Division durch Null".</span><span class="sxs-lookup"><span data-stu-id="a6dd2-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="a6dd2-128">Wenn `expression1` oder `expression2` als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird es als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="a6dd2-129">Versuchte Division durch Null</span><span class="sxs-lookup"><span data-stu-id="a6dd2-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="a6dd2-130">Wenn `expression2` den Wert 0 (null) ergibt, verhält sich der `/` Operator bei verschiedenen Operanden-Datentypen unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="a6dd2-131">In der folgenden Tabelle sind die möglichen Verhalten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="a6dd2-132">Operanden Datentypen</span><span class="sxs-lookup"><span data-stu-id="a6dd2-132">Operand data types</span></span>|<span data-ttu-id="a6dd2-133">Verhalten, wenn `expression2` NULL ist</span><span class="sxs-lookup"><span data-stu-id="a6dd2-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="a6dd2-134">Gleit Komma (`Single` oder `Double`)</span><span class="sxs-lookup"><span data-stu-id="a6dd2-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="a6dd2-135">Gibt unendlich (<xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity>) oder <xref:System.Double.NaN> (keine Zahl) zurück, wenn `expression1` ebenfalls 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="a6dd2-136">Löst <xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="a6dd2-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="a6dd2-137">Ganzzahl (signiert oder unsigniert)</span><span class="sxs-lookup"><span data-stu-id="a6dd2-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="a6dd2-138">Bei der Konvertierung in einen ganzzahligen Typ wird <xref:System.OverflowException> ausgelöst, da ganzzahlige Typen <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>oder <xref:System.Double.NaN> nicht akzeptieren können.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
> <span data-ttu-id="a6dd2-139">Der `/`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a6dd2-140">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a6dd2-141">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a6dd2-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6dd2-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6dd2-142">Example</span></span>  
 <span data-ttu-id="a6dd2-143">In diesem Beispiel wird der `/`-Operator verwendet, um eine Gleit Komma Division auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="a6dd2-144">Das Ergebnis ist der Quotienten der beiden Operanden.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="a6dd2-145">Die Ausdrücke im vorherigen Beispiel geben die Werte 2,5 und 3,333333 zurück.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="a6dd2-146">Beachten Sie, dass das Ergebnis immer Gleit Komma (`Double`) ist, obwohl beide Operanden ganzzahlige Konstanten sind.</span><span class="sxs-lookup"><span data-stu-id="a6dd2-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6dd2-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6dd2-147">See also</span></span>

- [<span data-ttu-id="a6dd2-148">Operator/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6dd2-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="a6dd2-149">Operator \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6dd2-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="a6dd2-150">Datentypen von Operatorergebnissen</span><span class="sxs-lookup"><span data-stu-id="a6dd2-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [<span data-ttu-id="a6dd2-151">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="a6dd2-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="a6dd2-152">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6dd2-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a6dd2-153">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="a6dd2-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="a6dd2-154">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a6dd2-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
