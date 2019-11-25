---
title: Operator /=
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: a8a031e968df90496a4e263ae78d47045ccdc923
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331036"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="0dae1-102">/=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0dae1-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="0dae1-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="0dae1-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dae1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0dae1-104">Syntax</span></span>  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="0dae1-105">Teile</span><span class="sxs-lookup"><span data-stu-id="0dae1-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="0dae1-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0dae1-106">Required.</span></span> <span data-ttu-id="0dae1-107">Any numeric variable or property.</span><span class="sxs-lookup"><span data-stu-id="0dae1-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="0dae1-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0dae1-108">Required.</span></span> <span data-ttu-id="0dae1-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="0dae1-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dae1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0dae1-110">Remarks</span></span>  
 <span data-ttu-id="0dae1-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span><span class="sxs-lookup"><span data-stu-id="0dae1-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="0dae1-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="0dae1-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="0dae1-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span><span class="sxs-lookup"><span data-stu-id="0dae1-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="0dae1-114">The operator then assigns the floating-point result of that operation to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="0dae1-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="0dae1-115">This statement assigns a `Double` value to the variable or property on the left.</span><span class="sxs-lookup"><span data-stu-id="0dae1-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="0dae1-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span><span class="sxs-lookup"><span data-stu-id="0dae1-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="0dae1-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span><span class="sxs-lookup"><span data-stu-id="0dae1-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="0dae1-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0dae1-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="0dae1-119">Überladen</span><span class="sxs-lookup"><span data-stu-id="0dae1-119">Overloading</span></span>  
 <span data-ttu-id="0dae1-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="0dae1-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="0dae1-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span><span class="sxs-lookup"><span data-stu-id="0dae1-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="0dae1-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="0dae1-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0dae1-123">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="0dae1-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0dae1-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0dae1-124">Example</span></span>  
 <span data-ttu-id="0dae1-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span><span class="sxs-lookup"><span data-stu-id="0dae1-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="0dae1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0dae1-126">See also</span></span>

- [<span data-ttu-id="0dae1-127">/ Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0dae1-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="0dae1-128">\\= Operator</span><span class="sxs-lookup"><span data-stu-id="0dae1-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="0dae1-129">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="0dae1-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="0dae1-130">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="0dae1-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="0dae1-131">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0dae1-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="0dae1-132">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="0dae1-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="0dae1-133">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="0dae1-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
