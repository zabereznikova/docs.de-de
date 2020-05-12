---
title: Zahlen in C# – Einführung in das C#-Tutorial
description: Machen Sie sich mit C# vertraut, indem Sie numerische Typen sowie deren Verwendung, Eigenschaften und Methoden erkunden.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: 3dc2a5afc6321da45351525a632f586cb84bf7fe
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794610"
---
# <a name="manipulate-integral-and-floating-point-numbers-in-c"></a><span data-ttu-id="32b4f-103">Bearbeiten von Ganzzahlen und Gleitkommazahlen in C\#</span><span class="sxs-lookup"><span data-stu-id="32b4f-103">Manipulate integral and floating point numbers in C\#</span></span>

<span data-ttu-id="32b4f-104">Dieses interaktive Tutorial erläutert die numerischen Typen in C#.</span><span class="sxs-lookup"><span data-stu-id="32b4f-104">This tutorial teaches you about the numeric types in C# interactively.</span></span> <span data-ttu-id="32b4f-105">Sie schreiben einen Teil des Codes, kompilieren diesen und führen ihn aus.</span><span class="sxs-lookup"><span data-stu-id="32b4f-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="32b4f-106">Das Tutorial enthält eine Reihe von Lektionen, in denen Zahlen und mathematische Vorgänge in C# untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="32b4f-106">The tutorial contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="32b4f-107">In diesen Lektionen lernen Sie die Grundlagen der Programmiersprache C# kennen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="32b4f-108">Für dieses Tutorial benötigen Sie einen Computer, den Sie für die Entwicklung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="32b4f-108">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="32b4f-109">Im .NET-Tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) (Hallo Welt in zehn Minuten) finden Sie eine Anleitung zum Einrichten Ihrer lokalen Entwicklungsumgebung unter Windows, Linux oder macOS.</span><span class="sxs-lookup"><span data-stu-id="32b4f-109">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="32b4f-110">Einen schnellen Überblick über die Befehle, die Sie verwenden werden, finden Sie im Artikel [Einführung in Entwicklungstools](local-environment.md), der Links zu weiteren Ressourcen enthält.</span><span class="sxs-lookup"><span data-stu-id="32b4f-110">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="32b4f-111">Erkunden von arithmetischen Operationen mit ganzen Zahlen</span><span class="sxs-lookup"><span data-stu-id="32b4f-111">Explore integer math</span></span>

<span data-ttu-id="32b4f-112">Erstellen Sie ein Verzeichnis mit dem Namen *numbers-quickstart*.</span><span class="sxs-lookup"><span data-stu-id="32b4f-112">Create a directory named *numbers-quickstart*.</span></span> <span data-ttu-id="32b4f-113">Legen Sie dieses als das aktuelle Verzeichnis fest, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="32b4f-113">Make that the current directory and run the following command:</span></span>

```dotnetcli
dotnet new console -n NumbersInCSharp -o .
```

<span data-ttu-id="32b4f-114">Öffnen Sie *Program.cs* in Ihrem bevorzugten Editor, und ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="32b4f-114">Open *Program.cs* in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="32b4f-115">Führen Sie diesen Code aus, indem Sie `dotnet run` in Ihr Befehlsfenster eingeben.</span><span class="sxs-lookup"><span data-stu-id="32b4f-115">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="32b4f-116">Sie haben eine der grundlegenden arithmetischen Operationen mit ganzen Zahlen kennengelernt.</span><span class="sxs-lookup"><span data-stu-id="32b4f-116">You've seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="32b4f-117">Der `int`-Typ steht für **integer**, d. h. eine Null oder eine positive oder negative ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="32b4f-117">The `int` type represents an **integer**, a zero, positive, or negative whole number.</span></span> <span data-ttu-id="32b4f-118">Sie verwenden zum Addieren das `+`-Symbol.</span><span class="sxs-lookup"><span data-stu-id="32b4f-118">You use the `+` symbol for addition.</span></span> <span data-ttu-id="32b4f-119">Zu den anderen häufig verwendeten arithmetischen Operationen für ganze Zahlen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="32b4f-119">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="32b4f-120">`-` zur Subtraktion</span><span class="sxs-lookup"><span data-stu-id="32b4f-120">`-` for subtraction</span></span>
- <span data-ttu-id="32b4f-121">`*` zur Multiplikation</span><span class="sxs-lookup"><span data-stu-id="32b4f-121">`*` for multiplication</span></span>
- <span data-ttu-id="32b4f-122">`/` zur Division</span><span class="sxs-lookup"><span data-stu-id="32b4f-122">`/` for division</span></span>

<span data-ttu-id="32b4f-123">Erkunden Sie zunächst die anderen Operationen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-123">Start by exploring those different operations.</span></span> <span data-ttu-id="32b4f-124">Fügen Sie diese Zeilen nach der Zeile hinzu, die den Wert von `c` schreibt:</span><span class="sxs-lookup"><span data-stu-id="32b4f-124">Add these lines after the line that writes the value of `c`:</span></span>

```csharp

// subtraction
c = a - b;
Console.WriteLine(c);

// multiplication
c = a * b;
Console.WriteLine(c);

// division
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="32b4f-125">Führen Sie diesen Code aus, indem Sie `dotnet run` in Ihr Befehlsfenster eingeben.</span><span class="sxs-lookup"><span data-stu-id="32b4f-125">Run this code by typing `dotnet run` in your command window.</span></span>

<span data-ttu-id="32b4f-126">Wenn Sie möchten, können Sie auch experimentieren, indem Sie mehrere arithmetische Operationen in dieselbe Zeile schreiben.</span><span class="sxs-lookup"><span data-stu-id="32b4f-126">You can also experiment by writing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="32b4f-127">Testen Sie zum Beispiel `c = a + b - 12 * 17;`.</span><span class="sxs-lookup"><span data-stu-id="32b4f-127">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="32b4f-128">Das Kombinieren von Variablen und konstanten Zahlen ist erlaubt.</span><span class="sxs-lookup"><span data-stu-id="32b4f-128">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="32b4f-129">Bei Ihren ersten Schritten mit C# (oder einer anderen Programmiersprache) kann es zu Fehlern kommen, wenn Sie Codes schreiben.</span><span class="sxs-lookup"><span data-stu-id="32b4f-129">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="32b4f-130">Der **Compiler** findet diese Fehler und meldet diese.</span><span class="sxs-lookup"><span data-stu-id="32b4f-130">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="32b4f-131">Sollte die Ausgabe Fehlermeldungen enthalten, sehen Sie sich den Beispielcode und den Code in Ihrem Fenster an, um festzustellen, was behoben werden muss.</span><span class="sxs-lookup"><span data-stu-id="32b4f-131">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="32b4f-132">Durch diese Übung lernen Sie die Struktur eines C#-Codes kennen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-132">That exercise will help you learn the structure of C# code.</span></span>

<span data-ttu-id="32b4f-133">Sie haben den ersten Schritt abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-133">You've finished the first step.</span></span> <span data-ttu-id="32b4f-134">Bevor Sie mit dem nächsten Abschnitt beginnen, verschieben wir den aktuellen Code in eine separate Methode.</span><span class="sxs-lookup"><span data-stu-id="32b4f-134">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="32b4f-135">Dies erleichtert das Arbeiten mit einem neuen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="32b4f-135">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="32b4f-136">Benennen Sie Ihre `Main` -Methode in `WorkingWithIntegers` um, und schreiben Sie eine neue `Main`-Methode, die `WorkingWithIntegers` aufruft.</span><span class="sxs-lookup"><span data-stu-id="32b4f-136">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="32b4f-137">Anschließend sollte der Code wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="32b4f-137">When you finish, your code should look like this:</span></span>

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
            c = a / b;
            Console.WriteLine(c);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();
        }
    }
}
```

## <a name="explore-order-of-operations"></a><span data-ttu-id="32b4f-138">Erkunden der Reihenfolge der Operationen</span><span class="sxs-lookup"><span data-stu-id="32b4f-138">Explore order of operations</span></span>

<span data-ttu-id="32b4f-139">Kommentieren Sie den Aufruf von `WorkingWithIntegers()` aus.</span><span class="sxs-lookup"><span data-stu-id="32b4f-139">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="32b4f-140">Dadurch wird die Ausgabe weniger überladen, wenn Sie in diesem Abschnitt arbeiten:</span><span class="sxs-lookup"><span data-stu-id="32b4f-140">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="32b4f-141">Mit `//` wird ein **Kommentar** in C# begonnen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-141">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="32b4f-142">Kommentare sind Texte, die Sie in Ihrem Quellcode beibehalten, jedoch nicht als Code ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="32b4f-142">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="32b4f-143">Der Compiler generiert keinen ausführbaren Code über die Kommentare.</span><span class="sxs-lookup"><span data-stu-id="32b4f-143">The compiler doesn't generate any executable code from comments.</span></span>

<span data-ttu-id="32b4f-144">Die Programmiersprache C# definiert anhand von Regeln, die Sie aus der Mathematik kennen, die Rangfolge verschiedener arithmetischer Operationen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-144">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="32b4f-145">Multiplikation und Division haben gegenüber der Addition und Subtraktion Vorrang.</span><span class="sxs-lookup"><span data-stu-id="32b4f-145">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="32b4f-146">Überprüfen Sie das, indem Sie den folgenden Code Ihrer `Main`-Methode hinzufügen und `dotnet run` ausführen:</span><span class="sxs-lookup"><span data-stu-id="32b4f-146">Explore that by adding the following code to your `Main` method, and executing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="32b4f-147">Die Ausgabe zeigt, dass vor der Addition die Multiplikation ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="32b4f-147">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="32b4f-148">Sie können eine andere Operationsreihenfolge erzwingen, indem Sie die Operation bzw. die Operationen, die zuerst ausgeführt werden soll bzw. sollen, mit Klammern umschließen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-148">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="32b4f-149">Fügen Sie die folgenden Zeilen hinzu, und führen Sie sie aus:</span><span class="sxs-lookup"><span data-stu-id="32b4f-149">Add the following lines and run again:</span></span>

```csharp
d = (a + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="32b4f-150">Machen Sie sich damit vertraut, indem Sie viele verschiedene Operationen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="32b4f-150">Explore more by combining many different operations.</span></span> <span data-ttu-id="32b4f-151">Fügen Sie eine Zeile hinzu, die ungefähr den folgenden Zeilen am Ende Ihrer `Main`-Methode entspricht.</span><span class="sxs-lookup"><span data-stu-id="32b4f-151">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="32b4f-152">Testen Sie erneut `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="32b4f-152">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="32b4f-153">Vielleicht haben Sie bereits ein interessantes Verhalten bei den ganzen Zahlen bemerkt.</span><span class="sxs-lookup"><span data-stu-id="32b4f-153">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="32b4f-154">Bei der Division ganzer Zahlen kommt immer ein ganzzahliges Ergebnis heraus, selbst wenn Sie als Ergebnis einen Dezimal- oder Bruchteil erwarten würden.</span><span class="sxs-lookup"><span data-stu-id="32b4f-154">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="32b4f-155">Wenn Sie dieses Verhalten noch nicht beobachtet haben, testen Sie den folgenden Code am Ende Ihrer `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="32b4f-155">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="32b4f-156">Geben Sie erneut `dotnet run` ein, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-156">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="32b4f-157">Bevor Sie fortfahren, kopieren Sie den gesamten Code, den Sie in diesem Abschnitt geschrieben haben, und fügen ihn in eine neue Methode ein.</span><span class="sxs-lookup"><span data-stu-id="32b4f-157">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="32b4f-158">Rufen Sie die neue Methode `OrderPrecedence` auf.</span><span class="sxs-lookup"><span data-stu-id="32b4f-158">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="32b4f-159">Sie sollten etwas wie das Folgende schreiben:</span><span class="sxs-lookup"><span data-stu-id="32b4f-159">You should write something like this:</span></span>

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;

            // addition
            int c = a + b;
            Console.WriteLine(c);

            // subtraction
            c = a - b;
            Console.WriteLine(c);

            // multiplication
            c = a * b;
            Console.WriteLine(c);

            // division
            c = a / b;
            Console.WriteLine(c);
        }

        static void OrderPrecedence()
        {
            int a = 5;
            int b = 4;
            int c = 2;
            int d = a + b * c;
            Console.WriteLine(d);

            d = (a + b) * c;
            Console.WriteLine(d);

            d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
            Console.WriteLine(d);

            int e = 7;
            int f = 4;
            int g = 3;
            int h = (e  + f) / g;
            Console.WriteLine(h);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();

            OrderPrecedence();

        }
    }
}
```

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="32b4f-160">Erkunden der Genauigkeit und Grenzwerte ganzer Zahlen</span><span class="sxs-lookup"><span data-stu-id="32b4f-160">Explore integer precision and limits</span></span>

<span data-ttu-id="32b4f-161">Im vorherigen Beispiel haben Sie gesehen, dass das Ergebnis bei der Division ganzer Zahlen abgeschnitten wird.</span><span class="sxs-lookup"><span data-stu-id="32b4f-161">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="32b4f-162">Sie erhalten den Restwert **remainder** mithilfe des **Modulo**-Operators, dem `%`-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-162">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="32b4f-163">Testen Sie den folgenden Code in Ihrer `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="32b4f-163">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="32b4f-164">Der integer-C#-Typ unterscheidet sich noch in einem weiteren Punkt von einer mathematischen ganzen Zahl: Der `int`-Typ ist mit minimalen und maximalen Grenzwerten versehen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-164">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="32b4f-165">Fügen Sie diesen Code zu Ihrer `Main`-Methode hinzu, um die jeweiligen Grenzwerte zu sehen:</span><span class="sxs-lookup"><span data-stu-id="32b4f-165">Add this code to your `Main` method to see those limits:</span></span>

```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="32b4f-166">Wenn bei einer Berechnung ein Wert herauskommt, der diese Grenzwerte überschreitet, liegt eine **Unterlauf-** oder **Überlaufbedingung** vor.</span><span class="sxs-lookup"><span data-stu-id="32b4f-166">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="32b4f-167">Die Antwort gibt dann den Bereich der Grenzwerte an.</span><span class="sxs-lookup"><span data-stu-id="32b4f-167">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="32b4f-168">Fügen Sie die folgenden zwei Zeilen zu Ihrer `Main`-Methode hinzu, um ein Beispiel zu sehen:</span><span class="sxs-lookup"><span data-stu-id="32b4f-168">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```

<span data-ttu-id="32b4f-169">Beachten Sie, dass die Antwort sehr nah an der minimalen (negativen) ganzen Zahl liegt.</span><span class="sxs-lookup"><span data-stu-id="32b4f-169">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="32b4f-170">Sie entspricht `min + 2`.</span><span class="sxs-lookup"><span data-stu-id="32b4f-170">It's the same as `min + 2`.</span></span>
<span data-ttu-id="32b4f-171">Die Additionsoperation hat die zulässigen Werte für ganze Zahlen **überlaufen**.</span><span class="sxs-lookup"><span data-stu-id="32b4f-171">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="32b4f-172">Die Antwort enthält eine sehr große negative Zahl, da ein Überlauf den größtmöglichen ganzzahligen Wert bis zum kleinstmöglichen Wert umschließt.</span><span class="sxs-lookup"><span data-stu-id="32b4f-172">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="32b4f-173">Wenn der `int`-Typ nicht Ihren Anforderungen entspricht, so gibt es verschiedene numerische Typen mit anderen Grenzwerten und Genauigkeitsgraden, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="32b4f-173">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="32b4f-174">Werfen wir im Folgenden einmal einen Blick auf diese anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-174">Let's explore those other types next.</span></span>

<span data-ttu-id="32b4f-175">Fügen Sie den Code, den Sie in diesem Abschnitt geschrieben haben, wieder in eine separate Methode ein.</span><span class="sxs-lookup"><span data-stu-id="32b4f-175">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="32b4f-176">Nennen Sie es `TestLimits`.</span><span class="sxs-lookup"><span data-stu-id="32b4f-176">Name it `TestLimits`.</span></span>

## <a name="work-with-the-double-type"></a><span data-ttu-id="32b4f-177">Arbeiten mit dem Double-Typ</span><span class="sxs-lookup"><span data-stu-id="32b4f-177">Work with the double type</span></span>

<span data-ttu-id="32b4f-178">Der numerische Typ `double` stellt eine Gleitkommazahl mit doppelter Genauigkeit dar.</span><span class="sxs-lookup"><span data-stu-id="32b4f-178">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="32b4f-179">Falls Ihnen diese Benennungen nichts sagen, beachten Sie die folgenden Erläuterungen:</span><span class="sxs-lookup"><span data-stu-id="32b4f-179">Those terms may be new to you.</span></span> <span data-ttu-id="32b4f-180">Eine **Gleitkommazahl** wird verwendet, um sehr große oder sehr kleine Zahlen, die keine ganzen Zahlen sind, darzustellen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-180">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="32b4f-181">**Doppelte Genauigkeit** ist ein relativer Begriff, der die Anzahl der binären Ziffern beschreibt, die zum Speichern des Werts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="32b4f-181">**Double-precision** is a relative term that describes the number of binary digits used to store the value.</span></span> <span data-ttu-id="32b4f-182">Zahlen mit **doppelter Genauigkeit** besitzen die doppelte Anzahl von binären Ziffern wie Zahlen mit **einfacher Genauigkeit**.</span><span class="sxs-lookup"><span data-stu-id="32b4f-182">**Double precision** numbers have twice the number of binary digits as **single-precision**.</span></span> <span data-ttu-id="32b4f-183">Auf Bei modernen Computern werden häufiger Zahlen mit doppelter Genauigkeit verwendet statt mit einfacher Genauigkeit.</span><span class="sxs-lookup"><span data-stu-id="32b4f-183">On modern computers, it's more common to use double precision than single precision numbers.</span></span> <span data-ttu-id="32b4f-184">Zahlen mit **einfacher Genauigkeit** werden mit dem Schlüsselwort `float` deklariert.</span><span class="sxs-lookup"><span data-stu-id="32b4f-184">**Single precision** numbers are declared using the `float` keyword.</span></span>
<span data-ttu-id="32b4f-185">Sehen wir uns dies einmal genauer an.</span><span class="sxs-lookup"><span data-stu-id="32b4f-185">Let's explore.</span></span> <span data-ttu-id="32b4f-186">Fügen Sie den folgenden Code hinzu, und zeigen Sie das Ergebnis an:</span><span class="sxs-lookup"><span data-stu-id="32b4f-186">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="32b4f-187">Beachten Sie, dass die Antwort die Dezimalzahl des Quotienten enthält.</span><span class="sxs-lookup"><span data-stu-id="32b4f-187">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="32b4f-188">Testen Sie einen etwas komplizierteren Ausdruck mit Werten vom Typ „double“:</span><span class="sxs-lookup"><span data-stu-id="32b4f-188">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="32b4f-189">Der Bereich eines Werts vom Typ „double“ ist weitaus größer als bei ganzzahligen Werten.</span><span class="sxs-lookup"><span data-stu-id="32b4f-189">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="32b4f-190">Fügen Sie den folgenden Code unter dem Code hinzu, den Sie bereits geschrieben haben:</span><span class="sxs-lookup"><span data-stu-id="32b4f-190">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="32b4f-191">Diese Werte werden in der wissenschaftlichen Schreibweise ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="32b4f-191">These values are printed out in scientific notation.</span></span> <span data-ttu-id="32b4f-192">Die Zahl links von `E` ist die Mantisse.</span><span class="sxs-lookup"><span data-stu-id="32b4f-192">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="32b4f-193">Die Zahl rechts ist der Exponent als Potenz von 10.</span><span class="sxs-lookup"><span data-stu-id="32b4f-193">The number to the right is the exponent, as a power of 10.</span></span>

<span data-ttu-id="32b4f-194">Wie bei Dezimalzahlen in der Mathematik können double-Werte in C# Rundungsfehler aufweisen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-194">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="32b4f-195">Testen Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="32b4f-195">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="32b4f-196">Denken Sie daran, dass `0.3` Periode nicht exakt `1/3` entspricht.</span><span class="sxs-lookup"><span data-stu-id="32b4f-196">You know that `0.3` repeating isn't exactly the same as `1/3`.</span></span>

<span data-ttu-id="32b4f-197">***Übung***</span><span class="sxs-lookup"><span data-stu-id="32b4f-197">***Challenge***</span></span>

<span data-ttu-id="32b4f-198">Testen Sie für den `double`-Typ andere Berechnungen mit großen und kleinen Zahlen sowie mit Multiplikation und Division.</span><span class="sxs-lookup"><span data-stu-id="32b4f-198">Try other calculations with large numbers, small numbers, multiplication, and division using the `double` type.</span></span> <span data-ttu-id="32b4f-199">Testen Sie kompliziertere Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-199">Try more complicated calculations.</span></span>

<span data-ttu-id="32b4f-200">Nachdem Sie sich nun einige Zeit lang mit der Übung auseinander gesetzt haben, kopieren Sie den von Ihnen geschriebenen Code, und fügen Sie ihn in eine neue Methode ein.</span><span class="sxs-lookup"><span data-stu-id="32b4f-200">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="32b4f-201">Vergeben Sie einen Namen für die neue Methode `WorkWithDoubles`.</span><span class="sxs-lookup"><span data-stu-id="32b4f-201">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-decimal-types"></a><span data-ttu-id="32b4f-202">Arbeiten mit Dezimaltypen</span><span class="sxs-lookup"><span data-stu-id="32b4f-202">Work with decimal types</span></span>

<span data-ttu-id="32b4f-203">Sie haben die grundlegenden numerischen Typen in C# – „integer“ und „double“ – kennengelernt.</span><span class="sxs-lookup"><span data-stu-id="32b4f-203">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="32b4f-204">Es gibt einen weiteren Typ, den Sie kennen sollten: den `decimal`-Typ.</span><span class="sxs-lookup"><span data-stu-id="32b4f-204">There's one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="32b4f-205">Der `decimal`-Typ weist einen kleineren Bereich als `double` auf, aber eine höhere Genauigkeit.</span><span class="sxs-lookup"><span data-stu-id="32b4f-205">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="32b4f-206">Sehen wir uns das einmal genauer an:</span><span class="sxs-lookup"><span data-stu-id="32b4f-206">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="32b4f-207">Beachten Sie, dass der Bereich kleiner ist als beim `double`-Typ.</span><span class="sxs-lookup"><span data-stu-id="32b4f-207">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="32b4f-208">Sie können sehen, dass die Genauigkeit beim Typ „decimal“ höher ist, wenn Sie den folgenden Code testen:</span><span class="sxs-lookup"><span data-stu-id="32b4f-208">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="32b4f-209">Mit dem Suffix `M` neben einer Zahl geben Sie an, dass eine Konstante den `decimal`-Typ verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="32b4f-209">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span> <span data-ttu-id="32b4f-210">Andernfalls nimmt der Compiler den Typ `double` an.</span><span class="sxs-lookup"><span data-stu-id="32b4f-210">Otherwise, the compiler assumes the `double` type.</span></span>

> [!NOTE]
> <span data-ttu-id="32b4f-211">Der Buchstabe `M` wurde als visuell eindeutigster Buchstabe zur Unterscheidung zwischen den Schlüsselwörtern `double` und `decimal` ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="32b4f-211">The letter `M` was chosen as the most visually distinct letter between the `double` and `decimal` keywords.</span></span>

<span data-ttu-id="32b4f-212">Beachten Sie, dass der aus dieser arithmetischen Operation resultierende Wert vom Typ „decimal“ rechts neben dem Dezimalpunkt mehr Ziffern enthält.</span><span class="sxs-lookup"><span data-stu-id="32b4f-212">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span>

<span data-ttu-id="32b4f-213">***Übung***</span><span class="sxs-lookup"><span data-stu-id="32b4f-213">***Challenge***</span></span>

<span data-ttu-id="32b4f-214">Nachdem Sie nun die verschiedenen numerischen Typen kennengelernt haben, schreiben Sie Code, der den Flächeninhalt eines Kreises mit einem Radius von 2,5 cm berechnet.</span><span class="sxs-lookup"><span data-stu-id="32b4f-214">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 centimeters.</span></span> <span data-ttu-id="32b4f-215">Denken Sie daran, dass der Flächeninhalt eines Kreises durch das Quadrat des Radius multipliziert mit Pi gebildet wird.</span><span class="sxs-lookup"><span data-stu-id="32b4f-215">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="32b4f-216">Hinweis: .NET bietet eine Konstante für Pi (<xref:System.Math.PI?displayProperty=nameWithType>), die Sie für die Berechnung dieses Werts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="32b4f-216">One hint: .NET contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> <span data-ttu-id="32b4f-217"><xref:System.Math.PI?displayProperty=nameWithType>, wie alle im `System.Math`-Namespace deklarierten Konstanten, ist ein `double`-Wert.</span><span class="sxs-lookup"><span data-stu-id="32b4f-217"><xref:System.Math.PI?displayProperty=nameWithType>, like all constants declared in the `System.Math` namespace, is a `double` value.</span></span> <span data-ttu-id="32b4f-218">Aus diesem Grund sollten Sie `double` anstelle von `decimal`-Werten für diese Aufgabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="32b4f-218">For that reason, you should use `double` instead of `decimal` values for this challenge.</span></span>

<span data-ttu-id="32b4f-219">Sie sollten eine Antwort zwischen 19 und 20 erhalten.</span><span class="sxs-lookup"><span data-stu-id="32b4f-219">You should get an answer between 19 and 20.</span></span>
<span data-ttu-id="32b4f-220">Sie können Ihre Antwort anhand des [fertig gestellten Beispielcodes auf GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106) prüfen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-220">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span></span>

<span data-ttu-id="32b4f-221">Wenn Sie möchten, testen Sie andere Formeln.</span><span class="sxs-lookup"><span data-stu-id="32b4f-221">Try some other formulas if you'd like.</span></span>

<span data-ttu-id="32b4f-222">Sie haben den Schnellstart „Zahlen in C#“ abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="32b4f-222">You've completed the "Numbers in C#" quickstart.</span></span> <span data-ttu-id="32b4f-223">Sie können mit dem Schnellstart [Branches und Schleifen](branches-and-loops-local.md) in Ihrer eigenen Entwicklungsumgebung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="32b4f-223">You can continue with the [Branches and loops](branches-and-loops-local.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="32b4f-224">Weitere Informationen zu Zahlen in C# finden Sie auch in folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="32b4f-224">You can learn more about numbers in C# in the following articles:</span></span>

- [<span data-ttu-id="32b4f-225">Integrale numerische Typen</span><span class="sxs-lookup"><span data-stu-id="32b4f-225">Integral numeric types</span></span>](../../language-reference/builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="32b4f-226">Numerische Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="32b4f-226">Floating-point numeric types</span></span>](../../language-reference/builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="32b4f-227">Integrierte numerischer Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="32b4f-227">Built-in numeric conversions</span></span>](../../language-reference/builtin-types/numeric-conversions.md)
