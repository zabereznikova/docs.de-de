---
title: +=-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: f12a0560d984f871110c02f1df2c2ec42b68809b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="fde8b-102">+=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fde8b-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="fde8b-103">Fügt den Wert eines numerischen Variablen oder einer Eigenschaft den Wert eines numerischen Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fde8b-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="fde8b-104">Kann auch zum Verketten verwendet eine `String` Ausdruck, der eine `String` Variablen oder einer Eigenschaft und das Ergebnis der Variablen oder Eigenschaft zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="fde8b-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fde8b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fde8b-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="fde8b-106">Teile</span><span class="sxs-lookup"><span data-stu-id="fde8b-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="fde8b-107">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fde8b-107">Required.</span></span> <span data-ttu-id="fde8b-108">Ein beliebiges numerisches oder `String` Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fde8b-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="fde8b-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fde8b-109">Required.</span></span> <span data-ttu-id="fde8b-110">Ein beliebiges numerisches oder `String` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="fde8b-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fde8b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fde8b-111">Remarks</span></span>  
 <span data-ttu-id="fde8b-112">Das Element auf der linken Seite von der `+=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="fde8b-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="fde8b-113">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="fde8b-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="fde8b-114">Die `+=` Operator fügt den Wert auf der rechten Seite der Variablen oder Eigenschaft auf der linken und weist das Ergebnis der Variablen oder Eigenschaft auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="fde8b-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="fde8b-115">Die `+=` -Operator kann auch zum Verketten verwendet werden die `String` Ausdruck auf der rechten Seite, um die `String` Variable oder die Eigenschaft auf der linken Seite und weisen das Ergebnis der Variablen oder Eigenschaft auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="fde8b-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fde8b-116">Bei Verwendung der `+=` -Operator, Sie möglicherweise nicht zu bestimmen, ob die Addition oder Zeichenfolge Verkettung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="fde8b-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="fde8b-117">Verwenden der `&=` Operator zum Verketten, um Mehrdeutigkeit zu vermeiden und sich selbst dokumentierenden Code bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="fde8b-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="fde8b-118">Dieser Zuweisungsoperator führt implizit erweiternde jedoch keine einschränkende Konvertierungen, wenn der kompilierungsumgebung strikte Semantik erzwingt.</span><span class="sxs-lookup"><span data-stu-id="fde8b-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="fde8b-119">Weitere Informationen zu dieser Konvertierungen finden Sie unter [Widening und einschränkende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="fde8b-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="fde8b-120">Weitere Informationen zu strikte und flexible Semantik, finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fde8b-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="fde8b-121">Wenn Semantik zulässig sind, die `+=` Operator führt implizit eine Vielzahl von Zeichenfolgen und numerische Konvertierungen identisch, mit denen die `+` Operator.</span><span class="sxs-lookup"><span data-stu-id="fde8b-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="fde8b-122">Ausführliche Informationen zu dieser Konvertierungen, finden Sie unter [+-Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="fde8b-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="fde8b-123">Überladen</span><span class="sxs-lookup"><span data-stu-id="fde8b-123">Overloading</span></span>  
 <span data-ttu-id="fde8b-124">Die `+` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="fde8b-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fde8b-125">Überladen der `+` Operator wirkt sich auf das Verhalten der `+=` Operator.</span><span class="sxs-lookup"><span data-stu-id="fde8b-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="fde8b-126">Wenn im Code verwendet `+=` auf eine Klasse oder Struktur, die Überladungen `+`, achten Sie verstehen, dass ihr neu definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="fde8b-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="fde8b-127">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fde8b-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fde8b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fde8b-128">Example</span></span>  
 <span data-ttu-id="fde8b-129">Im folgenden Beispiel wird die `+=` Operator, um den Wert einer Variablen mit einem anderen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="fde8b-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="fde8b-130">Der erste Teil verwendet `+=` mit numerischen Variablen einen Wert in einen anderen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fde8b-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="fde8b-131">Der zweite Teil verwendet `+=` mit `String` Variablen einen Wert mit einem anderen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="fde8b-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="fde8b-132">In beiden Fällen ist das Ergebnis der ersten Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="fde8b-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 <span data-ttu-id="fde8b-133">Der Wert der `num1` ist jetzt 13 und den Wert des `str1` ist jetzt "103".</span><span class="sxs-lookup"><span data-stu-id="fde8b-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde8b-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fde8b-134">See Also</span></span>  
 [<span data-ttu-id="fde8b-135">+-Operator</span><span class="sxs-lookup"><span data-stu-id="fde8b-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)  
 [<span data-ttu-id="fde8b-136">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="fde8b-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="fde8b-137">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="fde8b-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="fde8b-138">Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="fde8b-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="fde8b-139">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fde8b-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="fde8b-140">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="fde8b-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="fde8b-141">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="fde8b-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
