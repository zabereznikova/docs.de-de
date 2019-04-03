---
title: '\= -Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 377a14a76f67e938f24c973b5946abd63f851bfd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842537"
---
# <a name="-operator"></a><span data-ttu-id="9de80-102">\\= Operator</span><span class="sxs-lookup"><span data-stu-id="9de80-102">\\= Operator</span></span>
<span data-ttu-id="9de80-103">Dividiert den Wert einer Variablen oder Eigenschaft den Wert eines Ausdrucks und weist das ganzzahlige Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9de80-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9de80-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9de80-104">Syntax</span></span>  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="9de80-105">Teile</span><span class="sxs-lookup"><span data-stu-id="9de80-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="9de80-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9de80-106">Required.</span></span> <span data-ttu-id="9de80-107">Alle numerischen Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9de80-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="9de80-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9de80-108">Required.</span></span> <span data-ttu-id="9de80-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9de80-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9de80-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9de80-110">Remarks</span></span>  
 <span data-ttu-id="9de80-111">Das Element auf der linken Seite von der `\=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="9de80-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="9de80-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="9de80-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="9de80-113">Die `\=` Operator dividiert den Wert einer Variablen oder Eigenschaft auf der linken Seite durch den Wert auf der rechten Seite, und weist das ganzzahlige Ergebnis der Variablen oder Eigenschaft auf der linken Seite</span><span class="sxs-lookup"><span data-stu-id="9de80-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="9de80-114">Weitere Informationen zu ganzzahligen Division, finden Sie unter [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9de80-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9de80-115">Überladen</span><span class="sxs-lookup"><span data-stu-id="9de80-115">Overloading</span></span>  
 <span data-ttu-id="9de80-116">Die `\` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="9de80-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9de80-117">Das Überladen der `\` Operator beeinflusst das Verhalten von der `\=` Operator.</span><span class="sxs-lookup"><span data-stu-id="9de80-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="9de80-118">Wenn Ihr Code verwendet `\=` für eine Klasse oder Struktur, die Überladungen `\`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9de80-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9de80-119">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9de80-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9de80-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9de80-120">Example</span></span>  
 <span data-ttu-id="9de80-121">Im folgenden Beispiel wird die `\=` Operator, um eine teilen `Integer` Variable, indem Sie das zweite und das ganzzahlige Ergebnis der ersten Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9de80-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="9de80-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9de80-122">See also</span></span>

- [<span data-ttu-id="9de80-123">\-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9de80-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="9de80-124">/ =-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9de80-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="9de80-125">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="9de80-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="9de80-126">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="9de80-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="9de80-127">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9de80-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9de80-128">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="9de80-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9de80-129">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="9de80-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
