---
title: '\-Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: d1a46f99c21be007d33361ba095a3f0c52fe906c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701144"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="48755-102">\-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48755-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="48755-103">Dividiert zwei Zahlen und gibt ein ganzzahliges Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="48755-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48755-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48755-104">Syntax</span></span>  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="48755-105">Teile</span><span class="sxs-lookup"><span data-stu-id="48755-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="48755-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="48755-106">Required.</span></span> <span data-ttu-id="48755-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="48755-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="48755-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="48755-108">Required.</span></span> <span data-ttu-id="48755-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="48755-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="48755-110">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="48755-110">Supported Types</span></span>  
 <span data-ttu-id="48755-111">Alle numerischen Typen, einschließlich der nicht signierten-und Gleit Komma Typen `Decimal`und.</span><span class="sxs-lookup"><span data-stu-id="48755-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="48755-112">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="48755-112">Result</span></span>  
 <span data-ttu-id="48755-113">Das Ergebnis ist der ganzzahlige Quotienten `expression1` von `expression2`dividiert durch, der jeden Rest verwirft und nur den ganzzahligen Teil beibehält.</span><span class="sxs-lookup"><span data-stu-id="48755-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="48755-114">Dies wird als *Abschneiden*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="48755-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="48755-115">Der Ergebnis Datentyp ist ein numerischer Typ, der für die Daten `expression1` Typen `expression2`von und geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="48755-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="48755-116">Weitere Informationen finden Sie in den Tabellen "ganzzahlige Arithmetik" unter [Datentypen von Operator Ergebnissen](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)</span><span class="sxs-lookup"><span data-stu-id="48755-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="48755-117">Der [Operator/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt den vollständigen Quotienten zurück, der den Restwert im Bruch Teil beibehält.</span><span class="sxs-lookup"><span data-stu-id="48755-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48755-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48755-118">Remarks</span></span>  
 <span data-ttu-id="48755-119">Vor der Durchführung der Division versucht Visual Basic, den numerischen Gleit Komma Ausdruck in zu `Long`konvertieren.</span><span class="sxs-lookup"><span data-stu-id="48755-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="48755-120">Wenn `Option Strict`den Wert hat,tritteinCompilerfehlerauf.`On`</span><span class="sxs-lookup"><span data-stu-id="48755-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="48755-121">Wenn `Option Strict` den Wert `Off` aufweist, ist <xref:System.OverflowException> möglich, wenn der Wert außerhalb des Bereichs des [Long-Datentyps](../../../visual-basic/language-reference/data-types/long-data-type.md) liegt.</span><span class="sxs-lookup"><span data-stu-id="48755-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="48755-122">Die Konvertierung in "`Long`" unterliegt auch der über *Rundung von bankten*.</span><span class="sxs-lookup"><span data-stu-id="48755-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="48755-123">Weitere Informationen finden Sie unter "Bruchteile" in den [Typkonvertierungs Funktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="48755-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="48755-124">Wenn `expression1` oder`expression2` als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird es als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="48755-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="48755-125">Versuchte Division durch Null</span><span class="sxs-lookup"><span data-stu-id="48755-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="48755-126">Wenn `expression2` NULL ergibt, löst der `\` Operator eine <xref:System.DivideByZeroException> -Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="48755-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="48755-127">Dies gilt für alle numerischen Datentypen der Operanden.</span><span class="sxs-lookup"><span data-stu-id="48755-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48755-128">Der `\`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="48755-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="48755-129">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="48755-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="48755-130">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="48755-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="48755-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48755-131">Example</span></span>  
 <span data-ttu-id="48755-132">Im folgenden Beispiel wird der `\` -Operator verwendet, um eine ganz Zahl Division auszuführen.</span><span class="sxs-lookup"><span data-stu-id="48755-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="48755-133">Das Ergebnis ist eine ganze Zahl, die den ganzzahligen Quotienten der beiden Operanden darstellt, wobei der restliche Rest verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="48755-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 <span data-ttu-id="48755-134">Die Ausdrücke im vorherigen Beispiel geben Werte von 2, 3, 33 bzw.-22 zurück.</span><span class="sxs-lookup"><span data-stu-id="48755-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48755-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48755-135">See also</span></span>

- [<span data-ttu-id="48755-136">\\ =-Operator</span><span class="sxs-lookup"><span data-stu-id="48755-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="48755-137">Operator/(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48755-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="48755-138">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="48755-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="48755-139">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="48755-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="48755-140">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48755-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="48755-141">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="48755-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="48755-142">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48755-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
