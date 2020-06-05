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
ms.openlocfilehash: 516cb21e02d9fb2cd4b8d72282bb74163e1fb14b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371764"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="601de-102">=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="601de-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="601de-103">Weist einer Variablen oder Eigenschaft einen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="601de-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="601de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="601de-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="601de-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="601de-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="601de-106">Eine beliebige beschreibbare Variable oder eine beliebige Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="601de-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="601de-107">Beliebiges Literalzeichen, Konstante oder Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="601de-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="601de-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="601de-108">Remarks</span></span>  
 <span data-ttu-id="601de-109">Das Element auf der linken Seite des Gleichheitszeichens ( `=` ) kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="601de-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="601de-110">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="601de-110">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="601de-111">Der `=` Operator weist der Variablen oder der Eigenschaft auf der linken Seite den Wert auf der rechten Seite zu.</span><span class="sxs-lookup"><span data-stu-id="601de-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="601de-112">Der- `=` Operator wird auch als Vergleichs Operator verwendet.</span><span class="sxs-lookup"><span data-stu-id="601de-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="601de-113">Weitere Informationen finden Sie unter [Vergleichs Operatoren](comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="601de-113">For details, see [Comparison Operators](comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="601de-114">Überladen</span><span class="sxs-lookup"><span data-stu-id="601de-114">Overloading</span></span>  
 <span data-ttu-id="601de-115">Der `=` Operator kann nur als relationaler Vergleichs Operator, nicht als Zuweisungs Operator, überladen werden.</span><span class="sxs-lookup"><span data-stu-id="601de-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="601de-116">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="601de-116">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="601de-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="601de-117">Example</span></span>  
 <span data-ttu-id="601de-118">Im folgenden Beispiel wird der Zuweisungs Operator veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="601de-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="601de-119">Der Wert auf der rechten Seite wird der Variablen auf der linken Seite zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="601de-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="601de-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="601de-120">See also</span></span>

- [<span data-ttu-id="601de-121">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="601de-121">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="601de-122">Operator \* =</span><span class="sxs-lookup"><span data-stu-id="601de-122">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="601de-123">Operator + =</span><span class="sxs-lookup"><span data-stu-id="601de-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="601de-124">Operator-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="601de-124">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="601de-125">Operator/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="601de-125">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="601de-126">\\=-Operator</span><span class="sxs-lookup"><span data-stu-id="601de-126">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="601de-127">^ =-Operator</span><span class="sxs-lookup"><span data-stu-id="601de-127">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="601de-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="601de-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="601de-129">Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="601de-129">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="601de-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="601de-130">ReadOnly</span></span>](../modifiers/readonly.md)
- [<span data-ttu-id="601de-131">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="601de-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
