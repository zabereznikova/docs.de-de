---
title: Operatoren – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 551d4cd8bf26a1c1caf3cbf611d9f338ae2581be
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2019
ms.locfileid: "67609506"
---
# <a name="operators-c-programming-guide"></a><span data-ttu-id="2237f-102">Operatoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2237f-102">Operators (C# Programming Guide)</span></span>

<span data-ttu-id="2237f-103">In C# ist ein *Operator* ein Programmelement, das auf einen oder mehrere *Operanden* in einem Ausdruck oder einer Anweisung angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2237f-103">In C#, an *operator* is a program element that is applied to one or more *operands* in an expression or statement.</span></span> <span data-ttu-id="2237f-104">Operatoren mit einem Operanden, z. B. der Inkrementoperator (`++`) oder `new`, werden als *unäre* Operatoren bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2237f-104">Operators that take one operand, such as the increment operator (`++`) or `new`, are referred to as *unary* operators.</span></span> <span data-ttu-id="2237f-105">Operatoren mit zwei Operanden, z. B. arithmetische Operatoren (`+`,`-`,`*`,`/`), werden als *binäre* Operatoren bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2237f-105">Operators that take two operands, such as arithmetic operators (`+`,`-`,`*`,`/`), are referred to as *binary* operators.</span></span> <span data-ttu-id="2237f-106">Der bedingte Operator (`?:`) verfügt über drei Operanden. Er ist der einzige ternäre Operator in C#.</span><span class="sxs-lookup"><span data-stu-id="2237f-106">One operator, the conditional operator (`?:`), takes three operands and is the sole ternary operator in C#.</span></span>  
  
 <span data-ttu-id="2237f-107">Die folgende C#-Anweisung enthält einen einzelnen unären Operator und einen einzigen Operanden.</span><span class="sxs-lookup"><span data-stu-id="2237f-107">The following C# statement contains a single unary operator and a single operand.</span></span> <span data-ttu-id="2237f-108">Der Inkrementoperator `++`ändert den Wert des Operanden `y`.</span><span class="sxs-lookup"><span data-stu-id="2237f-108">The increment operator, `++`, modifies the value of the operand `y`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 <span data-ttu-id="2237f-109">Die folgende C#-Anweisung enthält zwei binäre Operatoren mit jeweils zwei Operanden.</span><span class="sxs-lookup"><span data-stu-id="2237f-109">The following C# statement contains two binary operators, each with two operands.</span></span> <span data-ttu-id="2237f-110">Die Operanden des Zuweisungsoperators `=`sind die ganzzahlige Variable `y` und der Ausdruck `2 + 3` .</span><span class="sxs-lookup"><span data-stu-id="2237f-110">The assignment operator, `=`, has the integer variable `y` and the expression `2 + 3` as operands.</span></span> <span data-ttu-id="2237f-111">Der Ausdruck `2 + 3` selbst besteht aus dem Additionsoperator und zwei Operanden: `2` und `3`.</span><span class="sxs-lookup"><span data-stu-id="2237f-111">The expression `2 + 3` itself consists of the addition operator and two operands, `2` and `3`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
<span data-ttu-id="2237f-112">Ein Operand kann ein gültiger Ausdruck sein, der aus beliebig langem Code zusammengesetzt ist, und kann eine beliebige Anzahl von Unterausdrücken enthalten.</span><span class="sxs-lookup"><span data-stu-id="2237f-112">An operand can be a valid expression that is composed of any length of code, and it can comprise any number of sub expressions.</span></span> <span data-ttu-id="2237f-113">In einem Ausdruck mit mehreren Operatoren wird die Reihenfolge, in der die Operatoren angewendet werden, von der *Operatorrangfolge*, der *Assoziativität*und von Klammern bestimmt.</span><span class="sxs-lookup"><span data-stu-id="2237f-113">In an expression that contains multiple operators, the order in which the operators are applied is determined by *operator precedence*, *associativity*, and parentheses.</span></span>  

## <a name="operator-precedence"></a><span data-ttu-id="2237f-114">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="2237f-114">Operator precedence</span></span>
  
<span data-ttu-id="2237f-115">Jeder Operator verfügt über einen definierten Vorrang.</span><span class="sxs-lookup"><span data-stu-id="2237f-115">Each operator has a defined precedence.</span></span> <span data-ttu-id="2237f-116">In einem Ausdruck, der mehrere Operatoren mit verschiedenen Rangfolgenebenen enthält, bestimmt die Rangfolge der Operatoren die Reihenfolge, in der die Operatoren ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="2237f-116">In an expression that contains multiple operators that have different precedence levels, the precedence of the operators determines the order in which the operators are evaluated.</span></span> <span data-ttu-id="2237f-117">Beispielsweise weist die folgende Anweisung `n1` 3 zu:</span><span class="sxs-lookup"><span data-stu-id="2237f-117">For example, the following statement assigns 3 to `n1`:</span></span>

```csharp
n1 = 11 - 2 * 4;
```

<span data-ttu-id="2237f-118">Die Multiplikation wird zuerst ausgeführt, da Multiplikation Vorrang vor Subtraktion enthält.</span><span class="sxs-lookup"><span data-stu-id="2237f-118">The multiplication is executed first because multiplication takes precedence over subtraction.</span></span>

<span data-ttu-id="2237f-119">Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie unter [C#-Operatoren](../../language-reference/operators/index.md).</span><span class="sxs-lookup"><span data-stu-id="2237f-119">For the complete list of C# operators ordered by precedence level, see [C# operators](../../language-reference/operators/index.md).</span></span>
  
## <a name="associativity"></a><span data-ttu-id="2237f-120">Assoziativität</span><span class="sxs-lookup"><span data-stu-id="2237f-120">Associativity</span></span>

 <span data-ttu-id="2237f-121">Wenn ein Ausdruck zwei oder mehr Operatoren mit demselben Rang enthält, wird die Auswertungsreihenfolge anhand des Assoziativitätsgesetzes festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2237f-121">When two or more operators that have the same precedence are present in an expression, they are evaluated based on associativity.</span></span> <span data-ttu-id="2237f-122">Linksassoziative Operatoren werden von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2237f-122">Left-associative operators are evaluated in order from left to right.</span></span> <span data-ttu-id="2237f-123">`x * y / z` wird beispielsweise als `(x * y) / z`ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2237f-123">For example, `x * y / z` is evaluated as `(x * y) / z`.</span></span> <span data-ttu-id="2237f-124">Rechtsassoziative Operatoren werden von rechts nach links ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2237f-124">Right-associative operators are evaluated in order from right to left.</span></span> <span data-ttu-id="2237f-125">Beispielsweise ist der Zuweisungsoperator rechtsassoziativ.</span><span class="sxs-lookup"><span data-stu-id="2237f-125">For example, the assignment operator is right associative.</span></span> <span data-ttu-id="2237f-126">Falls nicht, würde der folgende Code zu einem Fehler führen.</span><span class="sxs-lookup"><span data-stu-id="2237f-126">If it were not, the following code would result in an error.</span></span>  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 <span data-ttu-id="2237f-127">Ein weiteres Beispiel für einen rechtsassoziativen Operator ist der ternäre Operator ([?:](../../../csharp/language-reference/operators/conditional-operator.md)).</span><span class="sxs-lookup"><span data-stu-id="2237f-127">As another example the ternary operator ([?:](../../../csharp/language-reference/operators/conditional-operator.md)) is right associative.</span></span> <span data-ttu-id="2237f-128">Die meisten binäre Operatoren sind linksassoziativ.</span><span class="sxs-lookup"><span data-stu-id="2237f-128">Most binary operators are left associative.</span></span>  
  
 <span data-ttu-id="2237f-129">Unabhängig davon, ob Operatoren in einem Ausdruck linksassoziativ oder rechtsassoziativ sind, werden zuerst die Operanden aller Ausdrücke von links nach rechts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2237f-129">Whether the operators in an expression are left associative or right associative, the operands of each expression are evaluated first, from left to right.</span></span> <span data-ttu-id="2237f-130">Die folgenden Beispiele veranschaulichen die Auswertungsreihenfolge von Operatoren und Operanden.</span><span class="sxs-lookup"><span data-stu-id="2237f-130">The following examples illustrate the order of evaluation of operators and operands.</span></span>  
  
|<span data-ttu-id="2237f-131">Anweisung</span><span class="sxs-lookup"><span data-stu-id="2237f-131">Statement</span></span>|<span data-ttu-id="2237f-132">Reihenfolge der Auswertung</span><span class="sxs-lookup"><span data-stu-id="2237f-132">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = b`|<span data-ttu-id="2237f-133">a, b, =</span><span class="sxs-lookup"><span data-stu-id="2237f-133">a, b, =</span></span>|  
|`a = b + c`|<span data-ttu-id="2237f-134">a, b, c, +, =</span><span class="sxs-lookup"><span data-stu-id="2237f-134">a, b, c, +, =</span></span>|  
|`a = b + c * d`|<span data-ttu-id="2237f-135">a, b, c, d, \*, +, =</span><span class="sxs-lookup"><span data-stu-id="2237f-135">a, b, c, d, \*, +, =</span></span>|  
|`a = b * c + d`|<span data-ttu-id="2237f-136">a, b, c, \*, d, +, =</span><span class="sxs-lookup"><span data-stu-id="2237f-136">a, b, c, \*, d, +, =</span></span>|  
|`a = b - c + d`|<span data-ttu-id="2237f-137">a, b, c, -, d, +, =</span><span class="sxs-lookup"><span data-stu-id="2237f-137">a, b, c, -, d, +, =</span></span>|  
|`a += b -= c`|<span data-ttu-id="2237f-138">a, b, c, -=, +=</span><span class="sxs-lookup"><span data-stu-id="2237f-138">a, b, c, -=, +=</span></span>|  
  
## <a name="adding-parentheses"></a><span data-ttu-id="2237f-139">Hinzufügen von Klammern</span><span class="sxs-lookup"><span data-stu-id="2237f-139">Adding parentheses</span></span>

 <span data-ttu-id="2237f-140">Sie können die Reihenfolge ändern, die von Operatorenrangfolge und Assoziativität festgelegt wird, indem Sie Klammern verwenden.</span><span class="sxs-lookup"><span data-stu-id="2237f-140">You can change the order imposed by operator precedence and associativity by using parentheses.</span></span> <span data-ttu-id="2237f-141">Beispielsweise wird `2 + 3 * 2` gewöhnlich als 8 ausgewertet, da Multiplikationsoperatoren Vorrang gegenüber additiven Operatoren besitzen.</span><span class="sxs-lookup"><span data-stu-id="2237f-141">For example, `2 + 3 * 2` ordinarily evaluates to 8, because multiplicative operators take precedence over additive operators.</span></span> <span data-ttu-id="2237f-142">Wenn Sie jedoch den Ausdruck als `(2 + 3) * 2`schreiben, wird die Addition vor der Multiplikation ausgewertet, und das Ergebnis ist 10.</span><span class="sxs-lookup"><span data-stu-id="2237f-142">However, if you write the expression as `(2 + 3) * 2`, the addition is evaluated before the multiplication, and the result is 10.</span></span> <span data-ttu-id="2237f-143">Die folgenden Beispiele veranschaulichen die Auswertungsreihenfolge der in Klammern gesetzten Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="2237f-143">The following examples illustrate the order of evaluation in parenthesized expressions.</span></span> <span data-ttu-id="2237f-144">Wie in den vorherigen Beispielen werden die Operanden ausgewertet, bevor der Operator angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2237f-144">As in previous examples, the operands are evaluated before the operator is applied.</span></span>  
  
|<span data-ttu-id="2237f-145">Anweisung</span><span class="sxs-lookup"><span data-stu-id="2237f-145">Statement</span></span>|<span data-ttu-id="2237f-146">Reihenfolge der Auswertung</span><span class="sxs-lookup"><span data-stu-id="2237f-146">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = (b + c) * d`|<span data-ttu-id="2237f-147">a, b, c, +, d, \*, =</span><span class="sxs-lookup"><span data-stu-id="2237f-147">a, b, c, +, d, \*, =</span></span>|  
|`a = b - (c + d)`|<span data-ttu-id="2237f-148">a, b, c, d, +, -, =</span><span class="sxs-lookup"><span data-stu-id="2237f-148">a, b, c, d, +, -, =</span></span>|  
|`a = (b + c) * (d - e)`|<span data-ttu-id="2237f-149">a, b, c, +, d, e, -, \*, =</span><span class="sxs-lookup"><span data-stu-id="2237f-149">a, b, c, +, d, e, -, \*, =</span></span>|  
  
## <a name="operator-overloading"></a><span data-ttu-id="2237f-150">Überladen von Operatoren</span><span class="sxs-lookup"><span data-stu-id="2237f-150">Operator overloading</span></span>

<span data-ttu-id="2237f-151">Sie können das Verhalten bestimmter Operatoren für benutzerdefinierte Klassen und Strukturen definieren.</span><span class="sxs-lookup"><span data-stu-id="2237f-151">You can define the behavior of certain operators for custom classes and structs.</span></span> <span data-ttu-id="2237f-152">Dieser Prozess wird als *Operatorüberladung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2237f-152">This process is referred to as *operator overloading*.</span></span> <span data-ttu-id="2237f-153">Weitere Informationen finden Sie unter [Operatorüberladung](../../language-reference/operators/operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="2237f-153">For more information, see [Operator overloading](../../language-reference/operators/operator-overloading.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2237f-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2237f-154">See also</span></span>

- [<span data-ttu-id="2237f-155">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2237f-155">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2237f-156">Anweisungen, Ausdrücke und Operatoren</span><span class="sxs-lookup"><span data-stu-id="2237f-156">Statements, Expressions, and Operators</span></span>](index.md)
- [<span data-ttu-id="2237f-157">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="2237f-157">C# Operators</span></span>](../../language-reference/operators/index.md)
