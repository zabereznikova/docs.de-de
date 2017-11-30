---
title: Schnellstart - Verzweigungen und lops - C#-Handbuch
description: "In diesem Schnellstart zu Verzweigungen und Schleifen schreiben Sie C#-Code aus, um die Sprachsyntax untersuchen, die bedingte Verzweigungen und Schleifen wiederholte Ausführen von Anweisungen unterstützt."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 4b077a29cf42072a93b054f50a13a4580ad54304
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2017
---
# <a name="branches-and-loops"></a><span data-ttu-id="4740b-103">Verzweigungen und Schleifen</span><span class="sxs-lookup"><span data-stu-id="4740b-103">Branches and loops</span></span>

<span data-ttu-id="4740b-104">Dieser Schnellstart erfahren Sie, wie Sie Code schreiben, die Variablen untersucht und ändert den Ausführungspfad, der basierend auf diese Variablen.</span><span class="sxs-lookup"><span data-stu-id="4740b-104">This quick start teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="4740b-105">C#-Code schreiben und die Ergebnisse der kompilieren und Ausführen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4740b-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="4740b-106">Der Schnellstart enthält eine Reihe von Lektionen, in denen untersuchen, Verzweigungen und Schleifenkonstrukte in C# geschrieben.</span><span class="sxs-lookup"><span data-stu-id="4740b-106">The quick start contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="4740b-107">In diesen Lektionen lernen Sie die Grundlagen der Programmiersprache C# kennen.</span><span class="sxs-lookup"><span data-stu-id="4740b-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="4740b-108">Dieser Schnellstart erwartet, dass Sie einen Computer verfügen, den Sie für die Entwicklung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4740b-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="4740b-109">Das Thema .NET [Einstieg in 10 Minuten](https://www.microsoft.com/net/core) umfasst Anweisungen zum Einrichten der lokalen Entwicklungsumgebung auf Mac, PC oder Linux.</span><span class="sxs-lookup"><span data-stu-id="4740b-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="4740b-110">Treffen von Entscheidungen mithilfe der `if` Anweisung</span><span class="sxs-lookup"><span data-stu-id="4740b-110">Make decisions using the `if` statement</span></span>

<span data-ttu-id="4740b-111">Erstellen Sie ein Verzeichnis mit dem Namen **Verzweigungen Schnellstart**.</span><span class="sxs-lookup"><span data-stu-id="4740b-111">Create a directory named **branches-quickstart**.</span></span> <span data-ttu-id="4740b-112">Machen Sie dieses Verzeichnis zum aktuellen Verzeichnis, und führen Sie `dotnet new console -n BranchesAndLoops -o .` aus.</span><span class="sxs-lookup"><span data-stu-id="4740b-112">Make that the current directory and run `dotnet new console -n BranchesAndLoops -o .`.</span></span> <span data-ttu-id="4740b-113">Dieser Befehl erstellt eine neue Konsolenanwendung von .NET Core im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4740b-113">This command creates a new .NET Core console application in the current directory.</span></span> 

<span data-ttu-id="4740b-114">Open **"Program.cs"** in Ihrem bevorzugten Editor, und Ersetzen Sie die Zeile `Console.Writeline("Hello World!");` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="4740b-114">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="4740b-115">Versuchen Sie diesen Code durch Eingabe `dotnet run` in der Ihre Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="4740b-115">Try this code by typing `dotnet run` in the your console window.</span></span> <span data-ttu-id="4740b-116">Sie sollten der Nachricht finden Sie unter "die Antwort ist größer als 10".</span><span class="sxs-lookup"><span data-stu-id="4740b-116">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="4740b-117">in der Konsole gedruckt.</span><span class="sxs-lookup"><span data-stu-id="4740b-117">printed to your console.</span></span>

<span data-ttu-id="4740b-118">Ändern Sie die Deklaration von `b` so, dass die Summe kleiner als 10 ist:</span><span class="sxs-lookup"><span data-stu-id="4740b-118">Modify the declaration of `b` so that the sum is less than 10:</span></span> 

```csharp
int b = 3;
```

<span data-ttu-id="4740b-119">Typ `dotnet run` erneut aus.</span><span class="sxs-lookup"><span data-stu-id="4740b-119">Type `dotnet run` again.</span></span> <span data-ttu-id="4740b-120">Da die Antwort kleiner als 10 ist, wird nichts ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="4740b-120">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="4740b-121">Die von Ihnen getestete **Bedingung** ist falsch.</span><span class="sxs-lookup"><span data-stu-id="4740b-121">The **condition** you're testing is false.</span></span> <span data-ttu-id="4740b-122">Es ist kein Code auszuführen, da Sie lediglich eine der möglichen Verzweigungen für eine `if`-Anweisung geschrieben haben: die true-Verzweigung.</span><span class="sxs-lookup"><span data-stu-id="4740b-122">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="4740b-123">Bei Ihren ersten Schritten mit C# (oder einer anderen Programmiersprache) kann es zu Fehlern kommen, wenn Sie Codes schreiben.</span><span class="sxs-lookup"><span data-stu-id="4740b-123">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="4740b-124">Der Compiler findet und Fehler zu melden.</span><span class="sxs-lookup"><span data-stu-id="4740b-124">The compiler will find and report the errors.</span></span> <span data-ttu-id="4740b-125">Sehen Sie die Fehlerausgabe und den Code, der den Fehler generiert hat.</span><span class="sxs-lookup"><span data-stu-id="4740b-125">Look closely the the error output and the code that generated the error.</span></span> <span data-ttu-id="4740b-126">Der Compler Fehler können in der Regel das Problem zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="4740b-126">The compler error can usually help you find the problem.</span></span> 

<span data-ttu-id="4740b-127">Dieses erste Beispiel veranschaulicht die Leistungsfähigkeit von `if` und booleschen Typen.</span><span class="sxs-lookup"><span data-stu-id="4740b-127">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="4740b-128">Ein *booleschen* ist eine Variable, die einen von zwei Werten haben kann: `true` oder `false`.</span><span class="sxs-lookup"><span data-stu-id="4740b-128">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="4740b-129">C# definiert eine Sonderform `bool` für boolesche Variablen.</span><span class="sxs-lookup"><span data-stu-id="4740b-129">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="4740b-130">Die `if`-Anweisung überprüft den Wert eines `bool`-Typs.</span><span class="sxs-lookup"><span data-stu-id="4740b-130">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="4740b-131">Wenn der Wert `true` lautet, wird die nach `if` folgende Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4740b-131">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="4740b-132">Andernfalls wird diese übersprungen.</span><span class="sxs-lookup"><span data-stu-id="4740b-132">Otherwise, it is skipped.</span></span> 

<span data-ttu-id="4740b-133">Dieser Vorgang zum Überprüfen von Bedingungen und Ausführen von Anweisungen basierend auf diesen Bedingungen ist sehr nützlich.</span><span class="sxs-lookup"><span data-stu-id="4740b-133">This process of checking conditions and executing statements based on those conditions is very powerful.</span></span>


## <a name="make-if-and-else-work-together"></a><span data-ttu-id="4740b-134">Kombinieren von if- und else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="4740b-134">Make if and else work together</span></span>

<span data-ttu-id="4740b-135">Um einen anderen Code in den true- und false-Verzweigungen auszuführen, erstellen Sie eine `else`-Verzweigung, die ausgeführt wird, wenn die Bedingung falsch ist.</span><span class="sxs-lookup"><span data-stu-id="4740b-135">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="4740b-136">Wiederholen Sie diesen Vorgang.</span><span class="sxs-lookup"><span data-stu-id="4740b-136">Try this.</span></span> <span data-ttu-id="4740b-137">Fügen Sie die letzten beiden Zeilen in den folgenden Code, um Ihre `Main` Methode (Sie müssen bereits die ersten vier):</span><span class="sxs-lookup"><span data-stu-id="4740b-137">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="4740b-138">Die Anweisung, die nach dem Schlüsselwort `else` folgt, wird nur ausgeführt, wenn die zu testende Bedingung `false` lautet.</span><span class="sxs-lookup"><span data-stu-id="4740b-138">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="4740b-139">Kombinieren von `if` und `else` mit einem booleschen Operator Bedingungen bietet die Leistungsfähigkeit, die Sie beide behandeln müssen eine `true` und ein `false` Bedingung.</span><span class="sxs-lookup"><span data-stu-id="4740b-139">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4740b-140">Der Einzug unter den `if`- und `else`-Anweisungen dient zur besseren Lesbarkeit.</span><span class="sxs-lookup"><span data-stu-id="4740b-140">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="4740b-141">In der Programmiersprache C# werden Einzüge oder Leerräume nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="4740b-141">The C# language doesn't treat indentation or whitespace as significant.</span></span> <span data-ttu-id="4740b-142">Die Anweisung nach dem Schlüsselwort `if` bzw. `else` wird basierend auf der Bedingung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4740b-142">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="4740b-143">Alle Beispiele in diesem Schnellstart führen Sie üblicherweise um die Zeilen basierend auf dem Steuerungsfluss des Anweisungen einen Einzug festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4740b-143">All the samples in this quick start follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="4740b-144">Da Einzüge nicht relevant sind, müssen Sie mit `{` und `}` angeben, dass Sie mehr als eine Anweisung im Rahmen des bedingt ausgeführten Blocks verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4740b-144">Because indentation is not significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="4740b-145">C#-Programmierer verwenden solche geschweifte Klammern in der Regel bei allen `if`- und `else`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4740b-145">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="4740b-146">Das folgende Beispiel ist identisch mit dem soeben erstellten.</span><span class="sxs-lookup"><span data-stu-id="4740b-146">The following example is the same as the one you just created.</span></span> <span data-ttu-id="4740b-147">Ändern Sie den Code, der oben genannten entsprechend den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="4740b-147">Modify your code above to match the following code:</span></span>

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
> <span data-ttu-id="4740b-148">Über den Rest dieses Schnellstarts, enthalten alle Codebeispiele die geschweiften Klammern, die folgenden Methoden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4740b-148">Through the rest of this quick start, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="4740b-149">Sie können etwas kompliziertere Bedingungen testen.</span><span class="sxs-lookup"><span data-stu-id="4740b-149">You can test more complicated conditions.</span></span> <span data-ttu-id="4740b-150">Fügen Sie den folgenden Code in Ihrem `Main` Methode nach dem Code, Sie haben bisher geschrieben:</span><span class="sxs-lookup"><span data-stu-id="4740b-150">Add the following code in your `Main` method after the code you've written so far:</span></span>

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

<span data-ttu-id="4740b-151">Das Zeichen `&&` steht für „and“.</span><span class="sxs-lookup"><span data-stu-id="4740b-151">The `&&` represents "and".</span></span> <span data-ttu-id="4740b-152">Es bedeutet, dass beide Bedingungen „true“ lauten müssen, damit die Anweisung in der true-Verzweigung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4740b-152">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="4740b-153">Diese Beispiele zeigen außerdem, dass Sie in jeder bedingten Verzweigung mehrere Anweisungen verwenden können, sofern Sie sie mit `{` und `}` umschließen.</span><span class="sxs-lookup"><span data-stu-id="4740b-153">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="4740b-154">Sie können auch `||` zur Darstellung "oder".</span><span class="sxs-lookup"><span data-stu-id="4740b-154">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="4740b-155">Fügen Sie den folgenden Code nach dem Sie bisher geschrieben haben:</span><span class="sxs-lookup"><span data-stu-id="4740b-155">Add the following code after what you've written so far:</span></span>

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

<span data-ttu-id="4740b-156">Der erste Schritt ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4740b-156">You've finished the first step.</span></span> <span data-ttu-id="4740b-157">Bevor Sie mit dem nächsten Abschnitt beginnen, verschieben wir den aktuellen Code in eine separate Methode.</span><span class="sxs-lookup"><span data-stu-id="4740b-157">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="4740b-158">Dies erleichtert das Arbeiten mit einem neuen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="4740b-158">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="4740b-159">Benennen Sie Ihre `Main` -Methode in `ExploreIf` um, und schreiben Sie eine neue `Main`-Methode, die `ExploreIf` aufruft.</span><span class="sxs-lookup"><span data-stu-id="4740b-159">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="4740b-160">Anschließend sollte der Code wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="4740b-160">When you have finished, your code should look like this:</span></span>

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

<span data-ttu-id="4740b-161">Kommentieren Sie den Aufruf von `ExploreIf()`.</span><span class="sxs-lookup"><span data-stu-id="4740b-161">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="4740b-162">Die Ausgabe werden vorgenommen, die weniger überladen, wenn Sie in diesem Abschnitt arbeiten:</span><span class="sxs-lookup"><span data-stu-id="4740b-162">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="4740b-163">Die `//` startet eine **Kommentar** in C# geschrieben.</span><span class="sxs-lookup"><span data-stu-id="4740b-163">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="4740b-164">Kommentare sind Text, die Sie in Ihrem Quellcode beibehalten, aber nicht als Code ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="4740b-164">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="4740b-165">Der Compiler löst keine ausführbaren Code von den Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="4740b-165">The compiler does not generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="4740b-166">Wiederholen von Vorgängen durch Schleifen</span><span class="sxs-lookup"><span data-stu-id="4740b-166">Use loops to repeat operations</span></span>

<span data-ttu-id="4740b-167">In diesem Abschnitt verwenden Sie **Schleifen** Anweisungen wiederholen.</span><span class="sxs-lookup"><span data-stu-id="4740b-167">In this section you use **loops** to repeat statements.</span></span> <span data-ttu-id="4740b-168">Wiederholen Sie diesen Code in Ihrem `Main` Methode:</span><span class="sxs-lookup"><span data-stu-id="4740b-168">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="4740b-169">Die `while` -Anweisung überprüft eine Bedingung und führt die Anweisung oder der Anweisungsblock nach der `while`.</span><span class="sxs-lookup"><span data-stu-id="4740b-169">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="4740b-170">Er überprüft wiederholt die Bedingung und diese Anweisungen ausführen, bis die Bedingung "false" ist.</span><span class="sxs-lookup"><span data-stu-id="4740b-170">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="4740b-171">In diesem Beispiel kommt ein weiterer neuer Operator vor.</span><span class="sxs-lookup"><span data-stu-id="4740b-171">There's one other new operator in this example.</span></span> <span data-ttu-id="4740b-172">Das `++`-Zeichen nach der `counter`-Variable ist der **increment**-Operator.</span><span class="sxs-lookup"><span data-stu-id="4740b-172">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="4740b-173">Der Wert von 1 hinzugefügt `counter` und speichert diesen Wert in der `counter` Variable.</span><span class="sxs-lookup"><span data-stu-id="4740b-173">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4740b-174">Stellen Sie sicher, dass die `while` Schleife Bedingung Änderungen auf "false", wenn Sie den Code ausführen.</span><span class="sxs-lookup"><span data-stu-id="4740b-174">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="4740b-175">Erstellen Sie anderenfalls eine **Endlosschleife**, durch die das Programm niemals beendet wird.</span><span class="sxs-lookup"><span data-stu-id="4740b-175">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="4740b-176">Wird nicht in diesem Beispiel wird veranschaulicht, Schreibberechtigung erzwingen das Programm zu beenden, verwenden **STRG + C** oder auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="4740b-176">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="4740b-177">Die `while`-Schleife testet die Bedingung, bevor der Code nach `while` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4740b-177">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="4740b-178">Die `do` ... `while`-Schleife führt den Code zuerst aus und überprüft anschließend die Bedingung.</span><span class="sxs-lookup"><span data-stu-id="4740b-178">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="4740b-179">Die stimmen während der Schleife in den folgenden Code gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="4740b-179">The do while loop is shown in the following code:</span></span>

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="4740b-180">Dies `do` Schleife und die frühere `while` Schleife erzeugen dieselbe Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4740b-180">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="4740b-181">Arbeiten mit der for-Schleife</span><span class="sxs-lookup"><span data-stu-id="4740b-181">Work with the for loop</span></span>

<span data-ttu-id="4740b-182">Die **für** Schleife wird üblicherweise in c# verwendet.</span><span class="sxs-lookup"><span data-stu-id="4740b-182">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="4740b-183">Versuchen Sie diesen Code in der Main()-Methode aus:</span><span class="sxs-lookup"><span data-stu-id="4740b-183">Try this code in your Main() method:</span></span>

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

<span data-ttu-id="4740b-184">Dieser funktioniert auf dieselbe Weise wie die `while`-Schleife und die `do`-Schleife, die Sie bereits verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="4740b-184">This does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="4740b-185">Die `for`-Anweisung besteht aus drei Teilen, die steuern, wie sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4740b-185">The `for` statement has three parts that control how it works.</span></span> 

<span data-ttu-id="4740b-186">Der erste Teil ist der **for-Initialisierer**: `for index = 0;` deklariert, dass `index` die Schleifenvariable ist, und legt den Anfangswert auf `0` fest.</span><span class="sxs-lookup"><span data-stu-id="4740b-186">The first part is the **for initializer**: `for index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="4740b-187">Der mittlere Teil ist die **for-Bedingung**: `index < 10` deklariert, dass diese `for`-Schleife ausgeführt wird, solange der Wert des Zählers kleiner als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="4740b-187">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="4740b-188">Der letzte Teil ist der **for-Iterator**: `index++` gibt an, wie die Schleifenvariable geändert wird, nachdem der Block nach der `for`-Anweisung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="4740b-188">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="4740b-189">Hier gibt dieser an, dass `index` bei jeder Blockausführung um 1 erhöht werden soll.</span><span class="sxs-lookup"><span data-stu-id="4740b-189">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="4740b-190">Experimentieren Sie selbst damit.</span><span class="sxs-lookup"><span data-stu-id="4740b-190">Experiment with these yourself.</span></span> <span data-ttu-id="4740b-191">Testen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4740b-191">Try each of the following:</span></span>

- <span data-ttu-id="4740b-192">Ändern Sie den Initialisierer, um mit einem anderen Wert zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="4740b-192">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="4740b-193">Ändern Sie die Bedingung, um an einem anderen Wert anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="4740b-193">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="4740b-194">Wenn Sie fertig sind, fahren Sie damit fort, mithilfe der erworbenen Kenntnisse selbst Codes zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="4740b-194">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="4740b-195">Zusammenführen von Verzweigungen Schleifen</span><span class="sxs-lookup"><span data-stu-id="4740b-195">Combine branches and loops</span></span>

<span data-ttu-id="4740b-196">Nachdem Sie nun die `if`-Anweisung und die Schleifenkonstrukte in der Programmiersprache C# kennengelernt haben, versuchen Sie, einen C#-Code zu schreiben, der die Summe aller ganzen Zahlen von 1 bis 20 ermittelt, die durch 3 teilbar sind.</span><span class="sxs-lookup"><span data-stu-id="4740b-196">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="4740b-197">Im Folgenden einige Tipps:</span><span class="sxs-lookup"><span data-stu-id="4740b-197">Here are a few hints:</span></span>

- <span data-ttu-id="4740b-198">Der `%`-Operator ermittelt den Restwert einer Divisionsoperation.</span><span class="sxs-lookup"><span data-stu-id="4740b-198">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="4740b-199">Die `if` -Anweisung können Sie die Bedingung aus, um festzustellen, ob eine Zahl Teilen der Summe sein darf.</span><span class="sxs-lookup"><span data-stu-id="4740b-199">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="4740b-200">Die `for`-Schleife ermöglicht es, eine Reihe von Schritten für alle Zahlen von 1 bis 20 zu wiederholen.</span><span class="sxs-lookup"><span data-stu-id="4740b-200">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="4740b-201">Probieren Sie es selbst aus.</span><span class="sxs-lookup"><span data-stu-id="4740b-201">Try it yourself.</span></span> <span data-ttu-id="4740b-202">Prüfen Sie dann, wie Sie abgeschnitten haben.</span><span class="sxs-lookup"><span data-stu-id="4740b-202">Then check how you did.</span></span> <span data-ttu-id="4740b-203">Sehen Sie eine Antwort von [den fertigen Code auf GitHub anzeigen](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span><span class="sxs-lookup"><span data-stu-id="4740b-203">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="4740b-204">Sie haben die "Verzweigungen und Schleifen" Schnellstart abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4740b-204">You've completed the "branches and loops" quick start.</span></span>

<span data-ttu-id="4740b-205">Sie können weiterhin mit der [Arrays und Sammlungen](arrays-and-collections.md) schnellen Einstieg in die Entwicklungsumgebung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="4740b-205">You can continue with the [Arrays and collections](arrays-and-collections.md) quick start in your own development environment.</span></span>

<span data-ttu-id="4740b-206">Weitere Informationen zu diesen Begriffen finden Sie unter folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="4740b-206">You can learn more about these concepts in these topics:</span></span>

<span data-ttu-id="4740b-207">[if- und else-Anweisung](../language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="4740b-207">[If and else statement](../language-reference/keywords/if-else.md) </span></span>  
<span data-ttu-id="4740b-208">[while-Anweisung](../language-reference/keywords/while.md) </span><span class="sxs-lookup"><span data-stu-id="4740b-208">[While statement](../language-reference/keywords/while.md) </span></span>  
<span data-ttu-id="4740b-209">[do-Anweisung](../language-reference/keywords/do.md) </span><span class="sxs-lookup"><span data-stu-id="4740b-209">[Do statement](../language-reference/keywords/do.md) </span></span>  
[<span data-ttu-id="4740b-210">for-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4740b-210">For statement</span></span>](../language-reference/keywords/for.md)   
