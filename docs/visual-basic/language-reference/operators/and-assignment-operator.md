---
title: '&amp;=-Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: a79e779d8fcf549daeabc494e0a55deee30b5d22
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835465"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="fafc8-102">&amp;=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fafc8-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="fafc8-103">Verkettet eine `String` Ausdruck, der eine `String` Variable oder eine Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fafc8-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fafc8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fafc8-104">Syntax</span></span>  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="fafc8-105">Teile</span><span class="sxs-lookup"><span data-stu-id="fafc8-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="fafc8-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fafc8-106">Required.</span></span> <span data-ttu-id="fafc8-107">Alle `String` Variable oder eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fafc8-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="fafc8-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fafc8-108">Required.</span></span> <span data-ttu-id="fafc8-109">Beliebiger `String` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="fafc8-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fafc8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fafc8-110">Remarks</span></span>  
 <span data-ttu-id="fafc8-111">Das Element auf der linken Seite von der `&=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="fafc8-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="fafc8-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="fafc8-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="fafc8-113">Die `&=` Operator verkettet die `String` Ausdruck auf der rechten Seite, um die `String` Variable oder eine Eigenschaft auf der linken Seite und weist das Ergebnis der Variablen oder die Eigenschaft auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="fafc8-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="fafc8-114">Überladen</span><span class="sxs-lookup"><span data-stu-id="fafc8-114">Overloading</span></span>  
 <span data-ttu-id="fafc8-115">Die [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="fafc8-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fafc8-116">Das Überladen der `&` Operator beeinflusst das Verhalten von der `&=` Operator.</span><span class="sxs-lookup"><span data-stu-id="fafc8-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="fafc8-117">Wenn Ihr Code verwendet `&=` für eine Klasse oder Struktur, die Überladungen `&`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="fafc8-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="fafc8-118">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fafc8-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fafc8-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fafc8-119">Example</span></span>  
 <span data-ttu-id="fafc8-120">Im folgenden Beispiel wird die `&=` Operator zum Verketten von zwei `String` Variablen und das Ergebnis der ersten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="fafc8-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="fafc8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fafc8-121">See also</span></span>

- [<span data-ttu-id="fafc8-122">&-Operator</span><span class="sxs-lookup"><span data-stu-id="fafc8-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="fafc8-123">+=-Operator</span><span class="sxs-lookup"><span data-stu-id="fafc8-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="fafc8-124">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="fafc8-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="fafc8-125">Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="fafc8-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="fafc8-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fafc8-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="fafc8-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="fafc8-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="fafc8-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="fafc8-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
