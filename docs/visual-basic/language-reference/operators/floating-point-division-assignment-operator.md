---
title: / =-Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./=
dev_langs:
- VB
helpviewer_keywords:
- assignment statements, compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: 23
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
ms.openlocfilehash: e877e98104b5c9fd679485b50a88943fac80a696
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a50f6-102">/=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a50f6-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="a50f6-103">Dividiert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das Ergebnis Gleitkommazahl der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a50f6-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a50f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a50f6-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a50f6-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a50f6-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a50f6-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a50f6-106">Required.</span></span> <span data-ttu-id="a50f6-107">Alle numerischen Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a50f6-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="a50f6-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a50f6-108">Required.</span></span> <span data-ttu-id="a50f6-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a50f6-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a50f6-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a50f6-110">Remarks</span></span>  
 <span data-ttu-id="a50f6-111">Das Element auf der linken Seite von der `/=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="a50f6-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a50f6-112">Die Variable oder die Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="a50f6-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a50f6-113">Die `/=` Operator dividiert den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators) zuerst den Wert des Ausdrucks (auf der rechten Seite des Operators).</span><span class="sxs-lookup"><span data-stu-id="a50f6-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="a50f6-114">Der Operator weist die Gleitkommaergebnis dieses Vorgangs zu der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a50f6-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="a50f6-115">Diese Anweisung weist ein `Double` Wert der Variablen oder Eigenschaft auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="a50f6-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="a50f6-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span><span class="sxs-lookup"><span data-stu-id="a50f6-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="a50f6-117">Wenn `Option Strict` ist `Off`, Visual Basic eine implizite Konvertierung ausführt und weist den resultierenden Wert `variableorproperty`, wobei ein Fehler zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="a50f6-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="a50f6-118">Weitere Informationen finden Sie unter [Widening und einschränkende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a50f6-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a50f6-119">Überladen</span><span class="sxs-lookup"><span data-stu-id="a50f6-119">Overloading</span></span>  
 <span data-ttu-id="a50f6-120">Die [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="a50f6-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a50f6-121">Das Überladen der `/` Operator beeinflusst das Verhalten von der `/=` Operator.</span><span class="sxs-lookup"><span data-stu-id="a50f6-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="a50f6-122">Wenn im Code `/=` für eine Klasse oder Struktur, die Überladungen `/`, werden Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="a50f6-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a50f6-123">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a50f6-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a50f6-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a50f6-124">Example</span></span>  
 <span data-ttu-id="a50f6-125">Im folgenden Beispiel wird die `/=` Operator, um einen unterteilen `Integer` Variable, indem das zweite und das Zuweisen der Quotient der ersten Variablen.</span><span class="sxs-lookup"><span data-stu-id="a50f6-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 <span data-ttu-id="a50f6-126">[!code-vb[VbVbalrOperators&17;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a50f6-126">[!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-assignment-operator_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a50f6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a50f6-127">See Also</span></span>  
 <span data-ttu-id="a50f6-128">[/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a50f6-128">[/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) </span></span>  
<span data-ttu-id="a50f6-129"> [\\=-Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a50f6-129"> [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md) </span></span>  
<span data-ttu-id="a50f6-130"> [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md) </span><span class="sxs-lookup"><span data-stu-id="a50f6-130"> [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md) </span></span>  
<span data-ttu-id="a50f6-131"> [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="a50f6-131"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="a50f6-132"> [Operatorrangfolge in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="a50f6-132"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="a50f6-133"> [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="a50f6-133"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="a50f6-134"> [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="a50f6-134"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>

