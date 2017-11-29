---
title: "Operatorrangfolge in Visual Basic"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c0fb466b404cafdd4b91d061971fd683375c715
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="ba0da-102">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba0da-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="ba0da-103">Treten mehrere Operationen in einem Ausdruck, wird jeder Teil ausgewertet und in einem vorbestimmten Reihenfolge aufgelöst *Operatorrangfolge*.</span><span class="sxs-lookup"><span data-stu-id="ba0da-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="ba0da-104">Rangfolgeregeln</span><span class="sxs-lookup"><span data-stu-id="ba0da-104">Precedence Rules</span></span>  
 <span data-ttu-id="ba0da-105">Wenn Ausdrücke Operatoren aus mehr als einer Kategorie enthalten, werden sie anhand der folgenden Regeln ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="ba0da-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
-   <span data-ttu-id="ba0da-106">Die arithmetischen Operatoren und Verkettungsoperatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben, und alle haben Vorrang vor den Vergleichsoperatoren, logische und bitweise Operatoren.</span><span class="sxs-lookup"><span data-stu-id="ba0da-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
-   <span data-ttu-id="ba0da-107">Alle Vergleichsoperatoren haben denselben Rang und alle höheren Priorität als die logischen und bitweisen Operatoren, aber geringere Rangfolge als der arithmetischen Operatoren und Verkettungsoperatoren verfügen.</span><span class="sxs-lookup"><span data-stu-id="ba0da-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
-   <span data-ttu-id="ba0da-108">Die logischen und bitweisen Operatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben, und alle geringere Rangfolge als der Arithmetik, Verkettung und Vergleichsoperatoren haben.</span><span class="sxs-lookup"><span data-stu-id="ba0da-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
-   <span data-ttu-id="ba0da-109">Operatoren mit gleichem Rang werden links nach rechts ausgewertet in der Reihenfolge, in dem sie im Ausdruck angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ba0da-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="ba0da-110">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="ba0da-110">Precedence Order</span></span>  
 <span data-ttu-id="ba0da-111">Operatoren werden in der folgenden Rangfolge ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="ba0da-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="ba0da-112">Await-Operator</span><span class="sxs-lookup"><span data-stu-id="ba0da-112">Await Operator</span></span>  
 <span data-ttu-id="ba0da-113">Await-</span><span class="sxs-lookup"><span data-stu-id="ba0da-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="ba0da-114">Arithmetische Operatoren und Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="ba0da-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="ba0da-115">Potenzierung (`^`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="ba0da-116">Unäre Identität und Negation (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="ba0da-117">Multiplikation und Gleitkommadivision (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="ba0da-118">Ganzzahldivision (`\`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="ba0da-119">Modulo (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="ba0da-120">Addition und Subtraktion (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="ba0da-121">Verketten von Zeichenfolgen (`&`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="ba0da-122">Arithmetische bitverschiebung (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="ba0da-123">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="ba0da-123">Comparison Operators</span></span>  
 <span data-ttu-id="ba0da-124">Alle Vergleichsoperatoren (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="ba0da-125">Logische und bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="ba0da-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="ba0da-126">Negation (`Not`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="ba0da-127">Verbindung (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="ba0da-128">Inklusive Disjunktion (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="ba0da-129">Ausschließende Disjunktion (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="ba0da-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="ba0da-130">Kommentare</span><span class="sxs-lookup"><span data-stu-id="ba0da-130">Comments</span></span>  
 <span data-ttu-id="ba0da-131">Die `=` Operator wird nur der Gleichheitsvergleichsoperator, nicht der Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="ba0da-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="ba0da-132">Der Operator für zeichenfolgenverkettung (`&`) ist ein arithmetischer Operator, aber in der Rangfolge mit den arithmetischen Operatoren gruppieren.</span><span class="sxs-lookup"><span data-stu-id="ba0da-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="ba0da-133">Die `Is` und `IsNot` Operatoren sind, Referenz-Objektverweisvergleichsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="ba0da-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="ba0da-134">Nicht vergleichen sie die Werte von zwei Objekten; Sie überprüft nur, um festzustellen, ob zwei Objektvariablen auf die gleiche Objektinstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="ba0da-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="ba0da-135">Assoziativität</span><span class="sxs-lookup"><span data-stu-id="ba0da-135">Associativity</span></span>  
 <span data-ttu-id="ba0da-136">Wenn Operatoren mit gleichem Rang zusammen in einem Ausdruck, z. B. Multiplikations- und Divisionsaufgaben, angezeigt werden wertet der Compiler jeden Vorgang, wie sie von links nach rechts gefundenen.</span><span class="sxs-lookup"><span data-stu-id="ba0da-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="ba0da-137">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ba0da-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="ba0da-138">Der erste Ausdruck wertet die Division 96 / 8 (Vortäuschen 12), und klicken Sie dann die Division 12 / 4, was in drei führt.</span><span class="sxs-lookup"><span data-stu-id="ba0da-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="ba0da-139">Da der Compiler die Operationen für ergibt `n1` von links nach rechts, die Auswertung ist identisch, wenn diese Reihenfolge explizit angegeben wird, für die `n2`.</span><span class="sxs-lookup"><span data-stu-id="ba0da-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="ba0da-140">Beide `n1` und `n2` Ergebnis von drei haben.</span><span class="sxs-lookup"><span data-stu-id="ba0da-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="ba0da-141">Im Gegensatz dazu `n3` verfügt über ein Ergebnis von 48, da die Klammern den Compiler auszuwertende 8 zwingen / 4 erste.</span><span class="sxs-lookup"><span data-stu-id="ba0da-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="ba0da-142">Aufgrund dieses Verhaltens Operatoren gelten als *linksassoziativ* in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba0da-142">Because of this behavior, operators are said to be *left associative* in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="ba0da-143">Überschreiben von Rangfolge und Assoziativität</span><span class="sxs-lookup"><span data-stu-id="ba0da-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="ba0da-144">Sie können Klammern verwenden, erzwingen Sie einige Teile eines Ausdrucks vor anderen ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba0da-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="ba0da-145">Dadurch kann die Reihenfolge der Rangfolge und Assoziativität von links auf die überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ba0da-145">This can override both the order of precedence and the left associativity.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="ba0da-146">immer führt Vorgänge, die in Klammern vor den außerhalb eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="ba0da-146"> always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="ba0da-147">Verwaltet jedoch innerhalb der Klammern gewöhnliche Rangfolge und Assoziativität, es sei denn, Sie mithilfe von Klammern innerhalb der Klammern.</span><span class="sxs-lookup"><span data-stu-id="ba0da-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="ba0da-148">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ba0da-148">The following example illustrates this.</span></span>  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba0da-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba0da-149">See Also</span></span>  
 [<span data-ttu-id="ba0da-150">=-Operator</span><span class="sxs-lookup"><span data-stu-id="ba0da-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [<span data-ttu-id="ba0da-151">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="ba0da-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="ba0da-152">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="ba0da-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="ba0da-153">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="ba0da-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="ba0da-154">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="ba0da-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="ba0da-155">Await-Operator</span><span class="sxs-lookup"><span data-stu-id="ba0da-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)  
 [<span data-ttu-id="ba0da-156">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="ba0da-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="ba0da-157">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ba0da-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
