---
title: "Schlüsselwort „switch“ (C#-Referenz)"
ms.date: 03/07/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- switch_CSharpKeyword
- switch
- case
- case_CSharpKeyword
helpviewer_keywords:
- switch statement [C#]
- switch keyword [C#]
- case statement [C#]
- default keyword [C#]
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
caps.latest.revision: "47"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 66528c9804b74b0bba088627b3116be804c65eb0
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2017
---
# <a name="switch-c-reference"></a><span data-ttu-id="249a2-102">switch (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="249a2-102">switch (C# Reference)</span></span>
<span data-ttu-id="249a2-103">`switch` ist eine Auswahlanweisung, die einen einzelnen *switch-Abschnitt* zum Ausführen aus einer Liste von Kandidaten auswählt, die auf einem Mustertreffer mit dem *Vergleichsausdruck* basiert.</span><span class="sxs-lookup"><span data-stu-id="249a2-103">`switch` is a selection statement that chooses a single *switch section* to execute from a list of candidates based on a pattern match with the *match expression*.</span></span> 
  
 [!code-cs[switch#1](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]  

<span data-ttu-id="249a2-104">Die Anweisung `switch` wird häufig als Alternative zu einem [if-else](if-else.md)-Konstrukt verwendet, wenn ein einzelner Ausdruck mit drei oder mehr Bedingungen getestet wird.</span><span class="sxs-lookup"><span data-stu-id="249a2-104">The `switch` statement is often used as an alternative to an [if-else](if-else.md) construct if a single expression is tested against three or more conditions.</span></span> <span data-ttu-id="249a2-105">Die folgende Anweisung `switch` bestimmt z.B., ob eine Variable des Typs `Color` einen von drei Werten hat:</span><span class="sxs-lookup"><span data-stu-id="249a2-105">For example, the following `switch` statement determines whether a variable of type `Color` has one of three values:</span></span> 

[!code-cs[switch#3](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)] 

<span data-ttu-id="249a2-106">Dies entspricht dem folgenden Beispiel, das ein `if`-`else`-Konstrukt verwendet.</span><span class="sxs-lookup"><span data-stu-id="249a2-106">It is equivalent to the following example that uses an `if`-`else` construct.</span></span> 

[!code-cs[switch#3a](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)] 

## <a name="the-match-expression"></a><span data-ttu-id="249a2-107">Der Vergleichsausdruck</span><span class="sxs-lookup"><span data-stu-id="249a2-107">The match expression</span></span>

<span data-ttu-id="249a2-108">Der Vergleichsausdruck stellt den Wert bereit, mit dem die Muster in den Bezeichnungen `case` verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="249a2-108">The match expression provides the value to match against the patterns in `case` labels.</span></span> <span data-ttu-id="249a2-109">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="249a2-109">Its syntax is:</span></span>

```csharp
   switch (expr)
```

<span data-ttu-id="249a2-110">In C# 6 muss der Vergleichsausdruck ein Ausdruck sein, der einen Wert der folgenden Typen zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="249a2-110">In C# 6, the match expression must be an expression that returns a value of the following types:</span></span>

- <span data-ttu-id="249a2-111">Ein [char](char.md)</span><span class="sxs-lookup"><span data-stu-id="249a2-111">a [char](char.md).</span></span>
- <span data-ttu-id="249a2-112">Eine [Zeichenfolge](string.md)</span><span class="sxs-lookup"><span data-stu-id="249a2-112">a [string](string.md).</span></span>
- <span data-ttu-id="249a2-113">Ein [bool](bool.md)</span><span class="sxs-lookup"><span data-stu-id="249a2-113">a [bool](bool.md).</span></span> 
- <span data-ttu-id="249a2-114">Ein ganzzahliger Wert wie [int](int.md) oder [long](long.md)</span><span class="sxs-lookup"><span data-stu-id="249a2-114">an integral value, such as an [int](int.md) or a [long](long.md).</span></span>
- <span data-ttu-id="249a2-115">Ein [Enumerations](enum.md)wert</span><span class="sxs-lookup"><span data-stu-id="249a2-115">an [enum](enum.md) value.</span></span>

<span data-ttu-id="249a2-116">Ab C# 7 kann der Vergleichsausdruck jeder Ausdruck sein, der nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="249a2-116">Starting with C# 7, the match expression can be any non-null expression.</span></span>
 
## <a name="the-switch-section"></a><span data-ttu-id="249a2-117">Der switch-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="249a2-117">The switch section</span></span>
 
 <span data-ttu-id="249a2-118">Eine `switch`-Anweisung enthält eine oder mehrere switch-Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="249a2-118">A `switch` statement includes one or more switch sections.</span></span> <span data-ttu-id="249a2-119">Jeder switch-Abschnitt enthält eine oder mehrere *case-Bezeichnungen* und eine Liste mit mindestens einer Anweisung.</span><span class="sxs-lookup"><span data-stu-id="249a2-119">Each switch section contains one or more *case labels* followed by one or more statements.</span></span> <span data-ttu-id="249a2-120">Das folgende Beispiel zeigt eine einfache `switch`-Anweisung, die über drei switch-Abschnitte verfügt.</span><span class="sxs-lookup"><span data-stu-id="249a2-120">The following example shows a simple `switch` statement that has three switch sections.</span></span> <span data-ttu-id="249a2-121">Jeder switch-Abschnitt enthält eine case-Bezeichnung, z. B. `case 1:`, und zwei Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="249a2-121">Each switch section has one case label, such as `case 1:`, and two statements.</span></span>
 
  <span data-ttu-id="249a2-122">Eine `switch`-Anweisung kann eine beliebige Anzahl von switch-Abschnitten enthalten, und jeder Abschnitt kann eine oder mehrere case-Bezeichnungen haben, wie im folgend Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="249a2-122">A `switch` statement can include any number of switch sections, and each section can have one or more case labels, as shown in the following example.</span></span> <span data-ttu-id="249a2-123">Allerdings können zwei case-Bezeichnungen nicht denselben Ausdruck enthalten.</span><span class="sxs-lookup"><span data-stu-id="249a2-123">However, no two case labels may contain the same expression.</span></span>  

 [!code-cs[switch#2](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]  

 <span data-ttu-id="249a2-124">Nur ein switch-Abschnitt einer switch-Anweisung wir ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="249a2-124">Only one switch section in a switch statement executes.</span></span> <span data-ttu-id="249a2-125">C# lässt nicht zu, dass die Ausführung von einem switch-Abschnitt zum nächsten fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="249a2-125">C# does not allow execution to continue from one switch section to the next.</span></span> <span data-ttu-id="249a2-126">Aus diesem Grund generiert der folgende Code den Compilerfehler CS0163: „Das Steuerelement kann nicht von einer case-Bezeichnung (<case label>) zur nächsten fortfahren.“</span><span class="sxs-lookup"><span data-stu-id="249a2-126">Because of this, the following code generates a compiler error, CS0163: "Control cannot fall through from one case label (<case label>) to another."</span></span>   

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
<span data-ttu-id="249a2-127">Diese Anforderung wird normalerweise erfüllt, indem der switch-Abschnitt ausdrücklich durch Verwenden einer Anweisung [break](break.md), [goto](goto.md) oder [return](return.md) beendet wird.</span><span class="sxs-lookup"><span data-stu-id="249a2-127">This requirement is usually met by explicitly exiting the switch section by using a [break](break.md), [goto](goto.md), or [return](return.md) statement.</span></span> <span data-ttu-id="249a2-128">Der folgende Code ist jedoch auch gültig, da er sicherstellt, dass die Programmsteuerung nicht im switch-Abschnitt `default` fortfährt.</span><span class="sxs-lookup"><span data-stu-id="249a2-128">However, the following code is also valid, because it ensures that program control cannot fall through to the `default` switch section.</span></span>
  
 [!code-cs[switch#4](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]    
  
 <span data-ttu-id="249a2-129">Die Ausführung der Anweisungsliste im switch-Abschnitt mit einer case-Bezeichnung, die den Vergleichsausdruck vergleicht, beginnt mit der ersten Anweisung und durchläuft in der Regel die Anweisungsliste, bis eine jump-Anweisung erreicht wird, z.B. `break`, `goto case`, `goto label`, `return` oder `throw`.</span><span class="sxs-lookup"><span data-stu-id="249a2-129">Execution of the statement list in the switch section with a case label that matches the match expression begins with the first statement and proceeds through the statement list, typically until a jump statement, such as a `break`, `goto case`, `goto label`, `return`, or `throw`, is reached.</span></span> <span data-ttu-id="249a2-130">An diesem Punkt wird die Steuerung der `switch`-Anweisung entzogen oder an eine andere case-Bezeichnung übertragen.</span><span class="sxs-lookup"><span data-stu-id="249a2-130">At that point, control is transferred outside the `switch` statement or to another case label.</span></span> <span data-ttu-id="249a2-131">Eine `goto`-Anweisung muss bei Nichtverwendung die Steuerung an eine konstante Bezeichnung übergeben.</span><span class="sxs-lookup"><span data-stu-id="249a2-131">A `goto` statement, if it is used, must transfer control to a constant label.</span></span> <span data-ttu-id="249a2-132">Diese Einschränkung ist notwendig, da der Versuch, die Steuerung an eine nicht konstante Bezeichnung zu übergeben, unerwünschte Nebeneffekte haben kann, z.B. kann die Steuerung an eine nicht beabsichtigte Position im Code übergeben werden, oder es kann eine Endlosschleife entstehen.</span><span class="sxs-lookup"><span data-stu-id="249a2-132">This restriction is necessary, since attempting to transfer control to a non-constant label can have undesirable side-effects, such transferring control to an unintended location in code or creating an endless loop.</span></span>

## <a name="case-labels"></a><span data-ttu-id="249a2-133">case-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="249a2-133">Case labels</span></span>

 <span data-ttu-id="249a2-134">Jede case-Bezeichnung gibt ein Muster an, mit dem der Vergleichsausdruck verglichen werden soll (die Variable `caseSwitch` in den vorherigen Beispielen).</span><span class="sxs-lookup"><span data-stu-id="249a2-134">Each case label specifies a pattern to compare to the match expression (the `caseSwitch` variable in the previous examples).</span></span> <span data-ttu-id="249a2-135">Wenn sie übereinstimmen, wird das Steuerelement an den switch-Abschnitt übertragen, der die **erste** übereinstimmende case-Bezeichnung enthält.</span><span class="sxs-lookup"><span data-stu-id="249a2-135">If they match, control is transferred to the switch section that contains the **first** matching case label.</span></span> <span data-ttu-id="249a2-136">Wenn keine case-Bezeichnung mit dem Vergleichsausdruck übereinstimmt, wird das Steuerelement an den Abschnitt mit der `default`-case-Bezeichnung übertragen, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="249a2-136">If no case label pattern matches the match expression, control is transferred to the section with the `default` case label, if there is one.</span></span> <span data-ttu-id="249a2-137">Wenn es kein `default`-case gibt, werden keine Anweisungen in jeglichen switch-Abschnitten ausgeführt, und ein Steuerelement wird außerhalb der `switch`-Anweisung übertragen.</span><span class="sxs-lookup"><span data-stu-id="249a2-137">If there is no `default` case, no statements in any switch section are executed, and control is transferred outside the `switch` statement.</span></span>

 <span data-ttu-id="249a2-138">Informationen zur `switch`-Anweisung und zum Musterabgleich finden Sie im Abschnitt [Musterabgleich mit der `switch`-Anweisung](#pattern).</span><span class="sxs-lookup"><span data-stu-id="249a2-138">For information on the `switch` statement and pattern matching, see the [Pattern matching with the `switch` statement](#pattern) section.</span></span>

 <span data-ttu-id="249a2-139">Da C# 6 nur die Konstantenmuster unterstützt und die Wiederholung von Konstantenwerten nicht erlaubt, definieren case-Bezeichnungen exklusive Werte, und nur ein Muster kann mit dem Vergleichsausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="249a2-139">Because C# 6 supports only the constant pattern and does not allow the repetition of constant values, case labels define mutually exclusive values, and only one pattern can match the match expression.</span></span> <span data-ttu-id="249a2-140">Daher ist die Reihenfolge, in der die `case`-Anweisungen auftauchen, unwichtig.</span><span class="sxs-lookup"><span data-stu-id="249a2-140">As a result, the order in which `case` statements appear is unimportant.</span></span>

 <span data-ttu-id="249a2-141">Da in C# 7 jedoch andere Muster unterstützt werden, müssen case-Bezeichnungen keine gegenseitig ausschließenden Werte definieren, und mehrere Muster können mit dem Vergleichsausdruck übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="249a2-141">In C# 7, however, because other patterns are supported, case labels need not define mutually exclusive values, and multiple patterns can match the match expression.</span></span> <span data-ttu-id="249a2-142">Da nur die Anweisungen im switch-Abschnitt ausgeführt werden, die das erste übereinstimmende Muster enthalten, ist die Reihenfolge, in der `case`-Anweisungen erscheinen, nun wichtig.</span><span class="sxs-lookup"><span data-stu-id="249a2-142">Because only the statements in the switch section that contains the first matching pattern are executed, the order in which `case` statements appear is now important.</span></span> <span data-ttu-id="249a2-143">Wenn C# einen switch-Abschnitt erkennt, dessen case-Anweisung oder Anweisungen eine Teilmenge der vorherigen Anweisungen ist oder einer entsprechen, erzeugt der Abschnitt den Compilerfehler CS8120: „Der Parameter wurde bereits von einem vorherigen Parameter verarbeitet.“</span><span class="sxs-lookup"><span data-stu-id="249a2-143">If C# detects a switch section whose case statement or statements are equivalent to or are subsets of previous statements, it generates a compiler error, CS8120, "The switch case has already been handled by a previous case."</span></span> 

 <span data-ttu-id="249a2-144">Das folgende Beispiel veranschaulicht eine `switch`-Anweisung, die eine Reihe von sich nicht gegenseitig ausschließenden Mustern verwendet.</span><span class="sxs-lookup"><span data-stu-id="249a2-144">The following example illustrates a `switch` statement that uses a variety of non-mutually exclusive patterns.</span></span> <span data-ttu-id="249a2-145">Wenn Sie den switch-Abschnitt `case 0:` verschieben, sodass er nicht länger der erste Abschnitt in der `switch`-Anweisung ist, erzeugt C# einen Compilerfehler, da eine Ganzzahl, deren Wert 0 ist, eine Teilmenge aller Ganzzahlen ist, die das Muster anhand der `case int val`-Anweisung definiert.</span><span class="sxs-lookup"><span data-stu-id="249a2-145">If you move the `case 0:` switch section so that it is no longer the first section in the `switch` statement, C# generates a compiler error because an integer whose value is zero is a subset of all integers, which is the pattern defined by the `case int val` statement.</span></span>

 [!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]    

<span data-ttu-id="249a2-146">Sie können dieses Problem beheben und die Compilerwarnung auf eine von zwei Arten entfernen:</span><span class="sxs-lookup"><span data-stu-id="249a2-146">You can correct this issue and eliminate the compiler warning in one of two ways:</span></span>

- <span data-ttu-id="249a2-147">Durch das Ändern der Reihenfolge der switch-Abschnitte</span><span class="sxs-lookup"><span data-stu-id="249a2-147">By changing the order of the switch sections.</span></span> 
 
- <span data-ttu-id="249a2-148">Durch das Verwenden einer </a name=“when“>when-Klausel</a> in der `case`-Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="249a2-148">By using a </a name="when">when clause</a> in the `case` label.</span></span>
 
## <a name="the-default-case"></a><span data-ttu-id="249a2-149">Der `default`-Case</span><span class="sxs-lookup"><span data-stu-id="249a2-149">The `default` case</span></span>

<span data-ttu-id="249a2-150">Der `default`-Case gibt den auszuführenden switch-Abschnitt an, wenn der Vergleichsausdruck nicht mit einer anderen `case`-Bezeichnung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="249a2-150">The `default` case specifies the switch section to execute if the match expression does not match any other `case` label.</span></span> <span data-ttu-id="249a2-151">Wenn ein `default`-Case nicht vorhanden ist, und der Vergleichsausdruck nicht einer der anderen `case`-Bezeichnung entspricht, fährt der Programmablauf mit der `switch`-Anweisung fort.</span><span class="sxs-lookup"><span data-stu-id="249a2-151">If a `default` case is not present and the match expression does not match any other `case` label, program flow falls through the `switch` statement.</span></span>

<span data-ttu-id="249a2-152">Der `default`-Case kann in beliebiger Reihenfolge in der `switch`-Anweisung auftauchen.</span><span class="sxs-lookup"><span data-stu-id="249a2-152">The `default` case can appear in any order in the `switch` statement.</span></span> <span data-ttu-id="249a2-153">Unabhängig von der Reihenfolge im Quellcode wird er immer zuletzt ausgewertet, nachdem alle `case`-Bezeichnungen ausgewertet wurden.</span><span class="sxs-lookup"><span data-stu-id="249a2-153">Regardless of its order in the source code, it is always evaluated last, after all `case` labels have been evaluated.</span></span>

## <a name="a-namepattern--pattern-matching-with-the-switch-statement"></a><span data-ttu-id="249a2-154"><a name="pattern" /> Musterabgleich mit der `switch`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="249a2-154"><a name="pattern" /> Pattern matching with the `switch` statement</span></span>
  
<span data-ttu-id="249a2-155">Jede `case`-Anweisung definiert ein Muster, das, wenn es mit dem Vergleichsausdruck übereinstimmt, dafür sorgt, dass seine enthaltenden switch-Abschnitte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="249a2-155">Each `case` statement defines a pattern that, if it matches the match expression, causes its  containing switch section to be executed.</span></span> <span data-ttu-id="249a2-156">Alle Versionen von C# unterstützen Konstantenmuster.</span><span class="sxs-lookup"><span data-stu-id="249a2-156">All versions of C# support the constant pattern.</span></span> <span data-ttu-id="249a2-157">Die übrigen Muster werden ab C# 7 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="249a2-157">The remaining patterns are supported beginning with C# 7.</span></span> 
  
### <a name="constant-pattern"></a><span data-ttu-id="249a2-158">Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="249a2-158">Constant pattern</span></span> 

<span data-ttu-id="249a2-159">Das Konstantenmuster testet, ob der Vergleichsausdruck einer festgelegten Konstanten entspricht.</span><span class="sxs-lookup"><span data-stu-id="249a2-159">The constant pattern tests whether the match expression equals a specified constant.</span></span> <span data-ttu-id="249a2-160">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="249a2-160">Its syntax is:</span></span>

```csharp
   case constant:
```

<span data-ttu-id="249a2-161">wobei *constant* der zu testende Wert ist.</span><span class="sxs-lookup"><span data-stu-id="249a2-161">where *constant* is the value to test for.</span></span> <span data-ttu-id="249a2-162">*constant* kann eine der folgenden konstanten Ausdrücke sein:</span><span class="sxs-lookup"><span data-stu-id="249a2-162">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="249a2-163">Ein [bool](bool.md)-Literal, entweder `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="249a2-163">A [bool](bool.md) literal, either `true` or `false`.</span></span>
- <span data-ttu-id="249a2-164">Alle ganzzahligen Konstanten, z.B. [int](int.md), [lang](long.md) oder ein [Byte](byte.md)</span><span class="sxs-lookup"><span data-stu-id="249a2-164">Any integral constant, such as an [int](int.md), a [long](long.md), or a [byte](byte.md).</span></span> 
- <span data-ttu-id="249a2-165">Der Name einer deklarierten `const`-Variablen</span><span class="sxs-lookup"><span data-stu-id="249a2-165">The name of a declared `const` variable.</span></span>
- <span data-ttu-id="249a2-166">Eine Enumerationskonstante.</span><span class="sxs-lookup"><span data-stu-id="249a2-166">An enumeration constant.</span></span>
- <span data-ttu-id="249a2-167">Ein [char](char.md)-Literal</span><span class="sxs-lookup"><span data-stu-id="249a2-167">A [char](char.md) literal.</span></span>
- <span data-ttu-id="249a2-168">Ein [Zeichenfolgenliteral](string.md).</span><span class="sxs-lookup"><span data-stu-id="249a2-168">A [string](string.md) literal.</span></span>

<span data-ttu-id="249a2-169">Der Konstantenausdruck wird wie folgt ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="249a2-169">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="249a2-170">Wenn *expr* und *constant* integrale Typen sind, bestimmt der C#-Gleichheitsoperator, ob der Ausdruck `true` (d.h., ob `expr == constant`) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="249a2-170">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="249a2-171">Andernfalls wird der Wert des Ausdrucks durch einen Aufruf der statischen Methode [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="249a2-171">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="249a2-172">Das folgende Beispiel verwendet das Konstantenmuster, um zu bestimmen, ob ein bestimmtes Datum ein Wochenende, der erste Tag der Arbeitswoche, der letzte Tag der Arbeitswoche oder die Mitte der Arbeitswoche ist.</span><span class="sxs-lookup"><span data-stu-id="249a2-172">The following example uses the constant pattern to determine whether a particular date is a weekend, the first day of the work week, the last day of the work week, or the middle of the work week.</span></span> <span data-ttu-id="249a2-173">Es bewertet die Eigenschaft <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> des heutigen Tags mit den Membern der <xref:System.DayOfWeek>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="249a2-173">It evaluates the <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> property of the current day against the members of the <xref:System.DayOfWeek> enumeration.</span></span> 

[!code-cs[switch#7](../../../../samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]

<span data-ttu-id="249a2-174">Im folgenden Beispiel wird das Konstantenmuster verwendet, um Benutzereingaben in einer Konsolenanwendung zu steuern, die eine automatische Kaffeemaschine simuliert.</span><span class="sxs-lookup"><span data-stu-id="249a2-174">The following example uses the constant pattern to handle user input in a console application that simulates an automatic coffee machine.</span></span>
  
 [!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]  

### <a name="type-pattern"></a><span data-ttu-id="249a2-175">Typmuster</span><span class="sxs-lookup"><span data-stu-id="249a2-175">Type pattern</span></span>

<span data-ttu-id="249a2-176">Das Typmuster ermöglicht die präzise Auswertung und Konvertierung des Typs.</span><span class="sxs-lookup"><span data-stu-id="249a2-176">The type pattern enables concise type evaluation and conversion.</span></span> <span data-ttu-id="249a2-177">Wenn es mit der `switch`-Anweisung verwendet wird, um einen Musterabgleich auszuführen, wird getestet, ob eine Anweisung in einen bestimmten Typ konvertiert werden kann, und sofern dies möglich ist, wird es in eine Variable des Typs umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="249a2-177">When used with the `switch` statement to perform pattern matching, it tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="249a2-178">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="249a2-178">Its syntax is:</span></span>

```csharp
   case type varname 
```
<span data-ttu-id="249a2-179">bei der *Typ* der Name des Typs ist, in den das Ergebnis von *expr* konvertiert wird, und *varname* das Objekt ist, in das das Ergebnis von *expr* konvertiert wird, wenn der Abgleich erfolgreich ist</span><span class="sxs-lookup"><span data-stu-id="249a2-179">where *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the match succeeds.</span></span> 

<span data-ttu-id="249a2-180">Der `case`-Ausdruck ist `true`, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="249a2-180">The `case` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="249a2-181">*expr* ist eine Instanz des gleichen Typs wie *Typ*.</span><span class="sxs-lookup"><span data-stu-id="249a2-181">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="249a2-182">*expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="249a2-182">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="249a2-183">Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="249a2-183">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="249a2-184">*expr* hat einen Kompilierzeittyp, der eine Basisklasse von *type* ist, und *expr* hat einen Laufzeittyp,der *type* ist oder von *type* abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="249a2-184">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="249a2-185">Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie es in der Deklaration des Typs definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="249a2-185">The *compile-time type* of a variable is the variable's type as defined in its type declaration.</span></span> <span data-ttu-id="249a2-186">Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variable zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="249a2-186">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="249a2-187">*expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.</span><span class="sxs-lookup"><span data-stu-id="249a2-187">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="249a2-188">Wenn der case-Ausdruck TRUE ist, ist *varname* definitiv zugewiesen und hat nur innerhalb des switch-Abschnitts einen lokalen Geltungsbereich.</span><span class="sxs-lookup"><span data-stu-id="249a2-188">If the case expression is true, *varname* is definitely assigned and has local scope within the switch section only.</span></span>

<span data-ttu-id="249a2-189">Beachten Sie, dass `null` nicht mit einem Typ übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="249a2-189">Note that `null` does not match a type.</span></span> <span data-ttu-id="249a2-190">Verwenden Sie folgende `case`-Bezeichnung, um `null` abzugleichen:</span><span class="sxs-lookup"><span data-stu-id="249a2-190">To match a `null`, you use the following `case` label:</span></span>

```csharp
case null:
```
 
<span data-ttu-id="249a2-191">Im folgenden Beispiel wird mithilfe des Typmusters Informationen über die verschiedenen Arten von Auflistungstypen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="249a2-191">The following example uses the type pattern to provide information about various kinds of collection types.</span></span>

[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]

<span data-ttu-id="249a2-192">Ohne Musterabgleich könnte dieser Code wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="249a2-192">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="249a2-193">Die Verwendung des Typmusterabgleichs erzeugt einen kompakteren, lesbaren Code, indem nicht mehr getestet werden muss, ob das Ergebnis einer Umwandlung `null` ist, oder um wiederholte Umwandlungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="249a2-193">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null` or to perform repeated casts.</span></span>  

[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]

## <a name="the-case-statement-and-the-when-clause"></a><span data-ttu-id="249a2-194">Die `case`-Anweisung und die `when`-Klausel</span><span class="sxs-lookup"><span data-stu-id="249a2-194">The `case` statement and the `when` clause</span></span>

<span data-ttu-id="249a2-195">Da sich ab C# 7 case-Anweisungen nicht gegenseitig ausschließen müssen, können Sie eine `when`-Klausel hinzufügen, um eine zusätzliche Bedingung anzugeben, die erfüllt werden muss, damit die case-Anweisung als TRUE ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="249a2-195">Starting with C# 7, because case statements need not be mutually exclusive, you can use add a `when` clause to specify an additional condition that must be satisfied for the case statement to evaluate to true.</span></span> <span data-ttu-id="249a2-196">Die `when`-Klausel kann ein beliebiger Ausdruck sein, der einen booleschen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="249a2-196">The `when` clause can be any expression that returns a Boolean value.</span></span> <span data-ttu-id="249a2-197">Eine der häufigsten Verwendungsmöglichkeiten für die `when`-Klausel wird verwendet, um zu verhindern, dass ein switch-Abschnitt ausgeführt wird, wenn der Wert eines Ausdrucks mit `null` übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="249a2-197">One of the more common uses for the `when` clause is used to prevent a switch section from executing when the value of a match expression is `null`.</span></span> 

 <span data-ttu-id="249a2-198">Im folgenden Beispiel wird eine `Shape`-Basisklasse, eine `Rectangle`-Klasse, die von `Shape` abgeleitet wird, und eine `Square`-Klasse, die von `Rectangle` abgeleitet wird, definiert.</span><span class="sxs-lookup"><span data-stu-id="249a2-198">The following example defines a base `Shape` class, a `Rectangle` class that derives from `Shape`, and a `Square` class that derives from `Rectangle`.</span></span> <span data-ttu-id="249a2-199">Die `when`-Klausel wird verwendet, um sicherzustellen, dass `ShowShapeInfo` ein `Rectangle`-Objekt, dem eine gleiche Länge und Breite zugewiesen wurde, wie `Square` behandelt, selbst wenn es nicht als ein `Square`-Objekt instanziiert wurde.</span><span class="sxs-lookup"><span data-stu-id="249a2-199">It uses the `when` clause to ensure that the `ShowShapeInfo` treats a `Rectangle` object that has been assigned equal lengths and widths as a `Square` even if is has not been instantiated as a `Square` object.</span></span> <span data-ttu-id="249a2-200">Diese Methode versucht weder Informationen über ein Objekt anzuzeigen, das `null` ist, noch über eine Form, deren Bereich NULL ist.</span><span class="sxs-lookup"><span data-stu-id="249a2-200">The method does not attempt to display information either about an object that is `null` or a shape whose area is zero.</span></span> 

[!code-cs[switch#8](../../../../samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]
  
<span data-ttu-id="249a2-201">Beachten Sie, dass in diesem Beispiel die `when`-Klausel, die zu prüfen versucht, ob ein `Shape`-Objekt `null` ist, nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="249a2-201">Note that the `when` clause in the example that attempts to test whether a `Shape` object is `null` does not execute.</span></span> <span data-ttu-id="249a2-202">Das richtige Typmuster, um auf `null` zu testen, ist `case null:`.</span><span class="sxs-lookup"><span data-stu-id="249a2-202">The correct type pattern to test for a `null` is `case null:`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="249a2-203">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="249a2-203">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](../../../../includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="249a2-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="249a2-204">See Also</span></span>  

 <span data-ttu-id="249a2-205">[C#-Referenz](../index.md) </span><span class="sxs-lookup"><span data-stu-id="249a2-205">[C# Reference](../index.md) </span></span>  
 <span data-ttu-id="249a2-206">[C#-Programmierhandbuch](../../programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="249a2-206">[C# Programming Guide](../../programming-guide/index.md) </span></span>  
 <span data-ttu-id="249a2-207">[C#-Schlüsselwörter](index.md) </span><span class="sxs-lookup"><span data-stu-id="249a2-207">[C# Keywords](index.md) </span></span>  
 <span data-ttu-id="249a2-208">[if-else](if-else.md) </span><span class="sxs-lookup"><span data-stu-id="249a2-208">[if-else](if-else.md) </span></span>  
 [<span data-ttu-id="249a2-209">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="249a2-209">Pattern Matching</span></span>](../../pattern-matching.md)   
 

 
