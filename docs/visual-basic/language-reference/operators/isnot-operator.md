---
title: IsNot-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 969fdebdf15a1f779075c58616ccd16c64976a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="b552b-102">IsNot-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b552b-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="b552b-103">Vergleicht zwei Objektverweisvariablen.</span><span class="sxs-lookup"><span data-stu-id="b552b-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b552b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b552b-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="b552b-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b552b-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b552b-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b552b-106">Required.</span></span> <span data-ttu-id="b552b-107">Ein `Boolean`-Wert.</span><span class="sxs-lookup"><span data-stu-id="b552b-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="b552b-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b552b-108">Required.</span></span> <span data-ttu-id="b552b-109">Alle `Object` Variable oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b552b-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="b552b-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b552b-110">Required.</span></span> <span data-ttu-id="b552b-111">Alle `Object` Variable oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b552b-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b552b-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b552b-112">Remarks</span></span>  
 <span data-ttu-id="b552b-113">Die `IsNot` -Operator ermittelt, ob zwei Objektverweise auf unterschiedliche Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="b552b-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="b552b-114">Er führt jedoch keine Wertvergleiche.</span><span class="sxs-lookup"><span data-stu-id="b552b-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="b552b-115">Wenn `object1` und `object2` beide verweisen auf genau dieselbe Objektinstanz, `result` ist `False`; Wenn sie keinen `result` ist `True`.</span><span class="sxs-lookup"><span data-stu-id="b552b-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="b552b-116">`IsNot`ist das Gegenteil von der `Is` Operator.</span><span class="sxs-lookup"><span data-stu-id="b552b-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="b552b-117">Der Vorteil der `IsNot` ist, dass Sie vermeiden können, umständliche Syntax mit `Not` und `Is`, die schwer zu lesen sein können.</span><span class="sxs-lookup"><span data-stu-id="b552b-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="b552b-118">Sie können die `Is` und `IsNot` Operatoren, um früh gebundene und spät gebundene Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="b552b-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b552b-119">Die `IsNot` Operator kann nicht verwendet werden, um das Vergleichen von Ausdrücken, die zurückgegeben werden, aus der `TypeOf` Operator.</span><span class="sxs-lookup"><span data-stu-id="b552b-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="b552b-120">Stattdessen müssen Sie verwenden die `Not` und `Is` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="b552b-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b552b-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b552b-121">Example</span></span>  
 <span data-ttu-id="b552b-122">Das folgende Codebeispiel verwendet die `Is` Operator und die `IsNot` Operator, um denselben Vergleich zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="b552b-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b552b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b552b-123">See Also</span></span>  
 [<span data-ttu-id="b552b-124">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="b552b-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="b552b-125">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="b552b-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="b552b-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b552b-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="b552b-127">Gewusst wie: Überprüfen, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="b552b-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
