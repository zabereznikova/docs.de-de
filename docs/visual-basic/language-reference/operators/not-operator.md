---
title: Not-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 7d0beea16a2ac00be090c6a241f9790a0ba33390
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874799"
---
# <a name="not-operator-visual-basic"></a><span data-ttu-id="8e55b-102">Not-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e55b-102">Not Operator (Visual Basic)</span></span>

<span data-ttu-id="8e55b-103">Führt eine logische Negation für einen- `Boolean` Ausdruck oder eine bitweise Negation eines numerischen Ausdrucks aus.</span><span class="sxs-lookup"><span data-stu-id="8e55b-103">Performs logical negation on a `Boolean` expression, or bitwise negation on a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e55b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e55b-104">Syntax</span></span>  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a><span data-ttu-id="8e55b-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="8e55b-105">Parts</span></span>  

 `result`  
 <span data-ttu-id="8e55b-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e55b-106">Required.</span></span> <span data-ttu-id="8e55b-107">Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8e55b-107">Any `Boolean` or numeric expression.</span></span>  
  
 `expression`  
 <span data-ttu-id="8e55b-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e55b-108">Required.</span></span> <span data-ttu-id="8e55b-109">Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8e55b-109">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e55b-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8e55b-110">Remarks</span></span>  

 <span data-ttu-id="8e55b-111">In `Boolean` der folgenden Tabelle wird für Ausdrücke veranschaulicht, wie `result` bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="8e55b-111">For `Boolean` expressions, the following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="8e55b-112">Wenn `expression` gleich </span><span class="sxs-lookup"><span data-stu-id="8e55b-112">If `expression` is</span></span>|<span data-ttu-id="8e55b-113">Der Wert von `result` ist</span><span class="sxs-lookup"><span data-stu-id="8e55b-113">The value of `result` is</span></span>|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 <span data-ttu-id="8e55b-114">Bei numerischen Ausdrücken kehrt der `Not` Operator die Bitwerte eines beliebigen numerischen Ausdrucks um und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="8e55b-114">For numeric expressions, the `Not` operator inverts the bit values of any numeric expression and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="8e55b-115">Wenn `expression` Bit in</span><span class="sxs-lookup"><span data-stu-id="8e55b-115">If bit in `expression` is</span></span>|<span data-ttu-id="8e55b-116">Das Bit in `result` ist</span><span class="sxs-lookup"><span data-stu-id="8e55b-116">The bit in `result` is</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="8e55b-117">1</span><span class="sxs-lookup"><span data-stu-id="8e55b-117">1</span></span>|<span data-ttu-id="8e55b-118">0</span><span class="sxs-lookup"><span data-stu-id="8e55b-118">0</span></span>|  
|<span data-ttu-id="8e55b-119">0</span><span class="sxs-lookup"><span data-stu-id="8e55b-119">0</span></span>|<span data-ttu-id="8e55b-120">1</span><span class="sxs-lookup"><span data-stu-id="8e55b-120">1</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="8e55b-121">Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um eine exakte Ausführung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="8e55b-121">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="8e55b-122">Datentypen</span><span class="sxs-lookup"><span data-stu-id="8e55b-122">Data Types</span></span>  

 <span data-ttu-id="8e55b-123">Bei einer booleschen Negation ist der Datentyp des Ergebnisses `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="8e55b-123">For a Boolean negation, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="8e55b-124">Bei einer bitweisen Negation ist der Ergebnis Datentyp mit dem von identisch `expression` .</span><span class="sxs-lookup"><span data-stu-id="8e55b-124">For a bitwise negation, the result data type is the same as that of `expression`.</span></span> <span data-ttu-id="8e55b-125">Wenn Expression jedoch ist `Decimal` , ist das Ergebnis `Long` .</span><span class="sxs-lookup"><span data-stu-id="8e55b-125">However, if expression is `Decimal`, the result is `Long`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="8e55b-126">Überladen</span><span class="sxs-lookup"><span data-stu-id="8e55b-126">Overloading</span></span>  

 <span data-ttu-id="8e55b-127">Der `Not` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="8e55b-127">The `Not` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="8e55b-128">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="8e55b-128">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8e55b-129">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8e55b-129">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e55b-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e55b-130">Example</span></span>  

 <span data-ttu-id="8e55b-131">Im folgenden Beispiel wird der- `Not` Operator verwendet, um eine logische Negation für einen- `Boolean` Ausdruck auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8e55b-131">The following example uses the `Not` operator to perform logical negation on a `Boolean` expression.</span></span> <span data-ttu-id="8e55b-132">Das Ergebnis ist ein `Boolean` Wert, der das Gegenteil des Werts des Ausdrucks darstellt.</span><span class="sxs-lookup"><span data-stu-id="8e55b-132">The result is a `Boolean` value that represents the reverse of the value of the expression.</span></span>  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 <span data-ttu-id="8e55b-133">Das vorherige Beispiel erzeugt die Ergebnisse von `False` und `True` .</span><span class="sxs-lookup"><span data-stu-id="8e55b-133">The preceding example produces results of `False` and `True`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e55b-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e55b-134">Example</span></span>  

 <span data-ttu-id="8e55b-135">Im folgenden Beispiel wird der- `Not` Operator verwendet, um eine logische Negation der einzelnen Bits eines numerischen Ausdrucks auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8e55b-135">The following example uses the `Not` operator to perform logical negation of the individual bits of a numeric expression.</span></span> <span data-ttu-id="8e55b-136">Das Bit im Ergebnis Muster wird auf das Gegenteil des entsprechenden Bits im Operanden Muster festgelegt, einschließlich des Signier Bits.</span><span class="sxs-lookup"><span data-stu-id="8e55b-136">The bit in the result pattern is set to the reverse of the corresponding bit in the operand pattern, including the sign bit.</span></span>  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 <span data-ttu-id="8e55b-137">Im vorherigen Beispiel werden die Ergebnisse von – 11, – 9 bzw. – 7 erzeugt.</span><span class="sxs-lookup"><span data-stu-id="8e55b-137">The preceding example produces results of –11, –9, and –7, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e55b-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e55b-138">See also</span></span>

- [<span data-ttu-id="8e55b-139">Logische/bitweise Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e55b-139">Logical/Bitwise Operators (Visual Basic)</span></span>](logical-bitwise-operators.md)
- [<span data-ttu-id="8e55b-140">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e55b-140">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="8e55b-141">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="8e55b-141">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="8e55b-142">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e55b-142">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
