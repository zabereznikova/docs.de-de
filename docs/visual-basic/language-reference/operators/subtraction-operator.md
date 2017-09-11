---
title: '- Operator (Visual Basic) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Negate
- vb.-
dev_langs:
- VB
helpviewer_keywords:
- '- operator [Visual Basic]'
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator
- operators [Visual Basic], arithmetic
- subtraction operator, syntax
- arithmetic operators, subtraction
- difference operator
- math operators
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
caps.latest.revision: 14
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
ms.openlocfilehash: eb9b8e94877cce9aacde69c5f555f4a7f4a9ad7c
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="--operator-visual-basic"></a><span data-ttu-id="336c0-102">--Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="336c0-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="336c0-103">Gibt die Differenz zwischen zwei numerischen Ausdrücken oder den negativen Wert eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="336c0-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="336c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="336c0-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="336c0-105">Teile</span><span class="sxs-lookup"><span data-stu-id="336c0-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="336c0-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="336c0-106">Required.</span></span> <span data-ttu-id="336c0-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="336c0-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="336c0-108">Erforderlich, wenn die `–` Operator einen negativen Wert berechnet.</span><span class="sxs-lookup"><span data-stu-id="336c0-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="336c0-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="336c0-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="336c0-110">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="336c0-110">Result</span></span>  
 <span data-ttu-id="336c0-111">Das Ergebnis ist der Unterschied zwischen `expression1` und `expression2`, oder der negierte Wert der `expression1`.</span><span class="sxs-lookup"><span data-stu-id="336c0-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="336c0-112">Datentyp des Ergebnisses ist eine für die Datentypen der numerischen Typ `expression1` und `expression2`.</span><span class="sxs-lookup"><span data-stu-id="336c0-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="336c0-113">Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="336c0-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="336c0-114">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="336c0-114">Supported Types</span></span>  
 <span data-ttu-id="336c0-115">Alle numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="336c0-115">All numeric types.</span></span> <span data-ttu-id="336c0-116">Dies schließt die Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="336c0-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="336c0-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="336c0-117">Remarks</span></span>  
 <span data-ttu-id="336c0-118">Im ersten Anwendungsbeispiel in der zuvor gezeigten Syntax der `–` -Operator ist der *binäre* arithmetische Subtraktionsoperator für die Differenz zwischen zwei numerischen Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="336c0-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="336c0-119">Im zweiten Anwendungsbeispiel in der zuvor gezeigten Syntax der `–` -Operator ist der *unäre* Negationsoperator für den negativen Wert eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="336c0-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="336c0-120">In diesem Sinne Negation Umkehrung des Vorzeichens von besteht aus `expression1` , damit das Ergebnis positiv ist Wenn `expression1` ist negativ.</span><span class="sxs-lookup"><span data-stu-id="336c0-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="336c0-121">Wenn die beiden Ausdrücke ist [nichts](../../../visual-basic/language-reference/nothing.md)der `–` Operator wird er als&0; (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="336c0-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="336c0-122">Die `–` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="336c0-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="336c0-123">Wenn Ihr Code auf eine solche Klasse oder Struktur dieser Operator verwendet wird, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="336c0-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="336c0-124">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="336c0-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="336c0-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="336c0-125">Example</span></span>  
 <span data-ttu-id="336c0-126">Im folgenden Beispiel wird die `–` Operator berechnet und die Differenz zwischen zwei Zahlen zurückgibt und anschließend eine Zahl zu negieren.</span><span class="sxs-lookup"><span data-stu-id="336c0-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 <span data-ttu-id="336c0-127">[!code-vb[VbVbalrOperators&#10;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="336c0-127">[!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="336c0-128">Nach der Ausführung dieser Anweisungen `binaryResult` enthält 124.45 und `unaryResult` –334.90 enthält.</span><span class="sxs-lookup"><span data-stu-id="336c0-128">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="336c0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="336c0-129">See Also</span></span>  
 <span data-ttu-id="336c0-130">[-=-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
 [arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="336c0-130">[-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="336c0-131"> [Operatorrangfolge in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="336c0-131"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="336c0-132"> [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="336c0-132"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="336c0-133"> [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span><span class="sxs-lookup"><span data-stu-id="336c0-133"> [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span></span>

