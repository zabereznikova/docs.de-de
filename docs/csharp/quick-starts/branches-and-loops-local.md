---
title: "Schnellstart – Verzweigungen und Schleifen – C#-Leitfaden"
description: "In diesem Schnellstart zu Verzweigungen und Schleifen schreiben Sie einen C#-Code, um die Sprachsyntax zu erkunden, die bedingte Verzweigungen und Schleifen zur wiederholten Ausführung von Anweisungen unterstützt."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 609c8625b19025a20c1da1e767870eafbab4c4a0
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2018
---
# <a name="branches-and-loops"></a><span data-ttu-id="ad0b2-103">Verzweigungen und Schleifen</span><span class="sxs-lookup"><span data-stu-id="ad0b2-103">Branches and loops</span></span>

<span data-ttu-id="ad0b2-104">In diesem Schnellstart erfahren Sie, wie Sie einen Code schreiben, der Variablen untersucht und basierend auf diesen Variablen den Ausführungspfad ändert.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-104">This quick start teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="ad0b2-105">Sie schreiben einen C#-Code und sehen dort die Ergebnisse der Kompilierung und Ausführung Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="ad0b2-106">Dieser Schnellstart enthält eine Reihe von Lektionen, in denen Verzweigungs- und Schleifenkonstrukte in C# untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-106">The quick start contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="ad0b2-107">In diesen Lektionen lernen Sie die Grundlagen der Programmiersprache C# kennen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="ad0b2-108">Für diesen Schnellstart wird vorausgesetzt, dass Sie über einen Computer verfügen, den Sie für die Entwicklung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="ad0b2-109">Das .NET-Thema [Erste Schritte in 10 Minuten](https://www.microsoft.com/net/core) umfasst Anweisungen zum Einrichten Ihrer lokalen Entwicklungsumgebung auf einem Mac-, Windows- oder Linux-PC.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="ad0b2-110">Einen schnellen Überblick über die Befehle, die Sie verwenden werden, finden Sie in den [Schnellstarts mit der Einführung zu lokalen Umgebungen](local-environment.md), die Links mit weiteren Einzelheiten enthalten.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-110">A quick overview of the commands you'll use is in the [introduction to the local quick starts](local-environment.md) with links to more details.</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="ad0b2-111">Treffen von Entscheidungen mithilfe der `if`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ad0b2-111">Make decisions using the `if` statement</span></span>

<span data-ttu-id="ad0b2-112">Erstellen Sie ein Verzeichnis mit dem Namen **branches-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-112">Create a directory named **branches-quickstart**.</span></span> <span data-ttu-id="ad0b2-113">Machen Sie dieses Verzeichnis zum aktuellen Verzeichnis, und führen Sie `dotnet new console -n BranchesAndLoops -o .` aus.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-113">Make that the current directory and run `dotnet new console -n BranchesAndLoops -o .`.</span></span> <span data-ttu-id="ad0b2-114">Dieser Befehl erstellt im aktuellen Verzeichnis eine neue .NET Core-Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-114">This command creates a new .NET Core console application in the current directory.</span></span> 

<span data-ttu-id="ad0b2-115">Öffnen Sie **Program.cs** in Ihrem bevorzugten Editor, und ersetzen Sie die Zeile `Console.Writeline("Hello World!");` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-115">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="ad0b2-116">Testen Sie diesen Code, indem Sie `dotnet run` in Ihr Konsolenfenster eingeben.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-116">Try this code by typing `dotnet run` in the your console window.</span></span> <span data-ttu-id="ad0b2-117">Es sollte folgende Meldung in Ihrer Konsole angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-117">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="ad0b2-118">„Die Antwort ist größer als 10.“</span><span class="sxs-lookup"><span data-stu-id="ad0b2-118">printed to your console.</span></span>

<span data-ttu-id="ad0b2-119">Ändern Sie die Deklaration von `b` so, dass die Summe kleiner als 10 ist:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-119">Modify the declaration of `b` so that the sum is less than 10:</span></span> 

```csharp
int b = 3;
```

<span data-ttu-id="ad0b2-120">Geben Sie erneut `dotnet run` ein.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-120">Type `dotnet run` again.</span></span> <span data-ttu-id="ad0b2-121">Da die Antwort kleiner als 10 ist, wird nichts ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-121">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="ad0b2-122">Die von Ihnen getestete **Bedingung** ist falsch.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-122">The **condition** you're testing is false.</span></span> <span data-ttu-id="ad0b2-123">Es ist kein Code auszuführen, da Sie lediglich eine der möglichen Verzweigungen für eine `if`-Anweisung geschrieben haben: die true-Verzweigung.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-123">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="ad0b2-124">Bei Ihren ersten Schritten mit C# (oder einer anderen Programmiersprache) kann es zu Fehlern kommen, wenn Sie Codes schreiben.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-124">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="ad0b2-125">Der Compiler findet und meldet die Fehler.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-125">The compiler will find and report the errors.</span></span> <span data-ttu-id="ad0b2-126">Sehen Sie sich die Fehlerausgabe und den Code, der den Fehler erzeugt hat, genau an.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-126">Look closely at the error output and the code that generated the error.</span></span> <span data-ttu-id="ad0b2-127">Der Compilerfehler kann Ihnen in der Regel helfen, das Problem zu finden.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-127">The compler error can usually help you find the problem.</span></span> 

<span data-ttu-id="ad0b2-128">Das erste Beispiel veranschaulicht die Vorteile von `if`-Anweisungen und Boolean-Typen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-128">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="ad0b2-129">Ein *boolean*-Typ ist eine Variable, die einen der folgenden zwei Werte enthalten kann: `true` oder `false`.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-129">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="ad0b2-130">In C# ist ein besonderer Typ für boolesche Variablen, `bool`, definiert.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-130">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="ad0b2-131">Die `if`-Anweisung überprüft den Wert eines `bool`-Typs.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-131">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="ad0b2-132">Wenn der Wert `true` lautet, wird die nach `if` folgende Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-132">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="ad0b2-133">Andernfalls wird diese übersprungen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-133">Otherwise, it is skipped.</span></span> 

<span data-ttu-id="ad0b2-134">Dieser Vorgang zum Überprüfen von Bedingungen und Ausführen von Anweisungen basierend auf diesen Bedingungen ist sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-134">This process of checking conditions and executing statements based on those conditions is very powerful.</span></span>


## <a name="make-if-and-else-work-together"></a><span data-ttu-id="ad0b2-135">Kombinieren von if- und else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="ad0b2-135">Make if and else work together</span></span>

<span data-ttu-id="ad0b2-136">Um einen anderen Code in den true- und false-Verzweigungen auszuführen, erstellen Sie eine `else`-Verzweigung, die ausgeführt wird, wenn die Bedingung falsch ist.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-136">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="ad0b2-137">Testen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-137">Try this.</span></span> <span data-ttu-id="ad0b2-138">Fügen Sie die letzten beiden Zeilen im nachfolgenden Code zu Ihrer `Main`-Methode hinzu (die ersten vier sollten Sie bereits haben):</span><span class="sxs-lookup"><span data-stu-id="ad0b2-138">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="ad0b2-139">Die Anweisung, die nach dem Schlüsselwort `else` folgt, wird nur ausgeführt, wenn die zu testende Bedingung `false` lautet.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-139">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="ad0b2-140">Wenn Sie `if` und `else` mit booleschen Bedingungen kombinieren, müssen Sie sowohl eine `true`- als auch eine `false`-Bedingung verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-140">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad0b2-141">Der Einzug unter den `if`- und `else`-Anweisungen dient zur besseren Lesbarkeit.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-141">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="ad0b2-142">In der Programmiersprache C# werden Einzüge oder Leerräume nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-142">The C# language doesn't treat indentation or whitespace as significant.</span></span> <span data-ttu-id="ad0b2-143">Die Anweisung nach dem Schlüsselwort `if` bzw. `else` wird basierend auf der Bedingung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-143">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="ad0b2-144">Alle Beispiele in diesem Schnellstart folgen der gängigen Vorgehensweise, Zeilen basierend auf dem Steuerungsfluss von Anweisungen mit einem Einzug zu versehen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-144">All the samples in this quick start follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="ad0b2-145">Da Einzüge nicht relevant sind, müssen Sie mit `{` und `}` angeben, dass Sie mehr als eine Anweisung im Rahmen des bedingt ausgeführten Blocks verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-145">Because indentation is not significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="ad0b2-146">C#-Programmierer verwenden solche geschweifte Klammern in der Regel bei allen `if`- und `else`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-146">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="ad0b2-147">Das folgende Beispiel ist identisch mit dem Inhalt, den Sie soeben erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-147">The following example is the same as the one you just created.</span></span> <span data-ttu-id="ad0b2-148">Ändern Sie den obigen Code dahingehend, dass er mit dem folgenden Code übereinstimmt:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-148">Modify your code above to match the following code:</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> <span data-ttu-id="ad0b2-149">Im restlichen Schnellstart enthalten alle Codebeispiele geschweifte Klammern gemäß den allgemein gültigen Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-149">Through the rest of this quick start, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="ad0b2-150">Sie können kompliziertere Bedingungen testen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-150">You can test more complicated conditions.</span></span> <span data-ttu-id="ad0b2-151">Fügen Sie den folgenden Code in Ihrer `Main`-Methode unter dem Code, den Sie bisher geschrieben haben, hinzu:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-151">Add the following code in your `Main` method after the code you've written so far:</span></span>

```csharp
    int c = 4;
    if ((a + b + c > 10) && (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not greater than the second");
}
```

<span data-ttu-id="ad0b2-152">Das Zeichen `&&` steht für „and“.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-152">The `&&` represents "and".</span></span> <span data-ttu-id="ad0b2-153">Es bedeutet, dass beide Bedingungen „true“ lauten müssen, damit die Anweisung in der true-Verzweigung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-153">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="ad0b2-154">Diese Beispiele zeigen außerdem, dass Sie in jeder bedingten Verzweigung mehrere Anweisungen verwenden können, sofern Sie sie mit `{` und `}` umschließen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-154">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="ad0b2-155">Sie können auch `||` für „or“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-155">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="ad0b2-156">Fügen Sie den folgenden Code unter dem Code hinzu, den Sie bereits geschrieben haben:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-156">Add the following code after what you've written so far:</span></span>

```csharp
if ((a + b + c > 10) || (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not greater than the second");
}
```

<span data-ttu-id="ad0b2-157">Sie haben den ersten Schritt abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-157">You've finished the first step.</span></span> <span data-ttu-id="ad0b2-158">Bevor Sie mit dem nächsten Abschnitt beginnen, verschieben wir den aktuellen Code in eine separate Methode.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-158">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="ad0b2-159">Dies erleichtert das Arbeiten mit einem neuen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-159">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="ad0b2-160">Benennen Sie Ihre `Main` -Methode in `ExploreIf` um, und schreiben Sie eine neue `Main`-Methode, die `ExploreIf` aufruft.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-160">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="ad0b2-161">Anschließend sollte der Code wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-161">When you have finished, your code should look like this:</span></span>

```csharp
using System;

namespace BranchesAndLoops
{
    class Program
    {
        static void ExploreIf()
        {
            int a = 5;
            int b = 3;
            if (a + b > 10)
            {
                Console.WriteLine("The answer is greater than 10");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
            }

            if ((a + b + c > 10) && (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("And the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("Or the first number is not greater than the second");
            }

            if ((a + b + c > 10) || (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("Or the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("And the first number is not greater than the second");
            }            
        }

        static void Main(string[] args)
        {
            ExploreIf();
        }
    }
}
```

<span data-ttu-id="ad0b2-162">Kommentieren Sie den Aufruf von `ExploreIf()` aus.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-162">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="ad0b2-163">Dadurch wird die Ausgabe weniger überladen, wenn Sie in diesem Abschnitt arbeiten:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-163">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="ad0b2-164">Mit `//` wird ein **Kommentar** in C# begonnen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-164">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="ad0b2-165">Kommentare sind Texte, die Sie in Ihrem Quellcode beibehalten, jedoch nicht als Code ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-165">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="ad0b2-166">Der Compiler generiert keinen ausführbaren Code über die Kommentare.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-166">The compiler does not generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="ad0b2-167">Wiederholen von Vorgängen durch Schleifen</span><span class="sxs-lookup"><span data-stu-id="ad0b2-167">Use loops to repeat operations</span></span>

<span data-ttu-id="ad0b2-168">In diesem Abschnitt verwenden Sie **Schleifen**, um Anweisungen zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-168">In this section you use **loops** to repeat statements.</span></span> <span data-ttu-id="ad0b2-169">Testen Sie diesen Code in Ihrer `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-169">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="ad0b2-170">Die `while`-Anweisung prüft eine Bedingung und führt die Anweisung oder der Anweisungsblock nach `while` aus.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-170">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="ad0b2-171">Es wiederholt die Überprüfung der Bedingung und die Ausführung dieser Anweisungen, bis die Bedingung „false“ lautet.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-171">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="ad0b2-172">In diesem Beispiel kommt ein weiterer neuer Operator vor.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-172">There's one other new operator in this example.</span></span> <span data-ttu-id="ad0b2-173">Das `++`-Zeichen nach der `counter`-Variable ist der **increment**-Operator.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-173">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="ad0b2-174">Er erhöht den Wert von `counter` um 1 und speichert diesen Wert in der Variable `counter`.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-174">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad0b2-175">Stellen Sie sicher, dass die Schleifenbedingung `while` zu „false“ wechselt, nachdem Sie den Code ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-175">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="ad0b2-176">Erstellen Sie anderenfalls eine **Endlosschleife**, durch die das Programm niemals beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-176">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="ad0b2-177">Das wird in diesem Beispiel nicht gezeigt, weil Sie die programmseitige Verwendung von **STRG+C** oder anderen Mitteln unterbinden müssen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-177">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="ad0b2-178">Die `while`-Schleife testet die Bedingung, bevor der Code nach `while` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-178">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="ad0b2-179">Die `do` ... `while`-Schleife führt den Code zuerst aus und überprüft anschließend die Bedingung.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-179">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="ad0b2-180">Die do while-Schleife wird im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-180">The do while loop is shown in the following code:</span></span>

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="ad0b2-181">Diese `do`-Schleife und die vorherige `while`-Schleife erzeugen die gleiche Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-181">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="ad0b2-182">Arbeiten mit der for-Schleife</span><span class="sxs-lookup"><span data-stu-id="ad0b2-182">Work with the for loop</span></span>

<span data-ttu-id="ad0b2-183">Die **for**-Schleife wird üblicherweise in C# verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-183">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="ad0b2-184">Testen Sie diesen Code in Ihrer Main()-Methode:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-184">Try this code in your Main() method:</span></span>

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

<span data-ttu-id="ad0b2-185">Dieser funktioniert auf dieselbe Weise wie die `while`-Schleife und die `do`-Schleife, die Sie bereits verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-185">This does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="ad0b2-186">Die `for`-Anweisung besteht aus drei Teilen, die steuern, wie sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-186">The `for` statement has three parts that control how it works.</span></span> 

<span data-ttu-id="ad0b2-187">Der erste Teil ist der **for-Initialisierer**: `for index = 0;` deklariert, dass `index` die Schleifenvariable ist, und legt den Anfangswert auf `0` fest.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-187">The first part is the **for initializer**: `for index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="ad0b2-188">Der mittlere Teil ist die **for-Bedingung**: `index < 10` deklariert, dass diese `for`-Schleife ausgeführt wird, solange der Wert des Zählers kleiner als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-188">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="ad0b2-189">Der letzte Teil ist der **for-Iterator**: `index++` gibt an, wie die Schleifenvariable geändert wird, nachdem der Block nach der `for`-Anweisung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-189">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="ad0b2-190">Hier gibt dieser an, dass `index` bei jeder Blockausführung um 1 erhöht werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-190">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="ad0b2-191">Experimentieren Sie selbst damit.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-191">Experiment with these yourself.</span></span> <span data-ttu-id="ad0b2-192">Testen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-192">Try each of the following:</span></span>

- <span data-ttu-id="ad0b2-193">Ändern Sie den Initialisierer, um mit einem anderen Wert zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-193">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="ad0b2-194">Ändern Sie die Bedingung, um an einem anderen Wert anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-194">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="ad0b2-195">Wenn Sie fertig sind, fahren Sie damit fort, mithilfe der erworbenen Kenntnisse selbst Codes zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-195">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="ad0b2-196">Kombinieren von Branches und Schleifen</span><span class="sxs-lookup"><span data-stu-id="ad0b2-196">Combine branches and loops</span></span>

<span data-ttu-id="ad0b2-197">Nachdem Sie nun die `if`-Anweisung und die Schleifenkonstrukte in der Programmiersprache C# kennengelernt haben, versuchen Sie, einen C#-Code zu schreiben, der die Summe aller ganzen Zahlen von 1 bis 20 ermittelt, die durch 3 teilbar sind.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-197">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="ad0b2-198">Im Folgenden einige Tipps:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-198">Here are a few hints:</span></span>

- <span data-ttu-id="ad0b2-199">Der `%`-Operator ermittelt den Restwert einer Divisionsoperation.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-199">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="ad0b2-200">Die `if`-Anweisung ermittelt die Bedingung, um festzustellen, ob eine Zahl in der Summe berücksichtigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-200">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="ad0b2-201">Die `for`-Schleife ermöglicht es, eine Reihe von Schritten für alle Zahlen von 1 bis 20 zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-201">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="ad0b2-202">Probieren Sie es selbst aus.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-202">Try it yourself.</span></span> <span data-ttu-id="ad0b2-203">Prüfen Sie dann, wie Sie abgeschnitten haben.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-203">Then check how you did.</span></span> <span data-ttu-id="ad0b2-204">Sie sollten 63 als Antwort erhalten.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-204">You should get 63 for an answer.</span></span> <span data-ttu-id="ad0b2-205">Sie können eine mögliche Antwort sehen, indem Sie sich [den fertig gestellten Code auf GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54) ansehen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-205">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="ad0b2-206">Sie haben den Schnellstart „Branches und Schleifen“ abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-206">You've completed the "branches and loops" quick start.</span></span>

<span data-ttu-id="ad0b2-207">Sie können mit dem Schnellstart [Interpolierte Zeichenfolgen](interpolated-strings-local.md) in Ihrer eigenen Entwicklungsumgebung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ad0b2-207">You can continue with the [Interpolated strings](interpolated-strings-local.md) quick start in your own development environment.</span></span>

<span data-ttu-id="ad0b2-208">Weitere Informationen zu diesen Begriffen finden Sie unter folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ad0b2-208">You can learn more about these concepts in these topics:</span></span>

<span data-ttu-id="ad0b2-209">[if- und else-Anweisung](../language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="ad0b2-209">[If and else statement](../language-reference/keywords/if-else.md) </span></span>  
<span data-ttu-id="ad0b2-210">[while-Anweisung](../language-reference/keywords/while.md) </span><span class="sxs-lookup"><span data-stu-id="ad0b2-210">[While statement](../language-reference/keywords/while.md) </span></span>  
<span data-ttu-id="ad0b2-211">[do-Anweisung](../language-reference/keywords/do.md) </span><span class="sxs-lookup"><span data-stu-id="ad0b2-211">[Do statement](../language-reference/keywords/do.md) </span></span>  
[<span data-ttu-id="ad0b2-212">for-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ad0b2-212">For statement</span></span>](../language-reference/keywords/for.md)   
