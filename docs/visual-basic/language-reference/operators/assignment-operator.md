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
ms.openlocfilehash: eccea0b43564a4980778c9d1a5b8f9a8c2a9207d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874828"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="7e84a-102">=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e84a-102">= Operator (Visual Basic)</span></span>

<span data-ttu-id="7e84a-103">Weist einer Variablen oder Eigenschaft einen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="7e84a-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e84a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e84a-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="7e84a-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="7e84a-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="7e84a-106">Eine beliebige beschreibbare Variable oder eine beliebige Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7e84a-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="7e84a-107">Beliebiges Literalzeichen, Konstante oder Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="7e84a-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e84a-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7e84a-108">Remarks</span></span>  

 <span data-ttu-id="7e84a-109">Das Element auf der linken Seite des Gleichheitszeichens ( `=` ) kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="7e84a-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="7e84a-110">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="7e84a-110">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="7e84a-111">Der `=` Operator weist der Variablen oder der Eigenschaft auf der linken Seite den Wert auf der rechten Seite zu.</span><span class="sxs-lookup"><span data-stu-id="7e84a-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e84a-112">Der- `=` Operator wird auch als Vergleichs Operator verwendet.</span><span class="sxs-lookup"><span data-stu-id="7e84a-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="7e84a-113">Weitere Informationen finden Sie unter [Vergleichs Operatoren](comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="7e84a-113">For details, see [Comparison Operators](comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7e84a-114">Überladen</span><span class="sxs-lookup"><span data-stu-id="7e84a-114">Overloading</span></span>  

 <span data-ttu-id="7e84a-115">Der `=` Operator kann nur als relationaler Vergleichs Operator, nicht als Zuweisungs Operator, überladen werden.</span><span class="sxs-lookup"><span data-stu-id="7e84a-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="7e84a-116">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7e84a-116">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e84a-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e84a-117">Example</span></span>  

 <span data-ttu-id="7e84a-118">Im folgenden Beispiel wird der Zuweisungs Operator veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7e84a-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="7e84a-119">Der Wert auf der rechten Seite wird der Variablen auf der linken Seite zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7e84a-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="7e84a-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e84a-120">See also</span></span>

- [<span data-ttu-id="7e84a-121">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="7e84a-121">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="7e84a-122">Operator \* =</span><span class="sxs-lookup"><span data-stu-id="7e84a-122">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="7e84a-123">Operator + =</span><span class="sxs-lookup"><span data-stu-id="7e84a-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="7e84a-124">Operator-= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e84a-124">-= Operator (Visual Basic)</span></span>](subtraction-assignment-operator.md)
- [<span data-ttu-id="7e84a-125">Operator/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e84a-125">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="7e84a-126">\\=-Operator</span><span class="sxs-lookup"><span data-stu-id="7e84a-126">\\= Operator</span></span>](integer-division-assignment-operator.md)
- [<span data-ttu-id="7e84a-127">^ =-Operator</span><span class="sxs-lookup"><span data-stu-id="7e84a-127">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="7e84a-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7e84a-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="7e84a-129">Comparison Operators (Vergleichsoperatoren)</span><span class="sxs-lookup"><span data-stu-id="7e84a-129">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="7e84a-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="7e84a-130">ReadOnly</span></span>](../modifiers/readonly.md)
- [<span data-ttu-id="7e84a-131">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="7e84a-131">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
