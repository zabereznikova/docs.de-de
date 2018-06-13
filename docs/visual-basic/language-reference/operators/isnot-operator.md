---
title: IsNot-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: babee364d350ca84a8379f675acc4b5c87f98303
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603313"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="d48f2-102">IsNot-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d48f2-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="d48f2-103">Vergleicht zwei Objektverweisvariablen.</span><span class="sxs-lookup"><span data-stu-id="d48f2-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d48f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d48f2-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="d48f2-105">Teile</span><span class="sxs-lookup"><span data-stu-id="d48f2-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="d48f2-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d48f2-106">Required.</span></span> <span data-ttu-id="d48f2-107">Ein `Boolean`-Wert.</span><span class="sxs-lookup"><span data-stu-id="d48f2-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="d48f2-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d48f2-108">Required.</span></span> <span data-ttu-id="d48f2-109">Alle `Object` Variable oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="d48f2-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="d48f2-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d48f2-110">Required.</span></span> <span data-ttu-id="d48f2-111">Alle `Object` Variable oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="d48f2-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d48f2-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d48f2-112">Remarks</span></span>  
 <span data-ttu-id="d48f2-113">Die `IsNot` -Operator ermittelt, ob zwei Objektverweise auf unterschiedliche Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="d48f2-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="d48f2-114">Er führt jedoch keine Wertvergleiche.</span><span class="sxs-lookup"><span data-stu-id="d48f2-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="d48f2-115">Wenn `object1` und `object2` beide verweisen auf genau dieselbe Objektinstanz, `result` ist `False`; Wenn sie keinen `result` ist `True`.</span><span class="sxs-lookup"><span data-stu-id="d48f2-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="d48f2-116">`IsNot` ist das Gegenteil von der `Is` Operator.</span><span class="sxs-lookup"><span data-stu-id="d48f2-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="d48f2-117">Der Vorteil der `IsNot` ist, dass Sie vermeiden können, umständliche Syntax mit `Not` und `Is`, die schwer zu lesen sein können.</span><span class="sxs-lookup"><span data-stu-id="d48f2-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="d48f2-118">Sie können die `Is` und `IsNot` Operatoren, um früh gebundene und spät gebundene Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="d48f2-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d48f2-119">Die `IsNot` Operator kann nicht verwendet werden, um das Vergleichen von Ausdrücken, die zurückgegeben werden, aus der `TypeOf` Operator.</span><span class="sxs-lookup"><span data-stu-id="d48f2-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="d48f2-120">Stattdessen müssen Sie verwenden die `Not` und `Is` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="d48f2-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d48f2-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d48f2-121">Example</span></span>  
 <span data-ttu-id="d48f2-122">Das folgende Codebeispiel verwendet die `Is` Operator und die `IsNot` Operator, um denselben Vergleich zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="d48f2-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d48f2-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d48f2-123">See Also</span></span>  
 [<span data-ttu-id="d48f2-124">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="d48f2-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="d48f2-125">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="d48f2-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="d48f2-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d48f2-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="d48f2-127">Gewusst wie: Überprüfen, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="d48f2-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
