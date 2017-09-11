---
title: "Schlüsselwort „switch“ (C#-Referenz)"
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- switch_CSharpKeyword
- switch
- case
- case_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- switch statement [C#]
- switch keyword [C#]
- case statement [C#]
- default keyword [C#]
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
caps.latest.revision: 47
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 387c8c7e44ab818ca97e686330746f50df091bb9
ms.openlocfilehash: 5c151e3bbd46212f1234d46ff05d389f2384ca0e
ms.contentlocale: de-de
ms.lasthandoff: 08/01/2017

---
# <a name="switch-c-reference"></a><span data-ttu-id="45097-102">switch (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="45097-102">switch (C# Reference)</span></span>
<span data-ttu-id="45097-103">`switch` ist eine Auswahlanweisung, die einen einzelnen *switch-Abschnitt* zum Ausführen aus einer Liste von Kandidaten auswählt, die auf einem Mustertreffer mit dem *Vergleichsausdruck* basiert.</span><span class="sxs-lookup"><span data-stu-id="45097-103">`switch` is a selection statement that chooses a single *switch section* to execute from a list of candidates based on a pattern match with the *match expression*.</span></span> 
  
 <span data-ttu-id="45097-104">[!code-cs[switch#1](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="45097-104">[!code-cs[switch#1](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]</span></span>  

<span data-ttu-id="45097-105">Die Anweisung `switch` wird häufig als Alternative zu einem [if-else](if-else.md)-Konstrukt verwendet, wenn ein einzelner Ausdruck mit drei oder mehr Bedingungen getestet wird.</span><span class="sxs-lookup"><span data-stu-id="45097-105">The `switch` statement is often used as an alternative to an [if-else](if-else.md) construct if a single expression is tested against three or more conditions.</span></span> <span data-ttu-id="45097-106">Die folgende Anweisung `switch` bestimmt z.B., ob eine Variable des Typs `Color` einen von drei Werten hat:</span><span class="sxs-lookup"><span data-stu-id="45097-106">For example, the following `switch` statement determines whether a variable of type `Color` has one of three values:</span></span> 

<span data-ttu-id="45097-107">[!code-cs[switch#3](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="45097-107">[!code-cs[switch#3](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)]</span></span> 

<span data-ttu-id="45097-108">Dies entspricht dem folgenden Beispiel, das ein `if`-`else`-Konstrukt verwendet.</span><span class="sxs-lookup"><span data-stu-id="45097-108">It is equivalent to the following example that uses an `if`-`else` construct.</span></span> 

<span data-ttu-id="45097-109">[!code-cs[switch#3a](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="45097-109">[!code-cs[switch#3a](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)]</span></span> 

## <a name="the-match-expression"></a><span data-ttu-id="45097-110">Der Vergleichsausdruck</span><span class="sxs-lookup"><span data-stu-id="45097-110">The match expression</span></span>

<span data-ttu-id="45097-111">Der Vergleichsausdruck stellt den Wert bereit, mit dem die Muster in den Bezeichnungen `case` verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="45097-111">The match expression provides the value to match against the patterns in `case` labels.</span></span> <span data-ttu-id="45097-112">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="45097-112">Its syntax is:</span></span>

```csharp
   switch (expr)
```

<span data-ttu-id="45097-113">In C# 6 muss der Vergleichsausdruck ein Ausdruck sein, der einen Wert der folgenden Typen zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="45097-113">In C# 6, the match expression must be an expression that returns a value of the following types:</span></span>

- <span data-ttu-id="45097-114">Ein [char](char.md)</span><span class="sxs-lookup"><span data-stu-id="45097-114">a [char](char.md).</span></span>
- <span data-ttu-id="45097-115">Eine [Zeichenfolge](string.md)</span><span class="sxs-lookup"><span data-stu-id="45097-115">a [string](string.md).</span></span>
- <span data-ttu-id="45097-116">Ein [bool](bool.md)</span><span class="sxs-lookup"><span data-stu-id="45097-116">a [bool](bool.md).</span></span> 
- <span data-ttu-id="45097-117">Ein ganzzahliger Wert wie [int](int.md) oder [long](long.md)</span><span class="sxs-lookup"><span data-stu-id="45097-117">an integral value, such as an [int](int.md) or a [long](long.md).</span></span>
- <span data-ttu-id="45097-118">Ein [Enumerations](enum.md)wert</span><span class="sxs-lookup"><span data-stu-id="45097-118">an [enum](enum.md) value.</span></span>

<span data-ttu-id="45097-119">Ab C# 7 kann der Vergleichsausdruck jeder Ausdruck sein, der nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="45097-119">Starting with C# 7, the match expression can be any non-null expression.</span></span>
 
## <a name="the-switch-section"></a><span data-ttu-id="45097-120">Der switch-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="45097-120">The switch section</span></span>
 
 <span data-ttu-id="45097-121">Eine `switch`-Anweisung enthält eine oder mehrere switch-Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="45097-121">A `switch` statement includes one or more switch sections.</span></span> <span data-ttu-id="45097-122">Jeder switch-Abschnitt enthält eine oder mehrere *case-Bezeichnungen* und eine Liste mit mindestens einer Anweisung.</span><span class="sxs-lookup"><span data-stu-id="45097-122">Each switch section contains one or more *case labels* followed by one or more statements.</span></span> <span data-ttu-id="45097-123">Das folgende Beispiel zeigt eine einfache `switch`-Anweisung, die über drei switch-Abschnitte verfügt.</span><span class="sxs-lookup"><span data-stu-id="45097-123">The following example shows a simple `switch` statement that has three switch sections.</span></span> <span data-ttu-id="45097-124">Jeder switch-Abschnitt enthält eine case-Bezeichnung, z. B. `case 1:`, und zwei Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="45097-124">Each switch section has one case label, such as `case 1:`, and two statements.</span></span>
 
  <span data-ttu-id="45097-125">Eine `switch`-Anweisung kann eine beliebige Anzahl von switch-Abschnitten enthalten, und jeder Abschnitt kann eine oder mehrere case-Bezeichnungen haben, wie im folgend Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="45097-125">A `switch` statement can include any number of switch sections, and each section can have one or more case labels, as shown in the following example.</span></span> <span data-ttu-id="45097-126">Allerdings können zwei case-Bezeichnungen nicht denselben Ausdruck enthalten.</span><span class="sxs-lookup"><span data-stu-id="45097-126">However, no two case labels may contain the same expression.</span></span>  

 <span data-ttu-id="45097-127">[!code-cs[switch#2](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="45097-127">[!code-cs[switch#2](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]</span></span>  

 <span data-ttu-id="45097-128">Nur ein switch-Abschnitt einer switch-Anweisung wir ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="45097-128">Only one switch section in a switch statement executes.</span></span> <span data-ttu-id="45097-129">C# lässt nicht zu, dass die Ausführung von einem switch-Abschnitt zum nächsten fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="45097-129">C# does not allow execution to continue from one switch section to the next.</span></span> <span data-ttu-id="45097-130">Aus diesem Grund generiert der folgende Code den Compilerfehler CS0163: „Das Steuerelement kann nicht von einer case-Bezeichnung (<case label>) zur nächsten fortfahren.“</span><span class="sxs-lookup"><span data-stu-id="45097-130">Because of this, the following code generates a compiler error, CS0163: "Control cannot fall through from one case label (<case label>) to another."</span></span>   

```csharp  
switch (caseSwitch)  
{  
    // The following switch section causes an error.  
    case 1:  
        Console.WriteLine("Case 1...");  
        // Add a break or other jump statement here.  
    case 2:  
        Console.WriteLine("... and/or Case 2");  
        break;  
}  
```  
<span data-ttu-id="45097-131">Diese Anforderung wird normalerweise erfüllt, indem der switch-Abschnitt ausdrücklich durch Verwenden einer Anweisung [break](break.md), [goto](goto.md) oder [return](return.md) beendet wird.</span><span class="sxs-lookup"><span data-stu-id="45097-131">This requirement is usually met by explicitly exiting the switch section by using a [break](break.md), [goto](goto.md), or [return](return.md) statement.</span></span> <span data-ttu-id="45097-132">Der folgende Code ist jedoch auch gültig, da er sicherstellt, dass die Programmsteuerung nicht im switch-Abschnitt `default` fortfährt.</span><span class="sxs-lookup"><span data-stu-id="45097-132">However, the following code is also valid, because it ensures that program control cannot fall through to the `default` switch section.</span></span>
  
 <span data-ttu-id="45097-133">[!code-cs[switch#4](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="45097-133">[!code-cs[switch#4](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]</span></span>    
  
 <span data-ttu-id="45097-134">Die Ausführung der Anweisungsliste im switch-Abschnitt mit einer case-Bezeichnung, die den Vergleichsausdruck vergleicht, beginnt mit der ersten Anweisung und durchläuft in der Regel die Anweisungsliste, bis eine jump-Anweisung erreicht wird, z.B. `break`, `goto case`, `goto label`, `return` oder `throw`.</span><span class="sxs-lookup"><span data-stu-id="45097-134">Execution of the statement list in the switch section with a case label that matches the match expression begins with the first statement and proceeds through the statement list, typically until a jump statement, such as a `break`, `goto case`, `goto label`, `return`, or `throw`, is reached.</span></span> <span data-ttu-id="45097-135">An diesem Punkt wird die Steuerung der `switch`-Anweisung entzogen oder an eine andere case-Bezeichnung übertragen.</span><span class="sxs-lookup"><span data-stu-id="45097-135">At that point, control is transferred outside the `switch` statement or to another case label.</span></span> <span data-ttu-id="45097-136">Eine `goto`-Anweisung muss bei Nichtverwendung die Steuerung an eine konstante Bezeichnung übergeben.</span><span class="sxs-lookup"><span data-stu-id="45097-136">A `goto` statement, if it is used, must transfer control to a constant label.</span></span> <span data-ttu-id="45097-137">Diese Einschränkung ist notwendig, da der Versuch, die Steuerung an eine nicht konstante Bezeichnung zu übergeben, unerwünschte Nebeneffekte haben kann, z.B. kann die Steuerung an eine nicht beabsichtigte Position im Code übergeben werden, oder es kann eine Endlosschleife entstehen.</span><span class="sxs-lookup"><span data-stu-id="45097-137">This restriction is necessary, since attempting to transfer control to a non-constant label can have undesirable side-effects, such transferring control to an unintended location in code or creating an endless loop.</span></span>

## <a name="case-labels"></a><span data-ttu-id="45097-138">case-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="45097-138">Case labels</span></span>

 <span data-ttu-id="45097-139">Jede case-Bezeichnung gibt ein Muster an, mit dem der Vergleichsausdruck verglichen werden soll (die Variable `caseSwitch` in den vorherigen Beispielen).</span><span class="sxs-lookup"><span data-stu-id="45097-139">Each case label specifies a pattern to compare to the match expression (the `caseSwitch` variable in the previous examples).</span></span> <span data-ttu-id="45097-140">Wenn sie übereinstimmen, wird das Steuerelement an den switch-Abschnitt übertragen, der die **erste** übereinstimmende case-Bezeichnung enthält.</span><span class="sxs-lookup"><span data-stu-id="45097-140">If they match, control is transferred to the switch section that contains the **first** matching case label.</span></span> <span data-ttu-id="45097-141">Wenn keine case-Bezeichnung mit dem Vergleichsausdruck übereinstimmt, wird das Steuerelement an den Abschnitt mit der `default`-case-Bezeichnung übertragen, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="45097-141">If no case label pattern matches the match expression, control is transfered to the section with the `default` case label, if there is one.</span></span> <span data-ttu-id="45097-142">Wenn es kein `default`-case gibt, werden keine Anweisungen in jeglichen switch-Abschnitten ausgeführt, und ein Steuerelement wird außerhalb der `switch`-Anweisung übertragen.</span><span class="sxs-lookup"><span data-stu-id="45097-142">If there is no `default` case, no statements in any switch section are executed, and control is transferred outside the `switch` statement.</span></span>

 <span data-ttu-id="45097-143">Informationen zur `switch`-Anweisung und zum Musterabgleich finden Sie im Abschnitt [Musterabgleich mit der `switch`-Anweisung](#pattern).</span><span class="sxs-lookup"><span data-stu-id="45097-143">For information on the `switch` statement and pattern matching, see the [Pattern matching with the `switch` statement](#pattern) section.</span></span>

 <span data-ttu-id="45097-144">Da C# 6 nur die Konstantenmuster unterstützt und die Wiederholung von Konstantenwerten nicht erlaubt, definieren case-Bezeichnungen exklusive Werte, und nur ein Muster kann mit dem Vergleichsausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="45097-144">Because C# 6 supports only the constant pattern and does not allow the repetition of constant values, case labels define mutually exclusive values, and only one pattern can match the match expression.</span></span> <span data-ttu-id="45097-145">Daher ist die Reihenfolge, in der die `case`-Anweisungen auftauchen, unwichtig.</span><span class="sxs-lookup"><span data-stu-id="45097-145">As a result, the order in which `case` statements appear is unimportant.</span></span>

 <span data-ttu-id="45097-146">Da in C# 7 jedoch andere Muster unterstützt werden, müssen case-Bezeichnungen keine gegenseitig ausschließenden Werte definieren, und mehrere Muster können mit dem Vergleichsausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="45097-146">In C# 7, however, because other patterns are supported, case labels need not define mutually exclusive values, and multiple patterns can match the match expression.</span></span> <span data-ttu-id="45097-147">Da nur die Anweisungen im switch-Abschnitt ausgeführt werden, die das erste übereinstimmende Muster enthalten, ist die Reihenfolge, in der `case`-Anweisungen erscheinen, nun wichtig.</span><span class="sxs-lookup"><span data-stu-id="45097-147">Because only the statements in the switch section that contains the first matching pattern are executed, the order in which `case` statements appear is now important.</span></span> <span data-ttu-id="45097-148">Wenn C# einen switch-Abschnitt erkennt, dessen case-Anweisung oder Anweisungen eine Teilmenge der vorherigen Anweisungen ist oder einer entsprechen, erzeugt der Abschnitt den Compilerfehler CS8120: „Der Parameter wurde bereits von einem vorherigen Parameter verarbeitet.“</span><span class="sxs-lookup"><span data-stu-id="45097-148">If C# detects a switch section whose case statement or statements are equivalent to or are subsets of previous statements, it generates a compiler error, CS8120, "The switch case has already been handled by a previous case."</span></span> 

 <span data-ttu-id="45097-149">Das folgende Beispiel veranschaulicht eine `switch`-Anweisung, die eine Reihe von sich nicht gegenseitig ausschließenden Mustern verwendet.</span><span class="sxs-lookup"><span data-stu-id="45097-149">The following example illustrates a `switch` statement that uses a variety of non-mutually exclusive patterns.</span></span> <span data-ttu-id="45097-150">Wenn Sie den switch-Abschnitt `case 0:` verschieben, sodass er nicht länger der erste Abschnitt in der `switch`-Anweisung ist, erzeugt C# einen Compilerfehler, da eine Ganzzahl, deren Wert 0 ist, eine Teilmenge aller Ganzzahlen ist, die das Muster anhand der `case int val`-Anweisung definiert.</span><span class="sxs-lookup"><span data-stu-id="45097-150">If you move the `case 0:` switch section so that it is no longer the first section in the `switch` statement, C# generates a compiler error because an integer whose value is zero is a subset of all integers, which is the pattern defined by the `case int val` statement.</span></span>

 <span data-ttu-id="45097-151">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="45097-151">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]</span></span>    

<span data-ttu-id="45097-152">Sie können dieses Problem beheben und die Compilerwarnung auf eine von zwei Arten entfernen:</span><span class="sxs-lookup"><span data-stu-id="45097-152">You can correct this issue and eliminate the compiler warning in one of two ways:</span></span>

- <span data-ttu-id="45097-153">Durch das Ändern der Reihenfolge der switch-Abschnitte</span><span class="sxs-lookup"><span data-stu-id="45097-153">By changing the order of the switch sections.</span></span> 
 
- <span data-ttu-id="45097-154">Durch das Verwenden einer </a name=“when“>when-Klausel</a> in der `case`-Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="45097-154">By using a </a name="when">when clause</a> in the `case` label.</span></span>
 
## <a name="the-default-case"></a><span data-ttu-id="45097-155">Der `default`-Case</span><span class="sxs-lookup"><span data-stu-id="45097-155">The `default` case</span></span>

<span data-ttu-id="45097-156">Der `default`-Case gibt den auszuführenden switch-Abschnitt an, wenn der Vergleichsausdruck nicht mit einer anderen `case`-Bezeichnung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="45097-156">The `default` case specifies the switch section to execute if the match expression does not match any other `case` label.</span></span> <span data-ttu-id="45097-157">Wenn ein `default`-Case nicht vorhanden ist, und der Vergleichsausdruck nicht einer der anderen `case`-Bezeichnung entspricht, fährt der Programmablauf mit der `switch`-Anweisung fort.</span><span class="sxs-lookup"><span data-stu-id="45097-157">If a `default` case is not present and the match expression does not match any other `case` label, program flow falls through the `switch` statement.</span></span>

<span data-ttu-id="45097-158">Der `default`-Case kann in beliebiger Reihenfolge in der `switch`-Anweisung auftauchen.</span><span class="sxs-lookup"><span data-stu-id="45097-158">The `default` case can appear in any order in the `switch` statement.</span></span> <span data-ttu-id="45097-159">Unabhängig von der Reihenfolge im Quellcode wird er immer zuletzt ausgewertet, nachdem alle `case`-Bezeichnungen ausgewertet wurden.</span><span class="sxs-lookup"><span data-stu-id="45097-159">Regardless of its order in the source code, it is always evaluated last, after all `case` labels have been evaluated.</span></span>

## <a name="a-namepattern--pattern-matching-with-the-switch-statement"></a><span data-ttu-id="45097-160"><a name="pattern" /> Musterabgleich mit der `switch`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45097-160"><a name="pattern" /> Pattern matching with the `switch` statement</span></span>
  
<span data-ttu-id="45097-161">Jede `case`-Anweisung definiert ein Muster, das, wenn es mit dem Vergleichsausdruck übereinstimmt, dafür sorgt, dass seine enthaltenden switch-Abschnitte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="45097-161">Each `case` statement defines a pattern that, if it matches the match expression, causes its  containing switch section to be executed.</span></span> <span data-ttu-id="45097-162">Alle Versionen von C# unterstützen Konstantenmuster.</span><span class="sxs-lookup"><span data-stu-id="45097-162">All versions of C# support the constant pattern.</span></span> <span data-ttu-id="45097-163">Die übrigen Muster werden ab C# 7 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="45097-163">The remaining patterns are supported beginning with C# 7.</span></span> 
  
### <a name="constant-pattern"></a><span data-ttu-id="45097-164">Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="45097-164">Constant pattern</span></span> 

<span data-ttu-id="45097-165">Das Konstantenmuster testet, ob der Vergleichsausdruck einer festgelegten Konstanten entspricht.</span><span class="sxs-lookup"><span data-stu-id="45097-165">The constant pattern tests whether the match expression equals a specified constant.</span></span> <span data-ttu-id="45097-166">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="45097-166">Its syntax is:</span></span>

```csharp
   case constant:
```

<span data-ttu-id="45097-167">wobei *constant* der zu testende Wert ist.</span><span class="sxs-lookup"><span data-stu-id="45097-167">where *constant* is the value to test for.</span></span> <span data-ttu-id="45097-168">*constant* kann eine der folgenden konstanten Ausdrücke sein:</span><span class="sxs-lookup"><span data-stu-id="45097-168">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="45097-169">Ein [bool](bool.md)-Literal, entweder `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="45097-169">A [bool](bool.md) literal, either `true` or `false`.</span></span>
- <span data-ttu-id="45097-170">Alle ganzzahligen Konstanten, z.B. [int](int.md), [lang](long.md) oder ein [Byte](byte.md)</span><span class="sxs-lookup"><span data-stu-id="45097-170">Any integral constant, such as an [int](int.md), a [long](long.md), or a [byte](byte.md).</span></span> 
- <span data-ttu-id="45097-171">Der Name einer deklarierten `const`-Variablen</span><span class="sxs-lookup"><span data-stu-id="45097-171">The name of a declared `const` variable.</span></span>
- <span data-ttu-id="45097-172">Eine Enumerationskonstante.</span><span class="sxs-lookup"><span data-stu-id="45097-172">An enumeration constant.</span></span>
- <span data-ttu-id="45097-173">Ein [char](char.md)-Literal</span><span class="sxs-lookup"><span data-stu-id="45097-173">A [char](char.md) literal.</span></span>
- <span data-ttu-id="45097-174">Ein [Zeichenfolgenliteral](string.md).</span><span class="sxs-lookup"><span data-stu-id="45097-174">A [string](string.md) literal.</span></span>

<span data-ttu-id="45097-175">Der Konstantenausdruck wird wie folgt ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="45097-175">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="45097-176">Wenn *expr* und *constant* integrale Typen sind, bestimmt der C#-Gleichheitsoperator, ob der Ausdruck `true` (d.h., ob `expr == constant`) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="45097-176">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="45097-177">Andernfalls wird der Wert des Ausdrucks durch einen Aufruf der statischen Methode [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="45097-177">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="45097-178">Das folgende Beispiel verwendet das Konstantenmuster, um zu bestimmen, ob ein bestimmtes Datum ein Wochenende, der erste Tag der Arbeitswoche, der letzte Tag der Arbeitswoche oder die Mitte der Arbeitswoche ist.</span><span class="sxs-lookup"><span data-stu-id="45097-178">The following example uses the constant pattern to determine whether a particular date is a weekend, the first day of the work week, the last day of the work week, or the middle of the work week.</span></span> <span data-ttu-id="45097-179">Es bewertet die Eigenschaft [DateTime.DayOfWeek](xref:System.DateTime.DayOfWeek) des heutigen Tags mit den Membern der @System.DayOfWeek-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="45097-179">It evaluates the [DateTime.DayOfWeek](xref:System.DateTime.DayOfWeek) property of the current day against the members of the @System.DayOfWeek enumeration.</span></span> 

<span data-ttu-id="45097-180">[!code-cs[switch#7](../../../../samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="45097-180">[!code-cs[switch#7](../../../../samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]</span></span>

<span data-ttu-id="45097-181">Im folgenden Beispiel wird das Konstantenmuster verwendet, um Benutzereingaben in einer Konsolenanwendung zu steuern, die eine automatische Kaffeemaschine simuliert.</span><span class="sxs-lookup"><span data-stu-id="45097-181">The following example uses the constant pattern to handle user input in a console application that simulates an automatic coffee machine.</span></span>
  
 <span data-ttu-id="45097-182">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]</span><span class="sxs-lookup"><span data-stu-id="45097-182">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]</span></span>  

### <a name="type-pattern"></a><span data-ttu-id="45097-183">Typmuster</span><span class="sxs-lookup"><span data-stu-id="45097-183">Type pattern</span></span>

<span data-ttu-id="45097-184">Das Typmuster ermöglicht die präzise Auswertung und Konvertierung des Typs.</span><span class="sxs-lookup"><span data-stu-id="45097-184">The type pattern enables concise type evaluation and conversion.</span></span> <span data-ttu-id="45097-185">Wenn es mit der `switch`-Anweisung verwendet wird, um einen Musterabgleich auszuführen, wird getestet, ob eine Anweisung in einen bestimmten Typ konvertiert werden kann, und sofern dies möglich ist, wird es in eine Variable des Typs umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="45097-185">When used with the `switch` statement to perform pattern matching, it tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="45097-186">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="45097-186">Its syntax is:</span></span>

```csharp
   case type varname 
```
<span data-ttu-id="45097-187">bei der *Typ* der Name des Typs ist, in den das Ergebnis von *expr* konvertiert wird, und *varname* das Objekt ist, in das das Ergebnis von *expr* konvertiert wird, wenn der Abgleich erfolgreich ist</span><span class="sxs-lookup"><span data-stu-id="45097-187">where *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the match succeeds.</span></span> 

<span data-ttu-id="45097-188">Der `case`-Ausdruck ist `true`, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="45097-188">The `case` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="45097-189">*expr* ist eine Instanz des gleichen Typs wie *Typ*.</span><span class="sxs-lookup"><span data-stu-id="45097-189">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="45097-190">*expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="45097-190">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="45097-191">Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="45097-191">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="45097-192">*expr* hat einen Kompilierzeittyp, der eine Basisklasse von *type* ist, und *expr* hat einen Laufzeittyp,der *type* ist oder von *type* abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="45097-192">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="45097-193">Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie es in der Deklaration des Typs definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="45097-193">The *compile-time type* of a variable is the variable's type as defined in its type declaration.</span></span> <span data-ttu-id="45097-194">Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variable zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="45097-194">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="45097-195">*expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.</span><span class="sxs-lookup"><span data-stu-id="45097-195">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="45097-196">Wenn der case-Ausdruck TRUE ist, ist *varname* definitiv zugewiesen und hat nur innerhalb des switch-Abschnitts einen lokalen Geltungsbereich.</span><span class="sxs-lookup"><span data-stu-id="45097-196">If the case expression is true, *varname* is definitely assigned and has local scope within the switch section only.</span></span>

<span data-ttu-id="45097-197">Beachten Sie, dass `null` nicht mit einem Typ übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="45097-197">Note that `null` does not match a type.</span></span> <span data-ttu-id="45097-198">Verwenden Sie folgende `case`-Bezeichnung, um `null` abzugleichen:</span><span class="sxs-lookup"><span data-stu-id="45097-198">To match a `null`, you use the following `case` label:</span></span>

```csharp
case null:
```
 
<span data-ttu-id="45097-199">Im folgenden Beispiel wird mithilfe des Typmusters Informationen über die verschiedenen Arten von Auflistungstypen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="45097-199">The following example uses the type pattern to provide information about various kinds of collection types.</span></span>

<span data-ttu-id="45097-200">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="45097-200">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]</span></span>

<span data-ttu-id="45097-201">Ohne Musterabgleich könnte dieser Code wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="45097-201">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="45097-202">Die Verwendung des Typmusterabgleichs erzeugt einen kompakteren, lesbaren Code, indem nicht mehr getestet werden muss, ob das Ergebnis einer Umwandlung `null` ist, oder um wiederholte Umwandlungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="45097-202">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null` or to perform repeated casts.</span></span>  

<span data-ttu-id="45097-203">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="45097-203">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]</span></span>

## <a name="the-case-statement-and-the-when-clause"></a><span data-ttu-id="45097-204">Die `case`-Anweisung und die `when`-Klausel</span><span class="sxs-lookup"><span data-stu-id="45097-204">The `case` statement and the `when` clause</span></span>

<span data-ttu-id="45097-205">Da sich ab C# 7 case-Anweisungen nicht gegenseitig ausschließen müssen, können Sie eine `when`-Klausel hinzufügen, um eine zusätzliche Bedingung anzugeben, die erfüllt werden muss, damit die case-Anweisung als TRUE ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="45097-205">Starting with C# 7, because case statements need not be mutually exclusive, you can use add a `when` clause to specify an additional condition that must be satisfied for the case statement to evaluate to true.</span></span> <span data-ttu-id="45097-206">Die `when`-Klausel kann ein beliebiger Ausdruck sein, der einen booleschen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="45097-206">The `when` clause can be any expression that returns a Boolean value.</span></span> <span data-ttu-id="45097-207">Eine der häufigsten Verwendungsmöglichkeiten für die `when`-Klausel wird verwendet, um zu verhindern, dass ein switch-Abschnitt ausgeführt wird, wenn der Wert eines Ausdrucks mit `null` übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="45097-207">One of the more common uses for the `when` clause is used to prevent a switch section from executing when the value of a match expression is `null`.</span></span> 

 <span data-ttu-id="45097-208">Im folgenden Beispiel wird eine `Shape`-Basisklasse, eine `Rectangle`-Klasse, die von `Shape` abgeleitet wird, und eine `Square`-Klasse, die von `Rectangle` abgeleitet wird, definiert.</span><span class="sxs-lookup"><span data-stu-id="45097-208">The following example defines a base `Shape` class, a `Rectangle` class that derives from `Shape`, and a `Square` class that derives from `Rectangle`.</span></span> <span data-ttu-id="45097-209">Die `when`-Klausel wird verwendet, um sicherzustellen, dass `ShowShapeInfo` ein `Rectangle`-Objekt, dem eine gleiche Länge und Breite zugewiesen wurde, wie `Square` behandelt, selbst wenn es nicht als ein `Square`-Objekt instanziiert wurde.</span><span class="sxs-lookup"><span data-stu-id="45097-209">It uses the `when` clause to ensure that the `ShowShapeInfo` treats a `Rectangle` object that has been assigned equal lengths and widths as a `Square` even if is has not been instantiated as a `Square` object.</span></span> <span data-ttu-id="45097-210">Diese Methode versucht weder Informationen über ein Objekt anzuzeigen, das `null` ist, noch über eine Form, deren Bereich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="45097-210">The method does not attempt to display information either about an object that is `null` or a shape whose area is zero.</span></span> 

<span data-ttu-id="45097-211">[!code-cs[switch#8](../../../../samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="45097-211">[!code-cs[switch#8](../../../../samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]</span></span>
  
<span data-ttu-id="45097-212">Beachten Sie, dass in diesem Beispiel die `when`-Klausel, die zu prüfen versucht, ob ein `Shape`-Objekt `null` ist, nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="45097-212">Note that the `when` clause in the example that attempts to test whether a `Shape` object is `null` does not execute.</span></span> <span data-ttu-id="45097-213">Das richtige Typmuster, um auf `null` zu testen, ist `case null:`.</span><span class="sxs-lookup"><span data-stu-id="45097-213">The correct type pattern to test for a `null` is `case null:`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="45097-214">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="45097-214">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="45097-215">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45097-215">See Also</span></span>  

 <span data-ttu-id="45097-216">[C#-Referenz](../index.md) </span><span class="sxs-lookup"><span data-stu-id="45097-216">[C# Reference](../index.md) </span></span>  
 <span data-ttu-id="45097-217">[C#-Programmierhandbuch](../../programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="45097-217">[C# Programming Guide](../../programming-guide/index.md) </span></span>  
 <span data-ttu-id="45097-218">[C#-Schlüsselwörter](index.md) </span><span class="sxs-lookup"><span data-stu-id="45097-218">[C# Keywords](index.md) </span></span>  
 <span data-ttu-id="45097-219">[if-else](if-else.md) </span><span class="sxs-lookup"><span data-stu-id="45097-219">[if-else](if-else.md) </span></span>  
 [<span data-ttu-id="45097-220">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="45097-220">Pattern Matching</span></span>](../../pattern-matching.md)   
 

 

