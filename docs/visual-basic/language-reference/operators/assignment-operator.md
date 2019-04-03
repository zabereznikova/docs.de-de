---
title: =-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: ad74e3ebc947af4f36022be838b69df6ce24997a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840288"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="3d934-102">=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d934-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="3d934-103">Eine Variable oder Eigenschaft ein Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3d934-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d934-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d934-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="3d934-105">Teile</span><span class="sxs-lookup"><span data-stu-id="3d934-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="3d934-106">Jeder schreibbare Variable oder eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3d934-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="3d934-107">Jeder Literal, eine Konstante oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="3d934-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d934-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d934-108">Remarks</span></span>  
 <span data-ttu-id="3d934-109">Das Element auf der linken Seite des Gleichheitszeichens (`=`) kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="3d934-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="3d934-110">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="3d934-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="3d934-111">Die `=` Operator weist den Wert auf der rechten Seite auf die Variable oder Eigenschaft auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="3d934-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d934-112">Die `=` -Operator wird auch als Vergleichsoperator verwendet.</span><span class="sxs-lookup"><span data-stu-id="3d934-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="3d934-113">Weitere Informationen finden Sie unter [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="3d934-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="3d934-114">Überladen</span><span class="sxs-lookup"><span data-stu-id="3d934-114">Overloading</span></span>  
 <span data-ttu-id="3d934-115">Die `=` Operator kann nur als relationale Vergleichsoperator und nicht als ein Zuweisungsoperator überladen werden.</span><span class="sxs-lookup"><span data-stu-id="3d934-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="3d934-116">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3d934-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d934-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3d934-117">Example</span></span>  
 <span data-ttu-id="3d934-118">Im folgende Beispiel wird veranschaulicht, den Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="3d934-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="3d934-119">Der Wert auf der rechten Seite wird die Variable auf der linken Seite zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3d934-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="3d934-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d934-120">See also</span></span>

- [<span data-ttu-id="3d934-121">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="3d934-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="3d934-122">\* =-Operator</span><span class="sxs-lookup"><span data-stu-id="3d934-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="3d934-123">+=-Operator</span><span class="sxs-lookup"><span data-stu-id="3d934-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="3d934-124">Operator-=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d934-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="3d934-125">/ =-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d934-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="3d934-126">\\= Operator</span><span class="sxs-lookup"><span data-stu-id="3d934-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="3d934-127">^=-Operator</span><span class="sxs-lookup"><span data-stu-id="3d934-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="3d934-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="3d934-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="3d934-129">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="3d934-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="3d934-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="3d934-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="3d934-131">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="3d934-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
