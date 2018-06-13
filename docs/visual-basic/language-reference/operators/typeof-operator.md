---
title: TypeOf-Operator (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: fe287794423048e993d953c83fc8590a06b7a5e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604054"
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="21d78-102">TypeOf-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21d78-102">TypeOf Operator (Visual Basic)</span></span>
<span data-ttu-id="21d78-103">Vergleicht eine Objektverweisvariable mit einem Datentyp.</span><span class="sxs-lookup"><span data-stu-id="21d78-103">Compares an object reference variable to a data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21d78-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21d78-104">Syntax</span></span>  
  
```  
result = TypeOf objectexpression Is typename  
```  
  
```  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="21d78-105">Teile</span><span class="sxs-lookup"><span data-stu-id="21d78-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="21d78-106">Wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="21d78-106">Returned.</span></span> <span data-ttu-id="21d78-107">Ein `Boolean`-Wert.</span><span class="sxs-lookup"><span data-stu-id="21d78-107">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="21d78-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="21d78-108">Required.</span></span> <span data-ttu-id="21d78-109">Jeder Ausdruck, der als ein Verweistyp ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="21d78-109">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="21d78-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="21d78-110">Required.</span></span> <span data-ttu-id="21d78-111">Ein beliebiger Datentypname.</span><span class="sxs-lookup"><span data-stu-id="21d78-111">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21d78-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21d78-112">Remarks</span></span>  
 <span data-ttu-id="21d78-113">Der `TypeOf`-Operator bestimmt, ob der Laufzeittyp von `objectexpression` mit `typename` kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="21d78-113">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="21d78-114">Die Kompatibilität hängt von der Typkategorie von `typename` ab.</span><span class="sxs-lookup"><span data-stu-id="21d78-114">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="21d78-115">Die folgende Tabelle zeigt, wie die Kompatibilität bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="21d78-115">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="21d78-116">Typkategorie von `typename`</span><span class="sxs-lookup"><span data-stu-id="21d78-116">Type category of `typename`</span></span>|<span data-ttu-id="21d78-117">Kompatibilitätskriterium</span><span class="sxs-lookup"><span data-stu-id="21d78-117">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="21d78-118">Klasse</span><span class="sxs-lookup"><span data-stu-id="21d78-118">Class</span></span>|<span data-ttu-id="21d78-119">`objectexpression` ist vom Typ `typename` oder erbt von `typename`</span><span class="sxs-lookup"><span data-stu-id="21d78-119">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="21d78-120">Struktur</span><span class="sxs-lookup"><span data-stu-id="21d78-120">Structure</span></span>|<span data-ttu-id="21d78-121">`objectexpression` ist vom Typ `typename`</span><span class="sxs-lookup"><span data-stu-id="21d78-121">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="21d78-122">Interface</span><span class="sxs-lookup"><span data-stu-id="21d78-122">Interface</span></span>|<span data-ttu-id="21d78-123">`objectexpression` implementiert `typename` oder erbt von einer Klasse, die `typename` implementiert</span><span class="sxs-lookup"><span data-stu-id="21d78-123">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="21d78-124">Wenn der Laufzeittyp von `objectexpression` das Kompatibilitätskriterium erfüllt, ist `result` `True`.</span><span class="sxs-lookup"><span data-stu-id="21d78-124">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="21d78-125">Andernfalls ist `result` `False`.</span><span class="sxs-lookup"><span data-stu-id="21d78-125">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="21d78-126">Wenn `objectexpression` null ist, dann gibt `TypeOf`...`Is` `False` zurück, und ...`IsNot` gibt `True` zurück.</span><span class="sxs-lookup"><span data-stu-id="21d78-126">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="21d78-127">`TypeOf` wird immer mit dem Schlüsselwort `Is` verwendet, um einen `TypeOf`...`Is`-Ausdruck zu erstellen, oder mit dem Schlüsselwort `IsNot`, um einen `TypeOf`...`IsNot`-Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="21d78-127">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21d78-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21d78-128">Example</span></span>  
 <span data-ttu-id="21d78-129">Im folgenden Beispiel werden `TypeOf`...`Is`-Ausdrücke zum Testen der Typkompatibilität von zwei Objektverweisvariablen mit verschiedenen Datentypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="21d78-129">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/typeof-operator_1.vb)]  
  
 <span data-ttu-id="21d78-130">Die Variable `refInteger` verfügt über einen Laufzeittyp von `Integer`.</span><span class="sxs-lookup"><span data-stu-id="21d78-130">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="21d78-131">Sie ist mit `Integer`, jedoch nicht mit `Double` kompatibel.</span><span class="sxs-lookup"><span data-stu-id="21d78-131">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="21d78-132">Die Variable `refForm` verfügt über einen Laufzeittyp von <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="21d78-132">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="21d78-133">Sie ist mit <xref:System.Windows.Forms.Form> kompatibel, da es sich hierbei um ihren Typ handelt, sowie mit <xref:System.Windows.Forms.Control>, da <xref:System.Windows.Forms.Form> von <xref:System.Windows.Forms.Control> erbt, und mit <xref:System.ComponentModel.IComponent>, da <xref:System.Windows.Forms.Form> von <xref:System.ComponentModel.Component> erbt, welche wiederum <xref:System.ComponentModel.IComponent> implementiert.</span><span class="sxs-lookup"><span data-stu-id="21d78-133">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="21d78-134">`refForm` ist jedoch mit <xref:System.Windows.Forms.Label> nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="21d78-134">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d78-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21d78-135">See Also</span></span>  
 [<span data-ttu-id="21d78-136">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="21d78-136">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="21d78-137">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="21d78-137">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="21d78-138">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21d78-138">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="21d78-139">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21d78-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="21d78-140">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="21d78-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="21d78-141">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="21d78-141">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
