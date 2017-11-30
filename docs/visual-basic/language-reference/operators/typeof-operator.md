---
title: TypeOf-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 51bd2af7af28aa229fa62770c5b92d31e461333b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="27809-102">TypeOf-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27809-102">TypeOf Operator (Visual Basic)</span></span>
<span data-ttu-id="27809-103">Vergleicht eine Objektverweisvariable mit einem Datentyp.</span><span class="sxs-lookup"><span data-stu-id="27809-103">Compares an object reference variable to a data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27809-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27809-104">Syntax</span></span>  
  
```  
result = TypeOf objectexpression Is typename  
```  
  
```  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="27809-105">Teile</span><span class="sxs-lookup"><span data-stu-id="27809-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="27809-106">Wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27809-106">Returned.</span></span> <span data-ttu-id="27809-107">Ein `Boolean`-Wert.</span><span class="sxs-lookup"><span data-stu-id="27809-107">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="27809-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="27809-108">Required.</span></span> <span data-ttu-id="27809-109">Jeder Ausdruck, der als ein Verweistyp ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="27809-109">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="27809-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="27809-110">Required.</span></span> <span data-ttu-id="27809-111">Ein beliebiger Datentypname.</span><span class="sxs-lookup"><span data-stu-id="27809-111">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27809-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27809-112">Remarks</span></span>  
 <span data-ttu-id="27809-113">Der `TypeOf`-Operator bestimmt, ob der Laufzeittyp von `objectexpression` mit `typename` kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="27809-113">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="27809-114">Die Kompatibilität hängt von der Typkategorie von `typename` ab.</span><span class="sxs-lookup"><span data-stu-id="27809-114">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="27809-115">Die folgende Tabelle zeigt, wie die Kompatibilität bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="27809-115">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="27809-116">Typkategorie von `typename`</span><span class="sxs-lookup"><span data-stu-id="27809-116">Type category of `typename`</span></span>|<span data-ttu-id="27809-117">Kompatibilitätskriterium</span><span class="sxs-lookup"><span data-stu-id="27809-117">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="27809-118">Klasse</span><span class="sxs-lookup"><span data-stu-id="27809-118">Class</span></span>|<span data-ttu-id="27809-119">`objectexpression` ist vom Typ `typename` oder erbt von `typename`</span><span class="sxs-lookup"><span data-stu-id="27809-119">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="27809-120">Struktur</span><span class="sxs-lookup"><span data-stu-id="27809-120">Structure</span></span>|<span data-ttu-id="27809-121">`objectexpression` ist vom Typ `typename`</span><span class="sxs-lookup"><span data-stu-id="27809-121">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="27809-122">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27809-122">Interface</span></span>|<span data-ttu-id="27809-123">`objectexpression` implementiert `typename` oder erbt von einer Klasse, die `typename` implementiert</span><span class="sxs-lookup"><span data-stu-id="27809-123">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="27809-124">Wenn der Laufzeittyp von `objectexpression` das Kompatibilitätskriterium erfüllt, ist `result` `True`.</span><span class="sxs-lookup"><span data-stu-id="27809-124">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="27809-125">Andernfalls ist `result` `False`.</span><span class="sxs-lookup"><span data-stu-id="27809-125">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="27809-126">Wenn `objectexpression` null ist, dann gibt `TypeOf`...`Is` `False` zurück, und ...`IsNot` gibt `True` zurück.</span><span class="sxs-lookup"><span data-stu-id="27809-126">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="27809-127">`TypeOf` wird immer mit dem Schlüsselwort `Is` verwendet, um einen `TypeOf`...`Is`-Ausdruck zu erstellen, oder mit dem Schlüsselwort `IsNot`, um einen `TypeOf`...`IsNot`-Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="27809-127">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27809-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27809-128">Example</span></span>  
 <span data-ttu-id="27809-129">Im folgenden Beispiel werden `TypeOf`...`Is`-Ausdrücke zum Testen der Typkompatibilität von zwei Objektverweisvariablen mit verschiedenen Datentypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="27809-129">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/typeof-operator_1.vb)]  
  
 <span data-ttu-id="27809-130">Die Variable `refInteger` verfügt über einen Laufzeittyp von `Integer`.</span><span class="sxs-lookup"><span data-stu-id="27809-130">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="27809-131">Sie ist mit `Integer`, jedoch nicht mit `Double` kompatibel.</span><span class="sxs-lookup"><span data-stu-id="27809-131">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="27809-132">Die Variable `refForm` verfügt über einen Laufzeittyp von <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="27809-132">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="27809-133">Sie ist mit <xref:System.Windows.Forms.Form> kompatibel, da es sich hierbei um ihren Typ handelt, sowie mit <xref:System.Windows.Forms.Control>, da <xref:System.Windows.Forms.Form> von <xref:System.Windows.Forms.Control> erbt, und mit <xref:System.ComponentModel.IComponent>, da <xref:System.Windows.Forms.Form> von <xref:System.ComponentModel.Component> erbt, welche wiederum <xref:System.ComponentModel.IComponent> implementiert.</span><span class="sxs-lookup"><span data-stu-id="27809-133">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="27809-134">`refForm` ist jedoch mit <xref:System.Windows.Forms.Label> nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="27809-134">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27809-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27809-135">See Also</span></span>  
 [<span data-ttu-id="27809-136">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="27809-136">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="27809-137">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="27809-137">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="27809-138">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="27809-138">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="27809-139">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27809-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="27809-140">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="27809-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="27809-141">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="27809-141">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
