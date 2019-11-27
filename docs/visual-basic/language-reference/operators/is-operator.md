---
title: Is-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 52fbb39ab0a36c8b947b78f464fad26be05ce204
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349534"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="e4a9e-102">Is-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4a9e-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="e4a9e-103">Vergleicht zwei Objekt Verweis Variablen.</span><span class="sxs-lookup"><span data-stu-id="e4a9e-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4a9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4a9e-104">Syntax</span></span>  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="e4a9e-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="e4a9e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="e4a9e-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="e4a9e-106">Required.</span></span> <span data-ttu-id="e4a9e-107">Ein beliebiger `Boolean` Wert.</span><span class="sxs-lookup"><span data-stu-id="e4a9e-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="e4a9e-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="e4a9e-108">Required.</span></span> <span data-ttu-id="e4a9e-109">Jeder `Object` Name.</span><span class="sxs-lookup"><span data-stu-id="e4a9e-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="e4a9e-110">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="e4a9e-110">Required.</span></span> <span data-ttu-id="e4a9e-111">Jeder `Object` Name.</span><span class="sxs-lookup"><span data-stu-id="e4a9e-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4a9e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4a9e-112">Remarks</span></span>  
 <span data-ttu-id="e4a9e-113">Der `Is`-Operator bestimmt, ob zwei Objekt Verweise auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="e4a9e-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="e4a9e-114">Es werden jedoch keine Wert Vergleiche durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="e4a9e-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="e4a9e-115">Wenn `object1` und `object2` beide auf genau dieselbe Objektinstanz verweisen, ist `result` `True`. Wenn dies nicht der Fall ist, wird `result` `False`.</span><span class="sxs-lookup"><span data-stu-id="e4a9e-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="e4a9e-116">`Is` können auch mit dem Schlüsselwort `TypeOf` verwendet werden, um einen `TypeOf`...`Is` Ausdruck zu erstellen, der testet, ob eine Objekt Variable mit einem Datentyp kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="e4a9e-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4a9e-117">Das `Is`-Schlüsselwort wird auch im [SELECT... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e4a9e-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4a9e-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4a9e-118">Example</span></span>  
 <span data-ttu-id="e4a9e-119">Im folgenden Beispiel wird der `Is`-Operator verwendet, um Paare von Objekt verweisen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="e4a9e-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="e4a9e-120">Die Ergebnisse werden einem `Boolean` Wert zugewiesen, der angibt, ob die beiden-Objekte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="e4a9e-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="e4a9e-121">Wie das vorherige Beispiel zeigt, können Sie den `Is`-Operator verwenden, um früh gebundene und spät gebundene Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="e4a9e-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4a9e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4a9e-122">See also</span></span>

- [<span data-ttu-id="e4a9e-123">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="e4a9e-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="e4a9e-124">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="e4a9e-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="e4a9e-125">Vergleichs Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e4a9e-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="e4a9e-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4a9e-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e4a9e-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="e4a9e-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e4a9e-128">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="e4a9e-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
