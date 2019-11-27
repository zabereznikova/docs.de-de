---
title: Operator ^=
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: fe5e8fc2b64b9e7c33483612071d338a0ee22768
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331296"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="053c6-102">^=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="053c6-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="053c6-103">Löst den Wert einer Variablen oder Eigenschaft für die Potenz eines Ausdrucks aus und weist das Ergebnis wieder der Variablen oder der Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="053c6-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="053c6-104">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="053c6-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="053c6-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="053c6-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="053c6-106">Required.</span></span> <span data-ttu-id="053c6-107">Eine beliebige numerische Variable oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="053c6-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="053c6-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="053c6-108">Required.</span></span> <span data-ttu-id="053c6-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="053c6-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="053c6-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="053c6-110">Remarks</span></span>  
 <span data-ttu-id="053c6-111">Das Element auf der linken Seite des `^=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="053c6-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="053c6-112">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="053c6-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="053c6-113">Der `^=`-Operator löst zuerst den Wert der Variablen oder der Eigenschaft (auf der linken Seite des Operators) bis zur Potenz des Werts des Ausdrucks (auf der rechten Seite des Operators) aus.</span><span class="sxs-lookup"><span data-stu-id="053c6-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="053c6-114">Der Operator weist dann das Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="053c6-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="053c6-115">Visual Basic führt immer eine exponentiell im [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)aus.</span><span class="sxs-lookup"><span data-stu-id="053c6-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="053c6-116">Operanden eines beliebigen Typs werden in `Double`konvertiert, und das Ergebnis wird immer `Double`.</span><span class="sxs-lookup"><span data-stu-id="053c6-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="053c6-117">Der Wert von `expression` kann eine Bruch Zahl, eine negative oder beides sein.</span><span class="sxs-lookup"><span data-stu-id="053c6-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="053c6-118">Überladen</span><span class="sxs-lookup"><span data-stu-id="053c6-118">Overloading</span></span>  
 <span data-ttu-id="053c6-119">Der [^-Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) kann *überladen*werden, was bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="053c6-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="053c6-120">Das Überladen des `^` Operators wirkt sich auf das Verhalten des `^=` Operators aus.</span><span class="sxs-lookup"><span data-stu-id="053c6-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="053c6-121">Wenn Ihr Code `^=` in einer Klasse oder Struktur verwendet, die `^`überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="053c6-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="053c6-122">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="053c6-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="053c6-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="053c6-123">Example</span></span>  
 <span data-ttu-id="053c6-124">Im folgenden Beispiel wird der `^=`-Operator verwendet, um den Wert einer `Integer` Variablen auf die Potenz einer zweiten Variablen zu erhöhen und das Ergebnis der ersten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="053c6-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="053c6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="053c6-125">See also</span></span>

- [<span data-ttu-id="053c6-126">^-Operator</span><span class="sxs-lookup"><span data-stu-id="053c6-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [<span data-ttu-id="053c6-127">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="053c6-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="053c6-128">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="053c6-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="053c6-129">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="053c6-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="053c6-130">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="053c6-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="053c6-131">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="053c6-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
