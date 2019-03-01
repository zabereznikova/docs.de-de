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
ms.openlocfilehash: c3495c4e45fe5e1d497578ee3ee6afe874e90eed
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203044"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="eaa97-102">-=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eaa97-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="eaa97-103">Subtrahiert den Wert eines Ausdrucks vom Wert einer Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="eaa97-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaa97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eaa97-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="eaa97-105">Teile</span><span class="sxs-lookup"><span data-stu-id="eaa97-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="eaa97-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eaa97-106">Required.</span></span> <span data-ttu-id="eaa97-107">Alle numerischen Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="eaa97-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="eaa97-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eaa97-108">Required.</span></span> <span data-ttu-id="eaa97-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="eaa97-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaa97-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eaa97-110">Remarks</span></span>  
 <span data-ttu-id="eaa97-111">Das Element auf der linken Seite von der `-=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="eaa97-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="eaa97-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="eaa97-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="eaa97-113">Die `-=` Operator subtrahiert den Wert des Ausdrucks (auf der rechten Seite des Operators) zuerst aus dem Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators).</span><span class="sxs-lookup"><span data-stu-id="eaa97-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="eaa97-114">Der Operator weist das Ergebnis des Vorgangs klicken Sie dann die Variable oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="eaa97-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="eaa97-115">Überladen</span><span class="sxs-lookup"><span data-stu-id="eaa97-115">Overloading</span></span>  
 <span data-ttu-id="eaa97-116">Die [-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="eaa97-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="eaa97-117">Das Überladen der `-` Operator beeinflusst das Verhalten von der `-=` Operator.</span><span class="sxs-lookup"><span data-stu-id="eaa97-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="eaa97-118">Wenn Ihr Code verwendet `-=` für eine Klasse oder Struktur, die Überladungen `-`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="eaa97-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="eaa97-119">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="eaa97-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaa97-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eaa97-120">Example</span></span>  
 <span data-ttu-id="eaa97-121">Im folgenden Beispiel wird die `-=` Operator subtrahiert einen `Integer` Variable von einem anderen und das Ergebnis der zweiten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eaa97-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="eaa97-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eaa97-122">See also</span></span>
- [<span data-ttu-id="eaa97-123">--Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eaa97-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="eaa97-124">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="eaa97-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="eaa97-125">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="eaa97-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="eaa97-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eaa97-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="eaa97-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="eaa97-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="eaa97-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="eaa97-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
