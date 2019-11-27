---
title: '- Operator'
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
ms.openlocfilehash: 9687c366c5b23693c05ab5c6b34f50c04131dfda
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348228"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="4af49-102">--Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4af49-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="4af49-103">Gibt die Differenz zwischen zwei numerischen Ausdrücken oder dem negativen Wert eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="4af49-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af49-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4af49-104">Syntax</span></span>  
  
```vb  
expression1 – expression2
```
  
<span data-ttu-id="4af49-105">oder</span><span class="sxs-lookup"><span data-stu-id="4af49-105">or</span></span>

```vb  
–expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="4af49-106">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="4af49-106">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="4af49-107">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="4af49-107">Required.</span></span> <span data-ttu-id="4af49-108">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4af49-108">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="4af49-109">Erforderlich, es sei denn, der `–`-Operator berechnet einen negativen Wert.</span><span class="sxs-lookup"><span data-stu-id="4af49-109">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="4af49-110">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4af49-110">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="4af49-111">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="4af49-111">Result</span></span>  
 <span data-ttu-id="4af49-112">Das Ergebnis ist der Unterschied zwischen `expression1` und `expression2`oder dem negiert-Wert von `expression1`.</span><span class="sxs-lookup"><span data-stu-id="4af49-112">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="4af49-113">Der Ergebnis Datentyp ist ein numerischer Typ, der für die Datentypen von `expression1` und `expression2`geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="4af49-113">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="4af49-114">Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)</span><span class="sxs-lookup"><span data-stu-id="4af49-114">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="4af49-115">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="4af49-115">Supported Types</span></span>  
 <span data-ttu-id="4af49-116">allen numerischen Typen</span><span class="sxs-lookup"><span data-stu-id="4af49-116">All numeric types.</span></span> <span data-ttu-id="4af49-117">Dies schließt die unsignierten und Gleit Komma Typen und `Decimal`ein.</span><span class="sxs-lookup"><span data-stu-id="4af49-117">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4af49-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4af49-118">Remarks</span></span>  
 <span data-ttu-id="4af49-119">In der ersten Verwendung in der zuvor gezeigten Syntax ist der `–`-Operator der *binäre* arithmetische Subtraktions Operator für den Unterschied zwischen zwei numerischen Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="4af49-119">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="4af49-120">In der zweiten Syntax, die in der zuvor gezeigten Syntax angezeigt wird, ist der `–`-Operator der *unäre* Negations Operator für den negativen Wert eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="4af49-120">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="4af49-121">In diesem Sinne besteht die Negation darin, das Vorzeichen `expression1` umzukehren, damit das Ergebnis positiv ist, wenn `expression1` negativ ist.</span><span class="sxs-lookup"><span data-stu-id="4af49-121">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="4af49-122">Wenn ein Ausdruck zu " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, behandelt der `–` Operator ihn als 0 (null).</span><span class="sxs-lookup"><span data-stu-id="4af49-122">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4af49-123">Der `–`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="4af49-123">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4af49-124">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="4af49-124">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="4af49-125">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4af49-125">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4af49-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4af49-126">Example</span></span>  
 <span data-ttu-id="4af49-127">Im folgenden Beispiel wird der `–`-Operator verwendet, um die Differenz zwischen zwei Zahlen zu berechnen und zurückzugeben, und um dann eine Zahl zu negieren.</span><span class="sxs-lookup"><span data-stu-id="4af49-127">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="4af49-128">Nach der Ausführung dieser Anweisungen enthält `binaryResult` 124,45 und `unaryResult` enthält – 334,90.</span><span class="sxs-lookup"><span data-stu-id="4af49-128">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af49-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4af49-129">See also</span></span>

- [<span data-ttu-id="4af49-130">Operator-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4af49-130">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="4af49-131">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="4af49-131">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="4af49-132">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4af49-132">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="4af49-133">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="4af49-133">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="4af49-134">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4af49-134">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
