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
ms.openlocfilehash: 6539beb5cf8078281357445e2391fac189208087
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406352"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="003fc-102">--Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="003fc-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="003fc-103">Gibt die Differenz zwischen zwei numerischen Ausdrücken oder dem negativen Wert eines numerischen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="003fc-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="003fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="003fc-104">Syntax</span></span>  
  
```vb  
expression1 – expression2
```
  
<span data-ttu-id="003fc-105">oder</span><span class="sxs-lookup"><span data-stu-id="003fc-105">or</span></span>

```vb  
–expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="003fc-106">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="003fc-106">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="003fc-107">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="003fc-107">Required.</span></span> <span data-ttu-id="003fc-108">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="003fc-108">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="003fc-109">Erforderlich, es sei denn, der `–` Operator berechnet einen negativen Wert.</span><span class="sxs-lookup"><span data-stu-id="003fc-109">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="003fc-110">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="003fc-110">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="003fc-111">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="003fc-111">Result</span></span>  
 <span data-ttu-id="003fc-112">Das Ergebnis ist der Unterschied zwischen `expression1` und `expression2` oder dem negiert Wert von `expression1` .</span><span class="sxs-lookup"><span data-stu-id="003fc-112">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="003fc-113">Der Ergebnis Datentyp ist ein numerischer Typ, der für die Datentypen von und geeignet ist `expression1` `expression2` .</span><span class="sxs-lookup"><span data-stu-id="003fc-113">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="003fc-114">Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](data-types-of-operator-results.md)</span><span class="sxs-lookup"><span data-stu-id="003fc-114">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="003fc-115">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="003fc-115">Supported Types</span></span>  
 <span data-ttu-id="003fc-116">allen numerischen Typen</span><span class="sxs-lookup"><span data-stu-id="003fc-116">All numeric types.</span></span> <span data-ttu-id="003fc-117">Dies schließt die unsignierten-und Gleit Komma Typen und ein `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="003fc-117">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="003fc-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="003fc-118">Remarks</span></span>  
 <span data-ttu-id="003fc-119">In der ersten Verwendung, die in der zuvor gezeigten Syntax gezeigt wurde, `–` ist der Operator der *binäre* arithmetische Subtraktions Operator für den Unterschied zwischen zwei numerischen Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="003fc-119">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="003fc-120">In der zweiten Syntax, die in der zuvor gezeigten Syntax angezeigt wird, `–` ist der Operator der *unäre* Negations Operator für den negativen Wert eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="003fc-120">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="003fc-121">In diesem Sinne besteht die Negation darin, das Vorzeichen von umzukehren, `expression1` sodass das Ergebnis positiv ist, wenn `expression1` negativ ist.</span><span class="sxs-lookup"><span data-stu-id="003fc-121">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="003fc-122">Wenn ein Ausdruck zu " [Nothing](../nothing.md)" ausgewertet wird, `–` behandelt der Operator ihn als 0 (null).</span><span class="sxs-lookup"><span data-stu-id="003fc-122">If either expression evaluates to [Nothing](../nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="003fc-123">Der `–` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="003fc-123">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="003fc-124">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="003fc-124">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="003fc-125">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="003fc-125">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="003fc-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="003fc-126">Example</span></span>  
 <span data-ttu-id="003fc-127">Im folgenden Beispiel wird der- `–` Operator verwendet, um die Differenz zwischen zwei Zahlen zu berechnen und zurückzugeben und dann eine Zahl zu negieren.</span><span class="sxs-lookup"><span data-stu-id="003fc-127">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="003fc-128">Nach der Ausführung dieser Anweisungen `binaryResult` enthält 124,45 und `unaryResult` enthält – 334,90.</span><span class="sxs-lookup"><span data-stu-id="003fc-128">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003fc-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="003fc-129">See also</span></span>

- [<span data-ttu-id="003fc-130">Operator-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="003fc-130">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="003fc-131">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="003fc-131">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="003fc-132">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="003fc-132">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="003fc-133">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="003fc-133">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="003fc-134">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="003fc-134">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
