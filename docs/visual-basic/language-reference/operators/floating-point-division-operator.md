---
title: /-Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./
dev_langs:
- VB
helpviewer_keywords:
- division operator, floating point
- floating-point numbers, division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators, division
- division, by zero
- operators [Visual Basic], division
- division operator, syntax
- / operator [Visual Basic]
- math operators
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 82255339c3bdab7f6e760de9bef073f463260877
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="58859-102">/-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58859-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="58859-103">Dividiert zwei Zahlen und gibt ein Gleitkommaergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="58859-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58859-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58859-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="58859-105">Teile</span><span class="sxs-lookup"><span data-stu-id="58859-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="58859-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58859-106">Required.</span></span> <span data-ttu-id="58859-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="58859-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="58859-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58859-108">Required.</span></span> <span data-ttu-id="58859-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="58859-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="58859-110">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="58859-110">Supported Types</span></span>  
 <span data-ttu-id="58859-111">Alle numerischen Typen, einschließlich der Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="58859-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="58859-112">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="58859-112">Result</span></span>  
 <span data-ttu-id="58859-113">Das Ergebnis ist der volle Quotient von `expression1` geteilt durch `expression2`, einschließlich des Rests.</span><span class="sxs-lookup"><span data-stu-id="58859-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="58859-114">Die [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten zurück, wobei der Rest entfällt.</span><span class="sxs-lookup"><span data-stu-id="58859-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58859-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58859-115">Remarks</span></span>  
 <span data-ttu-id="58859-116">Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab.</span><span class="sxs-lookup"><span data-stu-id="58859-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="58859-117">Die folgende Tabelle zeigt, wie der Datentyp des Ergebnisses bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="58859-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="58859-118">Datentypen der Operanden</span><span class="sxs-lookup"><span data-stu-id="58859-118">Operand data types</span></span>|<span data-ttu-id="58859-119">Datentyp</span><span class="sxs-lookup"><span data-stu-id="58859-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="58859-120">Beide Ausdrücke sind ganzzahlige Datentypen ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [kurze](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Ganzzahl](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [lang](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="58859-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="58859-121">Ein Ausdruck ist ein [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) Daten und das andere ist ein [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="58859-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="58859-122">Ein Ausdruck ist eine [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) Daten und das andere ist eine [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) oder eine [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="58859-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="58859-123">Ein Ausdruck ist ein [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) -Datentyp</span><span class="sxs-lookup"><span data-stu-id="58859-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="58859-124">Vor der Division ist, werden alle ganzzahligen numerischen Ausdrücke zu erweitert `Double`.</span><span class="sxs-lookup"><span data-stu-id="58859-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="58859-125">Wenn Sie das Ergebnis einem ganzzahligen Datentyp zuweisen, versucht Visual Basic, das Ergebnis von konvertieren `Double` auf diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="58859-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="58859-126">Dies kann eine Ausnahme auslösen, wenn das Ergebnis nicht in diesem Typ passt.</span><span class="sxs-lookup"><span data-stu-id="58859-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="58859-127">Insbesondere finden Sie unter "Versuchte Division durch&0;" auf dieser Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="58859-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="58859-128">Wenn `expression1` oder `expression2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird er als&0; (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="58859-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="58859-129">Versuchte Division durch&0; (null)</span><span class="sxs-lookup"><span data-stu-id="58859-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="58859-130">Wenn `expression2` NULL ist, ergibt die `/` -Operator verhält sich anders, für die Operanden unterschiedliche Datentypen.</span><span class="sxs-lookup"><span data-stu-id="58859-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="58859-131">In der folgenden Tabelle sind die möglichen Verhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="58859-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="58859-132">Datentypen der Operanden</span><span class="sxs-lookup"><span data-stu-id="58859-132">Operand data types</span></span>|<span data-ttu-id="58859-133">Verhalten Wenn `expression2`&0; (null)</span><span class="sxs-lookup"><span data-stu-id="58859-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="58859-134">Gleitkomma (`Single` oder `Double`)</span><span class="sxs-lookup"><span data-stu-id="58859-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="58859-135">Gibt unendlich (<xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity>), oder <xref:System.Double.NaN>(keine Zahl) Wenn `expression1` sind ebenfalls NULL</xref:System.Double.NaN> </xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity></span><span class="sxs-lookup"><span data-stu-id="58859-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="58859-136">Löst aus<xref:System.DivideByZeroException></xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="58859-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="58859-137">Ganze Zahl (mit oder ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="58859-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="58859-138">Konvertierung in den ganzzahligen Typ löst versucht <xref:System.OverflowException>da Ganzzahltypen akzeptieren können <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, oder <xref:System.Double.NaN></xref:System.Double.NaN> </xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity> </xref:System.OverflowException></span><span class="sxs-lookup"><span data-stu-id="58859-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="58859-139">Die `/` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="58859-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="58859-140">Wenn Ihr Code auf eine solche Klasse oder Struktur dieser Operator verwendet wird, achten Sie darauf, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="58859-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="58859-141">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="58859-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58859-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58859-142">Example</span></span>  
 <span data-ttu-id="58859-143">Dieses Beispiel verwendet die `/` Operator, um Gleitkommadivisionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58859-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="58859-144">Das Ergebnis ist der Quotient der zwei Operanden.</span><span class="sxs-lookup"><span data-stu-id="58859-144">The result is the quotient of the two operands.</span></span>  
  
 <span data-ttu-id="58859-145">[!code-vb[VbVbalrOperators Nr.&16;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="58859-145">[!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="58859-146">Die Ausdrücke im vorangehenden Beispiel geben die Werte 2,5 und 3,333333 zurück.</span><span class="sxs-lookup"><span data-stu-id="58859-146">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="58859-147">Beachten Sie, dass das Ergebnis immer Gleitkomma (`Double`), obwohl beide Operanden ganzzahlige Konstanten sind.</span><span class="sxs-lookup"><span data-stu-id="58859-147">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58859-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58859-148">See Also</span></span>  
 <span data-ttu-id="58859-149">[/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="58859-149">[/= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span></span>  
<span data-ttu-id="58859-150"> [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) </span><span class="sxs-lookup"><span data-stu-id="58859-150"> [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) </span></span>  
<span data-ttu-id="58859-151"> [Datentypen von Operatorergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md) </span><span class="sxs-lookup"><span data-stu-id="58859-151"> [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md) </span></span>  
<span data-ttu-id="58859-152"> [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="58859-152"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="58859-153"> [Operatorrangfolge in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="58859-153"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="58859-154"> [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="58859-154"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="58859-155"> [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span><span class="sxs-lookup"><span data-stu-id="58859-155"> [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span></span>

