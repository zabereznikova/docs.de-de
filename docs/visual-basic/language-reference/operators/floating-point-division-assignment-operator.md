---
title: /=-Operator (Visual Basic)
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
ms.openlocfilehash: d9d3fa021654d3be1b9d304beb83caa737660264
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778468"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a1e69-102">/=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1e69-102">/= Operator (Visual Basic)</span></span>
<span data-ttu-id="a1e69-103">Dividiert den Wert einer Variablen oder Eigenschaft den Wert eines Ausdrucks und weist das Gleitkomma-Ergebnis der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a1e69-103">Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1e69-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1e69-104">Syntax</span></span>  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a1e69-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a1e69-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a1e69-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1e69-106">Required.</span></span> <span data-ttu-id="a1e69-107">Alle numerischen Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a1e69-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="a1e69-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1e69-108">Required.</span></span> <span data-ttu-id="a1e69-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a1e69-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1e69-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1e69-110">Remarks</span></span>  
 <span data-ttu-id="a1e69-111">Das Element auf der linken Seite von der `/=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="a1e69-111">The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a1e69-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="a1e69-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a1e69-113">Die `/=` Operator dividiert den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators) zuerst durch den Wert des Ausdrucks (auf der rechten Seite des Operators).</span><span class="sxs-lookup"><span data-stu-id="a1e69-113">The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="a1e69-114">Der Operator weist die Gleitkomma-Ergebnisses des Vorgangs klicken Sie dann zu der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a1e69-114">The operator then assigns the floating-point result of that operation to the variable or property.</span></span>  
  
 <span data-ttu-id="a1e69-115">Diese Anweisung weist ein `Double` Wert der Variablen oder die Eigenschaft auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="a1e69-115">This statement assigns a `Double` value to the variable or property on the left.</span></span> <span data-ttu-id="a1e69-116">Wenn `Option Strict` ist `On`, `variableorproperty` muss eine `Double`.</span><span class="sxs-lookup"><span data-stu-id="a1e69-116">If `Option Strict` is `On`, `variableorproperty` must be a `Double`.</span></span> <span data-ttu-id="a1e69-117">Wenn `Option Strict` ist `Off`, Visual Basic führt eine implizite Konvertierung und weist den resultierenden Wert `variableorproperty`, wobei ein Fehler zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="a1e69-117">If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time.</span></span> <span data-ttu-id="a1e69-118">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a1e69-118">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a1e69-119">Überladen</span><span class="sxs-lookup"><span data-stu-id="a1e69-119">Overloading</span></span>  
 <span data-ttu-id="a1e69-120">Die [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="a1e69-120">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a1e69-121">Das Überladen der `/` Operator beeinflusst das Verhalten von der `/=` Operator.</span><span class="sxs-lookup"><span data-stu-id="a1e69-121">Overloading the `/` operator affects the behavior of the `/=` operator.</span></span> <span data-ttu-id="a1e69-122">Wenn Ihr Code verwendet `/=` für eine Klasse oder Struktur, die Überladungen `/`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="a1e69-122">If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a1e69-123">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a1e69-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1e69-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1e69-124">Example</span></span>  
 <span data-ttu-id="a1e69-125">Im folgenden Beispiel wird die `/=` Operator, um eine teilen `Integer` Variable, indem Sie das zweite und das Zuweisen der Quotient der ersten Variablen.</span><span class="sxs-lookup"><span data-stu-id="a1e69-125">The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="a1e69-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1e69-126">See also</span></span>

- [<span data-ttu-id="a1e69-127">/-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1e69-127">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="a1e69-128">\\= Operator</span><span class="sxs-lookup"><span data-stu-id="a1e69-128">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="a1e69-129">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="a1e69-129">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="a1e69-130">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="a1e69-130">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="a1e69-131">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1e69-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a1e69-132">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="a1e69-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="a1e69-133">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="a1e69-133">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
