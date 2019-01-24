---
title: '*=-Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 3aa1d563b9657d4e80425b8c2d29e069ca2ef06a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601882"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="921f2-102">\*=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="921f2-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="921f2-103">Multipliziert den Wert einer Variablen oder die Eigenschaft durch den Wert eines Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="921f2-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="921f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="921f2-104">Syntax</span></span>  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="921f2-105">Teile</span><span class="sxs-lookup"><span data-stu-id="921f2-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="921f2-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="921f2-106">Required.</span></span> <span data-ttu-id="921f2-107">Alle numerischen Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="921f2-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="921f2-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="921f2-108">Required.</span></span> <span data-ttu-id="921f2-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="921f2-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="921f2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="921f2-110">Remarks</span></span>  
 <span data-ttu-id="921f2-111">Das Element auf der linken Seite von der `*=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="921f2-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="921f2-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="921f2-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="921f2-113">Die `*=` Operator multipliziert zunächst den Wert des Ausdrucks (auf der rechten Seite des Operators) durch den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators).</span><span class="sxs-lookup"><span data-stu-id="921f2-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="921f2-114">Der Operator weist das Ergebnis des Vorgangs klicken Sie dann die Variable oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="921f2-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="921f2-115">Überladen</span><span class="sxs-lookup"><span data-stu-id="921f2-115">Overloading</span></span>  
 <span data-ttu-id="921f2-116">Die [\*-Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="921f2-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="921f2-117">Das Überladen der `*` Operator beeinflusst das Verhalten von der `*=` Operator.</span><span class="sxs-lookup"><span data-stu-id="921f2-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="921f2-118">Wenn Ihr Code verwendet `*=` für eine Klasse oder Struktur, die Überladungen `*`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="921f2-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="921f2-119">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="921f2-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="921f2-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="921f2-120">Example</span></span>  
 <span data-ttu-id="921f2-121">Im folgenden Beispiel wird die `*=` Operator, um eine Multiplizieren `Integer` Variable, indem Sie das zweite und das Ergebnis der ersten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="921f2-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="921f2-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="921f2-122">See also</span></span>
- [<span data-ttu-id="921f2-123">\*-Operator</span><span class="sxs-lookup"><span data-stu-id="921f2-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="921f2-124">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="921f2-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="921f2-125">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="921f2-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="921f2-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="921f2-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="921f2-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="921f2-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="921f2-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="921f2-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
