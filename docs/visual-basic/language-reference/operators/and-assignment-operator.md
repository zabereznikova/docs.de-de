---
title: '&amp; =-Operator (Visual Basic)'
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
ms.openlocfilehash: 82d791e5d66c301442c99d2cc73e3172c3e30f17
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591637"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="18318-102">&amp; =-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18318-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="18318-103">Verkettet einen `String`-Ausdruck mit einer `String`-Variablen oder-Eigenschaft und weist das Ergebnis der Variablen oder der Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="18318-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18318-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18318-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="18318-105">Teile</span><span class="sxs-lookup"><span data-stu-id="18318-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="18318-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="18318-106">Required.</span></span> <span data-ttu-id="18318-107">Eine beliebige `String`-Variable oder-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="18318-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="18318-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="18318-108">Required.</span></span> <span data-ttu-id="18318-109">Beliebiger `String` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="18318-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18318-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18318-110">Remarks</span></span>  
 <span data-ttu-id="18318-111">Das Element auf der linken Seite des `&=`-Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="18318-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="18318-112">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="18318-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="18318-113">Der `&=`-Operator verkettet den `String`-Ausdruck rechts von der `String`-Variablen oder-Eigenschaft auf der linken Seite und weist das Ergebnis der Variablen oder der Eigenschaft auf der linken Seite zu.</span><span class="sxs-lookup"><span data-stu-id="18318-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="18318-114">Überladen</span><span class="sxs-lookup"><span data-stu-id="18318-114">Overloading</span></span>  
 <span data-ttu-id="18318-115">Der [&-Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="18318-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="18318-116">Das Überladen des `&`-Operators wirkt sich auf das Verhalten des `&=`-Operators aus.</span><span class="sxs-lookup"><span data-stu-id="18318-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="18318-117">Wenn Ihr Code `&=` für eine Klasse oder Struktur verwendet, die `&` überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="18318-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="18318-118">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="18318-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18318-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18318-119">Example</span></span>  
 <span data-ttu-id="18318-120">Im folgenden Beispiel wird der `&=`-Operator verwendet, um zwei `String`-Variablen zu verketten und das Ergebnis der ersten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="18318-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="18318-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18318-121">See also</span></span>

- [<span data-ttu-id="18318-122">&-Operator</span><span class="sxs-lookup"><span data-stu-id="18318-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="18318-123">+=-Operator</span><span class="sxs-lookup"><span data-stu-id="18318-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="18318-124">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="18318-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="18318-125">Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="18318-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="18318-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18318-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="18318-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="18318-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="18318-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="18318-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
