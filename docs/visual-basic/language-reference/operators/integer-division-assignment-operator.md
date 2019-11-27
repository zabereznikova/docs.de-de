---
title: '\=-Operator'
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
ms.openlocfilehash: 600acf9b41b63358da245fe602595fee4093b15b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330946"
---
# <a name="-operator"></a><span data-ttu-id="b896c-102">\\=-Operator</span><span class="sxs-lookup"><span data-stu-id="b896c-102">\\= Operator</span></span>
<span data-ttu-id="b896c-103">Dividiert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das ganzzahlige Ergebnis der Variablen oder Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="b896c-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b896c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b896c-104">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b896c-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="b896c-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="b896c-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="b896c-106">Required.</span></span> <span data-ttu-id="b896c-107">Eine beliebige numerische Variable oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b896c-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="b896c-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="b896c-108">Required.</span></span> <span data-ttu-id="b896c-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b896c-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b896c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b896c-110">Remarks</span></span>  
 <span data-ttu-id="b896c-111">Das Element auf der linken Seite des `\=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="b896c-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="b896c-112">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="b896c-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="b896c-113">Der `\=`-Operator dividiert den Wert einer Variablen oder Eigenschaft auf der linken Seite durch den Wert auf der rechten Seite und weist das ganzzahlige Ergebnis der Variablen oder der Eigenschaft auf der linken Seite zu.</span><span class="sxs-lookup"><span data-stu-id="b896c-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="b896c-114">Weitere Informationen zur ganzzahligen Division finden Sie unter [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b896c-114">For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b896c-115">Überladen</span><span class="sxs-lookup"><span data-stu-id="b896c-115">Overloading</span></span>  
 <span data-ttu-id="b896c-116">Der `\`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="b896c-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b896c-117">Das Überladen des `\` Operators wirkt sich auf das Verhalten des `\=` Operators aus.</span><span class="sxs-lookup"><span data-stu-id="b896c-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="b896c-118">Wenn Ihr Code `\=` in einer Klasse oder Struktur verwendet, die `\`überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="b896c-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b896c-119">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b896c-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b896c-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b896c-120">Example</span></span>  
 <span data-ttu-id="b896c-121">Im folgenden Beispiel wird der `\=`-Operator verwendet, um eine `Integer` Variable durch eine Sekunde zu teilen und das ganzzahlige Ergebnis der ersten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="b896c-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="b896c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b896c-122">See also</span></span>

- [<span data-ttu-id="b896c-123">Operator \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b896c-123">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="b896c-124">Operator/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b896c-124">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="b896c-125">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="b896c-125">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="b896c-126">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="b896c-126">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="b896c-127">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b896c-127">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b896c-128">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="b896c-128">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b896c-129">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="b896c-129">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
