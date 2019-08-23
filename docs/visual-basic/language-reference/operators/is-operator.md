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
ms.openlocfilehash: a5481a9bce01e84ce4f078335c8cd15a747a3c51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917221"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="2da86-102">Is-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2da86-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="2da86-103">Vergleicht zwei Objekt Verweis Variablen.</span><span class="sxs-lookup"><span data-stu-id="2da86-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2da86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2da86-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="2da86-105">Teile</span><span class="sxs-lookup"><span data-stu-id="2da86-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="2da86-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2da86-106">Required.</span></span> <span data-ttu-id="2da86-107">Ein `Boolean` beliebiger Wert.</span><span class="sxs-lookup"><span data-stu-id="2da86-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="2da86-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2da86-108">Required.</span></span> <span data-ttu-id="2da86-109">Ein `Object` beliebiger Name.</span><span class="sxs-lookup"><span data-stu-id="2da86-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="2da86-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2da86-110">Required.</span></span> <span data-ttu-id="2da86-111">Ein `Object` beliebiger Name.</span><span class="sxs-lookup"><span data-stu-id="2da86-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2da86-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2da86-112">Remarks</span></span>  
 <span data-ttu-id="2da86-113">Der `Is` -Operator bestimmt, ob zwei Objekt Verweise auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="2da86-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="2da86-114">Es werden jedoch keine Wert Vergleiche durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="2da86-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="2da86-115">Wenn `object1` `result` und `result` `False`beide auf genau`True`dieselbe Objektinstanz verweisen, ist. andernfalls ist der Wert. `object2`</span><span class="sxs-lookup"><span data-stu-id="2da86-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="2da86-116">`Is`kann auch mit dem `TypeOf` -Schlüsselwort verwendet werden, um eine `TypeOf`zu erstellen... `Is` Ausdruck, der testet, ob eine Objekt Variable mit einem Datentyp kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="2da86-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2da86-117">Das `Is` Schlüsselwort wird auch im [SELECT... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2da86-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2da86-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2da86-118">Example</span></span>  
 <span data-ttu-id="2da86-119">Im folgenden Beispiel wird der `Is` -Operator verwendet, um Paare von Objekt verweisen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="2da86-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="2da86-120">Die Ergebnisse werden einem `Boolean` Wert zugewiesen, der angibt, ob die beiden-Objekte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="2da86-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="2da86-121">Wie das vorherige Beispiel zeigt, können Sie den `Is` -Operator verwenden, um früh gebundene und spät gebundene Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="2da86-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da86-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2da86-122">See also</span></span>

- [<span data-ttu-id="2da86-123">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="2da86-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="2da86-124">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="2da86-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="2da86-125">Vergleichs Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2da86-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="2da86-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2da86-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="2da86-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="2da86-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="2da86-128">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="2da86-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
