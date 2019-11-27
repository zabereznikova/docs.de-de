---
title: Operator +=
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
ms.openlocfilehash: 31a6da163061b905b8ffddcfc4b44978f5cdd55e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350304"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="61276-102">+=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61276-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="61276-103">Fügt den Wert eines numerischen Ausdrucks zum Wert einer numerischen Variablen oder Eigenschaft hinzu und weist das Ergebnis der Variablen oder Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="61276-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="61276-104">Kann auch verwendet werden, um einen `String` Ausdruck mit einer `String` Variablen oder Eigenschaft zu verketten und das Ergebnis der Variablen oder der Eigenschaft zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="61276-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61276-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="61276-105">Syntax</span></span>  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="61276-106">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="61276-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="61276-107">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="61276-107">Required.</span></span> <span data-ttu-id="61276-108">Eine beliebige numerische Variable oder `String` Variable oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="61276-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="61276-109">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="61276-109">Required.</span></span> <span data-ttu-id="61276-110">Ein beliebiger numerischer Ausdruck oder `String` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="61276-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61276-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61276-111">Remarks</span></span>  
 <span data-ttu-id="61276-112">Das Element auf der linken Seite des `+=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="61276-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="61276-113">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="61276-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="61276-114">Der `+=`-Operator Fügt der Variablen oder der Eigenschaft auf der linken Seite den Wert auf der rechten Seite hinzu und weist das Ergebnis der Variablen oder der Eigenschaft auf der linken Seite zu.</span><span class="sxs-lookup"><span data-stu-id="61276-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="61276-115">Der `+=`-Operator kann auch verwendet werden, um den `String` Ausdruck rechts von der `String` Variablen oder Eigenschaft auf der linken Seite zu verketten und das Ergebnis der Variablen oder der Eigenschaft auf der linken Seite zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="61276-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61276-116">Wenn Sie den `+=`-Operator verwenden, sind Sie möglicherweise nicht in der Lage, zu bestimmen, ob Addition oder Zeichen folgen Verkettung stattfinden.</span><span class="sxs-lookup"><span data-stu-id="61276-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="61276-117">Verwenden Sie den `&=`-Operator für die Verkettung, um Mehrdeutigkeit zu vermeiden und selbst dokumentierenden Code bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="61276-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="61276-118">Dieser Zuweisungs Operator führt implizit erweiternde, aber keine einschränkenden Konvertierungen durch, wenn die Kompilierungs Umgebung strikte Semantik erzwingt.</span><span class="sxs-lookup"><span data-stu-id="61276-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="61276-119">Weitere Informationen zu diesen Konvertierungen finden Sie unter [erweiternde und einschränkende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="61276-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="61276-120">Weitere Informationen zu Strict-und einschränkend sein Semantik finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="61276-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="61276-121">Wenn eine einschränkend sein Semantik zulässig ist, führt der `+=` Operator implizit eine Vielzahl von Zeichen folgen-und numerischen Konvertierungen aus, die mit denen des `+`-Operators identisch sind.</span><span class="sxs-lookup"><span data-stu-id="61276-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="61276-122">Ausführliche Informationen zu diesen Konvertierungen finden Sie unter [+-Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="61276-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="61276-123">Überladen</span><span class="sxs-lookup"><span data-stu-id="61276-123">Overloading</span></span>  
 <span data-ttu-id="61276-124">Der `+`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="61276-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="61276-125">Das Überladen des `+` Operators wirkt sich auf das Verhalten des `+=` Operators aus.</span><span class="sxs-lookup"><span data-stu-id="61276-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="61276-126">Wenn Ihr Code `+=` in einer Klasse oder Struktur verwendet, die `+`überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="61276-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="61276-127">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="61276-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="61276-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61276-128">Example</span></span>  
 <span data-ttu-id="61276-129">Im folgenden Beispiel wird der `+=`-Operator verwendet, um den Wert einer Variablen mit einem anderen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="61276-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="61276-130">Im ersten Teil wird `+=` mit numerischen Variablen verwendet, um einen Wert zu einem anderen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="61276-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="61276-131">Im zweiten Teil wird `+=` mit `String` Variablen verwendet, um einen Wert mit einem anderen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="61276-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="61276-132">In beiden Fällen wird das Ergebnis der ersten Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="61276-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="61276-133">Der Wert von `num1` ist nun 13, und der Wert von `str1` ist nun "103".</span><span class="sxs-lookup"><span data-stu-id="61276-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61276-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61276-134">See also</span></span>

- [<span data-ttu-id="61276-135">+-Operator</span><span class="sxs-lookup"><span data-stu-id="61276-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="61276-136">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="61276-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="61276-137">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="61276-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="61276-138">Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="61276-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="61276-139">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61276-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="61276-140">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="61276-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="61276-141">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="61276-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
