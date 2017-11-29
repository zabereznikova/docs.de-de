---
title: '- Operator (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ffb7c96fe95e73dc857a15608df94ed8468f9df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="ee5cb-102">--Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee5cb-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="ee5cb-103">Gibt die Differenz zwischen zwei numerischen Ausdrücken oder den negativen Wert eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee5cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee5cb-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="ee5cb-105">Teile</span><span class="sxs-lookup"><span data-stu-id="ee5cb-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="ee5cb-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-106">Required.</span></span> <span data-ttu-id="ee5cb-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="ee5cb-108">Erforderlich, es sei denn, die `–` Operator einen negativen Wert berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="ee5cb-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="ee5cb-110">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="ee5cb-110">Result</span></span>  
 <span data-ttu-id="ee5cb-111">Das Ergebnis ist der Unterschied zwischen `expression1` und `expression2`, oder der negierte Wert der `expression1`.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="ee5cb-112">Datentyp des Ergebnisses ist ein numerischer Typ für die Datentypen der entsprechenden `expression1` und `expression2`.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="ee5cb-113">Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="ee5cb-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="ee5cb-114">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="ee5cb-114">Supported Types</span></span>  
 <span data-ttu-id="ee5cb-115">Alle numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-115">All numeric types.</span></span> <span data-ttu-id="ee5cb-116">Dazu gehören auch die Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee5cb-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee5cb-117">Remarks</span></span>  
 <span data-ttu-id="ee5cb-118">In der ersten Verwendung in der zuvor gezeigten Syntax gezeigt die `–` Operator ist der *binäre* arithmetischer Subtraktionsoperator für die Differenz zwischen zwei numerische Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="ee5cb-119">Im zweiten Anwendungsbeispiel in der zuvor gezeigten Syntax der `–` Operator ist der *unäre* Negationsoperator für den negativen Wert eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="ee5cb-120">In diesem Sinn, besteht die Negation Umkehrung des Vorzeichens eines `expression1` , damit das Ergebnis positiv ist. wenn `expression1` ist ein negativer Wert.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="ee5cb-121">Wenn einer der Ausdrücke ergibt [nichts](../../../visual-basic/language-reference/nothing.md)die `–` Operator wird er als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee5cb-122">Die `–` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ee5cb-123">Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie dessen neu definierten Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="ee5cb-124">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ee5cb-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee5cb-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ee5cb-125">Example</span></span>  
 <span data-ttu-id="ee5cb-126">Im folgenden Beispiel wird die `–` Operator zum Berechnen und Zurückgeben des Unterschied zwischen zwei Zahlen liegt, und klicken Sie dann eine Zahl zu negieren.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 <span data-ttu-id="ee5cb-127">Nach der Ausführung dieser Anweisungen `binaryResult` enthält 124.45 und `unaryResult` –334.90 enthält.</span><span class="sxs-lookup"><span data-stu-id="ee5cb-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5cb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee5cb-128">See Also</span></span>  
 <span data-ttu-id="ee5cb-129">[Operator-=-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)</span><span class="sxs-lookup"><span data-stu-id="ee5cb-129">[-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)</span></span>  
 [<span data-ttu-id="ee5cb-130">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee5cb-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="ee5cb-131">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="ee5cb-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="ee5cb-132">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ee5cb-132">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
