---
title: For...Next-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 6896c6cfb4ec5d6207011e56b72639c459120e53
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404640"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="03ab1-102">For...Next-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03ab1-102">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="03ab1-103">Wiederholt eine Gruppe von-Anweisungen so oft wie angegeben.</span><span class="sxs-lookup"><span data-stu-id="03ab1-103">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="03ab1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03ab1-104">Syntax</span></span>

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="03ab1-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="03ab1-105">Parts</span></span>

|<span data-ttu-id="03ab1-106">Teil</span><span class="sxs-lookup"><span data-stu-id="03ab1-106">Part</span></span>|<span data-ttu-id="03ab1-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="03ab1-107">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="03ab1-108">Erforderlich in der- `For` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="03ab1-108">Required in the `For` statement.</span></span> <span data-ttu-id="03ab1-109">Numerische Variable.</span><span class="sxs-lookup"><span data-stu-id="03ab1-109">Numeric variable.</span></span> <span data-ttu-id="03ab1-110">Die Steuerelement Variable für die Schleife.</span><span class="sxs-lookup"><span data-stu-id="03ab1-110">The control variable for the loop.</span></span> <span data-ttu-id="03ab1-111">Weitere Informationen finden Sie unter [Counter-Argument](#BKMK_Counter) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="03ab1-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="03ab1-112">Optional.</span><span class="sxs-lookup"><span data-stu-id="03ab1-112">Optional.</span></span> <span data-ttu-id="03ab1-113">Der Datentyp von `counter` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-113">Data type of `counter`.</span></span> <span data-ttu-id="03ab1-114">Weitere Informationen finden Sie unter [Counter-Argument](#BKMK_Counter) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="03ab1-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="03ab1-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03ab1-115">Required.</span></span> <span data-ttu-id="03ab1-116">Ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="03ab1-116">Numeric expression.</span></span> <span data-ttu-id="03ab1-117">Der Anfangswert von `counter`.</span><span class="sxs-lookup"><span data-stu-id="03ab1-117">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="03ab1-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03ab1-118">Required.</span></span> <span data-ttu-id="03ab1-119">Ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="03ab1-119">Numeric expression.</span></span> <span data-ttu-id="03ab1-120">Der endgültige Wert von `counter` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-120">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="03ab1-121">Optional.</span><span class="sxs-lookup"><span data-stu-id="03ab1-121">Optional.</span></span> <span data-ttu-id="03ab1-122">Ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="03ab1-122">Numeric expression.</span></span> <span data-ttu-id="03ab1-123">Der Betrag, um den `counter` jedes Mal durch die Schleife um 1 erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="03ab1-123">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="03ab1-124">Optional.</span><span class="sxs-lookup"><span data-stu-id="03ab1-124">Optional.</span></span> <span data-ttu-id="03ab1-125">Eine oder mehrere-Anweisungen zwischen `For` und `Next` , die die angegebene Anzahl von Uhrzeiten ausführen.</span><span class="sxs-lookup"><span data-stu-id="03ab1-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="03ab1-126">Optional.</span><span class="sxs-lookup"><span data-stu-id="03ab1-126">Optional.</span></span> <span data-ttu-id="03ab1-127">Überträgt die Steuerung an die nächste Schleifen Iterations-.</span><span class="sxs-lookup"><span data-stu-id="03ab1-127">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="03ab1-128">Optional.</span><span class="sxs-lookup"><span data-stu-id="03ab1-128">Optional.</span></span> <span data-ttu-id="03ab1-129">Überträgt die Steuerung aus der `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="03ab1-129">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="03ab1-130">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03ab1-130">Required.</span></span> <span data-ttu-id="03ab1-131">Beendet die Definition der `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="03ab1-131">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="03ab1-132">Das- `To` Schlüsselwort wird in dieser Anweisung verwendet, um den Bereich für den Leistungswert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="03ab1-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="03ab1-133">Sie können dieses Schlüsselwort auch im [SELECT... Case-Anweisung](select-case-statement.md) und in Array Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="03ab1-133">You can also use this keyword in the [Select...Case Statement](select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="03ab1-134">Weitere Informationen zu Array Deklarationen finden Sie unter [Dim-Anweisung](dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="03ab1-134">For more information about array declarations, see [Dim Statement](dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="03ab1-135"> Einfache Beispiele</span><span class="sxs-lookup"><span data-stu-id="03ab1-135">Simple Examples</span></span>

<span data-ttu-id="03ab1-136">Sie verwenden eine `For` ...- `Next` Struktur, wenn Sie einen Satz von-Anweisungen so oft wie mehrmals wiederholen möchten.</span><span class="sxs-lookup"><span data-stu-id="03ab1-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="03ab1-137">Im folgenden Beispiel `index` beginnt die-Variable mit einem Wert von 1 und wird bei jeder Iterations Schleife inkrementiert, wobei der Wert von `index` 5 erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="03ab1-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="03ab1-138">Im folgenden Beispiel `number` beginnt die-Variable bei 2 und wird bei jeder Iterations Schleife um 0,25 reduziert, wobei der Wert von `number` 0 erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="03ab1-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="03ab1-139">Das- `Step` Argument von `-.25` reduziert den Wert bei jeder Iterationen der Schleife um 0,25.</span><span class="sxs-lookup"><span data-stu-id="03ab1-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="03ab1-140">Eine [Weile... End While-Anweisung](while-end-while-statement.md) oder [Do... Die Schleifen Anweisung](do-loop-statement.md) funktioniert gut, wenn Sie nicht im Voraus wissen, wie oft die Anweisungen in der Schleife ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="03ab1-140">A [While...End While Statement](while-end-while-statement.md) or [Do...Loop Statement](do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="03ab1-141">Wenn Sie jedoch die Schleife beliebig oft ausführen, `For` ist eine...- `Next` Schleife eine bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="03ab1-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="03ab1-142">Sie bestimmen die Anzahl der Iterationen, wenn Sie die Schleife zum ersten Mal eingeben.</span><span class="sxs-lookup"><span data-stu-id="03ab1-142">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="03ab1-143">Schachtelungs Schleifen</span><span class="sxs-lookup"><span data-stu-id="03ab1-143">Nesting Loops</span></span>

<span data-ttu-id="03ab1-144">Sie können Schleifen schachteln, `For` indem Sie eine Schleife in eine andere einfügen.</span><span class="sxs-lookup"><span data-stu-id="03ab1-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="03ab1-145">Das folgende Beispiel veranschaulicht die `For` `Next` Struktur von Strukturen, die unterschiedliche Schritt Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="03ab1-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="03ab1-146">Die äußere Schleife erstellt eine Zeichenfolge für jede Iterations Schleife.</span><span class="sxs-lookup"><span data-stu-id="03ab1-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="03ab1-147">Die innere Schleife Dekremente eine Schleifen-Counter-Variable für jede Iterations Schleife.</span><span class="sxs-lookup"><span data-stu-id="03ab1-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="03ab1-148">Beim Schachteln von Schleifen muss jede Schleife über eine eindeutige `counter` Variable verfügen.</span><span class="sxs-lookup"><span data-stu-id="03ab1-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="03ab1-149">Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln.</span><span class="sxs-lookup"><span data-stu-id="03ab1-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="03ab1-150">Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.</span><span class="sxs-lookup"><span data-stu-id="03ab1-150">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="03ab1-151">Exit for und Continue für</span><span class="sxs-lookup"><span data-stu-id="03ab1-151">Exit For and Continue For</span></span>

<span data-ttu-id="03ab1-152">Die- `Exit For` Anweisung beendet sofort die `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="03ab1-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="03ab1-153">-Schleife und überträgt die Steuerung an die-Anweisung, die auf die- `Next` Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="03ab1-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="03ab1-154">Die- `Continue For` Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife.</span><span class="sxs-lookup"><span data-stu-id="03ab1-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="03ab1-155">Weitere Informationen finden Sie unter [Continue-Anweisung](continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="03ab1-155">For more information, see [Continue Statement](continue-statement.md).</span></span>

<span data-ttu-id="03ab1-156">Im folgenden Beispiel wird die Verwendung der `Continue For` -Anweisung und der- `Exit For` Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="03ab1-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="03ab1-157">Sie können eine beliebige Anzahl von `Exit For` Anweisungen in einer `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="03ab1-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="03ab1-158">loop.</span><span class="sxs-lookup"><span data-stu-id="03ab1-158">loop.</span></span> <span data-ttu-id="03ab1-159">Bei Verwendung in geschachtelten `For` ...`Next`</span><span class="sxs-lookup"><span data-stu-id="03ab1-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="03ab1-160">Schleifen, `Exit For` beendet die innerste Schleife und überträgt die Steuerung an die nächsthöhere Schachtelungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="03ab1-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="03ab1-161">`Exit For`wird häufig verwendet, nachdem Sie eine Bedingung ausgewertet haben (z. b `If` . in einer... `Then` ...`Else` -Struktur).</span><span class="sxs-lookup"><span data-stu-id="03ab1-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="03ab1-162">Möglicherweise möchten Sie `Exit For` für die folgenden Bedingungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="03ab1-162">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="03ab1-163">Das Fortsetzen der durchlaufen ist unnötig oder unmöglich.</span><span class="sxs-lookup"><span data-stu-id="03ab1-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="03ab1-164">Diese Bedingung kann durch einen fehlerhaften Wert oder eine Beendigungs Anforderung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="03ab1-164">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="03ab1-165">A `Try` ... `Catch` ...`Finally` die Anweisung fängt eine Ausnahme ab.</span><span class="sxs-lookup"><span data-stu-id="03ab1-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="03ab1-166">Sie können `Exit For` am Ende des-Blocks verwenden `Finally` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-166">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="03ab1-167">Sie verfügen über eine Endlosschleife, bei der es sich um eine Schleife handelt, die eine große oder sogar unendliche Anzahl von Zeiten ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="03ab1-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="03ab1-168">Wenn eine solche Bedingung erkannt wird, können Sie verwenden, um die Schleife mit Escapezeichen `Exit For` zu versehen.</span><span class="sxs-lookup"><span data-stu-id="03ab1-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="03ab1-169">Weitere Informationen finden Sie unter [Do... Loop-Anweisung](do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="03ab1-169">For more information, see [Do...Loop Statement](do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="03ab1-170">Technische Implementierung</span><span class="sxs-lookup"><span data-stu-id="03ab1-170">Technical Implementation</span></span>

<span data-ttu-id="03ab1-171">Wenn eine `For` ... `Next` -Schleife gestartet wird, Visual Basic wertet `start` , `end` und aus `step` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="03ab1-172">Visual Basic wertet diese Werte nur zu diesem Zeitpunkt aus und weist dann `start` zu zu `counter` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="03ab1-173">Bevor der-Anweisungsblock ausgeführt wird, wird Visual Basic `counter` mit verglichen `end` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="03ab1-174">Wenn `counter` bereits größer als der- `end` Wert ist (oder kleiner `step` , wenn negativ ist), wird die `For` -Schleife beendet, und die Steuerung wird an die-Anweisung weitergeleitet, die der `Next` Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="03ab1-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="03ab1-175">Andernfalls wird der Anweisungsblock ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03ab1-175">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="03ab1-176">Jedes Mal, wenn Visual Basic `Next` auf die-Anweisung stößt, wird Sie `counter` um erhöht `step` und zur-Anweisung zurückgegeben `For` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="03ab1-177">Auch hier `counter` wird verglichen `end` , und es wird entweder der-Block ausgeführt, oder die Schleife wird beendet, je nach Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="03ab1-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="03ab1-178">Dieser Prozess wird fortgesetzt, bis `counter` `end` eine-Anweisung oder eine- `Exit For` Anweisung gefunden wird</span><span class="sxs-lookup"><span data-stu-id="03ab1-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="03ab1-179">Die-Schleife wird erst beendet, wenn erfolgreich `counter` ist `end` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="03ab1-180">Wenn `counter` gleich ist `end` , wird die-Schleife fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="03ab1-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="03ab1-181">Der Vergleich, der bestimmt, ob der-Block ausgeführt wird, ist, `counter`  <=  `end` Wenn `step` positiv ist und `counter`  >=  `end` Wenn `step` negativ ist.</span><span class="sxs-lookup"><span data-stu-id="03ab1-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="03ab1-182">Wenn Sie den Wert von `counter` in einer Schleife ändern, kann es schwieriger sein, den Code zu lesen und zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="03ab1-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="03ab1-183">Das Ändern des Werts von `start` , `end` oder `step` wirkt sich nicht auf die Iterations Werte aus, die bei der ersten Eingabe der Schleife festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="03ab1-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="03ab1-184">Wenn Sie Schleifen schachteln, signalisiert der Compiler einen Fehler, wenn er auf die-Anweisung einer äußeren Schachtelungs `Next` Ebene vor der- `Next` Anweisung einer inneren Ebene trifft.</span><span class="sxs-lookup"><span data-stu-id="03ab1-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="03ab1-185">Der Compiler kann diesen überlappenden Fehler jedoch nur erkennen, wenn Sie `counter` in jeder `Next` Anweisung angeben.</span><span class="sxs-lookup"><span data-stu-id="03ab1-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="03ab1-186">Schritt Argument</span><span class="sxs-lookup"><span data-stu-id="03ab1-186">Step Argument</span></span>

<span data-ttu-id="03ab1-187">Der Wert von `step` kann entweder positiv oder negativ sein.</span><span class="sxs-lookup"><span data-stu-id="03ab1-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="03ab1-188">Dieser Parameter bestimmt die Schleifen Verarbeitung entsprechend der folgenden Tabelle:</span><span class="sxs-lookup"><span data-stu-id="03ab1-188">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="03ab1-189">**Schrittwert**</span><span class="sxs-lookup"><span data-stu-id="03ab1-189">**Step value**</span></span>|<span data-ttu-id="03ab1-190">**Schleife wird ausgeführt, wenn**</span><span class="sxs-lookup"><span data-stu-id="03ab1-190">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="03ab1-191">Positiv oder NULL</span><span class="sxs-lookup"><span data-stu-id="03ab1-191">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="03ab1-192">Negativ</span><span class="sxs-lookup"><span data-stu-id="03ab1-192">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="03ab1-193">Der Standardwert von `step` ist 1.</span><span class="sxs-lookup"><span data-stu-id="03ab1-193">The default value of `step` is 1.</span></span>

### <a name="counter-argument"></a><a name="BKMK_Counter"></a><span data-ttu-id="03ab1-194">Counter-Argument</span><span class="sxs-lookup"><span data-stu-id="03ab1-194">Counter Argument</span></span>

<span data-ttu-id="03ab1-195">In der folgenden Tabelle wird angegeben, ob `counter` eine neue lokale Variable definiert, die auf die gesamte Schleife beschränkt ist `For…Next` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="03ab1-196">Diese Bestimmung hängt davon ab, ob `datatype` vorhanden ist und ob `counter` bereits definiert ist.</span><span class="sxs-lookup"><span data-stu-id="03ab1-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="03ab1-197">Ist `datatype` vorhanden?</span><span class="sxs-lookup"><span data-stu-id="03ab1-197">Is `datatype` present?</span></span>|<span data-ttu-id="03ab1-198">Ist `counter` bereits definiert?</span><span class="sxs-lookup"><span data-stu-id="03ab1-198">Is `counter` already defined?</span></span>|<span data-ttu-id="03ab1-199">Result (ob `counter` eine neue lokale Variable definiert, die auf die gesamte Schleife beschränkt ist `For...Next` )</span><span class="sxs-lookup"><span data-stu-id="03ab1-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="03ab1-200">Nein</span><span class="sxs-lookup"><span data-stu-id="03ab1-200">No</span></span>|<span data-ttu-id="03ab1-201">Ja</span><span class="sxs-lookup"><span data-stu-id="03ab1-201">Yes</span></span>|<span data-ttu-id="03ab1-202">Nein, da `counter` bereits definiert ist.</span><span class="sxs-lookup"><span data-stu-id="03ab1-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="03ab1-203">Wenn der Bereich von `counter` für die Prozedur nicht lokal ist, tritt eine Warnung zur Kompilierzeit auf.</span><span class="sxs-lookup"><span data-stu-id="03ab1-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="03ab1-204">Nein</span><span class="sxs-lookup"><span data-stu-id="03ab1-204">No</span></span>|<span data-ttu-id="03ab1-205">Nein</span><span class="sxs-lookup"><span data-stu-id="03ab1-205">No</span></span>|<span data-ttu-id="03ab1-206">Ja.</span><span class="sxs-lookup"><span data-stu-id="03ab1-206">Yes.</span></span> <span data-ttu-id="03ab1-207">Der-Datentyp wird aus den `start` Ausdrücken, `end` und abgeleitet `step` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="03ab1-208">Weitere Informationen zum Typrückschluss finden Sie unter [Option Infer-Anweisung](option-infer-statement.md) und [lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="03ab1-208">For information about type inference, see [Option Infer Statement](option-infer-statement.md) and [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="03ab1-209">Ja</span><span class="sxs-lookup"><span data-stu-id="03ab1-209">Yes</span></span>|<span data-ttu-id="03ab1-210">Ja</span><span class="sxs-lookup"><span data-stu-id="03ab1-210">Yes</span></span>|<span data-ttu-id="03ab1-211">Ja, aber nur, wenn die vorhandene `counter` Variable außerhalb der Prozedur definiert ist.</span><span class="sxs-lookup"><span data-stu-id="03ab1-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="03ab1-212">Diese Variable bleibt getrennt.</span><span class="sxs-lookup"><span data-stu-id="03ab1-212">That variable remains separate.</span></span> <span data-ttu-id="03ab1-213">Wenn der Gültigkeitsbereich der vorhandenen `counter` Variablen für die Prozedur lokal ist, tritt ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="03ab1-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="03ab1-214">Ja</span><span class="sxs-lookup"><span data-stu-id="03ab1-214">Yes</span></span>|<span data-ttu-id="03ab1-215">Nein</span><span class="sxs-lookup"><span data-stu-id="03ab1-215">No</span></span>|<span data-ttu-id="03ab1-216">Ja.</span><span class="sxs-lookup"><span data-stu-id="03ab1-216">Yes.</span></span>|

<span data-ttu-id="03ab1-217">Der-Datentyp `counter` bestimmt den Typ der Iterations, bei dem es sich um einen der folgenden Typen handeln muss:</span><span class="sxs-lookup"><span data-stu-id="03ab1-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="03ab1-218">`Byte`, `SByte` ,, `UShort` `Short` , `UInteger` , `Integer` , `ULong` , `Long` , `Decimal` , `Single` Oder `Double` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="03ab1-219">Eine Enumeration, die Sie mit einer [enumerationsanweisung](enum-statement.md)deklarieren.</span><span class="sxs-lookup"><span data-stu-id="03ab1-219">An enumeration that you declare by using an [Enum Statement](enum-statement.md).</span></span>

- <span data-ttu-id="03ab1-220">Ein `Object`-Element.</span><span class="sxs-lookup"><span data-stu-id="03ab1-220">An `Object`.</span></span>

- <span data-ttu-id="03ab1-221">Ein Typ `T` , der über die folgenden Operatoren verfügt, wobei `B` ein Typ ist, der in einem-Ausdruck verwendet werden kann `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="03ab1-222">Optional können Sie die `counter` Variable in der- `Next` Anweisung angeben.</span><span class="sxs-lookup"><span data-stu-id="03ab1-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="03ab1-223">Diese Syntax verbessert die Lesbarkeit des Programms, insbesondere, wenn Sie über `For` schsted Loops verfügen.</span><span class="sxs-lookup"><span data-stu-id="03ab1-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="03ab1-224">Sie müssen die Variable angeben, die in der entsprechenden-Anweisung angezeigt wird `For` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="03ab1-225">Die `start` `end` -,-und- `step` Ausdrücke können zu jedem Datentyp ausgewertet werden, der zum Typ von erweitert wird `counter` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="03ab1-226">Wenn Sie für einen benutzerdefinierten Typ verwenden `counter` , müssen Sie möglicherweise den `CType` Konvertierungs Operator definieren, um die Typen von `start` , `end` oder `step` in den Typ von zu konvertieren `counter` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="03ab1-227">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03ab1-227">Example</span></span>

<span data-ttu-id="03ab1-228">Im folgenden Beispiel werden alle Elemente aus einer generischen Liste entfernt.</span><span class="sxs-lookup"><span data-stu-id="03ab1-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="03ab1-229">Anstelle eines [für jeden... Next-Anweisung](for-each-next-statement.md): das Beispiel zeigt eine `For` ...- `Next` Anweisung, die in absteigender Reihenfolge durchläuft.</span><span class="sxs-lookup"><span data-stu-id="03ab1-229">Instead of a [For Each...Next Statement](for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="03ab1-230">Im Beispiel wird diese Technik verwendet, da die- `removeAt` Methode bewirkt, dass Elemente hinter dem entfernten Element einen niedrigeren Indexwert haben.</span><span class="sxs-lookup"><span data-stu-id="03ab1-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="03ab1-231">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03ab1-231">Example</span></span>

<span data-ttu-id="03ab1-232">Das folgende Beispiel durchläuft eine Enumeration, die mithilfe einer [enumerationsanweisung](enum-statement.md)deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="03ab1-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="03ab1-233">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03ab1-233">Example</span></span>

<span data-ttu-id="03ab1-234">Im folgenden Beispiel wird für die-Anweisungs Parameter eine-Klasse verwendet, die über Operator Überladungen für die `+` `-` `>=` Operatoren,, und verfügt `<=` .</span><span class="sxs-lookup"><span data-stu-id="03ab1-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="03ab1-235">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03ab1-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="03ab1-236">Schleifenstrukturen</span><span class="sxs-lookup"><span data-stu-id="03ab1-236">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="03ab1-237">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="03ab1-237">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="03ab1-238">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="03ab1-238">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="03ab1-239">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="03ab1-239">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="03ab1-240">Exit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="03ab1-240">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="03ab1-241">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="03ab1-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
