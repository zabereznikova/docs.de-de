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
ms.openlocfilehash: 4b8f36397d0f52866ebe9fa188d6b163364aeffc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839012"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="9859e-102">+=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9859e-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="9859e-103">Der Wert einer numerischen Variablen oder Eigenschaft den Wert eines numerischen Ausdrucks hinzugefügt, und weist das Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9859e-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="9859e-104">Kann auch verwendet werden, zum Verketten von einer `String` Ausdruck, der eine `String` Variablen oder einer Eigenschaft sowie das Ergebnis der Variablen oder Eigenschaft zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="9859e-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9859e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9859e-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="9859e-106">Teile</span><span class="sxs-lookup"><span data-stu-id="9859e-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="9859e-107">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9859e-107">Required.</span></span> <span data-ttu-id="9859e-108">Alle numerischen oder `String` Variable oder eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9859e-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="9859e-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9859e-109">Required.</span></span> <span data-ttu-id="9859e-110">Alle numerischen oder `String` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9859e-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9859e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9859e-111">Remarks</span></span>  
 <span data-ttu-id="9859e-112">Das Element auf der linken Seite von der `+=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="9859e-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="9859e-113">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="9859e-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="9859e-114">Die `+=` Operator fügt den Wert auf der rechten Seite der Variablen oder die Eigenschaft auf der linken Seite und weist das Ergebnis der Variablen oder Eigenschaft auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="9859e-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="9859e-115">Die `+=` Operator kann auch zum Verketten verwendet werden die `String` Ausdruck auf der rechten Seite, um die `String` Variable oder Eigenschaft auf der linken Seite, und weisen Sie das Ergebnis der Variablen oder Eigenschaft in der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="9859e-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9859e-116">Bei Verwendung der `+=` Operator an, Sie möglicherweise nicht bestimmen, ob die Additions- oder Zeichenfolge Verkettung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="9859e-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="9859e-117">Verwenden der `&=` Operator zum Verketten, um Mehrdeutigkeit zu vermeiden und um selbst dokumentierender Code bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9859e-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="9859e-118">Dieser Zuweisungsoperator führt implizit erweitern, aber keine einschränkende Konvertierungen, wenn der kompilierungsumgebung strikte Semantik erzwingt.</span><span class="sxs-lookup"><span data-stu-id="9859e-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="9859e-119">Weitere Informationen zu dieser Konvertierungen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="9859e-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="9859e-120">Weitere Informationen zu strikte und flexible Semantik, finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9859e-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="9859e-121">Wenn Semantik zulässig sind, die `+=` Operator führt implizit eine Vielzahl von Zeichenfolgen- und numerische Konvertierungen identisch, mit denen die `+` Operator.</span><span class="sxs-lookup"><span data-stu-id="9859e-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="9859e-122">Weitere Informationen zu dieser Konvertierungen finden Sie unter [+-Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9859e-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9859e-123">Überladen</span><span class="sxs-lookup"><span data-stu-id="9859e-123">Overloading</span></span>  
 <span data-ttu-id="9859e-124">Die `+` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="9859e-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9859e-125">Das Überladen der `+` Operator beeinflusst das Verhalten von der `+=` Operator.</span><span class="sxs-lookup"><span data-stu-id="9859e-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="9859e-126">Wenn Ihr Code verwendet `+=` für eine Klasse oder Struktur, die Überladungen `+`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9859e-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9859e-127">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9859e-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9859e-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9859e-128">Example</span></span>  
 <span data-ttu-id="9859e-129">Im folgenden Beispiel wird die `+=` Operator, um den Wert einer Variablen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9859e-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="9859e-130">Der erste Teil verwendet `+=` mit numerischen Variablen einen Wert in einen anderen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9859e-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="9859e-131">Der zweite Teil verwendet `+=` mit `String` Variablen, einem Wert mit einem anderen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="9859e-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="9859e-132">In beiden Fällen wird das Ergebnis der ersten Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9859e-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="9859e-133">Der Wert des `num1` ist jetzt 13 und den Wert der `str1` ist jetzt "103".</span><span class="sxs-lookup"><span data-stu-id="9859e-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9859e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9859e-134">See also</span></span>

- [<span data-ttu-id="9859e-135">+-Operator</span><span class="sxs-lookup"><span data-stu-id="9859e-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="9859e-136">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="9859e-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="9859e-137">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="9859e-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="9859e-138">Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="9859e-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="9859e-139">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9859e-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9859e-140">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="9859e-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9859e-141">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="9859e-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
