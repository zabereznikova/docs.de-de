---
title: '- Operator (Visual Basic)'
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
ms.openlocfilehash: eb34b34986613f36b624c43c04f98390ffba4fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965866"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="096ea-102">--Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="096ea-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="096ea-103">Gibt die Differenz zwischen zwei numerischen Ausdrücken oder dem negativen Wert eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="096ea-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="096ea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="096ea-104">Syntax</span></span>  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="096ea-105">Teile</span><span class="sxs-lookup"><span data-stu-id="096ea-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="096ea-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="096ea-106">Required.</span></span> <span data-ttu-id="096ea-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="096ea-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="096ea-108">Erforderlich, es `–` sei denn, der Operator berechnet einen negativen Wert.</span><span class="sxs-lookup"><span data-stu-id="096ea-108">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="096ea-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="096ea-109">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="096ea-110">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="096ea-110">Result</span></span>  
 <span data-ttu-id="096ea-111">Das Ergebnis ist der Unterschied `expression1` zwischen `expression2`und oder dem negiert Wert von `expression1`.</span><span class="sxs-lookup"><span data-stu-id="096ea-111">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="096ea-112">Der Ergebnis Datentyp ist ein numerischer Typ, der für die Daten `expression1` Typen `expression2`von und geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="096ea-112">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="096ea-113">Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)</span><span class="sxs-lookup"><span data-stu-id="096ea-113">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="096ea-114">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="096ea-114">Supported Types</span></span>  
 <span data-ttu-id="096ea-115">allen numerischen Typen</span><span class="sxs-lookup"><span data-stu-id="096ea-115">All numeric types.</span></span> <span data-ttu-id="096ea-116">Dies schließt die unsignierten-und Gleit Komma Typen `Decimal`und ein.</span><span class="sxs-lookup"><span data-stu-id="096ea-116">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="096ea-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="096ea-117">Remarks</span></span>  
 <span data-ttu-id="096ea-118">In der ersten Verwendung, die in der zuvor gezeigten Syntax gezeigt `–` wurde, ist der Operator der *binäre* arithmetische Subtraktions Operator für den Unterschied zwischen zwei numerischen Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="096ea-118">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="096ea-119">In der zweiten Syntax, die in der zuvor gezeigten Syntax angezeigt `–` wird, ist der Operator der *unäre* Negations Operator für den negativen Wert eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="096ea-119">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="096ea-120">In diesem Sinne besteht die Negation darin, das Vorzeichen von `expression1` umzukehren, sodass das Ergebnis positiv ist, wenn `expression1` negativ ist.</span><span class="sxs-lookup"><span data-stu-id="096ea-120">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="096ea-121">Wenn ein Ausdruck zu " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet `–` wird, behandelt der Operator ihn als 0 (null).</span><span class="sxs-lookup"><span data-stu-id="096ea-121">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="096ea-122">Der `–` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="096ea-122">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="096ea-123">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="096ea-123">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="096ea-124">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="096ea-124">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="096ea-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="096ea-125">Example</span></span>  
 <span data-ttu-id="096ea-126">Im folgenden Beispiel wird der `–` -Operator verwendet, um die Differenz zwischen zwei Zahlen zu berechnen und zurückzugeben und dann eine Zahl zu negieren.</span><span class="sxs-lookup"><span data-stu-id="096ea-126">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="096ea-127">Nach der Ausführung dieser Anweisungen `binaryResult` enthält 124,45 und `unaryResult` enthält – 334,90.</span><span class="sxs-lookup"><span data-stu-id="096ea-127">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="096ea-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="096ea-128">See also</span></span>

- [<span data-ttu-id="096ea-129">Operator-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="096ea-129">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="096ea-130">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="096ea-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="096ea-131">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="096ea-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="096ea-132">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="096ea-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="096ea-133">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="096ea-133">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
