---
title: =-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 230005640b2b494e5413b14ba13a7cb82ee9f22b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="4ccd4-102">=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ccd4-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="4ccd4-103">Weist einen Wert an eine Variable oder eine Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="4ccd4-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ccd4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ccd4-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="4ccd4-105">Teile</span><span class="sxs-lookup"><span data-stu-id="4ccd4-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="4ccd4-106">Jede schreibbare Variable oder eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4ccd4-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="4ccd4-107">Ein Literal, eine Konstante oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4ccd4-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ccd4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ccd4-108">Remarks</span></span>  
 <span data-ttu-id="4ccd4-109">Das Element auf der linken Seite des Gleichheitszeichens (`=`) kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="4ccd4-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="4ccd4-110">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="4ccd4-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="4ccd4-111">Die `=` -Operator weist den Wert auf der rechten Seite der Variablen oder Eigenschaft auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="4ccd4-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ccd4-112">Die `=` Operator wird auch als Vergleichsoperator verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ccd4-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="4ccd4-113">Weitere Informationen finden Sie unter [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="4ccd4-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4ccd4-114">Überladen</span><span class="sxs-lookup"><span data-stu-id="4ccd4-114">Overloading</span></span>  
 <span data-ttu-id="4ccd4-115">Die `=` Operator kann nur als relationalen Vergleichsoperator und nicht als Zuweisungsoperator überladen werden.</span><span class="sxs-lookup"><span data-stu-id="4ccd4-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="4ccd4-116">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4ccd4-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ccd4-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4ccd4-117">Example</span></span>  
 <span data-ttu-id="4ccd4-118">Im folgende Beispiel wird veranschaulicht, den Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="4ccd4-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="4ccd4-119">Der Wert auf der rechten Seite ist die Variable auf der linken Seite zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4ccd4-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4ccd4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ccd4-120">See Also</span></span>  
 [<span data-ttu-id="4ccd4-121">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="4ccd4-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="4ccd4-122">\* =-Operator</span><span class="sxs-lookup"><span data-stu-id="4ccd4-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [<span data-ttu-id="4ccd4-123">+=-Operator</span><span class="sxs-lookup"><span data-stu-id="4ccd4-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [<span data-ttu-id="4ccd4-124">Operator-=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ccd4-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [<span data-ttu-id="4ccd4-125">/ =-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ccd4-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="4ccd4-126">\\=-Operator</span><span class="sxs-lookup"><span data-stu-id="4ccd4-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="4ccd4-127">^=-Operator</span><span class="sxs-lookup"><span data-stu-id="4ccd4-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [<span data-ttu-id="4ccd4-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="4ccd4-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="4ccd4-129">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="4ccd4-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="4ccd4-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="4ccd4-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [<span data-ttu-id="4ccd4-131">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="4ccd4-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
