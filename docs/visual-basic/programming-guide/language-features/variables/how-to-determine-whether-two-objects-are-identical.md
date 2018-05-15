---
title: 'Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: bbcac2fc51e57427b125ec2f5e68f017a60186d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="89de9-102">Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89de9-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="89de9-103">In Visual Basic werden Verweise auf zwei Variablen als identisch angesehen, wenn ihre Zeiger gleich, d. h. sind Wenn beide Variablen auf die gleiche Klasseninstanz im Arbeitsspeicher verweisen.</span><span class="sxs-lookup"><span data-stu-id="89de9-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="89de9-104">Beispielsweise sollten Sie in einer Windows Forms-Anwendung, stellen einen Vergleich aus, um zu bestimmen, ob die aktuelle Instanz (`Me`) ist identisch mit einer bestimmten Instanz, wie z. B. `Form2`.</span><span class="sxs-lookup"><span data-stu-id="89de9-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="89de9-105">Visual Basic bietet zwei Operatoren zum Vergleich von Zeigern.</span><span class="sxs-lookup"><span data-stu-id="89de9-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="89de9-106">Die [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) gibt `True` , wenn die Objekte identisch sind und die [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) gibt `True` sind.</span><span class="sxs-lookup"><span data-stu-id="89de9-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="89de9-107">Bestimmen, ob zwei Objekte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="89de9-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="89de9-108">Um festzustellen, ob zwei Objekte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="89de9-108">To determine if two objects are identical</span></span>  
  
1.  <span data-ttu-id="89de9-109">Einrichten einer `Boolean` Ausdruck, der die beiden Objekte getestet.</span><span class="sxs-lookup"><span data-stu-id="89de9-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="89de9-110">Testausdruck, verwenden die `Is` Operator mit den beiden Objekten als Operanden.</span><span class="sxs-lookup"><span data-stu-id="89de9-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="89de9-111">`Is` Gibt `True` , wenn die Objekte auf die gleiche Klasseninstanz zeigen.</span><span class="sxs-lookup"><span data-stu-id="89de9-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="89de9-112">Bestimmen, ob zwei Objekte nicht identisch sind.</span><span class="sxs-lookup"><span data-stu-id="89de9-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="89de9-113">Gelegentlich möchten Sie eine Aktion ausführen, wenn die beiden Objekte nicht überein stimmen, und es kann zu kombinierende hinderlich erweisen `Not` und `Is`, z. B. `If Not obj1 Is obj2`.</span><span class="sxs-lookup"><span data-stu-id="89de9-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="89de9-114">In diesem Fall können Sie die `IsNot` Operator.</span><span class="sxs-lookup"><span data-stu-id="89de9-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="89de9-115">Um festzustellen, ob zwei Objekte nicht identisch sind.</span><span class="sxs-lookup"><span data-stu-id="89de9-115">To determine if two objects are not identical</span></span>  
  
1.  <span data-ttu-id="89de9-116">Einrichten einer `Boolean` Ausdruck, der die beiden Objekte getestet.</span><span class="sxs-lookup"><span data-stu-id="89de9-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="89de9-117">Testausdruck, verwenden die `IsNot` Operator mit den beiden Objekten als Operanden.</span><span class="sxs-lookup"><span data-stu-id="89de9-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="89de9-118">`IsNot` Gibt `True` , wenn die Objekte nicht auf die gleiche Klasseninstanz zeigen.</span><span class="sxs-lookup"><span data-stu-id="89de9-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89de9-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89de9-119">Example</span></span>  
 <span data-ttu-id="89de9-120">Das folgende Beispiel testet Paare von `Object` Variablen, um festzustellen, ob sie auf der gleichen Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="89de9-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 <span data-ttu-id="89de9-121">Das obige Beispiel zeigt die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="89de9-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="89de9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89de9-122">See Also</span></span>  
 [<span data-ttu-id="89de9-123">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="89de9-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="89de9-124">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="89de9-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="89de9-125">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="89de9-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="89de9-126">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="89de9-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="89de9-127">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="89de9-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="89de9-128">Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten</span><span class="sxs-lookup"><span data-stu-id="89de9-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="89de9-129">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="89de9-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
