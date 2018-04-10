---
title: for (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cb7e83733fe026658f502b430975a0f8a27e9df3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="for-c-reference"></a><span data-ttu-id="123b0-102">for (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="123b0-102">for (C# Reference)</span></span>
<span data-ttu-id="123b0-103">Mithilfe einer `for`-Schleife können Sie eine Anweisung oder einen Anweisungsblock wiederholt ausführen, bis ein bestimmter Ausdruck nach `false` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="123b0-103">By using a `for` loop, you can run a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="123b0-104">Diese Art von Schleife eignet sich für Iterationen von Arrays und für andere Anwendungen, in denen Sie im Voraus wissen, wie oft die Schleife durchlaufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="123b0-104">This kind of loop is useful for iterating over arrays and for other applications in which you know in advance how many times you want the loop to iterate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="123b0-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="123b0-105">Example</span></span>  
 <span data-ttu-id="123b0-106">Im folgenden Beispiel wird der `i`-Wert in die Konsole geschrieben und bei jeder Iteration der Schleife um 1 erhöht.</span><span class="sxs-lookup"><span data-stu-id="123b0-106">In the following example, the value of `i` is written to the console and incremented by 1 during each iteration of the loop.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]  
  
 <span data-ttu-id="123b0-107">Die `for`-Anweisung im vorherigen Beispiel führt die folgenden Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="123b0-107">The `for` statement in the previous example performs the following actions.</span></span>  
  
1.  <span data-ttu-id="123b0-108">Zuerst wird der Anfangswert der Variable `i` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="123b0-108">First, the initial value of variable `i` is established.</span></span> <span data-ttu-id="123b0-109">Dieser Schritt wird unabhängig davon, wie oft die Schleife wiederholt wird, nur einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="123b0-109">This step happens only once, regardless of how many times the loop repeats.</span></span> <span data-ttu-id="123b0-110">Sie können sich diese Initialisierung als außerhalb der Schleife erfolgend vorstellen.</span><span class="sxs-lookup"><span data-stu-id="123b0-110">You can think of this initialization as happening outside the looping process.</span></span>  
  
2.  <span data-ttu-id="123b0-111">Um die Bedingung (`i <= 5`) auszuwerten, wird der Wert `i` mit 5 verglichen.</span><span class="sxs-lookup"><span data-stu-id="123b0-111">To evaluate the condition (`i <= 5`), the value of `i` is compared to 5.</span></span>  
  
    -   <span data-ttu-id="123b0-112">Wenn `i` ist kleiner als oder gleich 5 ist, wird die Bedingung nach `true` ausgewertet, und die folgenden Aktionen werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="123b0-112">If `i` is less than or equal to 5, the condition evaluates to `true`, and the following actions occur.</span></span>  
  
        1.  <span data-ttu-id="123b0-113">In der `Console.WriteLine`-Anweisung im Hauptteil der Schleife wird der `i`-Wert dargestellt.</span><span class="sxs-lookup"><span data-stu-id="123b0-113">The `Console.WriteLine` statement in the body of the loop displays the value of `i`.</span></span>  
  
        2.  <span data-ttu-id="123b0-114">Der `i`-Wert wird um 1 inkrementiert.</span><span class="sxs-lookup"><span data-stu-id="123b0-114">The value of `i` is incremented by 1.</span></span>  
  
        3.  <span data-ttu-id="123b0-115">Die Schleife kehrt zum Start von Schritt 2 zurück, um die Bedingung erneut auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="123b0-115">The loop returns to the start of step 2 to evaluate the condition again.</span></span>  
  
    -   <span data-ttu-id="123b0-116">Wenn `i` größer als 5 ist, wird die Bedingung nach `false` ausgewertet, und Sie beenden die Schleife.</span><span class="sxs-lookup"><span data-stu-id="123b0-116">If `i` is greater than 5, the condition evaluates to `false`, and you exit the loop.</span></span>  
  
 <span data-ttu-id="123b0-117">Beachten Sie, dass wenn der ursprüngliche `i`-Wert größer als 5 ist, wird der Hauptteil der Schleife kein einziges Mal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="123b0-117">Note that, if the initial value of `i` is greater than 5, the body of the loop doesn't run even once.</span></span>  
  
 <span data-ttu-id="123b0-118">Jede `for`-Anweisung definiert die Abschnitte „Initialisierer“, „Bedingung“ und „Iterator“.</span><span class="sxs-lookup"><span data-stu-id="123b0-118">Every `for` statement defines initializer, condition, and iterator sections.</span></span> <span data-ttu-id="123b0-119">Diese Abschnitte bestimmen, wie oft die Schleife in der Regel durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="123b0-119">These sections usually determine how many times the loop iterates.</span></span>  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
 <span data-ttu-id="123b0-120">Diese Abschnitte dienen den folgenden Zwecken.</span><span class="sxs-lookup"><span data-stu-id="123b0-120">The sections serve the following purposes.</span></span>  
  
-   <span data-ttu-id="123b0-121">Im Initialisiererabschnitt werden die anfänglichen Bedingung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="123b0-121">The initializer section sets the initial conditions.</span></span> <span data-ttu-id="123b0-122">Die Anweisungen in diesem Abschnitt werden nur einmal ausgeführt, bevor die Schleife beginnt.</span><span class="sxs-lookup"><span data-stu-id="123b0-122">The statements in this section run only once, before you enter the loop.</span></span> <span data-ttu-id="123b0-123">Der Abschnitt kann nur eine der beiden folgenden Optionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="123b0-123">The section can contain only one of the following two options.</span></span>  
  
    -   <span data-ttu-id="123b0-124">Die Deklaration und die Initialisierung einer lokalen Schleifenvariablen, wie das erste Beispiel zeigt (`int i = 1`).</span><span class="sxs-lookup"><span data-stu-id="123b0-124">The declaration and initialization of a local loop variable, as the first example shows (`int i = 1`).</span></span> <span data-ttu-id="123b0-125">Die Variable ist in der Schleife lokal; ein Zugriff darauf von außerhalb der Schleife ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="123b0-125">The variable is local to the loop and can't be accessed from outside the loop.</span></span>  
  
    -   <span data-ttu-id="123b0-126">Null oder mehr Anweisungsausdrücke aus der folgenden Liste, durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="123b0-126">Zero or more statement expressons from the following list, separated by commas.</span></span>  
  
        -   <span data-ttu-id="123b0-127">[Zuweisungsanweisung](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="123b0-127">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
        -   <span data-ttu-id="123b0-128">Aufruf einer Methode</span><span class="sxs-lookup"><span data-stu-id="123b0-128">invocation of a method</span></span>  
  
        -   <span data-ttu-id="123b0-129">Präfix- oder Postfix-[Inkrementausdruck](../../../csharp/language-reference/operators/increment-operator.md), z.B. `++i` oder `i++`</span><span class="sxs-lookup"><span data-stu-id="123b0-129">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
        -   <span data-ttu-id="123b0-130">Präfix- oder Postfix-[Dekrementausdruck](../../../csharp/language-reference/operators/decrement-operator.md), z.B. `--i` oder `i--`</span><span class="sxs-lookup"><span data-stu-id="123b0-130">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
        -   <span data-ttu-id="123b0-131">Erstellung eines Objekts mithilfe von [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="123b0-131">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
        -   <span data-ttu-id="123b0-132">[await](../../../csharp/language-reference/keywords/await.md)-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="123b0-132">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="123b0-133">Der Bedingungsabschnitt enthält einen booleschen Ausdruck, der ausgewertet wird, um festzustellen, ob die Schleife beendet oder erneut ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="123b0-133">The condition section contains a boolean expression that’s evaluated to determine whether the loop should exit or should run again.</span></span>  
  
-   <span data-ttu-id="123b0-134">Der Iteratorabschnitt definiert, was nach jeder Iteration des Hauptteils der Schleife geschieht.</span><span class="sxs-lookup"><span data-stu-id="123b0-134">The iterator section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="123b0-135">Der Iteratorabschnitt enthält keine oder mehrere der folgenden Anweisungsausdrücke, durch Kommas getrennt:</span><span class="sxs-lookup"><span data-stu-id="123b0-135">The iterator section contains zero or more of the following statement expressions, separated by commas:</span></span>  
  
    -   <span data-ttu-id="123b0-136">[Zuweisungsanweisung](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="123b0-136">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
    -   <span data-ttu-id="123b0-137">Aufruf einer Methode</span><span class="sxs-lookup"><span data-stu-id="123b0-137">invocation of a method</span></span>  
  
    -   <span data-ttu-id="123b0-138">Präfix- oder Postfix-[Inkrementausdruck](../../../csharp/language-reference/operators/increment-operator.md), z.B. `++i` oder `i++`</span><span class="sxs-lookup"><span data-stu-id="123b0-138">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
    -   <span data-ttu-id="123b0-139">Präfix- oder Postfix-[Dekrementausdruck](../../../csharp/language-reference/operators/decrement-operator.md), z.B. `--i` oder `i--`</span><span class="sxs-lookup"><span data-stu-id="123b0-139">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
    -   <span data-ttu-id="123b0-140">Erstellung eines Objekts mithilfe von [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="123b0-140">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
    -   <span data-ttu-id="123b0-141">[await](../../../csharp/language-reference/keywords/await.md)-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="123b0-141">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="123b0-142">Der Hauptteil der Schleife besteht aus einer Anweisung, einer leeren Anweisung oder einem Block von Anweisungen, die Sie erstellen, indem Sie 0 (null) oder mehrere Anweisungen in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="123b0-142">The body of the loop consists of a statement, an empty statement, or a block of statements, which you create by enclosing zero or more statements in braces.</span></span>  
  
     <span data-ttu-id="123b0-143">Sie können die Schleife an jedem Punkt im `for`-Block mit dem Schlüsselwort [break](../../../csharp/language-reference/keywords/break.md) unterbrechen oder mit dem Schlüsselwort [continue](../../../csharp/language-reference/keywords/continue.md) direkt zur nächsten Iteration der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="123b0-143">You can break out of a `for` loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or you can step to the next iteration by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span> <span data-ttu-id="123b0-144">Sie können jede beliebige Schleife auch mit einer [goto](../../../csharp/language-reference/keywords/goto.md)-, [return](../../../csharp/language-reference/keywords/return.md)- oder [throw](../../../csharp/language-reference/keywords/throw.md)-Anweisung beenden.</span><span class="sxs-lookup"><span data-stu-id="123b0-144">You also can exit any loop by using a [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement.</span></span>  
  
 <span data-ttu-id="123b0-145">Im ersten Beispiel in diesem Thema wird die häufigste Art der `for`-Schleife dargestellt, die die folgenden Optionen für die Abschnitte bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="123b0-145">The first example in this topic shows the most typical kind of `for` loop, which makes the following choices for the sections.</span></span>  
  
-   <span data-ttu-id="123b0-146">Der Initialisierer deklariert und initialisiert Sie eine lokale Schleifenvariable, `i`, die die Iterationen der Schleife mitzählt.</span><span class="sxs-lookup"><span data-stu-id="123b0-146">The initializer declares and initializes a local loop variable, `i`, that maintains a count of the iterations of the loop.</span></span>  
  
-   <span data-ttu-id="123b0-147">Die Bedingung überprüft den Wert der Schleifenvariablen gegen einen bekannten endgültigen Wert, 5.</span><span class="sxs-lookup"><span data-stu-id="123b0-147">The condition checks the value of the loop variable against a known final value, 5.</span></span>  
  
-   <span data-ttu-id="123b0-148">Der Iterator verwendet eine Postfix-Inkrementanweisung, `i++`, um den Zählerstand jeder Schleife festzuhalten.</span><span class="sxs-lookup"><span data-stu-id="123b0-148">The iterator section uses a postfix increment statement, `i++`, to tally each iteration of the loop.</span></span>  
  
 <span data-ttu-id="123b0-149">Das folgende Beispiel veranschaulicht mehrere weniger gängige Optionen: das Zuweisen eines Werts zu einer externen Schleifenvariablen im Initialisierer, das Aufrufen der `Console.WriteLine`-Methode im Initialisierer und im Iterator und das Ändern die Werte von zwei Variablen im Iterator.</span><span class="sxs-lookup"><span data-stu-id="123b0-149">The following example illustrates several less common choices: assigning a value to an external loop variable in the initializer section,  invoking the `Console.WriteLine` method in both the initializer and the iterator sections, and changing the values of two variables in the iterator section.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
 <span data-ttu-id="123b0-150">Alle Ausdrücke, die eine `for`-Anweisung definieren, sind optional.</span><span class="sxs-lookup"><span data-stu-id="123b0-150">All of the expressions that define a `for` statement are optional.</span></span> <span data-ttu-id="123b0-151">Die folgende Anweisung erstellt z.B. eine Endlosschleife.</span><span class="sxs-lookup"><span data-stu-id="123b0-151">For example, the following statement creates an infinite loop.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="123b0-152">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="123b0-152">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="123b0-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="123b0-153">See Also</span></span>  
 [<span data-ttu-id="123b0-154">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="123b0-154">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="123b0-155">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="123b0-155">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="123b0-156">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="123b0-156">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="123b0-157">foreach, in</span><span class="sxs-lookup"><span data-stu-id="123b0-157">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="123b0-158">for-Anweisung (C++)</span><span class="sxs-lookup"><span data-stu-id="123b0-158">for Statement (C++)</span></span>](/cpp/cpp/for-statement-cpp)  
 [<span data-ttu-id="123b0-159">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="123b0-159">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
