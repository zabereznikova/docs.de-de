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
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="8bb49-102">IsNot-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8bb49-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="8bb49-103">Vergleicht zwei Objekt Verweis Variablen.</span><span class="sxs-lookup"><span data-stu-id="8bb49-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="8bb49-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8bb49-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="8bb49-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="8bb49-105">Parts</span></span>
 <span data-ttu-id="8bb49-106">`result` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8bb49-106">`result` Required.</span></span> <span data-ttu-id="8bb49-107">Ein `Boolean`-Wert.</span><span class="sxs-lookup"><span data-stu-id="8bb49-107">A `Boolean` value.</span></span>

 <span data-ttu-id="8bb49-108">`object1` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8bb49-108">`object1` Required.</span></span> <span data-ttu-id="8bb49-109">Beliebige `Object` Variable oder Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8bb49-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="8bb49-110">`object2` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8bb49-110">`object2` Required.</span></span> <span data-ttu-id="8bb49-111">Beliebige `Object` Variable oder Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8bb49-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="8bb49-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8bb49-112">Remarks</span></span>
 <span data-ttu-id="8bb49-113">Der `IsNot`-Operator bestimmt, ob zwei Objekt Verweise auf unterschiedliche Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="8bb49-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="8bb49-114">Es werden jedoch keine Wert Vergleiche durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="8bb49-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="8bb49-115">Wenn `object1` und `object2` beide auf genau dieselbe Objektinstanz verweisen, ist `result` `False`. Wenn dies nicht der Fall ist, wird `result` `True`.</span><span class="sxs-lookup"><span data-stu-id="8bb49-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="8bb49-116">`IsNot` ist das Gegenteil des `Is`-Operators.</span><span class="sxs-lookup"><span data-stu-id="8bb49-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="8bb49-117">Der Vorteil von `IsNot` besteht darin, dass Sie eine umständliche Syntax mit `Not` und `Is`vermeiden können, was schwierig zu lesen ist.</span><span class="sxs-lookup"><span data-stu-id="8bb49-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="8bb49-118">Mit den Operatoren `Is` und `IsNot` können Sie sowohl früh gebundene als auch spät gebundene Objekte testen.</span><span class="sxs-lookup"><span data-stu-id="8bb49-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="8bb49-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8bb49-119">Example</span></span>
 <span data-ttu-id="8bb49-120">Im folgenden Codebeispiel werden sowohl der `Is`-Operator als auch der `IsNot`-Operator verwendet, um denselben Vergleich durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="8bb49-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="8bb49-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bb49-121">See also</span></span>

- [<span data-ttu-id="8bb49-122">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="8bb49-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="8bb49-123">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="8bb49-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="8bb49-124">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8bb49-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="8bb49-125">Gewusst wie: Überprüfen, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="8bb49-125">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
