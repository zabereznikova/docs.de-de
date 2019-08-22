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
ms.openlocfilehash: df40aced45442c9c7895c8d10ece64b21e292508
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659930"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="f461d-102">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f461d-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="f461d-103">Wenn mehrere Vorgänge in einem Ausdruck auftreten, wird jeder Teil in einer vordefinierten Reihenfolge ausgewertet und aufgelöst, die als *Operator Rangfolge*bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="f461d-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>

## <a name="precedence-rules"></a><span data-ttu-id="f461d-104">Rang Folge Regeln</span><span class="sxs-lookup"><span data-stu-id="f461d-104">Precedence Rules</span></span>
 <span data-ttu-id="f461d-105">Wenn Ausdrücke Operatoren aus mehr als einer Kategorie enthalten, werden Sie gemäß den folgenden Regeln ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="f461d-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>

- <span data-ttu-id="f461d-106">Der arithmetische und der Verkettungs Operator haben die Rangfolge, die im folgenden Abschnitt beschrieben wird, und alle haben Vorrang vor den Vergleichs-, logischen und bitweisen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="f461d-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>

- <span data-ttu-id="f461d-107">Alle Vergleichs Operatoren weisen die gleiche Rangfolge auf und haben Vorrang vor den logischen und bitweisen Operatoren, aber eine niedrigere Rangfolge als die arithmetischen Operatoren und die Verkettungs Operatoren.</span><span class="sxs-lookup"><span data-stu-id="f461d-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>

- <span data-ttu-id="f461d-108">Die logischen und bitweisen Operatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben wird, und alle haben Vorrang vor den Operatoren arithmetischer, Verkettungs-und Vergleichs Operatoren.</span><span class="sxs-lookup"><span data-stu-id="f461d-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>

- <span data-ttu-id="f461d-109">Operatoren mit gleicher Rangfolge werden in der Reihenfolge, in der Sie im Ausdruck angezeigt werden, von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f461d-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>

## <a name="precedence-order"></a><span data-ttu-id="f461d-110">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="f461d-110">Precedence Order</span></span>
 <span data-ttu-id="f461d-111">Operatoren werden in der folgenden Rangfolge ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="f461d-111">Operators are evaluated in the following order of precedence:</span></span>

### <a name="await-operator"></a><span data-ttu-id="f461d-112">Await-Operator</span><span class="sxs-lookup"><span data-stu-id="f461d-112">Await Operator</span></span>
 <span data-ttu-id="f461d-113">Await-</span><span class="sxs-lookup"><span data-stu-id="f461d-113">Await</span></span>

### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="f461d-114">Arithmetische Operatoren und Verkettungs Operatoren</span><span class="sxs-lookup"><span data-stu-id="f461d-114">Arithmetic and Concatenation Operators</span></span>
 <span data-ttu-id="f461d-115">Exponentiierung (`^`)</span><span class="sxs-lookup"><span data-stu-id="f461d-115">Exponentiation (`^`)</span></span>

 <span data-ttu-id="f461d-116">Unäre Identität und Negation (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="f461d-116">Unary identity and negation (`+`, `–`)</span></span>

 <span data-ttu-id="f461d-117">Multiplikation und Gleit Komma Division (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="f461d-117">Multiplication and floating-point division (`*`, `/`)</span></span>

 <span data-ttu-id="f461d-118">Ganzzahlige`\`Division ()</span><span class="sxs-lookup"><span data-stu-id="f461d-118">Integer division (`\`)</span></span>

 <span data-ttu-id="f461d-119">Modulare Arithmetik`Mod`()</span><span class="sxs-lookup"><span data-stu-id="f461d-119">Modular arithmetic (`Mod`)</span></span>

 <span data-ttu-id="f461d-120">Addition und Subtraktion (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="f461d-120">Addition and subtraction (`+`, `–`)</span></span>

 <span data-ttu-id="f461d-121">Zeichen folgen Verkettung (`&`)</span><span class="sxs-lookup"><span data-stu-id="f461d-121">String concatenation (`&`)</span></span>

 <span data-ttu-id="f461d-122">Arithmetische Bitverschiebung`<<`( `>>`,)</span><span class="sxs-lookup"><span data-stu-id="f461d-122">Arithmetic bit shift (`<<`, `>>`)</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="f461d-123">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="f461d-123">Comparison Operators</span></span>
 <span data-ttu-id="f461d-124">Alle Vergleichs Operatoren`=`( `<>`, `<`, `<=`, `>`,, `>=`, ,`IsNot`,, ..`TypeOf`. `Is` `Like` `Is`)</span><span class="sxs-lookup"><span data-stu-id="f461d-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>

### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="f461d-125">Logische und bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="f461d-125">Logical and Bitwise Operators</span></span>
 <span data-ttu-id="f461d-126">Negation (`Not`)</span><span class="sxs-lookup"><span data-stu-id="f461d-126">Negation (`Not`)</span></span>

 <span data-ttu-id="f461d-127">Verbindung (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="f461d-127">Conjunction (`And`, `AndAlso`)</span></span>

 <span data-ttu-id="f461d-128">Inklusive Disjunktion`Or`( `OrElse`,)</span><span class="sxs-lookup"><span data-stu-id="f461d-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>

 <span data-ttu-id="f461d-129">Exklusive Disjunktion`Xor`()</span><span class="sxs-lookup"><span data-stu-id="f461d-129">Exclusive disjunction (`Xor`)</span></span>

### <a name="comments"></a><span data-ttu-id="f461d-130">Kommentare</span><span class="sxs-lookup"><span data-stu-id="f461d-130">Comments</span></span>
 <span data-ttu-id="f461d-131">Der `=` Operator ist nur der Gleichheits Vergleichs Operator, nicht der Zuweisungs Operator.</span><span class="sxs-lookup"><span data-stu-id="f461d-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>

 <span data-ttu-id="f461d-132">Der Operator für die Zeichen folgen Verkettung (`&`) ist kein arithmetischer Operator, aber in der Rangfolge ist er mit den arithmetischen Operatoren gruppiert.</span><span class="sxs-lookup"><span data-stu-id="f461d-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>

 <span data-ttu-id="f461d-133">Die `Is` Operatoren und `IsNot` sind objektverweisvergleichs-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="f461d-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="f461d-134">Die Werte von zwei Objekten werden nicht verglichen. Sie überprüfen lediglich, ob zwei Objektvariablen auf dieselbe Objektinstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="f461d-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>

## <a name="associativity"></a><span data-ttu-id="f461d-135">Assoziativität</span><span class="sxs-lookup"><span data-stu-id="f461d-135">Associativity</span></span>
 <span data-ttu-id="f461d-136">Wenn Operatoren mit gleicher Rangfolge in einem Ausdruck angezeigt werden, z. b. Multiplikation und Division, wertet der Compiler jeden Vorgang aus, der von links nach rechts erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="f461d-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="f461d-137">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f461d-137">The following example illustrates this.</span></span>

```vb
Dim n1 As Integer = 96 / 8 / 4
Dim n2 As Integer = (96 / 8) / 4
Dim n3 As Integer = 96 / (8 / 4)
```

 <span data-ttu-id="f461d-138">Der erste Ausdruck wertet die Division 96/8 aus (die sich in 12 ergibt) und dann die Division 12/4, die drei ergibt.</span><span class="sxs-lookup"><span data-stu-id="f461d-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="f461d-139">Da der Compiler die Vorgänge für `n1` von links nach rechts auswertet, ist die Auswertung identisch, wenn diese Reihenfolge explizit für `n2`angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f461d-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="f461d-140">Sowohl `n1` als `n2` auch haben drei Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="f461d-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="f461d-141">Im Gegensatz dazu `n3` hat das Ergebnis 48, da die Klammern den Compiler zwingen, zuerst 8/4 auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="f461d-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>

 <span data-ttu-id="f461d-142">Aufgrund dieses Verhaltens werden Operatoren als *links assoziativ* in Visual Basic bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f461d-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>

## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="f461d-143">Überschreiben von Rangfolge und Assoziativität</span><span class="sxs-lookup"><span data-stu-id="f461d-143">Overriding Precedence and Associativity</span></span>
 <span data-ttu-id="f461d-144">Sie können Klammern verwenden, um zu erzwingen, dass einige Teile eines Ausdrucks vor anderen ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="f461d-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="f461d-145">Dies kann die Reihenfolge der Rangfolge und die linke Assoziativität überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f461d-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="f461d-146">Visual Basic führt immer Vorgänge aus, die in Klammern eingeschlossen werden, bevor Sie außerhalb von stehen.</span><span class="sxs-lookup"><span data-stu-id="f461d-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="f461d-147">Innerhalb von Klammern behält sie jedoch die normale Rangfolge und Assoziativität bei, es sei denn, Sie verwenden Klammern innerhalb der Klammern.</span><span class="sxs-lookup"><span data-stu-id="f461d-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="f461d-148">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f461d-148">The following example illustrates this.</span></span>

```vb
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

## <a name="see-also"></a><span data-ttu-id="f461d-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f461d-149">See also</span></span>

- [<span data-ttu-id="f461d-150">=-Operator</span><span class="sxs-lookup"><span data-stu-id="f461d-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="f461d-151">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="f461d-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="f461d-152">IsNot-Operator</span><span class="sxs-lookup"><span data-stu-id="f461d-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="f461d-153">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="f461d-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="f461d-154">TypeOf-Operator</span><span class="sxs-lookup"><span data-stu-id="f461d-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="f461d-155">Await-Operator</span><span class="sxs-lookup"><span data-stu-id="f461d-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="f461d-156">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="f461d-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f461d-157">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="f461d-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
