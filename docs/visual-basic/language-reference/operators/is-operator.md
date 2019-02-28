---
title: Is-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: c4b23bb2d81d1f5272a5813123681da7406c3368
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980338"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="5b361-102">Is-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b361-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="5b361-103">Vergleicht zwei Objektverweisvariablen.</span><span class="sxs-lookup"><span data-stu-id="5b361-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b361-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b361-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="5b361-105">Teile</span><span class="sxs-lookup"><span data-stu-id="5b361-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="5b361-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5b361-106">Required.</span></span> <span data-ttu-id="5b361-107">Alle `Boolean` Wert.</span><span class="sxs-lookup"><span data-stu-id="5b361-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="5b361-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5b361-108">Required.</span></span> <span data-ttu-id="5b361-109">Alle `Object` Name.</span><span class="sxs-lookup"><span data-stu-id="5b361-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="5b361-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5b361-110">Required.</span></span> <span data-ttu-id="5b361-111">Alle `Object` Name.</span><span class="sxs-lookup"><span data-stu-id="5b361-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b361-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b361-112">Remarks</span></span>  
 <span data-ttu-id="5b361-113">Die `Is` -Operator ermittelt, ob zwei Objektverweise auf dasselbe Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="5b361-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="5b361-114">Er führt jedoch keine vergleichen.</span><span class="sxs-lookup"><span data-stu-id="5b361-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="5b361-115">Wenn `object1` und `object2` beide verweisen auf genau dieselbe Objektinstanz, `result` ist `True`; Wenn dies nicht der Fall `result` ist `False`.</span><span class="sxs-lookup"><span data-stu-id="5b361-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="5b361-116">`Is` kann auch verwendet werden, mit der `TypeOf` Schlüsselwort, um die stellen eine `TypeOf`... `Is` Ausdruck, der testet, ob es sich bei eine Objektvariablen mit dem Datentyp kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="5b361-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b361-117">Die `Is` -Schlüsselwort wird auch verwendet, der [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5b361-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b361-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b361-118">Example</span></span>  
 <span data-ttu-id="5b361-119">Im folgenden Beispiel wird die `Is` Operator, um Paare von Objektverweisen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="5b361-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="5b361-120">Die Ergebnisse zugewiesen sind eine `Boolean` darstellt, ob die beiden Objekte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="5b361-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="5b361-121">Wie im vorherige Beispiel wird veranschaulicht, können Sie die `Is` Operator, um sowohl eine frühe Bindung und spät gebundene Objekte.</span><span class="sxs-lookup"><span data-stu-id="5b361-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b361-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b361-122">See also</span></span>
- [<span data-ttu-id="5b361-123">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="5b361-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="5b361-124">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="5b361-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="5b361-125">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5b361-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="5b361-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b361-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="5b361-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="5b361-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="5b361-128">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="5b361-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
