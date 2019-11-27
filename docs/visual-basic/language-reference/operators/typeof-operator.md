---
title: Operator TypeOf
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
ms.openlocfilehash: 22af5b8f8488ca44e388596530decd52e33525dc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350892"
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="603cc-102">TypeOf-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="603cc-102">TypeOf Operator (Visual Basic)</span></span>
<span data-ttu-id="603cc-103">Überprüft, ob der Lauf Zeittyp des Ergebnisses eines Ausdrucks typkompatibel mit dem angegebenen Typ ist.</span><span class="sxs-lookup"><span data-stu-id="603cc-103">Checks whether the runtime type of an expression's result is type-compatible with the specified type.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="603cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="603cc-104">Syntax</span></span>  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="603cc-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="603cc-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="603cc-106">Wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="603cc-106">Returned.</span></span> <span data-ttu-id="603cc-107">Ein `Boolean`-Wert.</span><span class="sxs-lookup"><span data-stu-id="603cc-107">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="603cc-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="603cc-108">Required.</span></span> <span data-ttu-id="603cc-109">Jeder Ausdruck, der als ein Verweistyp ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="603cc-109">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="603cc-110">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="603cc-110">Required.</span></span> <span data-ttu-id="603cc-111">Ein beliebiger Datentypname.</span><span class="sxs-lookup"><span data-stu-id="603cc-111">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="603cc-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="603cc-112">Remarks</span></span>  
 <span data-ttu-id="603cc-113">Der `TypeOf`-Operator bestimmt, ob der Laufzeittyp von `objectexpression` mit `typename` kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="603cc-113">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="603cc-114">Die Kompatibilität hängt von der Typkategorie von `typename` ab.</span><span class="sxs-lookup"><span data-stu-id="603cc-114">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="603cc-115">Die folgende Tabelle zeigt, wie die Kompatibilität bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="603cc-115">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="603cc-116">Typkategorie von `typename`</span><span class="sxs-lookup"><span data-stu-id="603cc-116">Type category of `typename`</span></span>|<span data-ttu-id="603cc-117">Kompatibilitätskriterium</span><span class="sxs-lookup"><span data-stu-id="603cc-117">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="603cc-118">Klasse</span><span class="sxs-lookup"><span data-stu-id="603cc-118">Class</span></span>|<span data-ttu-id="603cc-119">`objectexpression` ist vom Typ `typename` oder erbt von `typename`</span><span class="sxs-lookup"><span data-stu-id="603cc-119">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="603cc-120">Struktur</span><span class="sxs-lookup"><span data-stu-id="603cc-120">Structure</span></span>|<span data-ttu-id="603cc-121">`objectexpression` ist vom Typ `typename`</span><span class="sxs-lookup"><span data-stu-id="603cc-121">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="603cc-122">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="603cc-122">Interface</span></span>|<span data-ttu-id="603cc-123">`objectexpression` implementiert `typename` oder erbt von einer Klasse, die implementiert `typename`</span><span class="sxs-lookup"><span data-stu-id="603cc-123">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="603cc-124">Wenn der Laufzeittyp von `objectexpression` das Kompatibilitätskriterium erfüllt, ist `result``True`.</span><span class="sxs-lookup"><span data-stu-id="603cc-124">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="603cc-125">Andernfalls lautet `result` `False`.</span><span class="sxs-lookup"><span data-stu-id="603cc-125">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="603cc-126">Wenn `objectexpression` null ist, dann gibt `TypeOf`...`Is``False` zurück, und ...`IsNot` gibt `True` zurück.</span><span class="sxs-lookup"><span data-stu-id="603cc-126">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="603cc-127">`TypeOf` wird immer mit dem Schlüsselwort `Is` verwendet, um einen `TypeOf`...`Is` Ausdruck zu erstellen, oder mit dem `IsNot`-Schlüsselwort, um einen `TypeOf`Ausdruck`IsNot`... zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="603cc-127">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="603cc-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="603cc-128">Example</span></span>  
 <span data-ttu-id="603cc-129">Im folgenden Beispiel werden `TypeOf`...`Is`-Ausdrücke zum Testen der Typkompatibilität von zwei Objektverweisvariablen mit verschiedenen Datentypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="603cc-129">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 <span data-ttu-id="603cc-130">Die Variable `refInteger` verfügt über einen Laufzeittyp von `Integer`.</span><span class="sxs-lookup"><span data-stu-id="603cc-130">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="603cc-131">Sie ist mit `Integer`, jedoch nicht mit `Double` kompatibel.</span><span class="sxs-lookup"><span data-stu-id="603cc-131">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="603cc-132">Die Variable `refForm` verfügt über einen Laufzeittyp von <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="603cc-132">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="603cc-133">Sie ist mit <xref:System.Windows.Forms.Form> kompatibel, da es sich hierbei um ihren Typ handelt, sowie mit <xref:System.Windows.Forms.Control>, da <xref:System.Windows.Forms.Form> von <xref:System.Windows.Forms.Control> erbt, und mit <xref:System.ComponentModel.IComponent>, da <xref:System.Windows.Forms.Form> von <xref:System.ComponentModel.Component> erbt, welche wiederum <xref:System.ComponentModel.IComponent> implementiert.</span><span class="sxs-lookup"><span data-stu-id="603cc-133">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="603cc-134">`refForm` ist jedoch mit <xref:System.Windows.Forms.Label> nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="603cc-134">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="603cc-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="603cc-135">See also</span></span>

- [<span data-ttu-id="603cc-136">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="603cc-136">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="603cc-137">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="603cc-137">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="603cc-138">Vergleichs Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="603cc-138">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="603cc-139">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="603cc-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="603cc-140">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="603cc-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="603cc-141">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="603cc-141">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
