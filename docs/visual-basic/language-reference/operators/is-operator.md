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
ms.openlocfilehash: 1c2d87ef0a8202332c87af552f488d652c400213
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812262"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="8cc25-102">Is-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8cc25-102">Is operator (Visual Basic)</span></span>

<span data-ttu-id="8cc25-103">Vergleicht zwei Objekt Verweis Variablen.</span><span class="sxs-lookup"><span data-stu-id="8cc25-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="8cc25-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8cc25-104">Syntax</span></span>

```vb
result = object1 Is object2
```

## <a name="parts"></a><span data-ttu-id="8cc25-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="8cc25-105">Parts</span></span>

 `result`  
 <span data-ttu-id="8cc25-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8cc25-106">Required.</span></span> <span data-ttu-id="8cc25-107">Ein beliebiger `Boolean` Wert.</span><span class="sxs-lookup"><span data-stu-id="8cc25-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="8cc25-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8cc25-108">Required.</span></span> <span data-ttu-id="8cc25-109">Ein beliebiger `Object` Name.</span><span class="sxs-lookup"><span data-stu-id="8cc25-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="8cc25-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8cc25-110">Required.</span></span> <span data-ttu-id="8cc25-111">Ein beliebiger `Object` Name.</span><span class="sxs-lookup"><span data-stu-id="8cc25-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cc25-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8cc25-112">Remarks</span></span>

<span data-ttu-id="8cc25-113">Der- `Is` Operator bestimmt, ob zwei Objekt Verweise auf das gleiche Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="8cc25-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="8cc25-114">Es werden jedoch keine Wert Vergleiche durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="8cc25-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="8cc25-115">Wenn `object1` und `object2` beide auf genau dieselbe Objektinstanz verweisen, ist `result` `True` . andernfalls ist der Wert `result` `False` .</span><span class="sxs-lookup"><span data-stu-id="8cc25-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>

> [!NOTE]
> <span data-ttu-id="8cc25-116">Das `Is` Schlüsselwort wird auch im [SELECT... Case-Anweisung](../statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8cc25-116">The `Is` keyword is also used in the [Select...Case Statement](../statements/select-case-statement.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="8cc25-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8cc25-117">Example</span></span>

<span data-ttu-id="8cc25-118">Im folgenden Beispiel wird der- `Is` Operator verwendet, um Paare von Objekt verweisen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="8cc25-118">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="8cc25-119">Die Ergebnisse werden einem Wert zugewiesen, `Boolean` der angibt, ob die beiden-Objekte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="8cc25-119">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>

[!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]

<span data-ttu-id="8cc25-120">Wie das vorherige Beispiel zeigt, können Sie den- `Is` Operator verwenden, um früh gebundene und spät gebundene Objekte zu testen.</span><span class="sxs-lookup"><span data-stu-id="8cc25-120">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>

## <a name="use-typeof-operator-with-is-operator"></a><span data-ttu-id="8cc25-121">Typeof-Operator mit is-Operator verwenden</span><span class="sxs-lookup"><span data-stu-id="8cc25-121">Use TypeOf operator with Is operator</span></span>

<span data-ttu-id="8cc25-122">`Is` der-Operator kann auch mit dem-Schlüsselwort verwendet werden, `TypeOf` um einen `TypeOf` ...-Ausdruck zu erstellen `Is` , der testet, ob eine Objekt Variable mit einem-Datentyp kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="8cc25-122">`Is` operator can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span> <span data-ttu-id="8cc25-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8cc25-123">For example:</span></span>

```vb
If TypeOf sender Is Button Then
```

## <a name="see-also"></a><span data-ttu-id="8cc25-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8cc25-124">See also</span></span>

- [<span data-ttu-id="8cc25-125">Typeof-Operator</span><span class="sxs-lookup"><span data-stu-id="8cc25-125">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="8cc25-126">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="8cc25-126">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="8cc25-127">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8cc25-127">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="8cc25-128">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8cc25-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="8cc25-129">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="8cc25-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="8cc25-130">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8cc25-130">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
