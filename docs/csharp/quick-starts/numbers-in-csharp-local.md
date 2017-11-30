---
title: Schnellstart - Zahlen in c# - C#-Handbuch
description: Erlernen von c# durch das Durchsuchen von numerischen Typen, deren Eigenschaften und Methoden.
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 821cca4ea6d6148410e9b179f05d5b74c4844628
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2017
---
# <a name="numbers-in-c-quick-start"></a><span data-ttu-id="5339d-103">Zahlen in C#-Schnellstart</span><span class="sxs-lookup"><span data-stu-id="5339d-103">Numbers in C# quick start</span></span> #

<span data-ttu-id="5339d-104">Dieser Schnellstart erfahren Sie, über die Number-Typen in c# interaktiv.</span><span class="sxs-lookup"><span data-stu-id="5339d-104">This quick start teaches you about the number types in C# interactively.</span></span> <span data-ttu-id="5339d-105">Schreiben Sie kleine Mengen von Code, und Sie kompilieren und Ausführen dieses Codes.</span><span class="sxs-lookup"><span data-stu-id="5339d-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="5339d-106">Der Schnellstart enthält eine Reihe von Lektionen, in denen Zahlen und mathematische Operationen in c# zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="5339d-106">The quick start contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="5339d-107">In diesen Lektionen lernen Sie die Grundlagen der Programmiersprache C# kennen.</span><span class="sxs-lookup"><span data-stu-id="5339d-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="5339d-108">Dieser Schnellstart erwartet, dass Sie einen Computer verfügen, den Sie für die Entwicklung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5339d-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="5339d-109">Das Thema .NET [Einstieg in 10 Minuten](https://www.microsoft.com/net/core) umfasst Anweisungen zum Einrichten der lokalen Entwicklungsumgebung auf Mac, PC oder Linux.</span><span class="sxs-lookup"><span data-stu-id="5339d-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="5339d-110">Erkunden von arithmetischen Operationen mit ganzen Zahlen</span><span class="sxs-lookup"><span data-stu-id="5339d-110">Explore integer math</span></span>

<span data-ttu-id="5339d-111">Erstellen Sie ein Verzeichnis mit dem Namen **Zahlen Schnellstart**.</span><span class="sxs-lookup"><span data-stu-id="5339d-111">Create a directory named **numbers-quickstart**.</span></span> <span data-ttu-id="5339d-112">Machen Sie dieses Verzeichnis zum aktuellen Verzeichnis, und führen Sie `dotnet new console -n NumbersInCSharp -o .` aus.</span><span class="sxs-lookup"><span data-stu-id="5339d-112">Make that the current directory and run `dotnet new console -n NumbersInCSharp -o .`.</span></span>

<span data-ttu-id="5339d-113">Open **"Program.cs"** in Ihrem bevorzugten Editor, und Ersetzen Sie die Zeile `Console.Writeline("Hello World!");` durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5339d-113">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="5339d-114">Führen Sie diesen Code durch Eingabe `dotnet run` in das Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="5339d-114">Run this code by typing `dotnet run` in your command window.</span></span> 

<span data-ttu-id="5339d-115">Sie haben soeben eine der grundlegenden arithmetischen Operationen mit ganzen Zahlen kennengelernt.</span><span class="sxs-lookup"><span data-stu-id="5339d-115">You've just seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="5339d-116">Der `int`-Typ steht für **integer**, d.h. eine positive oder negative ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="5339d-116">The `int` type represents an **integer**, a positive or negative whole number.</span></span> <span data-ttu-id="5339d-117">Sie verwenden zum Addieren das `+`-Symbol.</span><span class="sxs-lookup"><span data-stu-id="5339d-117">You use the `+` symbol for addition.</span></span> <span data-ttu-id="5339d-118">Zu den anderen häufig verwendeten arithmetischen Operationen für ganze Zahlen zählen Folgende:</span><span class="sxs-lookup"><span data-stu-id="5339d-118">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="5339d-119">`-` zur Subtraktion</span><span class="sxs-lookup"><span data-stu-id="5339d-119">`-` for subtraction</span></span>
- <span data-ttu-id="5339d-120">`*` zur Multiplikation</span><span class="sxs-lookup"><span data-stu-id="5339d-120">`*` for multiplication</span></span>
- <span data-ttu-id="5339d-121">`/` zur Division</span><span class="sxs-lookup"><span data-stu-id="5339d-121">`/` for division</span></span>

<span data-ttu-id="5339d-122">Erkunden Sie zunächst die anderen Operationen.</span><span class="sxs-lookup"><span data-stu-id="5339d-122">Start by exploring those different operations.</span></span> <span data-ttu-id="5339d-123">Fügen Sie nach der Zeile, die den Wert der schreibt diese Zeilen `c`:</span><span class="sxs-lookup"><span data-stu-id="5339d-123">Add these lines after the line that writes the value of `c`:</span></span>

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="5339d-124">Führen Sie diesen Code durch Eingabe `dotnet run` in das Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="5339d-124">Run this code by typing `dotnet run` in your command window.</span></span> 
    
<span data-ttu-id="5339d-125">Wenn Sie möchten, können Sie auch experimentieren, indem Sie mehrere arithmetische Operationen in der gleichen Zeile ausführen.</span><span class="sxs-lookup"><span data-stu-id="5339d-125">You can also experiment by performing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="5339d-126">Wiederholen Sie den `c = a + b - 12 * 17;` beispielsweise.</span><span class="sxs-lookup"><span data-stu-id="5339d-126">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="5339d-127">Das Mischen von Variablen und Konstanten Zahlen ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="5339d-127">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="5339d-128">Bei Ihren ersten Schritten mit C# (oder einer anderen Programmiersprache) kann es zu Fehlern kommen, wenn Sie Codes schreiben.</span><span class="sxs-lookup"><span data-stu-id="5339d-128">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="5339d-129">Der **Compiler** findet diese Fehler und meldet diese.</span><span class="sxs-lookup"><span data-stu-id="5339d-129">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="5339d-130">Wenn die Ausgabe Fehlermeldungen enthält, sehen Sie sich den Beispielcode und den Code in das Fenster zu sehen, zu beheben.</span><span class="sxs-lookup"><span data-stu-id="5339d-130">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="5339d-131">Durch diese Übung lernen Sie die Struktur eines C#-Codes kennen.</span><span class="sxs-lookup"><span data-stu-id="5339d-131">That exercise will help you learn the structure of C# code.</span></span>     

<span data-ttu-id="5339d-132">Der erste Schritt ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5339d-132">You've finished the first step.</span></span> <span data-ttu-id="5339d-133">Bevor Sie mit dem nächsten Abschnitt beginnen, verschieben wir den aktuellen Code in eine separate Methode.</span><span class="sxs-lookup"><span data-stu-id="5339d-133">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="5339d-134">Dies erleichtert das Arbeiten mit einem neuen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5339d-134">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="5339d-135">Benennen Sie Ihre `Main` -Methode in `WorkingWithIntegers` um, und schreiben Sie eine neue `Main`-Methode, die `WorkingWithIntegers` aufruft.</span><span class="sxs-lookup"><span data-stu-id="5339d-135">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="5339d-136">Anschließend sollte der Code wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="5339d-136">When you have finished, your code should look like this:</span></span>

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
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
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

## <a name="explore-order-of-operations"></a><span data-ttu-id="5339d-137">Erkunden der Reihenfolge der Operationen</span><span class="sxs-lookup"><span data-stu-id="5339d-137">Explore order of operations</span></span>

<span data-ttu-id="5339d-138">Kommentieren Sie den Aufruf von `WorkingWithIntegers()`.</span><span class="sxs-lookup"><span data-stu-id="5339d-138">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="5339d-139">Die Ausgabe werden vorgenommen, die weniger überladen, wenn Sie in diesem Abschnitt arbeiten:</span><span class="sxs-lookup"><span data-stu-id="5339d-139">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="5339d-140">Die `//` startet eine **Kommentar** in C# geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5339d-140">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="5339d-141">Kommentare sind Text, die Sie in Ihrem Quellcode beibehalten, aber nicht als Code ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="5339d-141">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="5339d-142">Der Compiler löst keine ausführbaren Code von den Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="5339d-142">The compiler does not generate any executable code from comments.</span></span>

<span data-ttu-id="5339d-143">Die Programmiersprache C# definiert anhand von Regeln, die Sie aus der Mathematik kennen, die Rangfolge verschiedener arithmetischer Operationen.</span><span class="sxs-lookup"><span data-stu-id="5339d-143">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="5339d-144">Multiplikation und Division haben gegenüber der Addition und Subtraktion Vorrang.</span><span class="sxs-lookup"><span data-stu-id="5339d-144">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="5339d-145">Prüfen Sie, indem Sie den folgenden Code Hinzufügen Ihrer `Main` -Methode und Execuing `dotnet run`:</span><span class="sxs-lookup"><span data-stu-id="5339d-145">Explore that by adding the following code to your `Main` method, and execuing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="5339d-146">Die Ausgabe zeigt, dass vor der Addition die Multiplikation ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5339d-146">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="5339d-147">Eine andere Reihenfolge des Vorgangs können Sie erzwingen, durch Hinzufügen von Klammern um den Vorgang, oder Vorgänge, die gewünschten zuerst ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5339d-147">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="5339d-148">Fügen Sie die folgenden Zeilen hinzu, und führen Sie erneut aus:</span><span class="sxs-lookup"><span data-stu-id="5339d-148">Add the following lines and run again:</span></span>

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="5339d-149">Machen Sie sich damit vertraut, indem Sie viele verschiedene Operationen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="5339d-149">Explore more by combining many different operations.</span></span> <span data-ttu-id="5339d-150">Fügen Sie etwa die folgenden Zeilen am unteren Rand der `Main` Methode.</span><span class="sxs-lookup"><span data-stu-id="5339d-150">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="5339d-151">Wiederholen Sie den `dotnet run` erneut aus.</span><span class="sxs-lookup"><span data-stu-id="5339d-151">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="5339d-152">Vielleicht haben Sie bereits ein interessantes Verhalten bei den ganzen Zahlen bemerkt.</span><span class="sxs-lookup"><span data-stu-id="5339d-152">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="5339d-153">Ganzzahldivision immer erzeugt ein Ganzzahlergebnis, selbst wenn Sie das Ergebnis ein Teils Dezimalstellen oder Bruchzahlen enthalten erwarten würden.</span><span class="sxs-lookup"><span data-stu-id="5339d-153">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="5339d-154">Wenn Sie dieses Verhalten gesehen haben, wiederholen Sie den folgenden Code am Ende Ihrer `Main` Methode:</span><span class="sxs-lookup"><span data-stu-id="5339d-154">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="5339d-155">Typ `dotnet run` erneut aus, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5339d-155">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="5339d-156">Bevor Sie fortfahren, werfen wir den Code, den Sie in diesem Abschnitt selbst geschrieben haben, und fügen Sie ihn in eine neue Methode.</span><span class="sxs-lookup"><span data-stu-id="5339d-156">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="5339d-157">Diese neue Methode aufzurufen `OrderPrecedence`.</span><span class="sxs-lookup"><span data-stu-id="5339d-157">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="5339d-158">Sie sollte etwa wie folgt zum Schluss:</span><span class="sxs-lookup"><span data-stu-id="5339d-158">You should end up with something like this:</span></span>

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
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
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

            d = (a  + b) * c;
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

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="5339d-159">Erkunden der Genauigkeit und Grenzwerte ganzer Zahlen</span><span class="sxs-lookup"><span data-stu-id="5339d-159">Explore integer precision and limits</span></span>
<span data-ttu-id="5339d-160">Im vorherigen Beispiel haben Sie gesehen, dass das Ergebnis bei der Division ganzer Zahlen abgeschnitten wird.</span><span class="sxs-lookup"><span data-stu-id="5339d-160">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="5339d-161">Erhalten Sie die **Rest** mithilfe der **modulo** -Operator, der `%` Zeichen.</span><span class="sxs-lookup"><span data-stu-id="5339d-161">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="5339d-162">Wiederholen Sie den folgenden Code in Ihrem `Main` Methode:</span><span class="sxs-lookup"><span data-stu-id="5339d-162">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="5339d-163">Der integer-C#-Typ unterscheidet sich noch in einem weiteren Punkt von einer mathematischen ganzen Zahl: Der `int`-Typ ist mit minimalen und maximalen Grenzwerten versehen.</span><span class="sxs-lookup"><span data-stu-id="5339d-163">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="5339d-164">Fügen Sie diesen Code auf Ihre `Main` Methode, um diese Grenzen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="5339d-164">Add this code to your `Main` method to see those limits:</span></span>
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="5339d-165">Wenn bei einer Berechnung ein Wert herauskommt, der diese Grenzwerte überschreitet, liegt eine **Unterlauf-** oder **Überlaufbedingung** vor.</span><span class="sxs-lookup"><span data-stu-id="5339d-165">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="5339d-166">Die Antwort gibt dann den Bereich der Grenzwerte an.</span><span class="sxs-lookup"><span data-stu-id="5339d-166">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="5339d-167">Fügen Sie diese zwei Zeilen auf Ihre `Main` Methode, um ein Beispiel finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="5339d-167">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
<span data-ttu-id="5339d-168">Beachten Sie, dass die Antwort sehr nah an der minimalen (negativen) ganzen Zahl liegt.</span><span class="sxs-lookup"><span data-stu-id="5339d-168">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="5339d-169">Sie entspricht `min + 2`.</span><span class="sxs-lookup"><span data-stu-id="5339d-169">It's the same as `min + 2`.</span></span> <span data-ttu-id="5339d-170">Die Additionsoperation hat die zulässigen Werte für ganze Zahlen **überlaufen**.</span><span class="sxs-lookup"><span data-stu-id="5339d-170">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="5339d-171">Die Antwort enthält eine sehr große negative Zahl, da ein Überlauf den größtmöglichen ganzzahligen Wert bis zum kleinstmöglichen Wert umschließt.</span><span class="sxs-lookup"><span data-stu-id="5339d-171">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="5339d-172">Wenn der `int`-Typ nicht Ihren Anforderungen entspricht, so gibt es verschiedene numerische Typen mit anderen Grenzwerten und Genauigkeitsgraden, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5339d-172">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="5339d-173">Werfen wir im Folgenden einmal einen Blick auf diese.</span><span class="sxs-lookup"><span data-stu-id="5339d-173">Let's explore those next.</span></span>

<span data-ttu-id="5339d-174">Fahren wir noch einmal: des Codes, den Sie in diesem Abschnitt in eine separate Methode geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="5339d-174">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="5339d-175">Nennen Sie es `TestLimits`.</span><span class="sxs-lookup"><span data-stu-id="5339d-175">Name it `TestLimits`.</span></span> 

## <a name="work-with-the-double-type"></a><span data-ttu-id="5339d-176">Arbeiten mit dem Double-Typ</span><span class="sxs-lookup"><span data-stu-id="5339d-176">Work with the double type</span></span>

<span data-ttu-id="5339d-177">Der numerische Typ `double` stellt eine Gleitkommazahl mit doppelter Genauigkeit dar.</span><span class="sxs-lookup"><span data-stu-id="5339d-177">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="5339d-178">Falls Ihnen diese Benennungen nichts sagen, beachten Sie die folgenden Erläuterungen:</span><span class="sxs-lookup"><span data-stu-id="5339d-178">Those terms may be new to you.</span></span> <span data-ttu-id="5339d-179">Ein **Gleitkomma** Anzahl eignet sich zur Darstellung von nicht ganzzahligen Ziffern, die möglicherweise sehr große oder kleine Wert ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="5339d-179">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="5339d-180">**Doppelte Genauigkeit** bedeutet, dass diese Zahlen mit einer höheren Genauigkeit gespeichert werden als mit **einfacher Genauigkeit**.</span><span class="sxs-lookup"><span data-stu-id="5339d-180">**Double-precision** means that these numbers are stored using greater precision than **single-precision**.</span></span> <span data-ttu-id="5339d-181">Bei modernen Computern werden häufiger Zahlen mit doppelter Genauigkeit verwendet statt mit einfacher Genauigkeit.</span><span class="sxs-lookup"><span data-stu-id="5339d-181">On modern computers, it is more common to use double precision than single precision numbers.</span></span>
<span data-ttu-id="5339d-182">Sehen wir uns dies einmal genauer an.</span><span class="sxs-lookup"><span data-stu-id="5339d-182">Let's explore.</span></span> <span data-ttu-id="5339d-183">Fügen Sie den folgenden Code hinzu, und anzuzeigen Sie das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="5339d-183">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="5339d-184">Beachten Sie, dass die Antwort die Dezimalzahl des Quotienten enthält.</span><span class="sxs-lookup"><span data-stu-id="5339d-184">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="5339d-185">Testen Sie einen etwas komplizierteren Ausdruck mit Werten vom Typ „double“:</span><span class="sxs-lookup"><span data-stu-id="5339d-185">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="5339d-186">Der Bereich eines Werts vom Typ „double“ ist weitaus größer als bei ganzzahligen Werten.</span><span class="sxs-lookup"><span data-stu-id="5339d-186">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="5339d-187">Wiederholen Sie den folgenden Code unter Sie bisher geschrieben haben:</span><span class="sxs-lookup"><span data-stu-id="5339d-187">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="5339d-188">Diese Werte werden in der wissenschaftlichen Schreibweise ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="5339d-188">These values are printed out in scientific notation.</span></span> <span data-ttu-id="5339d-189">Die Anzahl auf der linken Seite des der `E` ist die Mantisse.</span><span class="sxs-lookup"><span data-stu-id="5339d-189">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="5339d-190">Die Zahl rechts ist der Exponent als Potenz von 10.</span><span class="sxs-lookup"><span data-stu-id="5339d-190">The number to the right is the exponent, as a power of 10.</span></span> 

<span data-ttu-id="5339d-191">Wie bei Dezimalzahlen in der Mathematik können double-Werte in C# Rundungsfehler aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5339d-191">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="5339d-192">Testen Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="5339d-192">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="5339d-193">Denken Sie daran, dass `0.3` nicht exakt `1/3` entspricht.</span><span class="sxs-lookup"><span data-stu-id="5339d-193">You know that `0.3` repeating is not exactly the same as `1/3`.</span></span>

<span data-ttu-id="5339d-194">***Übung***</span><span class="sxs-lookup"><span data-stu-id="5339d-194">***Challenge***</span></span>

<span data-ttu-id="5339d-195">Testen Sie für den `double`-Typ andere Berechnungen mit großen und kleinen Zahlen sowie mit Multiplikation und Division.</span><span class="sxs-lookup"><span data-stu-id="5339d-195">Try other calculations with large numbers, small numbers, multiplication and division using the `double` type.</span></span>  <span data-ttu-id="5339d-196">Testen Sie kompliziertere Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="5339d-196">Try more complicated calculations.</span></span>

<span data-ttu-id="5339d-197">Nachdem Sie einige Zeit mit der Aufforderung gearbeitet haben, nehmen Sie den Code, den Sie selbst geschrieben haben, und fügen Sie ihn in eine neue Methode.</span><span class="sxs-lookup"><span data-stu-id="5339d-197">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="5339d-198">Nennen Sie diese neue Methode `WorkWithDoubles`.</span><span class="sxs-lookup"><span data-stu-id="5339d-198">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-fixed-point-types"></a><span data-ttu-id="5339d-199">Arbeiten mit Festkommatypen</span><span class="sxs-lookup"><span data-stu-id="5339d-199">Work with fixed point types</span></span>

<span data-ttu-id="5339d-200">Sie haben die grundlegenden numerischen Typen in C# – „integer“ und „double“ – kennengelernt.</span><span class="sxs-lookup"><span data-stu-id="5339d-200">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="5339d-201">Es gibt einen weiteren Typ, den Sie kennen sollten: den `decimal`-Typ.</span><span class="sxs-lookup"><span data-stu-id="5339d-201">There is one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="5339d-202">Die `decimal` Typ hat einen kleineren Bereich aber größere Genauigkeit als `double`.</span><span class="sxs-lookup"><span data-stu-id="5339d-202">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="5339d-203">Die Benennung **Festkomma** bedeutet, dass die Position des Dezimalkommas (hier Dezimalpunkts bzw. Binärpunkts) unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5339d-203">The term **fixed point** means that the decimal point (or binary point) doesn't move.</span></span> <span data-ttu-id="5339d-204">Sehen wir uns das einmal genauer an:</span><span class="sxs-lookup"><span data-stu-id="5339d-204">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="5339d-205">Beachten Sie, dass der Bereich kleiner ist als beim `double`-Typ.</span><span class="sxs-lookup"><span data-stu-id="5339d-205">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="5339d-206">Sie können sehen, dass die Genauigkeit beim Typ „decimal“ höher ist, wenn Sie den folgenden Code testen:</span><span class="sxs-lookup"><span data-stu-id="5339d-206">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="5339d-207">Mit dem Suffix `M` neben einer Zahl geben Sie an, dass eine Konstante den `decimal`-Typ verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="5339d-207">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span>

<span data-ttu-id="5339d-208">Beachten Sie, dass der aus dieser arithmetischen Operation resultierende Wert vom Typ „decimal“ rechts neben dem Dezimalpunkt mehr Ziffern enthält.</span><span class="sxs-lookup"><span data-stu-id="5339d-208">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span> 

<span data-ttu-id="5339d-209">***Übung***</span><span class="sxs-lookup"><span data-stu-id="5339d-209">***Challenge***</span></span>

<span data-ttu-id="5339d-210">Nachdem Sie nun die verschiedenen numerischen Typen kennengelernt haben, schreiben Sie einen Code, der den Flächeninhalt eines Kreises mit einem Radius von 2,5 Zoll berechnet.</span><span class="sxs-lookup"><span data-stu-id="5339d-210">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 inches.</span></span> <span data-ttu-id="5339d-211">Denken Sie daran, dass der Flächeninhalt eines Kreises durch das Quadrat des Radius multipliziert mit Pi gebildet wird.</span><span class="sxs-lookup"><span data-stu-id="5339d-211">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="5339d-212">Einen Hinweis: c# enthält eine Konstante PI, <xref:System.Math.PI?displayProperty=nameWithType> , die Sie für diesen Wert verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5339d-212">One hint: C# contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> 

<span data-ttu-id="5339d-213">Sehen Sie sich Ihre Antwort von [Betrachtung der fertig gestellten Beispiel-Codes auf GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span><span class="sxs-lookup"><span data-stu-id="5339d-213">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span></span>

<span data-ttu-id="5339d-214">Wenn Sie möchten, versuchen Sie es von einigen anderen Formeln.</span><span class="sxs-lookup"><span data-stu-id="5339d-214">Try some other formulas if you'd like.</span></span> 

<span data-ttu-id="5339d-215">Sie haben die "Zahlen in c#" Schnellstart abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5339d-215">You've completed the "Numbers in C#" quick start.</span></span> <span data-ttu-id="5339d-216">Sie können weiterhin mit der [Verzweigungen und Schleifen](branches-and-loops-local.md) schnellen Einstieg in die Entwicklungsumgebung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="5339d-216">You can continue with the [Branches and loops](branches-and-loops-local.md) quick start in your own development environment.</span></span>

<span data-ttu-id="5339d-217">Weitere Informationen zu Zahlen in C# finden Sie auch unter folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="5339d-217">You can learn more about numbers in C# in the following topics:</span></span>

<span data-ttu-id="5339d-218">[Tabelle ganzzahliger Typen](../language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="5339d-218">[Integral Types Table](../language-reference/keywords/integral-types-table.md) </span></span>  
<span data-ttu-id="5339d-219">[Tabelle für Gleitkommatypen](../language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="5339d-219">[Floating-Point Types Table](../language-reference/keywords/floating-point-types-table.md) </span></span>  
<span data-ttu-id="5339d-220">[Tabelle integrierter Typen](../language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="5339d-220">[Built-In Types Table](../language-reference/keywords/built-in-types-table.md) </span></span>  
<span data-ttu-id="5339d-221">[Tabelle für implizite numerische Konvertierungen](../language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="5339d-221">[Implicit Numeric Conversions Table](../language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
[<span data-ttu-id="5339d-222">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="5339d-222">Explicit Numeric Conversions Table</span></span>](../language-reference/keywords/explicit-numeric-conversions-table.md)

