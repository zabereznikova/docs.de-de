---
title: for (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: 2c099411499c6ca8396c55955bdc634e48caf621
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/18/2018
ms.locfileid: "34306526"
---
# <a name="for-c-reference"></a><span data-ttu-id="6ca01-102">for (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6ca01-102">for (C# reference)</span></span>

<span data-ttu-id="6ca01-103">Mithilfe einer `for`-Schleife können Sie eine Anweisung oder einen Anweisungsblock wiederholt ausführen, bis ein bestimmter Ausdruck nach `false` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="6ca01-103">By using a `for` loop, you can run a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="6ca01-104">Diese Art von Schleife eignet sich für Iterationen von Arrays und für andere Anwendungen, in denen Sie im Voraus wissen, wie oft die Schleife durchlaufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="6ca01-104">This kind of loop is useful for iterating over arrays and for other applications in which you know in advance how many times you want the loop to iterate.</span></span>
  
## <a name="example"></a><span data-ttu-id="6ca01-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ca01-105">Example</span></span>

<span data-ttu-id="6ca01-106">Im folgenden Beispiel wird der `i`-Wert in die Konsole geschrieben und bei jeder Iteration der Schleife um 1 erhöht:</span><span class="sxs-lookup"><span data-stu-id="6ca01-106">In the following example, the value of `i` is written to the console and incremented by 1 during each iteration of the loop:</span></span>
  
[!code-csharp[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]
  
<span data-ttu-id="6ca01-107">Die [for-Anweisung](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement) im vorherigen Beispiel führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6ca01-107">The [for statement](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement) in the previous example performs the following actions:</span></span>
  
1.  <span data-ttu-id="6ca01-108">Zuerst wird der Anfangswert der Variable `i` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6ca01-108">First, the initial value of variable `i` is established.</span></span> <span data-ttu-id="6ca01-109">Dieser Schritt wird unabhängig davon, wie oft die Schleife wiederholt wird, nur einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6ca01-109">This step happens only once, regardless of how many times the loop repeats.</span></span> <span data-ttu-id="6ca01-110">Sie können sich diese Initialisierung als außerhalb der Schleife erfolgend vorstellen.</span><span class="sxs-lookup"><span data-stu-id="6ca01-110">You can think of this initialization as happening outside the looping process.</span></span>
  
2.  <span data-ttu-id="6ca01-111">Um die Bedingung (`i <= 5`) auszuwerten, wird der Wert `i` mit 5 verglichen.</span><span class="sxs-lookup"><span data-stu-id="6ca01-111">To evaluate the condition (`i <= 5`), the value of `i` is compared to 5.</span></span>
  
    -   <span data-ttu-id="6ca01-112">Wenn `i` ist kleiner als oder gleich 5 ist, wird die Bedingung nach `true` ausgewertet, und die folgenden Aktionen werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6ca01-112">If `i` is less than or equal to 5, the condition evaluates to `true`, and the following actions occur.</span></span>  
  
        1.  <span data-ttu-id="6ca01-113">In der `Console.WriteLine`-Anweisung im Hauptteil der Schleife wird der `i`-Wert dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6ca01-113">The `Console.WriteLine` statement in the body of the loop displays the value of `i`.</span></span>  
  
        2.  <span data-ttu-id="6ca01-114">Der `i`-Wert wird um 1 inkrementiert.</span><span class="sxs-lookup"><span data-stu-id="6ca01-114">The value of `i` is incremented by 1.</span></span>  
  
        3.  <span data-ttu-id="6ca01-115">Die Schleife kehrt zum Start von Schritt 2 zurück, um die Bedingung erneut auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="6ca01-115">The loop returns to the start of step 2 to evaluate the condition again.</span></span>  
  
    -   <span data-ttu-id="6ca01-116">Wenn `i` größer als 5 ist, wird die Bedingung nach `false` ausgewertet, und Sie beenden die Schleife.</span><span class="sxs-lookup"><span data-stu-id="6ca01-116">If `i` is greater than 5, the condition evaluates to `false`, and you exit the loop.</span></span>  
  
<span data-ttu-id="6ca01-117">Beachten Sie, dass wenn der ursprüngliche `i`-Wert größer als 5 ist, wird der Hauptteil der Schleife kein einziges Mal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6ca01-117">Note that, if the initial value of `i` is greater than 5, the body of the loop doesn't run even once.</span></span>

## <a name="sections-of-a-for-statement"></a><span data-ttu-id="6ca01-118">Abschnitte einer for-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6ca01-118">Sections of a for statement</span></span>
  
<span data-ttu-id="6ca01-119">Jede [for-Anweisung](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement) definiert die Abschnitte *Initialisierer*, *Bedingung* und *Iterator*.</span><span class="sxs-lookup"><span data-stu-id="6ca01-119">Every [for statement](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement) defines *initializer*, *condition*, and *iterator* sections.</span></span> <span data-ttu-id="6ca01-120">Diese Abschnitte bestimmen, wie oft die Schleife in der Regel durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="6ca01-120">These sections usually determine how many times the loop iterates.</span></span>  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
<span data-ttu-id="6ca01-121">Diese Abschnitte dienen den folgenden Zwecken:</span><span class="sxs-lookup"><span data-stu-id="6ca01-121">The sections serve the following purposes:</span></span>
  
-   <span data-ttu-id="6ca01-122">Im Initialisiererabschnitt werden die anfänglichen Bedingung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6ca01-122">The initializer section sets the initial conditions.</span></span> <span data-ttu-id="6ca01-123">Die Anweisungen in diesem Abschnitt werden nur einmal ausgeführt, bevor die Schleife beginnt.</span><span class="sxs-lookup"><span data-stu-id="6ca01-123">The statements in this section run only once, before you enter the loop.</span></span> <span data-ttu-id="6ca01-124">Der Abschnitt kann nur eine der beiden folgenden Optionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="6ca01-124">The section can contain only one of the following two options.</span></span>  
  
    -   <span data-ttu-id="6ca01-125">Die Deklaration und die Initialisierung einer lokalen Schleifenvariablen, wie das erste Beispiel zeigt (`int i = 1`).</span><span class="sxs-lookup"><span data-stu-id="6ca01-125">The declaration and initialization of a local loop variable, as the first example shows (`int i = 1`).</span></span> <span data-ttu-id="6ca01-126">Die Variable ist in der Schleife lokal; ein Zugriff darauf von außerhalb der Schleife ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="6ca01-126">The variable is local to the loop and can't be accessed from outside the loop.</span></span>  
  
    -   <span data-ttu-id="6ca01-127">Null oder mehr Anweisungsausdrücke aus der folgenden Liste, durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="6ca01-127">Zero or more statement expressons from the following list, separated by commas.</span></span>  
  
        -   <span data-ttu-id="6ca01-128">[Zuweisungsanweisung](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="6ca01-128">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
        -   <span data-ttu-id="6ca01-129">Aufruf einer Methode</span><span class="sxs-lookup"><span data-stu-id="6ca01-129">invocation of a method</span></span>  
  
        -   <span data-ttu-id="6ca01-130">Präfix- oder Postfix-[Inkrementausdruck](../../../csharp/language-reference/operators/increment-operator.md), z.B. `++i` oder `i++`</span><span class="sxs-lookup"><span data-stu-id="6ca01-130">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
        -   <span data-ttu-id="6ca01-131">Präfix- oder Postfix-[Dekrementausdruck](../../../csharp/language-reference/operators/decrement-operator.md), z.B. `--i` oder `i--`</span><span class="sxs-lookup"><span data-stu-id="6ca01-131">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
        -   <span data-ttu-id="6ca01-132">Erstellung eines Objekts mithilfe von [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="6ca01-132">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
        -   <span data-ttu-id="6ca01-133">[await](../../../csharp/language-reference/keywords/await.md)-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="6ca01-133">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="6ca01-134">Der Bedingungsabschnitt enthält einen booleschen Ausdruck, der ausgewertet wird, um festzustellen, ob die Schleife beendet oder erneut ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6ca01-134">The condition section contains a boolean expression that’s evaluated to determine whether the loop should exit or should run again.</span></span>  
  
-   <span data-ttu-id="6ca01-135">Der Iteratorabschnitt definiert, was nach jeder Iteration des Hauptteils der Schleife geschieht.</span><span class="sxs-lookup"><span data-stu-id="6ca01-135">The iterator section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="6ca01-136">Der Iteratorabschnitt enthält keine oder mehrere der folgenden Anweisungsausdrücke, durch Kommas getrennt:</span><span class="sxs-lookup"><span data-stu-id="6ca01-136">The iterator section contains zero or more of the following statement expressions, separated by commas:</span></span>  
  
    -   <span data-ttu-id="6ca01-137">[Zuweisungsanweisung](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="6ca01-137">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
    -   <span data-ttu-id="6ca01-138">Aufruf einer Methode</span><span class="sxs-lookup"><span data-stu-id="6ca01-138">invocation of a method</span></span>  
  
    -   <span data-ttu-id="6ca01-139">Präfix- oder Postfix-[Inkrementausdruck](../../../csharp/language-reference/operators/increment-operator.md), z.B. `++i` oder `i++`</span><span class="sxs-lookup"><span data-stu-id="6ca01-139">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
    -   <span data-ttu-id="6ca01-140">Präfix- oder Postfix-[Dekrementausdruck](../../../csharp/language-reference/operators/decrement-operator.md), z.B. `--i` oder `i--`</span><span class="sxs-lookup"><span data-stu-id="6ca01-140">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
    -   <span data-ttu-id="6ca01-141">Erstellung eines Objekts mithilfe von [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="6ca01-141">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
    -   <span data-ttu-id="6ca01-142">[await](../../../csharp/language-reference/keywords/await.md)-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="6ca01-142">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="6ca01-143">Der Hauptteil der Schleife besteht aus einer Anweisung, einer leeren Anweisung oder einem Block von Anweisungen, die Sie erstellen, indem Sie 0 (null) oder mehrere Anweisungen in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="6ca01-143">The body of the loop consists of a statement, an empty statement, or a block of statements, which you create by enclosing zero or more statements in braces.</span></span>  
  
     <span data-ttu-id="6ca01-144">Sie können die Schleife an jedem Punkt im `for`-Block mit dem Schlüsselwort [break](../../../csharp/language-reference/keywords/break.md) unterbrechen oder mit dem Schlüsselwort [continue](../../../csharp/language-reference/keywords/continue.md) direkt zur nächsten Iteration der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="6ca01-144">You can break out of a `for` loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or you can step to the next iteration by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span> <span data-ttu-id="6ca01-145">Sie können jede beliebige Schleife auch mit einer [goto](../../../csharp/language-reference/keywords/goto.md)-, [return](../../../csharp/language-reference/keywords/return.md)- oder [throw](../../../csharp/language-reference/keywords/throw.md)-Anweisung beenden.</span><span class="sxs-lookup"><span data-stu-id="6ca01-145">You also can exit any loop by using a [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement.</span></span>  
  
<span data-ttu-id="6ca01-146">Im ersten Beispiel in diesem Thema wird die häufigste Art der `for`-Schleife dargestellt, die die folgenden Optionen für die Abschnitte bereitstellt:</span><span class="sxs-lookup"><span data-stu-id="6ca01-146">The first example in this topic shows the most typical kind of `for` loop, which makes the following choices for the sections:</span></span>
  
-   <span data-ttu-id="6ca01-147">Der Initialisierer deklariert und initialisiert Sie eine lokale Schleifenvariable, `i`, die die Iterationen der Schleife mitzählt.</span><span class="sxs-lookup"><span data-stu-id="6ca01-147">The initializer declares and initializes a local loop variable, `i`, that maintains a count of the iterations of the loop.</span></span>  
  
-   <span data-ttu-id="6ca01-148">Die Bedingung überprüft den Wert der Schleifenvariablen gegen einen bekannten endgültigen Wert, 5.</span><span class="sxs-lookup"><span data-stu-id="6ca01-148">The condition checks the value of the loop variable against a known final value, 5.</span></span>  
  
-   <span data-ttu-id="6ca01-149">Der Iterator verwendet eine Postfix-Inkrementanweisung, `i++`, um den Zählerstand jeder Schleife festzuhalten.</span><span class="sxs-lookup"><span data-stu-id="6ca01-149">The iterator section uses a postfix increment statement, `i++`, to tally each iteration of the loop.</span></span>

## <a name="more-examples"></a><span data-ttu-id="6ca01-150">Weitere Beispiele</span><span class="sxs-lookup"><span data-stu-id="6ca01-150">More examples</span></span>
  
<span data-ttu-id="6ca01-151">Das folgende Beispiel veranschaulicht mehrere weniger gängige Optionen: das Zuweisen eines Werts zu einer externen Schleifenvariablen im Initialisierer, das Aufrufen der `Console.WriteLine`-Methode im Initialisierer und im Iterator und das Ändern der Werte zweier Variablen im Iterator.</span><span class="sxs-lookup"><span data-stu-id="6ca01-151">The following example illustrates several less common choices: assigning a value to an external loop variable in the initializer section, invoking the `Console.WriteLine` method in both the initializer and the iterator sections, and changing the values of two variables in the iterator section.</span></span>
  
[!code-csharp[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
<span data-ttu-id="6ca01-152">Alle Ausdrücke, die eine `for`-Anweisung definieren, sind optional.</span><span class="sxs-lookup"><span data-stu-id="6ca01-152">All of the expressions that define a `for` statement are optional.</span></span> <span data-ttu-id="6ca01-153">Die folgende Anweisung erstellt z.B. eine Endlosschleife:</span><span class="sxs-lookup"><span data-stu-id="6ca01-153">For example, the following statement creates an infinite loop:</span></span>
  
[!code-csharp[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6ca01-154">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="6ca01-154">C# language specification</span></span>  

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
  
## <a name="see-also"></a><span data-ttu-id="6ca01-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ca01-155">See also</span></span>

[<span data-ttu-id="6ca01-156">Die for-Anweisung (C#-Spezifikation)</span><span class="sxs-lookup"><span data-stu-id="6ca01-156">The for statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-for-statement)  
[<span data-ttu-id="6ca01-157">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6ca01-157">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="6ca01-158">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6ca01-158">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="6ca01-159">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6ca01-159">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="6ca01-160">foreach, in</span><span class="sxs-lookup"><span data-stu-id="6ca01-160">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
[<span data-ttu-id="6ca01-161">for-Anweisung (C++)</span><span class="sxs-lookup"><span data-stu-id="6ca01-161">for Statement (C++)</span></span>](/cpp/cpp/for-statement-cpp)  
[<span data-ttu-id="6ca01-162">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="6ca01-162">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
