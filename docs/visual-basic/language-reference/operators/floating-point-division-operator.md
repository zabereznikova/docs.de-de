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
ms.openlocfilehash: e9400b50a84522f87a9a2ea4cd05b479d7a4538e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371167"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="c7076-102">/-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7076-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="c7076-103">Dividiert zwei Zahlen und gibt ein Gleitkommaergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="c7076-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7076-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7076-104">Syntax</span></span>  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c7076-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="c7076-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="c7076-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c7076-106">Required.</span></span> <span data-ttu-id="c7076-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c7076-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="c7076-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c7076-108">Required.</span></span> <span data-ttu-id="c7076-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c7076-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="c7076-110">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="c7076-110">Supported Types</span></span>  
 <span data-ttu-id="c7076-111">Alle numerischen Typen, einschließlich der nicht signierten-und Gleit Komma Typen und `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="c7076-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="c7076-112">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="c7076-112">Result</span></span>  
 <span data-ttu-id="c7076-113">Das Ergebnis ist der vollständige Quotienten von `expression1` dividiert durch `expression2` , einschließlich Rest.</span><span class="sxs-lookup"><span data-stu-id="c7076-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="c7076-114">Der [Operator \ (Visual Basic)](integer-division-operator.md) gibt den ganzzahligen Quotienten zurück, der den Rest löscht.</span><span class="sxs-lookup"><span data-stu-id="c7076-114">The [\ Operator (Visual Basic)](integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7076-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c7076-115">Remarks</span></span>  
 <span data-ttu-id="c7076-116">Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab.</span><span class="sxs-lookup"><span data-stu-id="c7076-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="c7076-117">In der folgenden Tabelle wird gezeigt, wie der Datentyp des Ergebnisses bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="c7076-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="c7076-118">Operanden Datentypen</span><span class="sxs-lookup"><span data-stu-id="c7076-118">Operand data types</span></span>|<span data-ttu-id="c7076-119">Ergebnis Datentyp</span><span class="sxs-lookup"><span data-stu-id="c7076-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="c7076-120">Beide Ausdrücke sind [ganzzahlige](../data-types/uinteger-data-type.md)Datentypen ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), UInteger, [Long](../data-types/long-data-type.md), [ulong](../data-types/ulong-data-type.md)).</span><span class="sxs-lookup"><span data-stu-id="c7076-120">Both expressions are integral data types ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="c7076-121">Ein Ausdruck ist ein [einzelner](../data-types/single-data-type.md) Datentyp, und der andere ist kein [Double](../data-types/double-data-type.md) .</span><span class="sxs-lookup"><span data-stu-id="c7076-121">One expression is a [Single](../data-types/single-data-type.md) data type and the other is not a [Double](../data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="c7076-122">Ein Ausdruck ist ein [Decimal](../data-types/decimal-data-type.md) -Datentyp, der andere kein [einzelner](../data-types/single-data-type.md) oder [Double](../data-types/double-data-type.md) -Wert.</span><span class="sxs-lookup"><span data-stu-id="c7076-122">One expression is a [Decimal](../data-types/decimal-data-type.md) data type and the other is not a [Single](../data-types/single-data-type.md) or a [Double](../data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="c7076-123">Jeder Ausdruck ist ein [Double](../data-types/double-data-type.md) -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="c7076-123">Either expression is a [Double](../data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="c7076-124">Bevor die Division durchgeführt wird, werden alle ganzzahligen numerischen Ausdrücke auf erweitert `Double` .</span><span class="sxs-lookup"><span data-stu-id="c7076-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="c7076-125">Wenn Sie das Ergebnis einem ganzzahligen Datentyp zuweisen, versucht Visual Basic, das Ergebnis von `Double` in diesen Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c7076-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="c7076-126">Dadurch kann eine Ausnahme ausgelöst werden, wenn das Ergebnis nicht in diesen Typ passt.</span><span class="sxs-lookup"><span data-stu-id="c7076-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="c7076-127">Weitere Informationen finden Sie auf dieser Hilfeseite unter "versuchte Division durch Null".</span><span class="sxs-lookup"><span data-stu-id="c7076-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="c7076-128">Wenn `expression1` oder `expression2` als " [Nothing](../nothing.md)" ausgewertet wird, wird es als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="c7076-128">If `expression1` or `expression2` evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="c7076-129">Versuchte Division durch Null</span><span class="sxs-lookup"><span data-stu-id="c7076-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="c7076-130">Wenn `expression2` der Wert 0 (null) ergibt, verhält sich der `/` Operator für verschiedene Operanden-Datentypen unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="c7076-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="c7076-131">In der folgenden Tabelle sind die möglichen Verhalten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c7076-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="c7076-132">Operanden Datentypen</span><span class="sxs-lookup"><span data-stu-id="c7076-132">Operand data types</span></span>|<span data-ttu-id="c7076-133">Verhalten, wenn `expression2` NULL ist</span><span class="sxs-lookup"><span data-stu-id="c7076-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="c7076-134">Gleit Komma ( `Single` oder `Double` )</span><span class="sxs-lookup"><span data-stu-id="c7076-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="c7076-135">Gibt unendlich ( <xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity> ) oder <xref:System.Double.NaN> (keine Zahl) zurück, wenn `expression1` gleich 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="c7076-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="c7076-136">KEH<xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="c7076-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="c7076-137">Ganzzahl (signiert oder unsigniert)</span><span class="sxs-lookup"><span data-stu-id="c7076-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="c7076-138">Die Konvertierung in einen ganzzahligen Typ wird ausgelöst, da ganzzahlige <xref:System.OverflowException> Typen <xref:System.Double.PositiveInfinity> , oder nicht akzeptieren können. <xref:System.Double.NegativeInfinity><xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="c7076-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
> <span data-ttu-id="c7076-139">Der `/` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="c7076-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c7076-140">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="c7076-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c7076-141">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c7076-141">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7076-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7076-142">Example</span></span>  
 <span data-ttu-id="c7076-143">In diesem Beispiel wird der `/` -Operator verwendet, um die Gleit Komma Division auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c7076-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="c7076-144">Das Ergebnis ist der Quotienten der beiden Operanden.</span><span class="sxs-lookup"><span data-stu-id="c7076-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="c7076-145">Die Ausdrücke im vorherigen Beispiel geben die Werte 2,5 und 3,333333 zurück.</span><span class="sxs-lookup"><span data-stu-id="c7076-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="c7076-146">Beachten Sie, dass das Ergebnis immer ein Gleit Komma Wert ( `Double` ) ist, obwohl beide Operanden ganzzahlige Konstanten sind.</span><span class="sxs-lookup"><span data-stu-id="c7076-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7076-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7076-147">See also</span></span>

- [<span data-ttu-id="c7076-148">Operator/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7076-148">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="c7076-149">\-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7076-149">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
- [<span data-ttu-id="c7076-150">Datentypen von Operatorergebnissen</span><span class="sxs-lookup"><span data-stu-id="c7076-150">Data Types of Operator Results</span></span>](data-types-of-operator-results.md)
- [<span data-ttu-id="c7076-151">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="c7076-151">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="c7076-152">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7076-152">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="c7076-153">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="c7076-153">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="c7076-154">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7076-154">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
