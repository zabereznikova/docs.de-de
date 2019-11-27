---
title: 'Gewusst wie: Bestimmen der Gleichheit zweier Objekte'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 5deebd4ffc5b277c94f5ae36c00fd6e5010a1551
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348598"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="bd642-102">Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd642-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="bd642-103">In Visual Basic werden zwei Variablen Verweise als identisch betrachtet, wenn die Zeiger identisch sind, d. h., wenn beide Variablen auf dieselbe Klasseninstanz im Arbeitsspeicher verweisen.</span><span class="sxs-lookup"><span data-stu-id="bd642-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="bd642-104">Beispielsweise können Sie in einer Windows Forms Anwendung einen Vergleich durchführen, um zu bestimmen, ob die aktuelle Instanz (`Me`) mit einer bestimmten Instanz identisch ist, z. b. `Form2`.</span><span class="sxs-lookup"><span data-stu-id="bd642-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="bd642-105">Visual Basic stellt zwei Operatoren zum Vergleichen von Zeigern bereit.</span><span class="sxs-lookup"><span data-stu-id="bd642-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="bd642-106">Der [is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) gibt `True` zurück, wenn die Objekte identisch sind, und der [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) gibt `True` zurück, wenn dies nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="bd642-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="bd642-107">Ermitteln, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="bd642-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="bd642-108">So bestimmen Sie, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="bd642-108">To determine if two objects are identical</span></span>  
  
1. <span data-ttu-id="bd642-109">Richten Sie einen `Boolean` Ausdruck ein, um die beiden Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="bd642-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="bd642-110">Verwenden Sie im Test Ausdruck den `Is`-Operator mit den beiden-Objekten als Operanden.</span><span class="sxs-lookup"><span data-stu-id="bd642-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="bd642-111">`Is` gibt `True` zurück, wenn die Objekte auf dieselbe Klasseninstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="bd642-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="bd642-112">Ermitteln, ob zwei Objekte nicht identisch sind</span><span class="sxs-lookup"><span data-stu-id="bd642-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="bd642-113">Manchmal möchten Sie eine Aktion ausführen, wenn die beiden Objekte nicht identisch sind, und es kann umständlich sein, `Not` und `Is`zu kombinieren, z. b. `If Not obj1 Is obj2`.</span><span class="sxs-lookup"><span data-stu-id="bd642-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="bd642-114">In einem solchen Fall können Sie den `IsNot`-Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd642-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="bd642-115">So bestimmen Sie, ob zwei Objekte nicht identisch sind</span><span class="sxs-lookup"><span data-stu-id="bd642-115">To determine if two objects are not identical</span></span>  
  
1. <span data-ttu-id="bd642-116">Richten Sie einen `Boolean` Ausdruck ein, um die beiden Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="bd642-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="bd642-117">Verwenden Sie im Test Ausdruck den `IsNot`-Operator mit den beiden-Objekten als Operanden.</span><span class="sxs-lookup"><span data-stu-id="bd642-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="bd642-118">`IsNot` gibt `True` zurück, wenn die Objekte nicht auf dieselbe Klasseninstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="bd642-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd642-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd642-119">Example</span></span>  
 <span data-ttu-id="bd642-120">Im folgenden Beispiel werden Paare von `Object` Variablen getestet, um festzustellen, ob Sie auf dieselbe Klasseninstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="bd642-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 <span data-ttu-id="bd642-121">Im vorangehenden Beispiel wird die folgende Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd642-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="bd642-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd642-122">See also</span></span>

- [<span data-ttu-id="bd642-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="bd642-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="bd642-124">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="bd642-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="bd642-125">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="bd642-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="bd642-126">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="bd642-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="bd642-127">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="bd642-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="bd642-128">Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten</span><span class="sxs-lookup"><span data-stu-id="bd642-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="bd642-129">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="bd642-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
