---
title: '* -Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: a13461d7424415ef553dc9ba00de1bf775fda112
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965318"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="9275f-102">\*-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9275f-102">\* Operator (Visual Basic)</span></span>
<span data-ttu-id="9275f-103">Multipliziert zwei Zahlen miteinander.</span><span class="sxs-lookup"><span data-stu-id="9275f-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9275f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9275f-104">Syntax</span></span>  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="9275f-105">Teile</span><span class="sxs-lookup"><span data-stu-id="9275f-105">Parts</span></span>  
  
|<span data-ttu-id="9275f-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="9275f-106">Term</span></span>|<span data-ttu-id="9275f-107">Definition</span><span class="sxs-lookup"><span data-stu-id="9275f-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="9275f-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9275f-108">Required.</span></span> <span data-ttu-id="9275f-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9275f-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="9275f-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9275f-110">Required.</span></span> <span data-ttu-id="9275f-111">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9275f-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="9275f-112">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="9275f-112">Result</span></span>  
 <span data-ttu-id="9275f-113">Das Ergebnis ist das Produkt der `number1` und `number2`.</span><span class="sxs-lookup"><span data-stu-id="9275f-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="9275f-114">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="9275f-114">Supported Types</span></span>  
 <span data-ttu-id="9275f-115">Alle numerischen Typen, einschließlich der Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="9275f-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9275f-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9275f-116">Remarks</span></span>  
 <span data-ttu-id="9275f-117">Der Datentyp des Ergebnisses, hängt von den Typen der Operanden ab.</span><span class="sxs-lookup"><span data-stu-id="9275f-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="9275f-118">Die folgende Tabelle zeigt, wie der Datentyp des Ergebnisses bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="9275f-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="9275f-119">Datentypen der Operanden</span><span class="sxs-lookup"><span data-stu-id="9275f-119">Operand data types</span></span>|<span data-ttu-id="9275f-120">Der Ergebnisdatentyp</span><span class="sxs-lookup"><span data-stu-id="9275f-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="9275f-121">Beide Ausdrücke sind ganzzahlige Datentypen ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [kurze](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Ganzzahl](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [lange](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="9275f-121">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="9275f-122">Einen numerischen Datentyp aufweisen, die für die Datentypen der entsprechenden `number1` und `number2`.</span><span class="sxs-lookup"><span data-stu-id="9275f-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="9275f-123">Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="9275f-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="9275f-124">Beide Ausdrücke sind [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="9275f-124">Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="9275f-125">Beide Ausdrücke sind [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="9275f-125">Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="9275f-126">Einer der Ausdrücke ist ein Gleitkomma-Datentyp (`Single` oder [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md)) jedoch nicht beides `Single` (Hinweis `Decimal` ist kein Gleitkommadatentyp)</span><span class="sxs-lookup"><span data-stu-id="9275f-126">Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="9275f-127">Wenn ein Ausdruck ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird er als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="9275f-127">If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9275f-128">Überladen</span><span class="sxs-lookup"><span data-stu-id="9275f-128">Overloading</span></span>  
 <span data-ttu-id="9275f-129">Die `*` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="9275f-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9275f-130">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9275f-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9275f-131">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9275f-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9275f-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9275f-132">Example</span></span>  
 <span data-ttu-id="9275f-133">Dieses Beispiel verwendet die `*` Operator zum Multiplizieren zweier Zahlen.</span><span class="sxs-lookup"><span data-stu-id="9275f-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="9275f-134">Das Ergebnis ist das Produkt der beiden Operanden.</span><span class="sxs-lookup"><span data-stu-id="9275f-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="9275f-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9275f-135">See also</span></span>
- [<span data-ttu-id="9275f-136">\* =-Operator</span><span class="sxs-lookup"><span data-stu-id="9275f-136">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="9275f-137">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="9275f-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="9275f-138">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9275f-138">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9275f-139">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="9275f-139">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9275f-140">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9275f-140">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
