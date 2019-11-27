---
title: Operator =
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 75f303219b9bf32613989f65f90a9096ef70e02e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350206"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a8bd0-102">=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8bd0-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="a8bd0-103">Weist einer Variablen oder Eigenschaft einen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8bd0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8bd0-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="a8bd0-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="a8bd0-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a8bd0-106">Eine beliebige beschreibbare Variable oder eine beliebige Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="a8bd0-107">Beliebiges Literalzeichen, Konstante oder Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8bd0-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8bd0-108">Remarks</span></span>  
 <span data-ttu-id="a8bd0-109">Das Element auf der linken Seite des Gleichheitszeichens (`=`) kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a8bd0-110">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="a8bd0-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="a8bd0-111">Der `=`-Operator weist der Variablen oder der Eigenschaft auf der linken Seite den Wert auf der rechten Seite zu.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8bd0-112">Der `=`-Operator wird auch als Vergleichs Operator verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="a8bd0-113">Weitere Informationen finden Sie unter [Vergleichs Operatoren](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="a8bd0-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a8bd0-114">Überladen</span><span class="sxs-lookup"><span data-stu-id="a8bd0-114">Overloading</span></span>  
 <span data-ttu-id="a8bd0-115">Der `=`-Operator kann nur als relationaler Vergleichs Operator, nicht als Zuweisungs Operator, überladen werden.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="a8bd0-116">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a8bd0-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8bd0-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a8bd0-117">Example</span></span>  
 <span data-ttu-id="a8bd0-118">Im folgenden Beispiel wird der Zuweisungs Operator veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="a8bd0-119">Der Wert auf der rechten Seite wird der Variablen auf der linken Seite zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a8bd0-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="a8bd0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8bd0-120">See also</span></span>

- [<span data-ttu-id="a8bd0-121">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="a8bd0-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="a8bd0-122">\* =-Operator</span><span class="sxs-lookup"><span data-stu-id="a8bd0-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="a8bd0-123">+=-Operator</span><span class="sxs-lookup"><span data-stu-id="a8bd0-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="a8bd0-124">Operator-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8bd0-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="a8bd0-125">Operator/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8bd0-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="a8bd0-126">\\=-Operator</span><span class="sxs-lookup"><span data-stu-id="a8bd0-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="a8bd0-127">^=-Operator</span><span class="sxs-lookup"><span data-stu-id="a8bd0-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="a8bd0-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="a8bd0-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="a8bd0-129">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="a8bd0-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="a8bd0-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="a8bd0-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="a8bd0-131">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="a8bd0-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
