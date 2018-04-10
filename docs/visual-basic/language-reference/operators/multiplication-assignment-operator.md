---
title: '*=-Operator (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0a2c638f3faaf20fadb745ef437941ee29d4f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="441dc-102">\*=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="441dc-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="441dc-103">Multipliziert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="441dc-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="441dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="441dc-104">Syntax</span></span>  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="441dc-105">Teile</span><span class="sxs-lookup"><span data-stu-id="441dc-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="441dc-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="441dc-106">Required.</span></span> <span data-ttu-id="441dc-107">Eine beliebige numerische Variable oder eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="441dc-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="441dc-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="441dc-108">Required.</span></span> <span data-ttu-id="441dc-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="441dc-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="441dc-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="441dc-110">Remarks</span></span>  
 <span data-ttu-id="441dc-111">Das Element auf der linken Seite von der `*=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="441dc-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="441dc-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="441dc-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="441dc-113">Die `*=` Operator multipliziert zuerst den Wert des Ausdrucks (auf der rechten Seite des Operators), durch den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators).</span><span class="sxs-lookup"><span data-stu-id="441dc-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="441dc-114">Der Operator weist das Ergebnis dieses Vorgangs dann der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="441dc-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="441dc-115">Überladen</span><span class="sxs-lookup"><span data-stu-id="441dc-115">Overloading</span></span>  
 <span data-ttu-id="441dc-116">Die [\*-Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="441dc-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="441dc-117">Überladen der `*` Operator wirkt sich auf das Verhalten der `*=` Operator.</span><span class="sxs-lookup"><span data-stu-id="441dc-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="441dc-118">Wenn im Code verwendet `*=` auf eine Klasse oder Struktur, die Überladungen `*`, achten Sie verstehen, dass ihr neu definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="441dc-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="441dc-119">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="441dc-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="441dc-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="441dc-120">Example</span></span>  
 <span data-ttu-id="441dc-121">Im folgenden Beispiel wird die `*=` Operator, um eine Multiplizieren `Integer` Variable, indem das zweite und das Ergebnis die erste Variable zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="441dc-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="441dc-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="441dc-122">See Also</span></span>  
 [<span data-ttu-id="441dc-123">\*-Operator</span><span class="sxs-lookup"><span data-stu-id="441dc-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)  
 [<span data-ttu-id="441dc-124">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="441dc-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="441dc-125">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="441dc-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="441dc-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="441dc-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="441dc-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="441dc-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="441dc-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="441dc-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
