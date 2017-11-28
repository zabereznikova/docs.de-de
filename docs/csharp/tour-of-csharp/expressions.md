---
title: "C#-Ausdrücke – Überblick über C#"
description: "Ausdrücke, Operanden und Operatoren sind Bausteine der Sprache C#."
keywords: .NET, Csharp, Ausdruck, Operator, Operand
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 7b7e321e6554818924a8a2b68afa4c787807bcba
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2017
---
# <a name="expressions"></a><span data-ttu-id="1c2d8-104">Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="1c2d8-104">Expressions</span></span>

<span data-ttu-id="1c2d8-105">*Ausdrücke* bestehen aus *Operanden* und *Operatoren*.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-105">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="1c2d8-106">Die Operatoren eines Ausdrucks geben an, welche Operationen auf die Operanden angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-106">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="1c2d8-107">Beispiele für Operatoren sind `+`, `-`, `*`, `/` und `new`.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-107">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="1c2d8-108">Beispiele für Operanden sind Literale, Felder, lokale Variablen und Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-108">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="1c2d8-109">Wenn ein Ausdruck mehrere Operatoren enthält, bestimmt die *Rangfolge* der Operatoren die Reihenfolge, in der die einzelnen Operatoren ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-109">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="1c2d8-110">Der Ausdruck `x + y * z` wird z.B. als `x + (y * z)` ausgewertet, da der `*`-Operator Vorrang vor dem `+`-Operator hat.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-110">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="1c2d8-111">Tritt ein Operand zwischen zwei Operatoren mit gleicher Rangfolge auf, steuert die *Assoziativität* der Operatoren die Reihenfolge, in der die Vorgänge ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="1c2d8-111">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

*   <span data-ttu-id="1c2d8-112">Mit Ausnahme der Zuweisungsoperatoren sind alle binären Operatoren *linksassoziativ*, was bedeutet, dass Vorgänge von links nach rechts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-112">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="1c2d8-113">`x + y + z` wird beispielsweise als `(x + y) + z` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-113">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
*   <span data-ttu-id="1c2d8-114">Die Zuweisungsoperatoren und der bedingte Operator (`?:`) sind *rechtsassoziativ*, d.h., die Operationen werden von rechts nach links ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-114">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="1c2d8-115">`x = y = z` wird beispielsweise als `x = (y = z)` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-115">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="1c2d8-116">Rangfolge und Assoziativität können mit Klammern gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-116">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="1c2d8-117">In `x + y * z` wird beispielsweise zuerst `y` mit `z` multipliziert und dann das Ergebnis zu `x` addiert, aber in `(x + y) * z` werden zunächst `x` und `y` addiert, und dann wird das Ergebnis mit `z` multipliziert.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-117">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="1c2d8-118">Die meisten Operatoren können *überladen* werden.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-118">Most operators can be *overloaded*.</span></span> <span data-ttu-id="1c2d8-119">Das Überladen von Operatoren ermöglicht die Angabe benutzerdefinierter Operatorimplementierungen für Vorgänge, in denen einer der Operanden oder beide einer benutzerdefinierten Klasse oder einem benutzerdefinierten Strukturtyp angehören.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-119">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="1c2d8-120">In der folgenden Übersicht der C#-Operatoren werden die Operatorkategorien gemäß der Rangfolge von oben nach unten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-120">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="1c2d8-121">Operatoren der gleichen Kategorie haben den gleichen Rang.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-121">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="1c2d8-122">Jede Kategorie enthält eine Liste von Ausdrücken mit der Beschreibung des jeweiligen Ausdruckstyps.</span><span class="sxs-lookup"><span data-stu-id="1c2d8-122">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="1c2d8-123">Primär</span><span class="sxs-lookup"><span data-stu-id="1c2d8-123">Primary</span></span>
    - <span data-ttu-id="1c2d8-124">`x.m`: Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="1c2d8-124">`x.m`: Member access</span></span>
    - <span data-ttu-id="1c2d8-125">`x(...)`: Methoden- und Delegataufruf</span><span class="sxs-lookup"><span data-stu-id="1c2d8-125">`x(...)`: Method and delegate invocation</span></span>
    - <span data-ttu-id="1c2d8-126">`x[...]`: Array- und Indexerzugriff</span><span class="sxs-lookup"><span data-stu-id="1c2d8-126">`x[...]`: Array and indexer access</span></span>
    - <span data-ttu-id="1c2d8-127">`x++`: Postinkrement</span><span class="sxs-lookup"><span data-stu-id="1c2d8-127">`x++`: Post-increment</span></span>
    - <span data-ttu-id="1c2d8-128">`x--`: Postdekrement</span><span class="sxs-lookup"><span data-stu-id="1c2d8-128">`x--`: Post-decrement</span></span>
    - <span data-ttu-id="1c2d8-129">`new T(...)`: Objekt- und Delegaterstellung</span><span class="sxs-lookup"><span data-stu-id="1c2d8-129">`new T(...)`: Object and delegate creation</span></span>
    - <span data-ttu-id="1c2d8-130">`new T(...){...}`: Objekterstellung mit Initialisierer</span><span class="sxs-lookup"><span data-stu-id="1c2d8-130">`new T(...){...}`: Object creation with initializer</span></span>
    - <span data-ttu-id="1c2d8-131">`new {...}`: Anonymer Objektinitialisierer</span><span class="sxs-lookup"><span data-stu-id="1c2d8-131">`new {...}`:  Anonymous object initializer</span></span>
    - <span data-ttu-id="1c2d8-132">`new T[...]`: Arrayerstellung</span><span class="sxs-lookup"><span data-stu-id="1c2d8-132">`new T[...]`: Array creation</span></span>
    - <span data-ttu-id="1c2d8-133">`typeof(T)`: Abrufen von <xref:System.Type> Objekt für `T`</span><span class="sxs-lookup"><span data-stu-id="1c2d8-133">`typeof(T)`: Obtain <xref:System.Type> object for `T`</span></span>
    - <span data-ttu-id="1c2d8-134">`checked(x)`: Auswerten von Ausdrücken in geprüftem Kontext</span><span class="sxs-lookup"><span data-stu-id="1c2d8-134">`checked(x)`: Evaluate expression in checked context</span></span>
    - <span data-ttu-id="1c2d8-135">`unchecked(x)`: Auswerten von Ausdrücken in nicht geprüftem Kontext</span><span class="sxs-lookup"><span data-stu-id="1c2d8-135">`unchecked(x)`: Evaluate expression in unchecked context</span></span>
    - <span data-ttu-id="1c2d8-136">`default(T)`: Abrufen des Standardwerts von Typ `T`</span><span class="sxs-lookup"><span data-stu-id="1c2d8-136">`default(T)`: Obtain default value of type `T`</span></span>
    - <span data-ttu-id="1c2d8-137">`delegate {...}`: Anonyme Funktion (anonyme Methode)</span><span class="sxs-lookup"><span data-stu-id="1c2d8-137">`delegate {...}`: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="1c2d8-138">Unär</span><span class="sxs-lookup"><span data-stu-id="1c2d8-138">Unary</span></span>
    - <span data-ttu-id="1c2d8-139">`+x`: Identität</span><span class="sxs-lookup"><span data-stu-id="1c2d8-139">`+x`: Identity</span></span>
    - <span data-ttu-id="1c2d8-140">`-x`: Negation</span><span class="sxs-lookup"><span data-stu-id="1c2d8-140">`-x`: Negation</span></span>
    - <span data-ttu-id="1c2d8-141">`!x`: Logische Negation</span><span class="sxs-lookup"><span data-stu-id="1c2d8-141">`!x`: Logical negation</span></span>
    - <span data-ttu-id="1c2d8-142">`~x`: Bitweise Negation</span><span class="sxs-lookup"><span data-stu-id="1c2d8-142">`~x`: Bitwise negation</span></span>
    - <span data-ttu-id="1c2d8-143">`++x`: Präinkrement</span><span class="sxs-lookup"><span data-stu-id="1c2d8-143">`++x`: Pre-increment</span></span>
    - <span data-ttu-id="1c2d8-144">`--x`: Prädekrement</span><span class="sxs-lookup"><span data-stu-id="1c2d8-144">`--x`: Pre-decrement</span></span>
    - <span data-ttu-id="1c2d8-145">`(T)x`: Explizites Konvertieren von `x` in den Typ `T`</span><span class="sxs-lookup"><span data-stu-id="1c2d8-145">`(T)x`: Explicitly convert `x` to type `T`</span></span>
    - <span data-ttu-id="1c2d8-146">`await x`: Asynchrones Warten auf den Abschluss von `x`</span><span class="sxs-lookup"><span data-stu-id="1c2d8-146">`await x`: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="1c2d8-147">Multiplikativ</span><span class="sxs-lookup"><span data-stu-id="1c2d8-147">Multiplicative</span></span>
    - <span data-ttu-id="1c2d8-148">`x * y`: Multiplikation</span><span class="sxs-lookup"><span data-stu-id="1c2d8-148">`x * y`: Multiplication</span></span>
    - <span data-ttu-id="1c2d8-149">`x / y`: Division</span><span class="sxs-lookup"><span data-stu-id="1c2d8-149">`x / y`: Division</span></span>
    - <span data-ttu-id="1c2d8-150">`x % y`: Rest</span><span class="sxs-lookup"><span data-stu-id="1c2d8-150">`x % y`: Remainder</span></span>
* <span data-ttu-id="1c2d8-151">Additiv</span><span class="sxs-lookup"><span data-stu-id="1c2d8-151">Additive</span></span>
    - <span data-ttu-id="1c2d8-152">`x + y`: Addition, Zeichenfolgenverkettung, Delegatkombination</span><span class="sxs-lookup"><span data-stu-id="1c2d8-152">`x + y`: Addition, string concatenation, delegate combination</span></span>
    - <span data-ttu-id="1c2d8-153">`x – y`: Subtraktion, Delegatentfernung</span><span class="sxs-lookup"><span data-stu-id="1c2d8-153">`x – y`: Subtraction, delegate removal</span></span>
* <span data-ttu-id="1c2d8-154">Shift</span><span class="sxs-lookup"><span data-stu-id="1c2d8-154">Shift</span></span>
    - <span data-ttu-id="1c2d8-155">`x << y`: Linksverschiebung</span><span class="sxs-lookup"><span data-stu-id="1c2d8-155">`x << y`: Shift left</span></span>
    - <span data-ttu-id="1c2d8-156">`x >> y`: Rechtsverschiebung</span><span class="sxs-lookup"><span data-stu-id="1c2d8-156">`x >> y`: Shift right</span></span>
* <span data-ttu-id="1c2d8-157">Relational und Typtest</span><span class="sxs-lookup"><span data-stu-id="1c2d8-157">Relational and type testing</span></span>
    - <span data-ttu-id="1c2d8-158">`x < y`: Kleiner als</span><span class="sxs-lookup"><span data-stu-id="1c2d8-158">`x < y`: Less than</span></span>
    - <span data-ttu-id="1c2d8-159">`x > y`: Größer als</span><span class="sxs-lookup"><span data-stu-id="1c2d8-159">`x > y`: Greater than</span></span>
    - <span data-ttu-id="1c2d8-160">`x <= y`: Kleiner oder gleich</span><span class="sxs-lookup"><span data-stu-id="1c2d8-160">`x <= y`: Less than or equal</span></span>
    - <span data-ttu-id="1c2d8-161">`x >= y`: Größer oder gleich</span><span class="sxs-lookup"><span data-stu-id="1c2d8-161">`x >= y`: Greater than or equal</span></span>
    - <span data-ttu-id="1c2d8-162">`x is T`: `true` zurückgeben, wenn `x` ein `T` ist, andernfalls `false`</span><span class="sxs-lookup"><span data-stu-id="1c2d8-162">`x is T`: Return `true` if `x` is a `T`, `false` otherwise</span></span>
    - <span data-ttu-id="1c2d8-163">`x as T`: `x` als `T` typisiert zurückgeben, oder `null`, wenn `x` kein `T` ist</span><span class="sxs-lookup"><span data-stu-id="1c2d8-163">`x as T`: Return `x` typed as `T`, or `null` if `x` is not a `T`</span></span>
* <span data-ttu-id="1c2d8-164">Gleichheit</span><span class="sxs-lookup"><span data-stu-id="1c2d8-164">Equality</span></span>
    - <span data-ttu-id="1c2d8-165">`x == y`: Gleich</span><span class="sxs-lookup"><span data-stu-id="1c2d8-165">`x == y`: Equal</span></span>
    - <span data-ttu-id="1c2d8-166">`x != y`: Ungleich</span><span class="sxs-lookup"><span data-stu-id="1c2d8-166">`x != y`: Not equal</span></span>
* <span data-ttu-id="1c2d8-167">Logisches AND</span><span class="sxs-lookup"><span data-stu-id="1c2d8-167">Logical AND</span></span>
    - <span data-ttu-id="1c2d8-168">`x & y`: Ganzzahliges bitweises AND, boolesches logisches AND</span><span class="sxs-lookup"><span data-stu-id="1c2d8-168">`x & y`: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="1c2d8-169">Logisches XOR</span><span class="sxs-lookup"><span data-stu-id="1c2d8-169">Logical XOR</span></span>
    - <span data-ttu-id="1c2d8-170">`x ^ y`: Ganzzahliges bitweises XOR, boolesches logisches XOR</span><span class="sxs-lookup"><span data-stu-id="1c2d8-170">`x ^ y`: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="1c2d8-171">Logisches OR</span><span class="sxs-lookup"><span data-stu-id="1c2d8-171">Logical OR</span></span>
    - <span data-ttu-id="1c2d8-172">`x | y`: Ganzzahliges bitweises OR, boolesches logisches OR</span><span class="sxs-lookup"><span data-stu-id="1c2d8-172">`x | y`: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="1c2d8-173">Bedingtes AND</span><span class="sxs-lookup"><span data-stu-id="1c2d8-173">Conditional AND</span></span>
    - <span data-ttu-id="1c2d8-174">`x && y`: Wertet `y` nur aus, wenn `x` nicht `false` ist</span><span class="sxs-lookup"><span data-stu-id="1c2d8-174">`x && y`: Evaluates `y` only if `x` is not `false`</span></span>
* <span data-ttu-id="1c2d8-175">Bedingtes OR</span><span class="sxs-lookup"><span data-stu-id="1c2d8-175">Conditional OR</span></span>
    - <span data-ttu-id="1c2d8-176">`x || y`: Wertet `y` nur aus, wenn `x` nicht `true` ist</span><span class="sxs-lookup"><span data-stu-id="1c2d8-176">`x || y`: Evaluates `y` only if `x` is not `true`</span></span>
* <span data-ttu-id="1c2d8-177">NULL-Sammeloperator</span><span class="sxs-lookup"><span data-stu-id="1c2d8-177">Null coalescing</span></span>
    - <span data-ttu-id="1c2d8-178">`x ?? y`: Wertet `y` aus, wenn `x` NULL ist, andernfalls `x`</span><span class="sxs-lookup"><span data-stu-id="1c2d8-178">`x ?? y`: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="1c2d8-179">Bedingt</span><span class="sxs-lookup"><span data-stu-id="1c2d8-179">Conditional</span></span>
    - <span data-ttu-id="1c2d8-180">`x ? y : z`: Wertet `y` aus, wenn `x` `true` ist, `z`, wenn `x` `false` ist</span><span class="sxs-lookup"><span data-stu-id="1c2d8-180">`x ? y : z`: Evaluates `y` if `x` is `true`, `z` if `x` is `false`</span></span>
* <span data-ttu-id="1c2d8-181">Zuweisung oder anonyme Funktion</span><span class="sxs-lookup"><span data-stu-id="1c2d8-181">Assignment or anonymous function</span></span>
    - <span data-ttu-id="1c2d8-182">`x = y`: Zuweisung</span><span class="sxs-lookup"><span data-stu-id="1c2d8-182">`x = y`: Assignment</span></span>
    - <span data-ttu-id="1c2d8-183">`x op= y`: Zusammengesetzte Zuweisung; unterstützte Operatoren sind</span><span class="sxs-lookup"><span data-stu-id="1c2d8-183">`x op= y`: Compound assignment; supported operators are</span></span>
        - <span data-ttu-id="1c2d8-184">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span><span class="sxs-lookup"><span data-stu-id="1c2d8-184">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span></span>
    - <span data-ttu-id="1c2d8-185">`(T x) => y`: Anonyme Funktion (Lambdaausdruck)</span><span class="sxs-lookup"><span data-stu-id="1c2d8-185">`(T x) => y`: Anonymous function (lambda expression)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="1c2d8-186">[Zurück](types-and-variables.md)
[Weiter](statements.md)</span><span class="sxs-lookup"><span data-stu-id="1c2d8-186">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>
