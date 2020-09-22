---
title: '&amp;=-Operator'
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
ms.openlocfilehash: 9b77c44aa77afd59e36e1d21451205d3929ef527
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874875"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="8d8eb-102">&amp;Operator = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d8eb-102">&amp;= Operator (Visual Basic)</span></span>

<span data-ttu-id="8d8eb-103">Verkettet einen `String` -Ausdruck mit einer `String` Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder der Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="8d8eb-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d8eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d8eb-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="8d8eb-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="8d8eb-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="8d8eb-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8d8eb-106">Required.</span></span> <span data-ttu-id="8d8eb-107">Eine beliebige `String` Variable oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8d8eb-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="8d8eb-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8d8eb-108">Required.</span></span> <span data-ttu-id="8d8eb-109">Beliebiger `String` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8d8eb-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d8eb-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8d8eb-110">Remarks</span></span>  

 <span data-ttu-id="8d8eb-111">Das Element auf der linken Seite des `&=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="8d8eb-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="8d8eb-112">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="8d8eb-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="8d8eb-113">Der `&=` Operator verkettet den `String` Ausdruck auf der rechten Seite mit der `String` Variablen oder der Eigenschaft auf der linken Seite und weist das Ergebnis der Variablen oder der Eigenschaft auf der linken Seite zu.</span><span class="sxs-lookup"><span data-stu-id="8d8eb-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8d8eb-114">Überladen</span><span class="sxs-lookup"><span data-stu-id="8d8eb-114">Overloading</span></span>  

 <span data-ttu-id="8d8eb-115">Der [&-Operator](concatenation-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="8d8eb-115">The [& Operator](concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="8d8eb-116">Das Überladen des- `&` Operators wirkt sich auf das Verhalten des- `&=` Operators aus.</span><span class="sxs-lookup"><span data-stu-id="8d8eb-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="8d8eb-117">Wenn Ihr Code `&=` für eine Klasse oder Struktur verwendet, die überlastet `&` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="8d8eb-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8d8eb-118">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8d8eb-118">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d8eb-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d8eb-119">Example</span></span>  

 <span data-ttu-id="8d8eb-120">Im folgenden Beispiel wird der `&=` -Operator verwendet, um zwei Variablen zu verketten `String` und das Ergebnis der ersten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="8d8eb-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8d8eb-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d8eb-121">See also</span></span>

- [<span data-ttu-id="8d8eb-122">&-Operator</span><span class="sxs-lookup"><span data-stu-id="8d8eb-122">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="8d8eb-123">Operator + =</span><span class="sxs-lookup"><span data-stu-id="8d8eb-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="8d8eb-124">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="8d8eb-124">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="8d8eb-125">Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="8d8eb-125">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="8d8eb-126">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8d8eb-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="8d8eb-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="8d8eb-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="8d8eb-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="8d8eb-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
