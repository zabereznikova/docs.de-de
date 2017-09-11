---
title: -=-Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.-=
dev_langs:
- VB
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements, compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
caps.latest.revision: 19
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
ms.openlocfilehash: 694033ec89e32b5fdba4092bd60292af536f58dd
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="--operator-visual-basic"></a><span data-ttu-id="75a95-102">-=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75a95-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="75a95-103">Subtrahiert den Wert eines Ausdrucks vom Wert einer Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="75a95-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75a95-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75a95-104">Syntax</span></span>  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="75a95-105">Teile</span><span class="sxs-lookup"><span data-stu-id="75a95-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="75a95-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="75a95-106">Required.</span></span> <span data-ttu-id="75a95-107">Alle numerischen Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="75a95-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="75a95-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="75a95-108">Required.</span></span> <span data-ttu-id="75a95-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="75a95-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75a95-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75a95-110">Remarks</span></span>  
 <span data-ttu-id="75a95-111">Das Element auf der linken Seite von der `-=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="75a95-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="75a95-112">Die Variable oder die Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="75a95-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="75a95-113">Die `-=` Operator subtrahiert den Wert des Ausdrucks (auf der rechten Seite des Operators) zuerst aus dem Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators).</span><span class="sxs-lookup"><span data-stu-id="75a95-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="75a95-114">Der Operator weist dann das Ergebnis des Vorgangs der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="75a95-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="75a95-115">Überladen</span><span class="sxs-lookup"><span data-stu-id="75a95-115">Overloading</span></span>  
 <span data-ttu-id="75a95-116">Die [-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="75a95-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="75a95-117">Das Überladen der `-` Operator beeinflusst das Verhalten von der `-=` Operator.</span><span class="sxs-lookup"><span data-stu-id="75a95-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="75a95-118">Wenn im Code `-=` für eine Klasse oder Struktur, die Überladungen `-`, werden Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="75a95-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="75a95-119">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="75a95-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75a95-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75a95-120">Example</span></span>  
 <span data-ttu-id="75a95-121">Im folgenden Beispiel wird die `-=` Operator, um eins subtrahieren `Integer` -Variable von einer anderen und das Ergebnis der zweiten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="75a95-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 <span data-ttu-id="75a95-122">[!code-vb[VbVbalrOperators&#11;](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="75a95-122">[!code-vb[VbVbalrOperators#11](codesnippet/VisualBasic/subtraction-assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a95-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75a95-123">See Also</span></span>  
 <span data-ttu-id="75a95-124">[-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) </span><span class="sxs-lookup"><span data-stu-id="75a95-124">[- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) </span></span>  
<span data-ttu-id="75a95-125"> [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md) </span><span class="sxs-lookup"><span data-stu-id="75a95-125"> [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md) </span></span>  
<span data-ttu-id="75a95-126"> [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="75a95-126"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="75a95-127"> [Operatorrangfolge in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="75a95-127"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="75a95-128"> [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="75a95-128"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="75a95-129"> [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="75a95-129"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>

