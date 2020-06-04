---
title: '* Operator'
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
ms.openlocfilehash: f1a7653fb3006ab3c9736ec168a8c5ea028f4763
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409317"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="5de85-102">\*-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5de85-102">\* Operator (Visual Basic)</span></span>
<span data-ttu-id="5de85-103">Multipliziert zwei Zahlen.</span><span class="sxs-lookup"><span data-stu-id="5de85-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de85-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5de85-104">Syntax</span></span>  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="5de85-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="5de85-105">Parts</span></span>  
  
|<span data-ttu-id="5de85-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="5de85-106">Term</span></span>|<span data-ttu-id="5de85-107">Definition</span><span class="sxs-lookup"><span data-stu-id="5de85-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="5de85-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5de85-108">Required.</span></span> <span data-ttu-id="5de85-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5de85-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="5de85-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5de85-110">Required.</span></span> <span data-ttu-id="5de85-111">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5de85-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="5de85-112">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="5de85-112">Result</span></span>  
 <span data-ttu-id="5de85-113">Das Ergebnis ist das Produkt von `number1` und `number2` .</span><span class="sxs-lookup"><span data-stu-id="5de85-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="5de85-114">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="5de85-114">Supported Types</span></span>  
 <span data-ttu-id="5de85-115">Alle numerischen Typen, einschließlich der nicht signierten-und Gleit Komma Typen und `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="5de85-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5de85-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5de85-116">Remarks</span></span>  
 <span data-ttu-id="5de85-117">Der Datentyp des Ergebnisses hängt von den Typen der Operanden ab.</span><span class="sxs-lookup"><span data-stu-id="5de85-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="5de85-118">In der folgenden Tabelle wird gezeigt, wie der Datentyp des Ergebnisses bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="5de85-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="5de85-119">Operanden Datentypen</span><span class="sxs-lookup"><span data-stu-id="5de85-119">Operand data types</span></span>|<span data-ttu-id="5de85-120">Ergebnis Datentyp</span><span class="sxs-lookup"><span data-stu-id="5de85-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="5de85-121">Beide Ausdrücke sind [ganzzahlige](../data-types/uinteger-data-type.md)Datentypen ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), UInteger, [Long](../data-types/long-data-type.md), [ulong](../data-types/ulong-data-type.md)).</span><span class="sxs-lookup"><span data-stu-id="5de85-121">Both expressions are integral data types ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="5de85-122">Ein numerischer Datentyp, der für die Datentypen von und geeignet ist `number1` `number2` .</span><span class="sxs-lookup"><span data-stu-id="5de85-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="5de85-123">Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](data-types-of-operator-results.md)</span><span class="sxs-lookup"><span data-stu-id="5de85-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="5de85-124">Beide Ausdrücke sind [Decimal](../data-types/decimal-data-type.md) .</span><span class="sxs-lookup"><span data-stu-id="5de85-124">Both expressions are [Decimal](../data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="5de85-125">Beide Ausdrücke sind [Single](../data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="5de85-125">Both expressions are [Single](../data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="5de85-126">Jeder Ausdruck ist ein Gleit Komma Datentyp ( `Single` oder [Double](../data-types/double-data-type.md)), aber nicht beides `Single` (Beachten Sie, dass `Decimal` es sich nicht um einen Gleit Komma Datentyp handelt).</span><span class="sxs-lookup"><span data-stu-id="5de85-126">Either expression is a floating-point data type (`Single` or [Double](../data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="5de85-127">Wenn ein Ausdruck zu " [Nothing](../nothing.md)" ausgewertet wird, wird er als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="5de85-127">If an expression evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5de85-128">Überladen</span><span class="sxs-lookup"><span data-stu-id="5de85-128">Overloading</span></span>  
 <span data-ttu-id="5de85-129">Der `*` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="5de85-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5de85-130">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="5de85-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5de85-131">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5de85-131">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5de85-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5de85-132">Example</span></span>  
 <span data-ttu-id="5de85-133">Dieses Beispiel verwendet den- `*` Operator, um zwei Zahlen zu multiplizieren.</span><span class="sxs-lookup"><span data-stu-id="5de85-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="5de85-134">Das Ergebnis ist das Produkt der beiden-Operanden.</span><span class="sxs-lookup"><span data-stu-id="5de85-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="5de85-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5de85-135">See also</span></span>

- [<span data-ttu-id="5de85-136">Operator \* =</span><span class="sxs-lookup"><span data-stu-id="5de85-136">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="5de85-137">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="5de85-137">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="5de85-138">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5de85-138">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="5de85-139">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="5de85-139">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="5de85-140">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5de85-140">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
