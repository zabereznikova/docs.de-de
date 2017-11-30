---
title: Is-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b1f3f0fa1fd782550c08c816f47b7541399198e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="ad27b-102">Is-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad27b-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="ad27b-103">Vergleicht zwei Objektverweisvariablen.</span><span class="sxs-lookup"><span data-stu-id="ad27b-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad27b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad27b-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="ad27b-105">Teile</span><span class="sxs-lookup"><span data-stu-id="ad27b-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="ad27b-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ad27b-106">Required.</span></span> <span data-ttu-id="ad27b-107">Alle `Boolean` Wert.</span><span class="sxs-lookup"><span data-stu-id="ad27b-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="ad27b-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ad27b-108">Required.</span></span> <span data-ttu-id="ad27b-109">Alle `Object` Name.</span><span class="sxs-lookup"><span data-stu-id="ad27b-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="ad27b-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ad27b-110">Required.</span></span> <span data-ttu-id="ad27b-111">Alle `Object` Name.</span><span class="sxs-lookup"><span data-stu-id="ad27b-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad27b-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad27b-112">Remarks</span></span>  
 <span data-ttu-id="ad27b-113">Die `Is` -Operator ermittelt, ob zwei Objektverweise auf dasselbe Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="ad27b-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="ad27b-114">Er führt jedoch keine Wertvergleiche.</span><span class="sxs-lookup"><span data-stu-id="ad27b-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="ad27b-115">Wenn `object1` und `object2` beide verweisen auf genau dieselbe Objektinstanz, `result` ist `True`; Wenn sie keinen `result` ist `False`.</span><span class="sxs-lookup"><span data-stu-id="ad27b-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="ad27b-116">`Is`kann auch verwendet werden, mit der `TypeOf` Schlüsselwort stellen eine `TypeOf`... `Is` Ausdruck, der testet, ob eine Objektvariable mit dem Datentyp kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="ad27b-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad27b-117">Die `Is` Schlüsselwort werden auch in der [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ad27b-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad27b-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad27b-118">Example</span></span>  
 <span data-ttu-id="ad27b-119">Im folgenden Beispiel wird die `Is` Operator, um Paare von Objektverweisen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="ad27b-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="ad27b-120">Die Ergebnisse zugewiesen sind eine `Boolean` Wert darstellt, ob die beiden Objekte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="ad27b-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 <span data-ttu-id="ad27b-121">Wie im vorherige Beispiel veranschaulicht, können Sie die `Is` Operator, um beide testen früh gebundener Aufruf und spät gebundene Objekte.</span><span class="sxs-lookup"><span data-stu-id="ad27b-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad27b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad27b-122">See Also</span></span>  
 [<span data-ttu-id="ad27b-123">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="ad27b-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="ad27b-124">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="ad27b-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="ad27b-125">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad27b-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="ad27b-126">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad27b-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="ad27b-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="ad27b-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="ad27b-128">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ad27b-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
