---
title: '- -Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 1a5c47a2f1bc8a8b9e1b0263b90006a0e58e17bb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830668"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="535d6-102">--Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="535d6-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="535d6-103">Gibt die Differenz zwischen zwei numerischen Ausdrücken oder den negativen Wert eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="535d6-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="535d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="535d6-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="535d6-105">Teile</span><span class="sxs-lookup"><span data-stu-id="535d6-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="535d6-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="535d6-106">Required.</span></span> <span data-ttu-id="535d6-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="535d6-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="535d6-108">Erforderlich, wenn die `–` Operator einen negativen Wert berechnet.</span><span class="sxs-lookup"><span data-stu-id="535d6-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="535d6-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="535d6-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="535d6-110">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="535d6-110">Result</span></span>  
 <span data-ttu-id="535d6-111">Das Ergebnis ist der Unterschied zwischen `expression1` und `expression2`, oder der negierte Wert der `expression1`.</span><span class="sxs-lookup"><span data-stu-id="535d6-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="535d6-112">Der Ergebniswert vom Datentyp eines numerischen Typs, die für die Datentypen der entsprechenden `expression1` und `expression2`.</span><span class="sxs-lookup"><span data-stu-id="535d6-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="535d6-113">Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="535d6-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="535d6-114">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="535d6-114">Supported Types</span></span>  
 <span data-ttu-id="535d6-115">allen numerischen Typen</span><span class="sxs-lookup"><span data-stu-id="535d6-115">All numeric types.</span></span> <span data-ttu-id="535d6-116">Dazu gehören auch die Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="535d6-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="535d6-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="535d6-117">Remarks</span></span>  
 <span data-ttu-id="535d6-118">In der ersten Verwendung angezeigt, in der zuvor gezeigten Syntax der `–` Operator ist der *binäre* arithmetischer Subtraktionsoperator für den Unterschied zwischen zwei numerische Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="535d6-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="535d6-119">Im zweiten Anwendungsbeispiel in der zuvor gezeigten Syntax der `–` Operator ist der *unäre* Negationsoperator für den negativen Wert eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="535d6-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="535d6-120">In diesem Sinne, das die Negation Umkehrung des Vorzeichens von besteht aus `expression1` , damit das Ergebnis positiv ist. wenn `expression1` ist negativ.</span><span class="sxs-lookup"><span data-stu-id="535d6-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="535d6-121">Wenn die beiden Ausdrücke ist ["Nothing"](../../../visual-basic/language-reference/nothing.md), `–` Operator wird er als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="535d6-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="535d6-122">Die `–` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="535d6-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="535d6-123">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet werden, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="535d6-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="535d6-124">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="535d6-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="535d6-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="535d6-125">Example</span></span>  
 <span data-ttu-id="535d6-126">Im folgenden Beispiel wird die `–` Operator zum Berechnen und Zurückgeben des Unterschied zwischen zwei Zahlen, und klicken Sie dann eine Zahl zu negieren.</span><span class="sxs-lookup"><span data-stu-id="535d6-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="535d6-127">Nach der Ausführung dieser Anweisungen ist `binaryResult` 124.45 enthält und `unaryResult` –334.90 enthält.</span><span class="sxs-lookup"><span data-stu-id="535d6-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="535d6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="535d6-128">See also</span></span>

- [<span data-ttu-id="535d6-129">Operator-=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="535d6-129">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="535d6-130">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="535d6-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="535d6-131">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="535d6-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="535d6-132">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="535d6-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="535d6-133">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="535d6-133">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
