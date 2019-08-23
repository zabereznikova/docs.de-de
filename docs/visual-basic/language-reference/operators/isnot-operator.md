---
title: IsNot-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966927"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="a3892-102">IsNot-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3892-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="a3892-103">Vergleicht zwei Objekt Verweis Variablen.</span><span class="sxs-lookup"><span data-stu-id="a3892-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3892-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3892-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="a3892-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a3892-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="a3892-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3892-106">Required.</span></span> <span data-ttu-id="a3892-107">Ein `Boolean`-Wert.</span><span class="sxs-lookup"><span data-stu-id="a3892-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="a3892-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3892-108">Required.</span></span> <span data-ttu-id="a3892-109">Eine `Object` beliebige Variable oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a3892-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="a3892-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a3892-110">Required.</span></span> <span data-ttu-id="a3892-111">Eine `Object` beliebige Variable oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a3892-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3892-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3892-112">Remarks</span></span>  
 <span data-ttu-id="a3892-113">Der `IsNot` -Operator bestimmt, ob zwei Objekt Verweise auf unterschiedliche Objekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="a3892-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="a3892-114">Es werden jedoch keine Wert Vergleiche durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="a3892-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="a3892-115">Wenn `object1` `result` und `result` `True`beide auf genau`False`dieselbe Objektinstanz verweisen, ist. andernfalls ist der Wert. `object2`</span><span class="sxs-lookup"><span data-stu-id="a3892-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="a3892-116">`IsNot`ist das Gegenteil des `Is` -Operators.</span><span class="sxs-lookup"><span data-stu-id="a3892-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="a3892-117">Der Vorteil von `IsNot` besteht darin, dass Sie eine umständliche `Not` Syntax `Is`mit und vermeiden können, was schwierig zu lesen ist.</span><span class="sxs-lookup"><span data-stu-id="a3892-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="a3892-118">Sie können die `Is` Operatoren `IsNot` und verwenden, um früh gebundene und spät gebundene Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="a3892-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3892-119">Der `IsNot` Operator kann nicht zum Vergleichen von Ausdrücken verwendet werden, `TypeOf` die vom Operator zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a3892-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="a3892-120">Stattdessen müssen Sie die `Not` Operatoren und `Is` verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3892-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3892-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a3892-121">Example</span></span>  
 <span data-ttu-id="a3892-122">Im folgenden Codebeispiel wird der `Is` `IsNot` -Operator und der-Operator verwendet, um denselben Vergleich durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a3892-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a><span data-ttu-id="a3892-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3892-123">See also</span></span>

- [<span data-ttu-id="a3892-124">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="a3892-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="a3892-125">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="a3892-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="a3892-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3892-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a3892-127">Vorgehensweise: Testen, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="a3892-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
