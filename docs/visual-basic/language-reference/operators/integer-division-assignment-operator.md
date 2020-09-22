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
ms.openlocfilehash: 6e749e13c0427354db9e361538d4bef10b6c6b04
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873401"
---
# <a name="-operator"></a><span data-ttu-id="a8e51-102">\\=-Operator</span><span class="sxs-lookup"><span data-stu-id="a8e51-102">\\= Operator</span></span>

<span data-ttu-id="a8e51-103">Dividiert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das ganzzahlige Ergebnis der Variablen oder Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="a8e51-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8e51-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8e51-104">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a8e51-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="a8e51-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="a8e51-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a8e51-106">Required.</span></span> <span data-ttu-id="a8e51-107">Eine beliebige numerische Variable oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a8e51-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="a8e51-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a8e51-108">Required.</span></span> <span data-ttu-id="a8e51-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a8e51-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8e51-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a8e51-110">Remarks</span></span>  

 <span data-ttu-id="a8e51-111">Das Element auf der linken Seite des `\=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="a8e51-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a8e51-112">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="a8e51-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a8e51-113">Der `\=` Operator dividiert den Wert einer Variablen oder Eigenschaft auf der linken Seite durch den Wert auf der rechten Seite und weist das ganzzahlige Ergebnis der Variablen oder der Eigenschaft auf der linken Seite zu.</span><span class="sxs-lookup"><span data-stu-id="a8e51-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="a8e51-114">Weitere Informationen zur ganzzahligen Division finden Sie unter [\-Operator (Visual Basic)](integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a8e51-114">For further information on integer division, see [\ Operator (Visual Basic)](integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a8e51-115">Überladen</span><span class="sxs-lookup"><span data-stu-id="a8e51-115">Overloading</span></span>  

 <span data-ttu-id="a8e51-116">Der `\` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="a8e51-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a8e51-117">Das Überladen des- `\` Operators wirkt sich auf das Verhalten des- `\=` Operators aus.</span><span class="sxs-lookup"><span data-stu-id="a8e51-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="a8e51-118">Wenn Ihr Code `\=` für eine Klasse oder Struktur verwendet, die überlastet `\` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="a8e51-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a8e51-119">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a8e51-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8e51-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a8e51-120">Example</span></span>  

 <span data-ttu-id="a8e51-121">Im folgenden Beispiel wird der `\=` -Operator verwendet, um eine `Integer` Variable durch eine Sekunde zu teilen und das ganzzahlige Ergebnis der ersten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="a8e51-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="a8e51-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8e51-122">See also</span></span>

- [<span data-ttu-id="a8e51-123">Operator \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8e51-123">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
- [<span data-ttu-id="a8e51-124">Operator/= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8e51-124">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="a8e51-125">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="a8e51-125">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="a8e51-126">Arithmetic Operators (Arithmetische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="a8e51-126">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="a8e51-127">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8e51-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="a8e51-128">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="a8e51-128">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="a8e51-129">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="a8e51-129">Statements</span></span>](../../programming-guide/language-features/statements.md)
