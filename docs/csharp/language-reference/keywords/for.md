---
title: for (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- for
- for_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d65c198b0fd763bddae4832290af038b8992eb48
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="for-c-reference"></a><span data-ttu-id="37c0e-102">for (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="37c0e-102">for (C# Reference)</span></span>
<span data-ttu-id="37c0e-103">Mithilfe einer `for`-Schleife können Sie eine Anweisung oder einen Anweisungsblock wiederholt ausführen, bis ein bestimmter Ausdruck nach `false` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="37c0e-103">By using a `for` loop, you can run a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="37c0e-104">Diese Art von Schleife eignet sich für Iterationen von Arrays und für andere Anwendungen, in denen Sie im Voraus wissen, wie oft die Schleife durchlaufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="37c0e-104">This kind of loop is useful for iterating over arrays and for other applications in which you know in advance how many times you want the loop to iterate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37c0e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37c0e-105">Example</span></span>  
 <span data-ttu-id="37c0e-106">Im folgenden Beispiel wird der `i`-Wert in die Konsole geschrieben und bei jeder Iteration der Schleife um 1 erhöht.</span><span class="sxs-lookup"><span data-stu-id="37c0e-106">In the following example, the value of `i` is written to the console and incremented by 1 during each iteration of the loop.</span></span>  
  
 <span data-ttu-id="37c0e-107">[!code-cs[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="37c0e-107">[!code-cs[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]</span></span>  
  
 <span data-ttu-id="37c0e-108">Die `for`-Anweisung im vorherigen Beispiel führt die folgenden Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="37c0e-108">The `for` statement in the previous example performs the following actions.</span></span>  
  
1.  <span data-ttu-id="37c0e-109">Zuerst wird der Anfangswert der Variable `i` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="37c0e-109">First, the initial value of variable `i` is established.</span></span> <span data-ttu-id="37c0e-110">Dieser Schritt wird unabhängig davon, wie oft die Schleife wiederholt wird, nur einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="37c0e-110">This step happens only once, regardless of how many times the loop repeats.</span></span> <span data-ttu-id="37c0e-111">Sie können sich diese Initialisierung als außerhalb der Schleife erfolgend vorstellen.</span><span class="sxs-lookup"><span data-stu-id="37c0e-111">You can think of this initialization as happening outside the looping process.</span></span>  
  
2.  <span data-ttu-id="37c0e-112">Um die Bedingung (`i <= 5`) auszuwerten, wird der Wert `i` mit 5 verglichen.</span><span class="sxs-lookup"><span data-stu-id="37c0e-112">To evaluate the condition (`i <= 5`), the value of `i` is compared to 5.</span></span>  
  
    -   <span data-ttu-id="37c0e-113">Wenn `i` ist kleiner als oder gleich 5 ist, wird die Bedingung nach `true` ausgewertet, und die folgenden Aktionen werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="37c0e-113">If `i` is less than or equal to 5, the condition evaluates to `true`, and the following actions occur.</span></span>  
  
        1.  <span data-ttu-id="37c0e-114">In der `Console.WriteLine`-Anweisung im Hauptteil der Schleife wird der `i`-Wert dargestellt.</span><span class="sxs-lookup"><span data-stu-id="37c0e-114">The `Console.WriteLine` statement in the body of the loop displays the value of `i`.</span></span>  
  
        2.  <span data-ttu-id="37c0e-115">Der `i`-Wert wird um 1 inkrementiert.</span><span class="sxs-lookup"><span data-stu-id="37c0e-115">The value of `i` is incremented by 1.</span></span>  
  
        3.  <span data-ttu-id="37c0e-116">Die Schleife kehrt zum Start von Schritt 2 zurück, um die Bedingung erneut auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="37c0e-116">The loop returns to the start of step 2 to evaluate the condition again.</span></span>  
  
    -   <span data-ttu-id="37c0e-117">Wenn `i` größer als 5 ist, wird die Bedingung nach `false` ausgewertet, und Sie beenden die Schleife.</span><span class="sxs-lookup"><span data-stu-id="37c0e-117">If `i` is greater than 5, the condition evaluates to `false`, and you exit the loop.</span></span>  
  
 <span data-ttu-id="37c0e-118">Beachten Sie, dass wenn der ursprüngliche `i`-Wert größer als 5 ist, wird der Hauptteil der Schleife kein einziges Mal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="37c0e-118">Note that, if the initial value of `i` is greater than 5, the body of the loop doesn't run even once.</span></span>  
  
 <span data-ttu-id="37c0e-119">Jede `for`-Anweisung definiert die Abschnitte „Initialisierer“, „Bedingung“ und „Iterator“.</span><span class="sxs-lookup"><span data-stu-id="37c0e-119">Every `for` statement defines initializer, condition, and iterator sections.</span></span> <span data-ttu-id="37c0e-120">Diese Abschnitte bestimmen, wie oft die Schleife in der Regel durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="37c0e-120">These sections usually determine how many times the loop iterates.</span></span>  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
 <span data-ttu-id="37c0e-121">Diese Abschnitte dienen den folgenden Zwecken.</span><span class="sxs-lookup"><span data-stu-id="37c0e-121">The sections serve the following purposes.</span></span>  
  
-   <span data-ttu-id="37c0e-122">Im Initialisiererabschnitt werden die anfänglichen Bedingung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="37c0e-122">The initializer section sets the initial conditions.</span></span> <span data-ttu-id="37c0e-123">Die Anweisungen in diesem Abschnitt werden nur einmal ausgeführt, bevor die Schleife beginnt.</span><span class="sxs-lookup"><span data-stu-id="37c0e-123">The statements in this section run only once, before you enter the loop.</span></span> <span data-ttu-id="37c0e-124">Der Abschnitt kann nur eine der beiden folgenden Optionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="37c0e-124">The section can contain only one of the following two options.</span></span>  
  
    -   <span data-ttu-id="37c0e-125">Die Deklaration und die Initialisierung einer lokalen Schleifenvariablen, wie das erste Beispiel zeigt (`int i = 1`).</span><span class="sxs-lookup"><span data-stu-id="37c0e-125">The declaration and initialization of a local loop variable, as the first example shows (`int i = 1`).</span></span> <span data-ttu-id="37c0e-126">Die Variable ist in der Schleife lokal; ein Zugriff darauf von außerhalb der Schleife ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="37c0e-126">The variable is local to the loop and can't be accessed from outside the loop.</span></span>  
  
    -   <span data-ttu-id="37c0e-127">Null oder mehr Anweisungsausdrücke aus der folgenden Liste, durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="37c0e-127">Zero or more statement expressons from the following list, separated by commas.</span></span>  
  
        -   <span data-ttu-id="37c0e-128">[Zuweisungsanweisung](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="37c0e-128">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
        -   <span data-ttu-id="37c0e-129">Aufruf einer Methode</span><span class="sxs-lookup"><span data-stu-id="37c0e-129">invocation of a method</span></span>  
  
        -   <span data-ttu-id="37c0e-130">Präfix- oder Postfix-[Inkrementausdruck](../../../csharp/language-reference/operators/increment-operator.md), z.B. `++i` oder `i++`</span><span class="sxs-lookup"><span data-stu-id="37c0e-130">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
        -   <span data-ttu-id="37c0e-131">Präfix- oder Postfix-[Dekrementausdruck](../../../csharp/language-reference/operators/decrement-operator.md), z.B. `--i` oder `i--`</span><span class="sxs-lookup"><span data-stu-id="37c0e-131">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
        -   <span data-ttu-id="37c0e-132">Erstellung eines Objekts mithilfe von [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="37c0e-132">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
        -   <span data-ttu-id="37c0e-133">[await](../../../csharp/language-reference/keywords/await.md)-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="37c0e-133">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="37c0e-134">Der Bedingungsabschnitt enthält einen booleschen Ausdruck, der ausgewertet wird, um festzustellen, ob die Schleife beendet oder erneut ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="37c0e-134">The condition section contains a boolean expression that’s evaluated to determine whether the loop should exit or should run again.</span></span>  
  
-   <span data-ttu-id="37c0e-135">Der Iteratorabschnitt definiert, was nach jeder Iteration des Hauptteils der Schleife geschieht.</span><span class="sxs-lookup"><span data-stu-id="37c0e-135">The iterator section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="37c0e-136">Der Iteratorabschnitt enthält keine oder mehrere der folgenden Anweisungsausdrücke, durch Kommas getrennt:</span><span class="sxs-lookup"><span data-stu-id="37c0e-136">The iterator section contains zero or more of the following statement expressions, separated by commas:</span></span>  
  
    -   <span data-ttu-id="37c0e-137">[Zuweisungsanweisung](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="37c0e-137">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
    -   <span data-ttu-id="37c0e-138">Aufruf einer Methode</span><span class="sxs-lookup"><span data-stu-id="37c0e-138">invocation of a method</span></span>  
  
    -   <span data-ttu-id="37c0e-139">Präfix- oder Postfix-[Inkrementausdruck](../../../csharp/language-reference/operators/increment-operator.md), z.B. `++i` oder `i++`</span><span class="sxs-lookup"><span data-stu-id="37c0e-139">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
    -   <span data-ttu-id="37c0e-140">Präfix- oder Postfix-[Dekrementausdruck](../../../csharp/language-reference/operators/decrement-operator.md), z.B. `--i` oder `i--`</span><span class="sxs-lookup"><span data-stu-id="37c0e-140">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
    -   <span data-ttu-id="37c0e-141">Erstellung eines Objekts mithilfe von [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="37c0e-141">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
    -   <span data-ttu-id="37c0e-142">[await](../../../csharp/language-reference/keywords/await.md)-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="37c0e-142">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="37c0e-143">Der Hauptteil der Schleife besteht aus einer Anweisung, einer leeren Anweisung oder einem Block von Anweisungen, die Sie erstellen, indem Sie 0 (null) oder mehrere Anweisungen in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="37c0e-143">The body of the loop consists of a statement, an empty statement, or a block of statements, which you create by enclosing zero or more statements in braces.</span></span>  
  
     <span data-ttu-id="37c0e-144">Sie können die Schleife an jedem Punkt im `for`-Block mit dem Schlüsselwort [break](../../../csharp/language-reference/keywords/break.md) unterbrechen oder mit dem Schlüsselwort [continue](../../../csharp/language-reference/keywords/continue.md) direkt zur nächsten Iteration der Schleife springen.</span><span class="sxs-lookup"><span data-stu-id="37c0e-144">You can break out of a `for` loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or you can step to the next iteration by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span> <span data-ttu-id="37c0e-145">Sie können jede beliebige Schleife auch mit einer [goto](../../../csharp/language-reference/keywords/goto.md)-, [return](../../../csharp/language-reference/keywords/return.md)- oder [throw](../../../csharp/language-reference/keywords/throw.md)-Anweisung beenden.</span><span class="sxs-lookup"><span data-stu-id="37c0e-145">You also can exit any loop by using a [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement.</span></span>  
  
 <span data-ttu-id="37c0e-146">Im ersten Beispiel in diesem Thema wird die häufigste Art der `for`-Schleife dargestellt, die die folgenden Optionen für die Abschnitte bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="37c0e-146">The first example in this topic shows the most typical kind of `for` loop, which makes the following choices for the sections.</span></span>  
  
-   <span data-ttu-id="37c0e-147">Der Initialisierer deklariert und initialisiert Sie eine lokale Schleifenvariable, `i`, die die Iterationen der Schleife mitzählt.</span><span class="sxs-lookup"><span data-stu-id="37c0e-147">The initializer declares and initializes a local loop variable, `i`, that maintains a count of the iterations of the loop.</span></span>  
  
-   <span data-ttu-id="37c0e-148">Die Bedingung überprüft den Wert der Schleifenvariablen gegen einen bekannten endgültigen Wert, 5.</span><span class="sxs-lookup"><span data-stu-id="37c0e-148">The condition checks the value of the loop variable against a known final value, 5.</span></span>  
  
-   <span data-ttu-id="37c0e-149">Der Iterator verwendet eine Postfix-Inkrementanweisung, `i++`, um den Zählerstand jeder Schleife festzuhalten.</span><span class="sxs-lookup"><span data-stu-id="37c0e-149">The iterator section uses a postfix increment statement, `i++`, to tally each iteration of the loop.</span></span>  
  
 <span data-ttu-id="37c0e-150">Das folgende Beispiel veranschaulicht mehrere weniger gängige Optionen: das Zuweisen eines Werts zu einer externen Schleifenvariablen im Initialisierer, das Aufrufen der `Console.WriteLine`-Methode im Initialisierer und im Iterator und das Ändern die Werte von zwei Variablen im Iterator.</span><span class="sxs-lookup"><span data-stu-id="37c0e-150">The following example illustrates several less common choices: assigning a value to an external loop variable in the initializer section,  invoking the `Console.WriteLine` method in both the initializer and the iterator sections, and changing the values of two variables in the iterator section.</span></span>  
  
 <span data-ttu-id="37c0e-151">[!code-cs[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="37c0e-151">[!code-cs[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]</span></span>  
  
 <span data-ttu-id="37c0e-152">Alle Ausdrücke, die eine `for`-Anweisung definieren, sind optional.</span><span class="sxs-lookup"><span data-stu-id="37c0e-152">All of the expressions that define a `for` statement are optional.</span></span> <span data-ttu-id="37c0e-153">Die folgende Anweisung erstellt z.B. eine Endlosschleife.</span><span class="sxs-lookup"><span data-stu-id="37c0e-153">For example, the following statement creates an infinite loop.</span></span>  
  
 <span data-ttu-id="37c0e-154">[!code-cs[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="37c0e-154">[!code-cs[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="37c0e-155">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="37c0e-155">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37c0e-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37c0e-156">See Also</span></span>  
 <span data-ttu-id="37c0e-157">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="37c0e-157">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="37c0e-158">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="37c0e-158">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="37c0e-159">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="37c0e-159">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="37c0e-160">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="37c0e-160">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 <span data-ttu-id="37c0e-161">[for-Anweisung (C++)](/cpp/cpp/for-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="37c0e-161">[for Statement (C++)](/cpp/cpp/for-statement-cpp) </span></span>  
 [<span data-ttu-id="37c0e-162">Iterationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="37c0e-162">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

