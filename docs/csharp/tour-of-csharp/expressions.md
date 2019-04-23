---
title: C#-Ausdrücke – Überblick über C#
description: Ausdrücke, Operanden und Operatoren sind Bausteine der Sprache C#.
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 4ffe947a4cb8c36a5925a4b3846486e44a9d8ec4
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480754"
---
# <a name="expressions"></a><span data-ttu-id="01440-103">Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="01440-103">Expressions</span></span>

<span data-ttu-id="01440-104">*Ausdrücke* bestehen aus *Operanden* und *Operatoren*.</span><span class="sxs-lookup"><span data-stu-id="01440-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="01440-105">Die Operatoren eines Ausdrucks geben an, welche Operationen auf die Operanden angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="01440-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="01440-106">Beispiele für Operatoren sind `+`, `-`, `*`, `/` und `new`.</span><span class="sxs-lookup"><span data-stu-id="01440-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="01440-107">Beispiele für Operanden sind Literale, Felder, lokale Variablen und Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="01440-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="01440-108">Wenn ein Ausdruck mehrere Operatoren enthält, bestimmt die *Rangfolge* der Operatoren die Reihenfolge, in der die einzelnen Operatoren ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="01440-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="01440-109">Der Ausdruck `x + y * z` wird z.B. als `x + (y * z)` ausgewertet, da der `*`-Operator Vorrang vor dem `+`-Operator hat.</span><span class="sxs-lookup"><span data-stu-id="01440-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="01440-110">Tritt ein Operand zwischen zwei Operatoren mit gleicher Rangfolge auf, steuert die *Assoziativität* der Operatoren die Reihenfolge, in der die Vorgänge ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="01440-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

* <span data-ttu-id="01440-111">Mit Ausnahme der Zuweisungsoperatoren sind alle binären Operatoren *linksassoziativ*, was bedeutet, dass Vorgänge von links nach rechts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="01440-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="01440-112">`x + y + z` wird beispielsweise als `(x + y) + z` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="01440-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
* <span data-ttu-id="01440-113">Die Zuweisungsoperatoren und der bedingte Operator (`?:`) sind *rechtsassoziativ*, d.h., die Operationen werden von rechts nach links ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="01440-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="01440-114">`x = y = z` wird beispielsweise als `x = (y = z)` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="01440-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="01440-115">Rangfolge und Assoziativität können mit Klammern gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="01440-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="01440-116">In `x + y * z` wird beispielsweise zuerst `y` mit `z` multipliziert und dann das Ergebnis zu `x` addiert, aber in `(x + y) * z` werden zunächst `x` und `y` addiert, und dann wird das Ergebnis mit `z` multipliziert.</span><span class="sxs-lookup"><span data-stu-id="01440-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="01440-117">Die meisten Operatoren können *überladen* werden.</span><span class="sxs-lookup"><span data-stu-id="01440-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="01440-118">Das Überladen von Operatoren ermöglicht die Angabe benutzerdefinierter Operatorimplementierungen für Vorgänge, in denen einer der Operanden oder beide einer benutzerdefinierten Klasse oder einem benutzerdefinierten Strukturtyp angehören.</span><span class="sxs-lookup"><span data-stu-id="01440-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="01440-119">In der folgenden Übersicht der C#-Operatoren werden die Operatorkategorien gemäß der Rangfolge von oben nach unten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="01440-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="01440-120">Operatoren der gleichen Kategorie haben den gleichen Rang.</span><span class="sxs-lookup"><span data-stu-id="01440-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="01440-121">Jede Kategorie enthält eine Liste von Ausdrücken mit der Beschreibung des jeweiligen Ausdruckstyps.</span><span class="sxs-lookup"><span data-stu-id="01440-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="01440-122">Primär</span><span class="sxs-lookup"><span data-stu-id="01440-122">Primary</span></span>
  - `x.m`<span data-ttu-id="01440-123">: Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="01440-123">: Member access</span></span>
  - `x(...)`<span data-ttu-id="01440-124">: Methoden- und Delegataufruf</span><span class="sxs-lookup"><span data-stu-id="01440-124">: Method and delegate invocation</span></span>
  - `x[...]`<span data-ttu-id="01440-125">: Array- und Indexerzugriff</span><span class="sxs-lookup"><span data-stu-id="01440-125">: Array and indexer access</span></span>
  - `x++`<span data-ttu-id="01440-126">: Postinkrement</span><span class="sxs-lookup"><span data-stu-id="01440-126">: Post-increment</span></span>
  - `x--`<span data-ttu-id="01440-127">: Postdekrement</span><span class="sxs-lookup"><span data-stu-id="01440-127">: Post-decrement</span></span>
  - `new T(...)`<span data-ttu-id="01440-128">: Objekt- und Delegaterstellung</span><span class="sxs-lookup"><span data-stu-id="01440-128">: Object and delegate creation</span></span>
  - `new T(...){...}`<span data-ttu-id="01440-129">: Objekterstellung mit Initialisierer</span><span class="sxs-lookup"><span data-stu-id="01440-129">: Object creation with initializer</span></span>
  - `new {...}`<span data-ttu-id="01440-130">:  Anonymer Objektinitialisierer</span><span class="sxs-lookup"><span data-stu-id="01440-130">:  Anonymous object initializer</span></span>
  - `new T[...]`<span data-ttu-id="01440-131">: Arrayerstellung</span><span class="sxs-lookup"><span data-stu-id="01440-131">: Array creation</span></span>
  - `typeof(T)`<span data-ttu-id="01440-132">: Abrufen von <xref:System.Type>-Objekt für</span><span class="sxs-lookup"><span data-stu-id="01440-132">: Obtain <xref:System.Type> object for</span></span> `T`
  - `checked(x)`<span data-ttu-id="01440-133">: Auswerten von Ausdrücken in geprüftem Kontext</span><span class="sxs-lookup"><span data-stu-id="01440-133">: Evaluate expression in checked context</span></span>
  - `unchecked(x)`<span data-ttu-id="01440-134">: Auswerten von Ausdrücken in nicht geprüftem Kontext</span><span class="sxs-lookup"><span data-stu-id="01440-134">: Evaluate expression in unchecked context</span></span>
  - `default(T)`<span data-ttu-id="01440-135">: Abrufen des Standardwerts vom Typ</span><span class="sxs-lookup"><span data-stu-id="01440-135">: Obtain default value of type</span></span> `T`
  - `delegate {...}`<span data-ttu-id="01440-136">: Anonyme Funktion (anonyme Methode)</span><span class="sxs-lookup"><span data-stu-id="01440-136">: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="01440-137">Unär</span><span class="sxs-lookup"><span data-stu-id="01440-137">Unary</span></span>
  - `+x`<span data-ttu-id="01440-138">: Identität</span><span class="sxs-lookup"><span data-stu-id="01440-138">: Identity</span></span>
  - `-x`<span data-ttu-id="01440-139">: Negation</span><span class="sxs-lookup"><span data-stu-id="01440-139">: Negation</span></span>
  - `!x`<span data-ttu-id="01440-140">: Logische Negation</span><span class="sxs-lookup"><span data-stu-id="01440-140">: Logical negation</span></span>
  - `~x`<span data-ttu-id="01440-141">: Bitweise Negation</span><span class="sxs-lookup"><span data-stu-id="01440-141">: Bitwise negation</span></span>
  - `++x`<span data-ttu-id="01440-142">: Präinkrement</span><span class="sxs-lookup"><span data-stu-id="01440-142">: Pre-increment</span></span>
  - `--x`<span data-ttu-id="01440-143">: Prädekrement</span><span class="sxs-lookup"><span data-stu-id="01440-143">: Pre-decrement</span></span>
  - `(T)x`<span data-ttu-id="01440-144">: Explizites Konvertieren von `x` in den Typ</span><span class="sxs-lookup"><span data-stu-id="01440-144">: Explicitly convert `x` to type</span></span> `T`
  - `await x`<span data-ttu-id="01440-145">: Asynchrones Warten auf den Abschluss von `x`</span><span class="sxs-lookup"><span data-stu-id="01440-145">: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="01440-146">Multiplikativ</span><span class="sxs-lookup"><span data-stu-id="01440-146">Multiplicative</span></span>
  - `x * y`<span data-ttu-id="01440-147">: Multiplikation</span><span class="sxs-lookup"><span data-stu-id="01440-147">: Multiplication</span></span>
  - `x / y`<span data-ttu-id="01440-148">: Division</span><span class="sxs-lookup"><span data-stu-id="01440-148">: Division</span></span>
  - `x % y`<span data-ttu-id="01440-149">: Rest</span><span class="sxs-lookup"><span data-stu-id="01440-149">: Remainder</span></span>
* <span data-ttu-id="01440-150">Additiv</span><span class="sxs-lookup"><span data-stu-id="01440-150">Additive</span></span>
  - `x + y`<span data-ttu-id="01440-151">: Addition, Zeichenfolgenverkettung, Delegatkombination</span><span class="sxs-lookup"><span data-stu-id="01440-151">: Addition, string concatenation, delegate combination</span></span>
  - `x – y`<span data-ttu-id="01440-152">: Subtraktion, Delegatentfernung</span><span class="sxs-lookup"><span data-stu-id="01440-152">: Subtraction, delegate removal</span></span>
* <span data-ttu-id="01440-153">Shift</span><span class="sxs-lookup"><span data-stu-id="01440-153">Shift</span></span>
  - `x << y`<span data-ttu-id="01440-154">: Linksverschiebung</span><span class="sxs-lookup"><span data-stu-id="01440-154">: Shift left</span></span>
  - `x >> y`<span data-ttu-id="01440-155">: Rechtsverschiebung</span><span class="sxs-lookup"><span data-stu-id="01440-155">: Shift right</span></span>
* <span data-ttu-id="01440-156">Relational und Typtest</span><span class="sxs-lookup"><span data-stu-id="01440-156">Relational and type testing</span></span>
  - `x < y`<span data-ttu-id="01440-157">: Kleiner als </span><span class="sxs-lookup"><span data-stu-id="01440-157">: Less than</span></span>
  - `x > y`<span data-ttu-id="01440-158">: Größer als</span><span class="sxs-lookup"><span data-stu-id="01440-158">: Greater than</span></span>
  - `x <= y`<span data-ttu-id="01440-159">: Kleiner oder gleich </span><span class="sxs-lookup"><span data-stu-id="01440-159">: Less than or equal</span></span>
  - `x >= y`<span data-ttu-id="01440-160">: Größer oder gleich</span><span class="sxs-lookup"><span data-stu-id="01440-160">: Greater than or equal</span></span>
  - `x is T`<span data-ttu-id="01440-161">: `true` zurückgeben, wenn `x` ein `T` ist, andernfalls `false`</span><span class="sxs-lookup"><span data-stu-id="01440-161">: Return `true` if `x` is a `T`, `false` otherwise</span></span>
  - `x as T`<span data-ttu-id="01440-162">: `x`als `T` typisiert zurückgeben, oder `null`,wenn `x` kein ist</span><span class="sxs-lookup"><span data-stu-id="01440-162">: Return `x` typed as `T`, or `null` if `x` is not a</span></span> `T`
* <span data-ttu-id="01440-163">Gleichheit</span><span class="sxs-lookup"><span data-stu-id="01440-163">Equality</span></span>
  - `x == y`<span data-ttu-id="01440-164">: Gleich</span><span class="sxs-lookup"><span data-stu-id="01440-164">: Equal</span></span>
  - `x != y`<span data-ttu-id="01440-165">: Ungleich</span><span class="sxs-lookup"><span data-stu-id="01440-165">: Not equal</span></span>
* <span data-ttu-id="01440-166">Logisches AND</span><span class="sxs-lookup"><span data-stu-id="01440-166">Logical AND</span></span>
  - `x & y`<span data-ttu-id="01440-167">: Ganzzahliges bitweises AND, boolesches logisches AND</span><span class="sxs-lookup"><span data-stu-id="01440-167">: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="01440-168">Logisches XOR</span><span class="sxs-lookup"><span data-stu-id="01440-168">Logical XOR</span></span>
  - `x ^ y`<span data-ttu-id="01440-169">: Ganzzahliges bitweises XOR, boolesches logisches XOR</span><span class="sxs-lookup"><span data-stu-id="01440-169">: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="01440-170">Logisches OR</span><span class="sxs-lookup"><span data-stu-id="01440-170">Logical OR</span></span>
  - `x | y`<span data-ttu-id="01440-171">: Ganzzahliges bitweises OR, boolesches logisches OR</span><span class="sxs-lookup"><span data-stu-id="01440-171">: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="01440-172">Bedingtes AND</span><span class="sxs-lookup"><span data-stu-id="01440-172">Conditional AND</span></span>
  - `x && y`<span data-ttu-id="01440-173">: Wertet `y` nur aus, wenn `x` nicht ist</span><span class="sxs-lookup"><span data-stu-id="01440-173">: Evaluates `y` only if `x` is not</span></span> `false`
* <span data-ttu-id="01440-174">Bedingtes OR</span><span class="sxs-lookup"><span data-stu-id="01440-174">Conditional OR</span></span>
  - `x || y`<span data-ttu-id="01440-175">: Wertet `y` nur aus, wenn `x` nicht ist</span><span class="sxs-lookup"><span data-stu-id="01440-175">: Evaluates `y` only if `x` is not</span></span> `true`
* <span data-ttu-id="01440-176">NULL-Sammeloperator</span><span class="sxs-lookup"><span data-stu-id="01440-176">Null coalescing</span></span>
  - `x ?? y`<span data-ttu-id="01440-177">: Wird zu `y` ausgewertet, wenn `x` NULL ist, andernfalls zu `x`</span><span class="sxs-lookup"><span data-stu-id="01440-177">: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="01440-178">Bedingt</span><span class="sxs-lookup"><span data-stu-id="01440-178">Conditional</span></span>
  - `x ? y : z`<span data-ttu-id="01440-179">: Wertet `y` aus, wenn `x` `true`ist, `z`, wenn `x` ist</span><span class="sxs-lookup"><span data-stu-id="01440-179">: Evaluates `y` if `x` is `true`, `z` if `x` is</span></span> `false`
* <span data-ttu-id="01440-180">Zuweisung oder anonyme Funktion</span><span class="sxs-lookup"><span data-stu-id="01440-180">Assignment or anonymous function</span></span>
  - `x = y`<span data-ttu-id="01440-181">: Zuweisung</span><span class="sxs-lookup"><span data-stu-id="01440-181">: Assignment</span></span>
  - `x op= y`<span data-ttu-id="01440-182">: Zusammengesetzte Zuweisung; unterstützte Operatoren sind</span><span class="sxs-lookup"><span data-stu-id="01440-182">: Compound assignment; supported operators are</span></span>
    - `*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`
  - `(T x) => y`<span data-ttu-id="01440-183">: Anonyme Funktion (Lambda-Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="01440-183">: Anonymous function (lambda expression)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="01440-184">[Zurück](types-and-variables.md)
> [Weiter](statements.md)</span><span class="sxs-lookup"><span data-stu-id="01440-184">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>
