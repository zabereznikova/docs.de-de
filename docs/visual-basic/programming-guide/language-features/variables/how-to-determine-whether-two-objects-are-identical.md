---
title: 'Vorgehensweise: Bestimmen der Gleichheit zweier Objekte'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 1bbc8083fcfb6f5ff0f4328c32b83a2e7218ecd6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072274"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="e5dbf-102">Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5dbf-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>

<span data-ttu-id="e5dbf-103">In Visual Basic werden zwei Variablen Verweise als identisch betrachtet, wenn die Zeiger identisch sind, d. h., wenn beide Variablen auf dieselbe Klasseninstanz im Arbeitsspeicher verweisen.</span><span class="sxs-lookup"><span data-stu-id="e5dbf-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="e5dbf-104">Beispielsweise können Sie in einer Windows Forms Anwendung einen Vergleich durchführen, um zu bestimmen, ob die aktuelle Instanz ( `Me` ) mit einer bestimmten Instanz identisch ist, z. b `Form2` ..</span><span class="sxs-lookup"><span data-stu-id="e5dbf-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="e5dbf-105">Visual Basic stellt zwei Operatoren zum Vergleichen von Zeigern bereit.</span><span class="sxs-lookup"><span data-stu-id="e5dbf-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="e5dbf-106">Der [is-Operator](../../../language-reference/operators/is-operator.md) gibt zurück `True` , wenn die Objekte identisch sind, und der [IsNot-Operator](../../../language-reference/operators/isnot-operator.md) gibt zurück, wenn dies nicht der Fall ist `True` .</span><span class="sxs-lookup"><span data-stu-id="e5dbf-106">The [Is Operator](../../../language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="e5dbf-107">Ermitteln, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="e5dbf-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="e5dbf-108">So bestimmen Sie, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="e5dbf-108">To determine if two objects are identical</span></span>  
  
1. <span data-ttu-id="e5dbf-109">Richten Sie einen- `Boolean` Ausdruck ein, um die beiden-Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="e5dbf-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="e5dbf-110">Verwenden Sie im Test Ausdruck den- `Is` Operator mit den beiden-Objekten als Operanden.</span><span class="sxs-lookup"><span data-stu-id="e5dbf-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="e5dbf-111">`Is` Gibt zurück `True` , wenn die Objekte auf dieselbe Klasseninstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="e5dbf-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="e5dbf-112">Ermitteln, ob zwei Objekte nicht identisch sind</span><span class="sxs-lookup"><span data-stu-id="e5dbf-112">Determining if Two Objects Are Not Identical</span></span>  

 <span data-ttu-id="e5dbf-113">Manchmal möchten Sie eine Aktion durchführen, wenn die beiden Objekte nicht identisch sind, und das kombinieren und beispielsweise umständlich sein kann `Not` `Is` `If Not obj1 Is obj2` .</span><span class="sxs-lookup"><span data-stu-id="e5dbf-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="e5dbf-114">In einem solchen Fall können Sie den- `IsNot` Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5dbf-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="e5dbf-115">So bestimmen Sie, ob zwei Objekte nicht identisch sind</span><span class="sxs-lookup"><span data-stu-id="e5dbf-115">To determine if two objects are not identical</span></span>  
  
1. <span data-ttu-id="e5dbf-116">Richten Sie einen- `Boolean` Ausdruck ein, um die beiden-Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="e5dbf-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="e5dbf-117">Verwenden Sie im Test Ausdruck den- `IsNot` Operator mit den beiden-Objekten als Operanden.</span><span class="sxs-lookup"><span data-stu-id="e5dbf-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="e5dbf-118">`IsNot` Gibt zurück `True` , wenn die Objekte nicht auf dieselbe Klasseninstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="e5dbf-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5dbf-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5dbf-119">Example</span></span>  

 <span data-ttu-id="e5dbf-120">Im folgenden Beispiel `Object` werden Variablen Paare getestet, um festzustellen, ob Sie auf dieselbe Klasseninstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="e5dbf-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 <span data-ttu-id="e5dbf-121">Im vorangehenden Beispiel wird die folgende Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5dbf-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="e5dbf-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5dbf-122">See also</span></span>

- [<span data-ttu-id="e5dbf-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="e5dbf-123">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="e5dbf-124">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="e5dbf-124">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="e5dbf-125">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="e5dbf-125">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="e5dbf-126">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="e5dbf-126">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="e5dbf-127">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="e5dbf-127">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="e5dbf-128">Vorgehensweise: Bestimmen des Bezugs zwischen zwei Objekten</span><span class="sxs-lookup"><span data-stu-id="e5dbf-128">How to: Determine Whether Two Objects Are Related</span></span>](how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="e5dbf-129">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="e5dbf-129">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
