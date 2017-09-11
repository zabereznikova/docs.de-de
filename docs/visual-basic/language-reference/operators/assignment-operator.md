---
title: = Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
dev_langs:
- VB
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 46dc9e6018cf2ae71f1fc6dc2b8f19c2f0aadb62
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="9d031-102">=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d031-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="9d031-103">Weist einen Wert einer Variablen oder Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="9d031-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d031-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d031-104">Syntax</span></span>  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="9d031-105">Teile</span><span class="sxs-lookup"><span data-stu-id="9d031-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="9d031-106">Jede schreibbare Variable oder jede Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9d031-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="9d031-107">Jeder Literal, eine Konstante oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9d031-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d031-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d031-108">Remarks</span></span>  
 <span data-ttu-id="9d031-109">Das Element auf der linken Seite des Gleichheitszeichens (`=`) kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="9d031-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="9d031-110">Die Variable oder die Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="9d031-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="9d031-111">Die `=` -Operator weist den Wert auf der rechten Seite der Variablen oder Eigenschaft auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="9d031-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d031-112">Die `=` Operator wird auch als Vergleichsoperator verwendet.</span><span class="sxs-lookup"><span data-stu-id="9d031-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="9d031-113">Weitere Informationen finden Sie unter [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="9d031-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9d031-114">Überladen</span><span class="sxs-lookup"><span data-stu-id="9d031-114">Overloading</span></span>  
 <span data-ttu-id="9d031-115">Die `=` Operator kann nur als ein relationaler Vergleichsoperator und nicht als Zuweisungsoperator überladen werden.</span><span class="sxs-lookup"><span data-stu-id="9d031-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="9d031-116">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9d031-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d031-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d031-117">Example</span></span>  
 <span data-ttu-id="9d031-118">Das folgende Beispiel zeigt den Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="9d031-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="9d031-119">Der Wert auf der rechten Seite wird der Variablen auf der linken Seite zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9d031-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 <span data-ttu-id="9d031-120">[!code-vb[VbVbalrOperators&#9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9d031-120">[!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d031-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d031-121">See Also</span></span>  
 <span data-ttu-id="9d031-122">[& = (Operator)](../../../visual-basic/language-reference/operators/and-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="9d031-122">[&= Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md) </span></span>  
<span data-ttu-id="9d031-123"> [* =-Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="9d031-123"> [*= Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md) </span></span>  
<span data-ttu-id="9d031-124"> [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="9d031-124"> [+= Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md) </span></span>  
<span data-ttu-id="9d031-125"> [-=-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="9d031-125"> [-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md) </span></span>  
<span data-ttu-id="9d031-126"> [/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="9d031-126"> [/= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span></span>  
<span data-ttu-id="9d031-127"> [\\=-Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="9d031-127"> [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span></span>  
<span data-ttu-id="9d031-128"> [^ =-Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="9d031-128"> [^= Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md) </span></span>  
<span data-ttu-id="9d031-129"> [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md) </span><span class="sxs-lookup"><span data-stu-id="9d031-129"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md) </span></span>  
<span data-ttu-id="9d031-130"> [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="9d031-130"> [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="9d031-131"> [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) </span><span class="sxs-lookup"><span data-stu-id="9d031-131"> [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) </span></span>  
<span data-ttu-id="9d031-132"> [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span><span class="sxs-lookup"><span data-stu-id="9d031-132"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)</span></span>

