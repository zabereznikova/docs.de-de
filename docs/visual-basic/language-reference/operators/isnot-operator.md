---
title: IsNot-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: e07a775eec003a3e488f6909181aed3f742b4b91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768346"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="5174a-102">IsNot-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5174a-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="5174a-103">Vergleicht zwei Objektverweisvariablen.</span><span class="sxs-lookup"><span data-stu-id="5174a-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5174a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5174a-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="5174a-105">Teile</span><span class="sxs-lookup"><span data-stu-id="5174a-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="5174a-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5174a-106">Required.</span></span> <span data-ttu-id="5174a-107">Ein `Boolean`-Wert.</span><span class="sxs-lookup"><span data-stu-id="5174a-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="5174a-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5174a-108">Required.</span></span> <span data-ttu-id="5174a-109">Alle `Object` Variable oder einen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5174a-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="5174a-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5174a-110">Required.</span></span> <span data-ttu-id="5174a-111">Alle `Object` Variable oder einen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5174a-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5174a-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5174a-112">Remarks</span></span>  
 <span data-ttu-id="5174a-113">Die `IsNot` -Operator ermittelt, ob zwei Objektverweise auf unterschiedliche Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="5174a-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="5174a-114">Er führt jedoch keine vergleichen.</span><span class="sxs-lookup"><span data-stu-id="5174a-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="5174a-115">Wenn `object1` und `object2` beide verweisen auf genau dieselbe Objektinstanz, `result` ist `False`; Wenn dies nicht der Fall `result` ist `True`.</span><span class="sxs-lookup"><span data-stu-id="5174a-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="5174a-116">`IsNot` ist das Gegenteil von dem `Is` Operator.</span><span class="sxs-lookup"><span data-stu-id="5174a-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="5174a-117">Der Vorteil der `IsNot` besteht darin, dass Sie das umständlich Syntax mit vermeiden können `Not` und `Is`, die schwierig zu lesen sein können.</span><span class="sxs-lookup"><span data-stu-id="5174a-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="5174a-118">Sie können die `Is` und `IsNot` Abfrageoperatoren, um sowohl früh gebundenen und spät gebundenen Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="5174a-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5174a-119">Die `IsNot` Operator kann nicht verwendet werden, zum Vergleich von Ausdrücken, die zurückgegeben werden, aus der `TypeOf` Operator.</span><span class="sxs-lookup"><span data-stu-id="5174a-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="5174a-120">Sie müssen stattdessen die `Not` und `Is` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="5174a-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5174a-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5174a-121">Example</span></span>  
 <span data-ttu-id="5174a-122">Das folgende Codebeispiel verwendet die `Is` Operator und die `IsNot` Operator, um denselben Vergleich.</span><span class="sxs-lookup"><span data-stu-id="5174a-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a><span data-ttu-id="5174a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5174a-123">See also</span></span>

- [<span data-ttu-id="5174a-124">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="5174a-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="5174a-125">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="5174a-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="5174a-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5174a-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="5174a-127">Vorgehensweise: Überprüfen Sie, ob zwei Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="5174a-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
