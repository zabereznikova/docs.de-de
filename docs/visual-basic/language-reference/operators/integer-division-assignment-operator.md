---
title: '\= Operator'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 4ebbf2eca7fb3cd208d979d7f3c77aa106569119
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603560"
---
# <a name="-operator"></a><span data-ttu-id="a7ffa-102">\\=-Operator</span><span class="sxs-lookup"><span data-stu-id="a7ffa-102">\\= Operator</span></span>
<span data-ttu-id="a7ffa-103">Dividiert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das ganzzahlige Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a7ffa-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ffa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7ffa-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a7ffa-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a7ffa-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a7ffa-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a7ffa-106">Required.</span></span> <span data-ttu-id="a7ffa-107">Eine beliebige numerische Variable oder eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a7ffa-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="a7ffa-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a7ffa-108">Required.</span></span> <span data-ttu-id="a7ffa-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a7ffa-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7ffa-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7ffa-110">Remarks</span></span>  
 <span data-ttu-id="a7ffa-111">Das Element auf der linken Seite von der `\=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="a7ffa-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a7ffa-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="a7ffa-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a7ffa-113">Die `\=` Operator dividiert durch den Wert auf der rechten Seite den Wert einer Variablen oder Eigenschaft auf der linken und weist das ganzzahlige Ergebnis der Variablen oder Eigenschaft auf der linken Seite</span><span class="sxs-lookup"><span data-stu-id="a7ffa-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="a7ffa-114">Weitere Informationen zu ganzzahligen Division, finden Sie unter [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a7ffa-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a7ffa-115">Überladen</span><span class="sxs-lookup"><span data-stu-id="a7ffa-115">Overloading</span></span>  
 <span data-ttu-id="a7ffa-116">Die `\` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="a7ffa-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a7ffa-117">Überladen der `\` Operator wirkt sich auf das Verhalten der `\=` Operator.</span><span class="sxs-lookup"><span data-stu-id="a7ffa-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="a7ffa-118">Wenn im Code verwendet `\=` auf eine Klasse oder Struktur, die Überladungen `\`, achten Sie verstehen, dass ihr neu definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="a7ffa-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a7ffa-119">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a7ffa-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7ffa-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7ffa-120">Example</span></span>  
 <span data-ttu-id="a7ffa-121">Im folgenden Beispiel wird die `\=` Operator, um einen unterteilen `Integer` Variable, indem das zweite und das ganzzahlige Ergebnis der ersten Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a7ffa-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](codesnippet/VisualBasic/integer-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a7ffa-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7ffa-122">See Also</span></span>  
 [<span data-ttu-id="a7ffa-123">\-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7ffa-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [<span data-ttu-id="a7ffa-124">/ =-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7ffa-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="a7ffa-125">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="a7ffa-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="a7ffa-126">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="a7ffa-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="a7ffa-127">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7ffa-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="a7ffa-128">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="a7ffa-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="a7ffa-129">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="a7ffa-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
