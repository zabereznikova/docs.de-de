---
title: Operatorrangfolge in Visual Basic | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- arithmetic operators, precedence
- operator precedence
- logical operators, precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators
- operators [Visual Basic], precedence
- precedence, of operators
- comparison operators, precedence
- math operators
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f653dd83c9778dddfe0e52db27065f7d73866e37
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="7815d-102">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7815d-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="7815d-103">Treten mehrere Operationen in einem Ausdruck, wird jeder Teil ausgewertet und aufgelöst, die in einer vorbestimmten Reihenfolge *Operatorrangfolge*.</span><span class="sxs-lookup"><span data-stu-id="7815d-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="7815d-104">Regeln</span><span class="sxs-lookup"><span data-stu-id="7815d-104">Precedence Rules</span></span>  
 <span data-ttu-id="7815d-105">Wenn Ausdrücke Operatoren aus mehreren Kategorien enthalten, werden sie gemäß den folgenden Regeln ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="7815d-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
-   <span data-ttu-id="7815d-106">Die arithmetischen Operatoren und Verkettungsoperatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben, und alle haben Vorrang vor den Vergleichsoperatoren, logische und bitweise Operatoren.</span><span class="sxs-lookup"><span data-stu-id="7815d-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
-   <span data-ttu-id="7815d-107">Alle Vergleichsoperatoren haben denselben Rang, und alle haben Vorrang vor den logischen und bitweisen Operatoren, sind jedoch die arithmetischen Operatoren und Verkettungsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="7815d-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
-   <span data-ttu-id="7815d-108">Die logischen und bitweisen Operatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben, und alle haben Vorrang vor den Arithmetik, Verkettung und Vergleichsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="7815d-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
-   <span data-ttu-id="7815d-109">Operatoren mit gleichem Rang links nach rechts ausgewertet werden in der Reihenfolge, in der sie im Ausdruck vorkommen.</span><span class="sxs-lookup"><span data-stu-id="7815d-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="7815d-110">Rangfolge</span><span class="sxs-lookup"><span data-stu-id="7815d-110">Precedence Order</span></span>  
 <span data-ttu-id="7815d-111">Operatoren werden in der folgenden Reihenfolge bewertet:</span><span class="sxs-lookup"><span data-stu-id="7815d-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="7815d-112">Await-Operator</span><span class="sxs-lookup"><span data-stu-id="7815d-112">Await Operator</span></span>  
 <span data-ttu-id="7815d-113">Await-</span><span class="sxs-lookup"><span data-stu-id="7815d-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="7815d-114">Arithmetische Operatoren und Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="7815d-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="7815d-115">Potenzierung (`^`)</span><span class="sxs-lookup"><span data-stu-id="7815d-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="7815d-116">Unäre Identität und Negation (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="7815d-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="7815d-117">Multiplikation und Gleitkommadivision (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="7815d-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="7815d-118">Division ganzer Zahlen (`\`)</span><span class="sxs-lookup"><span data-stu-id="7815d-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="7815d-119">Modulo-Arithmetik (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="7815d-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="7815d-120">Addition und Subtraktion (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="7815d-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="7815d-121">Verketten von Zeichenfolgen (`&`)</span><span class="sxs-lookup"><span data-stu-id="7815d-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="7815d-122">Bit-arithmetische Verschiebung (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="7815d-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="7815d-123">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="7815d-123">Comparison Operators</span></span>  
 <span data-ttu-id="7815d-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)</span><span class="sxs-lookup"><span data-stu-id="7815d-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="7815d-125">Logische und bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="7815d-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="7815d-126">Negation (`Not`)</span><span class="sxs-lookup"><span data-stu-id="7815d-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="7815d-127">Verbindung (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="7815d-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="7815d-128">Inklusive Disjunktion (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="7815d-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="7815d-129">Exklusive Disjunktion (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="7815d-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="7815d-130">Kommentare</span><span class="sxs-lookup"><span data-stu-id="7815d-130">Comments</span></span>  
 <span data-ttu-id="7815d-131">Die `=` -Operator ist nur der Gleichheitsvergleichsoperator, nicht der Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="7815d-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="7815d-132">Der Operator für zeichenfolgenverkettung (`&`) kein arithmetischer Operator, sondern in der Rangfolge mit arithmetischen Operatoren gruppieren.</span><span class="sxs-lookup"><span data-stu-id="7815d-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="7815d-133">Die `Is` und `IsNot` Operatoren sind Objektverweisvergleichsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="7815d-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="7815d-134">Nicht vergleichen sie die Werte von zwei Objekten; Sie überprüft nur, ob zwei Object-Variablen auf die gleiche Objektinstanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="7815d-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="7815d-135">Assoziativität</span><span class="sxs-lookup"><span data-stu-id="7815d-135">Associativity</span></span>  
 <span data-ttu-id="7815d-136">Wenn Operatoren mit gleichem Rang zusammen in einem Ausdruck, z. B. Multiplikation und Division, angezeigt werden wertet der Compiler jede Operation, wie sie von links nach rechts gefundenen.</span><span class="sxs-lookup"><span data-stu-id="7815d-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="7815d-137">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7815d-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="7815d-138">Der erste Ausdruck wertet die Division 96 / 8 (wodurch 12) und dann die Division 12 / 4, der drei führt.</span><span class="sxs-lookup"><span data-stu-id="7815d-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="7815d-139">Da der Compiler die Operationen für ergibt `n1` von links nach rechts, die Bewertung ist identisch, wenn diese Reihenfolge explizit angegeben wird, für die `n2`.</span><span class="sxs-lookup"><span data-stu-id="7815d-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="7815d-140">Beide `n1` und `n2` ergeben drei.</span><span class="sxs-lookup"><span data-stu-id="7815d-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="7815d-141">Im Gegensatz dazu `n3` hat ein Ergebnis 48, da die Klammern erzwingen die vom Compiler ausgewertet 8 / 4 erste.</span><span class="sxs-lookup"><span data-stu-id="7815d-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="7815d-142">Aufgrund dieses Verhaltens können Operatoren gelten als *linksassoziativ* in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="7815d-142">Because of this behavior, operators are said to be *left associative* in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="7815d-143">Überschreiben von Rangfolge und Assoziativität</span><span class="sxs-lookup"><span data-stu-id="7815d-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="7815d-144">Sie können Klammern verwenden, um einige Teile eines Ausdrucks vor anderen ausgewertet werden zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="7815d-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="7815d-145">Dadurch kann die Rangfolge und Assoziativität von links überschrieben.</span><span class="sxs-lookup"><span data-stu-id="7815d-145">This can override both the order of precedence and the left associativity.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7815d-146">Vorgänge, die in Klammern vor den außerhalb stehen durchgeführt immer.</span><span class="sxs-lookup"><span data-stu-id="7815d-146"> always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="7815d-147">Es verwaltet jedoch innerhalb der Klammern normale Rangfolge und Assoziativität, es sei denn, Sie Klammern innerhalb der Klammern verwenden.</span><span class="sxs-lookup"><span data-stu-id="7815d-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="7815d-148">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7815d-148">The following example illustrates this.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7815d-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7815d-149">See Also</span></span>  
 <span data-ttu-id="7815d-150">[=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="7815d-150">[= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) </span></span>  
<span data-ttu-id="7815d-151"> [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md) </span><span class="sxs-lookup"><span data-stu-id="7815d-151"> [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md) </span></span>  
<span data-ttu-id="7815d-152"> [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md) </span><span class="sxs-lookup"><span data-stu-id="7815d-152"> [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md) </span></span>  
<span data-ttu-id="7815d-153"> [LIKE-Operator](../../../visual-basic/language-reference/operators/like-operator.md) </span><span class="sxs-lookup"><span data-stu-id="7815d-153"> [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md) </span></span>  
<span data-ttu-id="7815d-154"> [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="7815d-154"> [TypeOf Operator](../../../visual-basic/language-reference/operators/typeof-operator.md) </span></span>  
<span data-ttu-id="7815d-155"> [Await-Operator](../../../visual-basic/language-reference/operators/await-operator.md) </span><span class="sxs-lookup"><span data-stu-id="7815d-155"> [Await Operator](../../../visual-basic/language-reference/operators/await-operator.md) </span></span>  
<span data-ttu-id="7815d-156"> [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="7815d-156"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="7815d-157"> [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)</span><span class="sxs-lookup"><span data-stu-id="7815d-157"> [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)</span></span>
