---
title: ^=-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa9d87d2f090a8c18aaab742e73878c7b80f55c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e1b5d-102">^=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1b5d-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="e1b5d-103">Löst den Wert einer Variablen oder Eigenschaft, um die Leistungsfähigkeit eines Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1b5d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1b5d-104">Syntax</span></span>  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="e1b5d-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e1b5d-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="e1b5d-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-106">Required.</span></span> <span data-ttu-id="e1b5d-107">Eine beliebige numerische Variable oder eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="e1b5d-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-108">Required.</span></span> <span data-ttu-id="e1b5d-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1b5d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1b5d-110">Remarks</span></span>  
 <span data-ttu-id="e1b5d-111">Das Element auf der linken Seite von der `^=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="e1b5d-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="e1b5d-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="e1b5d-113">Die `^=` löst der Operator zuerst den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators) mit der der Wert des Ausdrucks (auf der rechten Seite des Operators).</span><span class="sxs-lookup"><span data-stu-id="e1b5d-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="e1b5d-114">Der Operator weist das Ergebnis dieses Vorgangs dann der Variablen oder Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="e1b5d-115">Visual Basic führt immer Potenzierung der [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="e1b5d-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="e1b5d-116">Die Operanden eines anderen Typs konvertiert werden `Double`, und das Ergebnis ist immer `Double`.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="e1b5d-117">Der Wert des `expression` kann Bruch, negativ oder beides.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e1b5d-118">Überladen</span><span class="sxs-lookup"><span data-stu-id="e1b5d-118">Overloading</span></span>  
 <span data-ttu-id="e1b5d-119">Die [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e1b5d-120">Überladen der `^` Operator wirkt sich auf das Verhalten der `^=` Operator.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="e1b5d-121">Wenn im Code verwendet `^=` auf eine Klasse oder Struktur, die Überladungen `^`, achten Sie verstehen, dass ihr neu definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e1b5d-122">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e1b5d-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1b5d-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1b5d-123">Example</span></span>  
 <span data-ttu-id="e1b5d-124">Im folgenden Beispiel wird die `^=` Operator zum Auslösen des Wertes eines `Integer` Variable mit einer zweiten Variable und das Ergebnis die erste Variable zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="e1b5d-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e1b5d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1b5d-125">See Also</span></span>  
 [<span data-ttu-id="e1b5d-126">^-Operator</span><span class="sxs-lookup"><span data-stu-id="e1b5d-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)  
 [<span data-ttu-id="e1b5d-127">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="e1b5d-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="e1b5d-128">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="e1b5d-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="e1b5d-129">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1b5d-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="e1b5d-130">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="e1b5d-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="e1b5d-131">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="e1b5d-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
