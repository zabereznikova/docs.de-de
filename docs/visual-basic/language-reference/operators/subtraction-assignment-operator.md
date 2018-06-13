---
title: -=-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: 598fd9db4262d0a33bf0408ebe9455760d5e4506
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603872"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="69001-102">-=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69001-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="69001-103">Subtrahiert den Wert eines Ausdrucks vom Wert einer Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="69001-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69001-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69001-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="69001-105">Teile</span><span class="sxs-lookup"><span data-stu-id="69001-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="69001-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="69001-106">Required.</span></span> <span data-ttu-id="69001-107">Eine beliebige numerische Variable oder eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="69001-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="69001-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="69001-108">Required.</span></span> <span data-ttu-id="69001-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="69001-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69001-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69001-110">Remarks</span></span>  
 <span data-ttu-id="69001-111">Das Element auf der linken Seite von der `-=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="69001-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="69001-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="69001-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="69001-113">Die `-=` Operator subtrahiert den Wert des Ausdrucks (auf der rechten Seite des Operators) zuerst aus dem Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators).</span><span class="sxs-lookup"><span data-stu-id="69001-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="69001-114">Der Operator weist das Ergebnis dieses Vorgangs dann der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="69001-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="69001-115">Überladen</span><span class="sxs-lookup"><span data-stu-id="69001-115">Overloading</span></span>  
 <span data-ttu-id="69001-116">Die [-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="69001-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="69001-117">Überladen der `-` Operator wirkt sich auf das Verhalten der `-=` Operator.</span><span class="sxs-lookup"><span data-stu-id="69001-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="69001-118">Wenn im Code verwendet `-=` auf eine Klasse oder Struktur, die Überladungen `-`, achten Sie verstehen, dass ihr neu definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="69001-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="69001-119">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="69001-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="69001-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="69001-120">Example</span></span>  
 <span data-ttu-id="69001-121">Im folgenden Beispiel wird die `-=` Operator subtrahiert einen `Integer` Variable von einem anderen und das Ergebnis der zweiten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="69001-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="69001-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69001-122">See Also</span></span>  
 [<span data-ttu-id="69001-123">--Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69001-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)  
 [<span data-ttu-id="69001-124">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="69001-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="69001-125">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="69001-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="69001-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69001-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="69001-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="69001-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="69001-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="69001-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
