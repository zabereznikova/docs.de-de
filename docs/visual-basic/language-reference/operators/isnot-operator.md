---
title: IsNot-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ea978f8874cee20fb3a005189fd846f7564da777
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811040"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="dd882-102">IsNot-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd882-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="dd882-103">Vergleicht zwei Objekt Verweis Variablen.</span><span class="sxs-lookup"><span data-stu-id="dd882-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="dd882-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd882-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="dd882-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="dd882-105">Parts</span></span>

- `result`

  <span data-ttu-id="dd882-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dd882-106">Required.</span></span> <span data-ttu-id="dd882-107">Ein `Boolean`-Wert.</span><span class="sxs-lookup"><span data-stu-id="dd882-107">A `Boolean` value.</span></span>

- `object1`

  <span data-ttu-id="dd882-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dd882-108">Required.</span></span> <span data-ttu-id="dd882-109">Eine beliebige `Object` Variable oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="dd882-109">Any `Object` variable or expression.</span></span>

- `object2`

  <span data-ttu-id="dd882-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dd882-110">Required.</span></span> <span data-ttu-id="dd882-111">Eine beliebige `Object` Variable oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="dd882-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd882-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd882-112">Remarks</span></span>

<span data-ttu-id="dd882-113">Der- `IsNot` Operator bestimmt, ob zwei Objekt Verweise auf unterschiedliche Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="dd882-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="dd882-114">Es werden jedoch keine Wert Vergleiche durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="dd882-114">However, it doesn't perform value comparisons.</span></span> <span data-ttu-id="dd882-115">Wenn `object1` und `object2` beide auf genau dieselbe Objektinstanz verweisen, ist `result` . wenn dies nicht der Fall ist `False` , `result` ist `True` .</span><span class="sxs-lookup"><span data-stu-id="dd882-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they don't, `result` is `True`.</span></span>

<span data-ttu-id="dd882-116">`IsNot` ist das Gegenteil des- `Is` Operators.</span><span class="sxs-lookup"><span data-stu-id="dd882-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="dd882-117">Der Vorteil von `IsNot` besteht darin, dass Sie eine umständliche Syntax mit und vermeiden können `Not` `Is` , was schwierig zu lesen ist.</span><span class="sxs-lookup"><span data-stu-id="dd882-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="dd882-118">Sie können die `Is` `IsNot` Operatoren und verwenden, um früh gebundene und spät gebundene Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="dd882-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="dd882-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd882-119">Example</span></span>

<span data-ttu-id="dd882-120">Im folgenden Codebeispiel wird der `Is` -Operator und der `IsNot` -Operator verwendet, um denselben Vergleich durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="dd882-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a><span data-ttu-id="dd882-121">Typeof-Operator mit IsNot-Operator verwenden</span><span class="sxs-lookup"><span data-stu-id="dd882-121">Use TypeOf operator with IsNot operator</span></span>

<span data-ttu-id="dd882-122">Ab Visual Basic 14 können Sie den- `TypeOf` Operator mit dem-Operator verwenden, `IsNot` um zu testen, ob ein Objekt *nicht* mit einem-Datentyp kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="dd882-122">Starting with Visual Basic 14, you can use the `TypeOf` operator with the `IsNot` operator to test whether an object is *not* compatible with a data type.</span></span> <span data-ttu-id="dd882-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dd882-123">For example:</span></span>

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a><span data-ttu-id="dd882-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd882-124">See also</span></span>

- [<span data-ttu-id="dd882-125">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="dd882-125">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="dd882-126">Typeof-Operator</span><span class="sxs-lookup"><span data-stu-id="dd882-126">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="dd882-127">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd882-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="dd882-128">Vorgehensweise: Überprüfen, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="dd882-128">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
