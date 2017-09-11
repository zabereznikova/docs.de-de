---
title: 'Gewusst wie: bestimmen, ob zwei Objekte identisch (Visual Basic) sind | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- testing, objects
- objects [Visual Basic], comparing
- object variables, determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c9621412eb1429ed07d8861114a67a67b6c1d58c
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="c44b9-102">Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c44b9-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="c44b9-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], Verweise auf zwei Variablen gelten als identisch, wenn deren Zeiger übereinstimmen, d. h., wenn beide Variablen auf die gleiche Klasseninstanz im Arbeitsspeicher verweisen.</span><span class="sxs-lookup"><span data-stu-id="c44b9-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="c44b9-104">Z. B. in einer Windows Forms-Anwendung möglicherweise soll einen Vergleich aus, um zu bestimmen, ob die aktuelle Instanz (`Me`) ist identisch mit einer bestimmten Instanz, wie z. B. `Form2`.</span><span class="sxs-lookup"><span data-stu-id="c44b9-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="c44b9-105">bietet zwei Operatoren zum Vergleich von Zeigern.</span><span class="sxs-lookup"><span data-stu-id="c44b9-105"> provides two operators to compare pointers.</span></span> <span data-ttu-id="c44b9-106">Die [Is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) gibt `True` , wenn die Objekte identisch sind und die [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) gibt `True` sind.</span><span class="sxs-lookup"><span data-stu-id="c44b9-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="c44b9-107">Bestimmen, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="c44b9-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="c44b9-108">Bestimmt, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="c44b9-108">To determine if two objects are identical</span></span>  
  
1.  <span data-ttu-id="c44b9-109">Einrichten einer `Boolean` Ausdruck, der die beiden Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="c44b9-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="c44b9-110">Verwenden Sie im Testausdruck den `Is` Operator mit den beiden Objekten als Operanden.</span><span class="sxs-lookup"><span data-stu-id="c44b9-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="c44b9-111">`Is`Gibt `True` , wenn die Objekte auf die gleiche Klasseninstanz zeigen.</span><span class="sxs-lookup"><span data-stu-id="c44b9-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="c44b9-112">Bestimmen, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="c44b9-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="c44b9-113">Manchmal möchten Sie eine Aktion durchführen, wenn die beiden Objekte nicht identisch sind, und es kann schwierig zu kombinieren `Not` und `Is`, z. B. `If Not obj1 Is obj2`.</span><span class="sxs-lookup"><span data-stu-id="c44b9-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="c44b9-114">In diesem Fall können Sie die `IsNot` Operator.</span><span class="sxs-lookup"><span data-stu-id="c44b9-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="c44b9-115">Bestimmt, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="c44b9-115">To determine if two objects are not identical</span></span>  
  
1.  <span data-ttu-id="c44b9-116">Einrichten einer `Boolean` Ausdruck, der die beiden Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="c44b9-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="c44b9-117">Verwenden Sie im Testausdruck den `IsNot` Operator mit den beiden Objekten als Operanden.</span><span class="sxs-lookup"><span data-stu-id="c44b9-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="c44b9-118">`IsNot`Gibt `True` , wenn die Objekte nicht auf die gleiche Klasseninstanz zeigen.</span><span class="sxs-lookup"><span data-stu-id="c44b9-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c44b9-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c44b9-119">Example</span></span>  
 <span data-ttu-id="c44b9-120">Das folgende Beispiel testet Paare von `Object` Variablen, um festzustellen, ob sie auf die gleiche Klasseninstanz zeigen.</span><span class="sxs-lookup"><span data-stu-id="c44b9-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 <span data-ttu-id="c44b9-121">[!code-vb[VbVbalrKeywords&14;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c44b9-121">[!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]</span></span>  
  
 <span data-ttu-id="c44b9-122">Im vorhergehenden Beispiel wird die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c44b9-122">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="c44b9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c44b9-123">See Also</span></span>  
 <span data-ttu-id="c44b9-124">[Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="c44b9-124">[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="c44b9-125"> [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="c44b9-125"> [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="c44b9-126"> [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span><span class="sxs-lookup"><span data-stu-id="c44b9-126"> [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span></span>  
<span data-ttu-id="c44b9-127"> [Is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) </span><span class="sxs-lookup"><span data-stu-id="c44b9-127"> [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) </span></span>  
<span data-ttu-id="c44b9-128"> [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) </span><span class="sxs-lookup"><span data-stu-id="c44b9-128"> [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) </span></span>  
<span data-ttu-id="c44b9-129"> [Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span><span class="sxs-lookup"><span data-stu-id="c44b9-129"> [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span></span>  
<span data-ttu-id="c44b9-130"> [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="c44b9-130"> [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>
