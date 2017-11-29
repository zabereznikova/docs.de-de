---
title: /=-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94448856072a949582e64577287134c4b975bfec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="5d70e-102">/=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d70e-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="5d70e-103">Dividiert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das Gleitkomma Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5d70e-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d70e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d70e-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="5d70e-105">Teile</span><span class="sxs-lookup"><span data-stu-id="5d70e-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="5d70e-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5d70e-106">Required.</span></span> <span data-ttu-id="5d70e-107">Eine beliebige numerische Variable oder eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5d70e-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="5d70e-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5d70e-108">Required.</span></span> <span data-ttu-id="5d70e-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5d70e-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d70e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d70e-110">Remarks</span></span>  
 <span data-ttu-id="5d70e-111">Das Element auf der linken Seite von der `/=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="5d70e-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="5d70e-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="5d70e-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="5d70e-113">Die `/=` Operator dividiert zuerst den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators) durch den Wert des Ausdrucks (auf der rechten Seite des Operators).</span><span class="sxs-lookup"><span data-stu-id="5d70e-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="5d70e-114">Der Operator weist die Gleitkommaergebnis dieses Vorgangs zu der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5d70e-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="5d70e-115">Diese Anweisung weist ein `Double` Wert der Variablen oder Eigenschaft auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="5d70e-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="5d70e-116">Wenn `Option Strict` ist `On`, `variableorproperty` muss eine `Double`.</span><span class="sxs-lookup"><span data-stu-id="5d70e-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="5d70e-117">Wenn `Option Strict` ist `Off`, Visual Basic führt eine implizite Konvertierung und weist den resultierenden Wert `variableorproperty`, mit der ein möglicher Fehler zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="5d70e-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="5d70e-118">Weitere Informationen finden Sie unter [Widening und einschränkende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5d70e-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5d70e-119">Überladen</span><span class="sxs-lookup"><span data-stu-id="5d70e-119">Overloading</span></span>  
 <span data-ttu-id="5d70e-120">Die [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="5d70e-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5d70e-121">Überladen der `/` Operator wirkt sich auf das Verhalten der `/=` Operator.</span><span class="sxs-lookup"><span data-stu-id="5d70e-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="5d70e-122">Wenn im Code verwendet `/=` auf eine Klasse oder Struktur, die Überladungen `/`, achten Sie verstehen, dass ihr neu definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="5d70e-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5d70e-123">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5d70e-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d70e-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d70e-124">Example</span></span>  
 <span data-ttu-id="5d70e-125">Im folgenden Beispiel wird die `/=` Operator, um einen unterteilen `Integer` Variable, indem das zweite und das Zuweisen der Quotient der ersten Variablen.</span><span class="sxs-lookup"><span data-stu-id="5d70e-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5d70e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d70e-126">See Also</span></span>  
 [<span data-ttu-id="5d70e-127">/-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d70e-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [<span data-ttu-id="5d70e-128">\\=-Operator</span><span class="sxs-lookup"><span data-stu-id="5d70e-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="5d70e-129">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="5d70e-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="5d70e-130">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="5d70e-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="5d70e-131">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d70e-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="5d70e-132">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="5d70e-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="5d70e-133">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="5d70e-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
