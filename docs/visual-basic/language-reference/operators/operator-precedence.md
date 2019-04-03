---
title: Operatorrangfolge in Visual Basic
ms.date: 07/20/2015
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
ms.openlocfilehash: 568927eb4759c214311ad34a5b45e28094dd80be
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830031"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="8cd71-102">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8cd71-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="8cd71-103">Treten mehrere Operationen in einem Ausdruck, wird jeder Teil ausgewertet und in einer vorbestimmten Reihenfolge aufgelöst *Operatorrangfolge*.</span><span class="sxs-lookup"><span data-stu-id="8cd71-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="8cd71-104">Regeln für die Berechnungsrangfolge</span><span class="sxs-lookup"><span data-stu-id="8cd71-104">Precedence Rules</span></span>  
 <span data-ttu-id="8cd71-105">Ausdrücke, Operatoren, die von mehr als einer Kategorie enthalten, werden sie gemäß den folgenden Regeln ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="8cd71-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
-   <span data-ttu-id="8cd71-106">Die arithmetischen Operatoren und Verkettungsoperatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben, und alle haben der Rangfolge höher eingestuft als die Vergleichsoperatoren, logische und bitweise Operatoren.</span><span class="sxs-lookup"><span data-stu-id="8cd71-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
-   <span data-ttu-id="8cd71-107">Alle Vergleichsoperatoren haben denselben Rang, und alles, was der Rangfolge höher eingestuft als die logischen und bitweisen Operatoren, jedoch geringere Rangfolge als der arithmetischen Operatoren und Verkettungsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="8cd71-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
-   <span data-ttu-id="8cd71-108">Die logischen und bitweisen Operatoren die Reihenfolge der Rangfolge, die im folgenden Abschnitt beschrieben, und alle niedrigeren Rangfolge als der arithmetische, Verkettung und Vergleichsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="8cd71-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
-   <span data-ttu-id="8cd71-109">Operatoren mit gleichem Rang werden links nach rechts ausgewertet in der Reihenfolge, in der sie den Ausdruck angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8cd71-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="8cd71-110">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="8cd71-110">Precedence Order</span></span>  
 <span data-ttu-id="8cd71-111">Operatoren werden in der folgenden Rangfolge ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="8cd71-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="8cd71-112">Await-Operator</span><span class="sxs-lookup"><span data-stu-id="8cd71-112">Await Operator</span></span>  
 <span data-ttu-id="8cd71-113">Await-</span><span class="sxs-lookup"><span data-stu-id="8cd71-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="8cd71-114">Arithmetische Operatoren und Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="8cd71-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="8cd71-115">Potenzierung (`^`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="8cd71-116">Unäre Identität und Negation (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="8cd71-117">Multiplikation und Gleitkommadivision (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="8cd71-118">Division ganzer Zahlen (`\`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="8cd71-119">Arithmetischer Modulo (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="8cd71-120">Addition und Subtraktion (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="8cd71-121">Verketten von Zeichenfolgen (`&`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="8cd71-122">Arithmetische-Bit-Verschiebung (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="8cd71-123">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="8cd71-123">Comparison Operators</span></span>  
 <span data-ttu-id="8cd71-124">Alle Vergleichsoperatoren (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="8cd71-125">Logische und bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="8cd71-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="8cd71-126">Negation (`Not`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="8cd71-127">Verbindung (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="8cd71-128">Inklusive Disjunktion (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="8cd71-129">Exklusive Disjunktion (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="8cd71-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="8cd71-130">Kommentare</span><span class="sxs-lookup"><span data-stu-id="8cd71-130">Comments</span></span>  
 <span data-ttu-id="8cd71-131">Die `=` Operator wird nur der Gleichheitsvergleichsoperator, nicht der Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="8cd71-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="8cd71-132">Der Operator für zeichenfolgenverkettung (`&`) kein arithmetischer Operator, sondern in der Rangfolge mit den arithmetischen Operatoren gruppieren.</span><span class="sxs-lookup"><span data-stu-id="8cd71-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="8cd71-133">Die `Is` und `IsNot` Operatoren sind die Vergleichsoperatoren für Objekt-Verweis.</span><span class="sxs-lookup"><span data-stu-id="8cd71-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="8cd71-134">Sie führen nicht die Werte von zwei Objekten Vergleich. Sie überprüfen, nur um zu bestimmen, ob zwei Objektvariablen auf die gleiche Objektinstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="8cd71-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="8cd71-135">Assoziativität</span><span class="sxs-lookup"><span data-stu-id="8cd71-135">Associativity</span></span>  
 <span data-ttu-id="8cd71-136">Wenn Operatoren mit gleichem Rang zusammen in einem Ausdruck, z. B. die Multiplikations- und Divisionsaufgaben, angezeigt werden wertet der Compiler jeder Vorgang, wie sie von links nach rechts gefundenen.</span><span class="sxs-lookup"><span data-stu-id="8cd71-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="8cd71-137">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8cd71-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="8cd71-138">Der erste Ausdruck wertet die Division 96 / 8 (wodurch 12), und klicken Sie dann die Division 12 / 4, die in drei führt.</span><span class="sxs-lookup"><span data-stu-id="8cd71-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="8cd71-139">Da der Compiler die Vorgänge für wertet `n1` von links nach rechts, die Auswertung ist identisch, wenn diese Reihenfolge explizit angegeben wird, für die `n2`.</span><span class="sxs-lookup"><span data-stu-id="8cd71-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="8cd71-140">Beide `n1` und `n2` Ergebnis 3 haben.</span><span class="sxs-lookup"><span data-stu-id="8cd71-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="8cd71-141">Im Gegensatz dazu `n3` ein Ergebnis 48, hat, da die Klammern erzwingen, den Compiler zum Auswerten von 8 dass / 4 ersten.</span><span class="sxs-lookup"><span data-stu-id="8cd71-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="8cd71-142">Aufgrund dieses Verhaltens der Operatoren gelten als *linksassoziativ* in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8cd71-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="8cd71-143">Überschreiben der Rangfolge und Assoziativität</span><span class="sxs-lookup"><span data-stu-id="8cd71-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="8cd71-144">Sie können mithilfe von Klammern zu erzwingen, dass einige Teile eines Ausdrucks vor anderen ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8cd71-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="8cd71-145">Dadurch kann sowohl die Reihenfolge der Rangfolge und Assoziativität von links auf die überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8cd71-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="8cd71-146">Visual Basic führt immer Vorgänge, die in Klammern vor den außerhalb eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="8cd71-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="8cd71-147">Es verwaltet jedoch innerhalb der Klammern normale Rangfolge und Assoziativität, es sei denn, Sie mithilfe von Klammern innerhalb der Klammern.</span><span class="sxs-lookup"><span data-stu-id="8cd71-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="8cd71-148">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8cd71-148">The following example illustrates this.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8cd71-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cd71-149">See also</span></span>

- [<span data-ttu-id="8cd71-150">=-Operator</span><span class="sxs-lookup"><span data-stu-id="8cd71-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="8cd71-151">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="8cd71-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="8cd71-152">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="8cd71-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="8cd71-153">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="8cd71-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="8cd71-154">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="8cd71-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="8cd71-155">Await-Operator</span><span class="sxs-lookup"><span data-stu-id="8cd71-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="8cd71-156">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="8cd71-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="8cd71-157">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8cd71-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
