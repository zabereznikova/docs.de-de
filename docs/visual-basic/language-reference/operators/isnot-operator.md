---
title: IsNot-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336064"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="9344c-102">IsNot-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9344c-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="9344c-103">Compares two object reference variables.</span><span class="sxs-lookup"><span data-stu-id="9344c-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="9344c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9344c-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="9344c-105">Teile</span><span class="sxs-lookup"><span data-stu-id="9344c-105">Parts</span></span>
 <span data-ttu-id="9344c-106">`result` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9344c-106">`result` Required.</span></span> <span data-ttu-id="9344c-107">Ein `Boolean`-Wert.</span><span class="sxs-lookup"><span data-stu-id="9344c-107">A `Boolean` value.</span></span>

 <span data-ttu-id="9344c-108">`object1` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9344c-108">`object1` Required.</span></span> <span data-ttu-id="9344c-109">Any `Object` variable or expression.</span><span class="sxs-lookup"><span data-stu-id="9344c-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="9344c-110">`object2` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9344c-110">`object2` Required.</span></span> <span data-ttu-id="9344c-111">Any `Object` variable or expression.</span><span class="sxs-lookup"><span data-stu-id="9344c-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="9344c-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9344c-112">Remarks</span></span>
 <span data-ttu-id="9344c-113">The `IsNot` operator determines if two object references refer to different objects.</span><span class="sxs-lookup"><span data-stu-id="9344c-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="9344c-114">However, it does not perform value comparisons.</span><span class="sxs-lookup"><span data-stu-id="9344c-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="9344c-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span><span class="sxs-lookup"><span data-stu-id="9344c-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="9344c-116">`IsNot` is the opposite of the `Is` operator.</span><span class="sxs-lookup"><span data-stu-id="9344c-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="9344c-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span><span class="sxs-lookup"><span data-stu-id="9344c-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="9344c-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span><span class="sxs-lookup"><span data-stu-id="9344c-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="9344c-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9344c-119">Example</span></span>
 <span data-ttu-id="9344c-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span><span class="sxs-lookup"><span data-stu-id="9344c-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="9344c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9344c-121">See also</span></span>

- [<span data-ttu-id="9344c-122">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="9344c-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="9344c-123">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="9344c-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="9344c-124">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9344c-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="9344c-125">Gewusst wie: Überprüfen, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="9344c-125">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
