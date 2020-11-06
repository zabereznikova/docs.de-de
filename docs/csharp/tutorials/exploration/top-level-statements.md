---
title: Anweisungen der obersten Ebene – C#-Tutorial
description: In diesem Tutorial wird gezeigt, wie Sie Anweisungen der obersten Ebene verwenden, um Konzepte zu testen und mithilfe Ihrer eigenen Ideen in der Praxis umzusetzen.
ms.date: 10/28/2020
ms.openlocfilehash: 210fbd83bf4677061cab303089d0b27f1a4a7d01
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189364"
---
# <a name="tutorial-explore-ideas-using-top-level-statements-to-build-code-as-you-learn"></a><span data-ttu-id="46e7e-103">Tutorial: Schreiben von Code durch das Umsetzen eigener Ideen mithilfe von Anweisungen der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="46e7e-103">Tutorial: Explore ideas using top-level statements to build code as you learn</span></span>

<span data-ttu-id="46e7e-104">In diesem Tutorial lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="46e7e-104">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="46e7e-105">Kennenlernen der Regeln für die Verwendung von Anweisungen der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="46e7e-105">Learn the rules governing your use of top-level statements.</span></span>
> - <span data-ttu-id="46e7e-106">Verwenden von Anweisungen der obersten Ebene zum Untersuchen von Algorithmen</span><span class="sxs-lookup"><span data-stu-id="46e7e-106">Use top-level statements to explore algorithms.</span></span>
> - <span data-ttu-id="46e7e-107">Umwandeln von Erkenntnissen in wiederverwendbare Komponenten</span><span class="sxs-lookup"><span data-stu-id="46e7e-107">Refactor explorations into reusable components.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="46e7e-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="46e7e-108">Prerequisites</span></span>

<span data-ttu-id="46e7e-109">Sie müssen Ihren Computer zur Ausführung von .NET 5 einrichten, einschließlich des C# 9-Compilers.</span><span class="sxs-lookup"><span data-stu-id="46e7e-109">You'll need to set up your machine to run .NET 5, which includes the C# 9 compiler.</span></span> <span data-ttu-id="46e7e-110">Der C# 9-Compiler steht ab [Visual Studio 2019 Version 16.9 Preview 1](https://visualstudio.microsoft.com/vs/preview/) oder [.NET 5.0 SDK](https://dot.net/get-dotnet5) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="46e7e-110">The C# 9 compiler is available starting with [Visual Studio 2019 version 16.9 preview 1](https://visualstudio.microsoft.com/vs/preview/) or [.NET 5.0 SDK](https://dot.net/get-dotnet5).</span></span>

<span data-ttu-id="46e7e-111">In diesem Tutorial wird vorausgesetzt, dass Sie C# und .NET, einschließlich Visual Studio oder die .NET Core-CLI kennen.</span><span class="sxs-lookup"><span data-stu-id="46e7e-111">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="start-exploring"></a><span data-ttu-id="46e7e-112">Ausprobieren</span><span class="sxs-lookup"><span data-stu-id="46e7e-112">Start exploring</span></span>

<span data-ttu-id="46e7e-113">Mithilfe von Anweisungen der obersten Ebene können Sie den zusätzlichen erforderlichen Schritt vermeiden, indem Sie den Einstiegspunkt Ihres Programms in einer statischen Methode in einer Klasse platzieren.</span><span class="sxs-lookup"><span data-stu-id="46e7e-113">Top-level statements enable you to avoid the extra ceremony required by placing your program's entry point in a static method in a class.</span></span> <span data-ttu-id="46e7e-114">Der typische Startpunkt für eine neue Konsolenanwendung sieht wie der folgende Code aus:</span><span class="sxs-lookup"><span data-stu-id="46e7e-114">The typical starting point for a new console application looks like the following code:</span></span>

```csharp
using System;

namespace Application
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="46e7e-115">Der vorangehende Code ist das Ergebnis der Ausführung des `dotnet new console`-Befehls und der Erstellung einer neuen Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="46e7e-115">The preceding code is the result of running the `dotnet new console` command and creating a new console application.</span></span> <span data-ttu-id="46e7e-116">Diese elf Zeilen enthalten nur eine Zeile ausführbaren Codes.</span><span class="sxs-lookup"><span data-stu-id="46e7e-116">Those 11 lines contain only one line of executable code.</span></span> <span data-ttu-id="46e7e-117">Sie können dieses Programm mit dem neuen Feature für Anweisungen der obersten Ebene vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="46e7e-117">You can simplify that program with the new top-level statements feature.</span></span> <span data-ttu-id="46e7e-118">Dadurch können Sie in diesem Programm bis auf zwei Zeilen alle anderen Zeilen entfernen.</span><span class="sxs-lookup"><span data-stu-id="46e7e-118">That enables you to remove all but two of the lines in this program:</span></span>

```csharp
using System;

Console.WriteLine("Hello World!");
```

<span data-ttu-id="46e7e-119">Durch diese Aktion wird das Umsetzen neuer Ideen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="46e7e-119">This action simplifies what's needed to begin exploring new ideas.</span></span> <span data-ttu-id="46e7e-120">Sie können Anweisungen der obersten Ebene für Skripterstellungsszenarios oder zum Durchsuchen verwenden.</span><span class="sxs-lookup"><span data-stu-id="46e7e-120">You can use top-level statements for scripting scenarios, or to explore.</span></span> <span data-ttu-id="46e7e-121">Sobald Sie die Grundlagen beherrschen, können Sie mit dem Umgestalten des Codes beginnen und Methoden, Klassen oder andere Assemblys für von Ihnen entwickelte wiederverwendbare Komponenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="46e7e-121">Once you've got the basics working, you can start refactoring the code and create methods, classes, or other assemblies for reusable components you've built.</span></span> <span data-ttu-id="46e7e-122">Anweisungen der obersten Ebene ermöglichen das schnelle Testen von Code und bieten eine gute Grundlage für Einsteigertutorials.</span><span class="sxs-lookup"><span data-stu-id="46e7e-122">Top-level statements do enable quick experimentation and beginner tutorials.</span></span> <span data-ttu-id="46e7e-123">Außerdem bieten sie eine praktische Möglichkeit für den Übergang von Experimenten mit Code hin zu vollständigen Programmen.</span><span class="sxs-lookup"><span data-stu-id="46e7e-123">They also provide a smooth path from experimentation to full programs.</span></span>

<span data-ttu-id="46e7e-124">Anweisungen der obersten Ebene werden in der Reihenfolge ausgeführt, in der sie in der Datei aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="46e7e-124">Top-level statements are executed in the order they appear in the file.</span></span> <span data-ttu-id="46e7e-125">Sie können nur in einer Quelldatei in der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="46e7e-125">Top-level statements can only be used in one source file in your application.</span></span> <span data-ttu-id="46e7e-126">Der Compiler generiert einen Fehler, wenn Sie die Anweisungen in mehr als einer Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="46e7e-126">The compiler generates an error if you use them in more than one file.</span></span>

## <a name="build-a-magic-net-answer-machine"></a><span data-ttu-id="46e7e-127">Entwickeln eines „magischen“ .NET-Programms zum Ausgeben von Antworten</span><span class="sxs-lookup"><span data-stu-id="46e7e-127">Build a magic .NET answer machine</span></span>

<span data-ttu-id="46e7e-128">In diesem Tutorial erstellen Sie eine Konsolenanwendung, die eine Frage, die mit „Ja“ oder „Nein“ beantwortet wird, zufällig beantwortet.</span><span class="sxs-lookup"><span data-stu-id="46e7e-128">For this tutorial, let's build a console application that answers a "yes" or "no" question with a random answer.</span></span> <span data-ttu-id="46e7e-129">Sie erstellen die Funktionalität Schritt für Schritt.</span><span class="sxs-lookup"><span data-stu-id="46e7e-129">You'll build out the functionality step by step.</span></span> <span data-ttu-id="46e7e-130">Sie können sich auf Ihre Aufgabe konzentrieren, anstatt sich mit dem Prozess zum Entwickeln der Struktur eines typischen Programms beschäftigen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="46e7e-130">You can focus on your task rather than ceremony needed for the structure of a typical program.</span></span> <span data-ttu-id="46e7e-131">Sobald Sie mit der Funktionalität zufrieden sind, können Sie die Anwendung nach Bedarf umgestalten.</span><span class="sxs-lookup"><span data-stu-id="46e7e-131">Then, once you're happy with the functionality, you can refactor the application as you see fit.</span></span>

<span data-ttu-id="46e7e-132">Es ist ein guter Startpunkt, die Frage wieder in die Konsole zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="46e7e-132">A good starting point is to write the question back to the console.</span></span> <span data-ttu-id="46e7e-133">Sie können beginnen, indem Sie den folgenden Code schreiben:</span><span class="sxs-lookup"><span data-stu-id="46e7e-133">You can start by writing the following code:</span></span>

```csharp
using System;

Console.WriteLine(args);
```

<span data-ttu-id="46e7e-134">Sie deklarieren keine `args`-Variable.</span><span class="sxs-lookup"><span data-stu-id="46e7e-134">You don't declare an `args` variable.</span></span> <span data-ttu-id="46e7e-135">Im Zusammenhang mit der einzelnen Quelldatei, die die Anweisungen der obersten Ebene enthält, erkennt der Compiler, dass `args` für die Befehlszeilenargumente steht.</span><span class="sxs-lookup"><span data-stu-id="46e7e-135">For the single source file that contains your top-level statements, the compiler recognizes `args` to mean the command-line arguments.</span></span> <span data-ttu-id="46e7e-136">Dies sind wie in allen C#-Programmen Argumente vom Typ `string[]`.</span><span class="sxs-lookup"><span data-stu-id="46e7e-136">The type of args is a `string[]`, as in all C# programs.</span></span>

<span data-ttu-id="46e7e-137">Sie können den Code testen, indem Sie den folgenden `dotnet run`-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="46e7e-137">You can test your code by running the following `dotnet run` command:</span></span>

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?
```

<span data-ttu-id="46e7e-138">Die Argumente nach `--` in der Befehlszeile werden an das Programm weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="46e7e-138">The arguments after the `--` on the command line are passed to the program.</span></span> <span data-ttu-id="46e7e-139">Sie können den Typ der `args`-Variable sehen, da diese Information in der Konsole angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="46e7e-139">You can see the type of the `args` variable, because that's what's printed to the console:</span></span>

```console
System.String[]
```

<span data-ttu-id="46e7e-140">Sie müssen die Argumente einzeln benennen und durch ein Leerzeichen trennen, um die Frage in die Konsole zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="46e7e-140">To write the question to the console, you'll need to enumerate the arguments and separate them with a space.</span></span> <span data-ttu-id="46e7e-141">Ersetzen Sie den `WriteLine`-Aufruf durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="46e7e-141">Replace the `WriteLine` call with the following code:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="EchoInput":::

<span data-ttu-id="46e7e-142">Wenn Sie das Programm ausführen, wird die Frage nun ordnungsgemäß als Zeichenfolge von Argumenten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46e7e-142">Now, when you run the program, it will correctly display the question as a string of arguments.</span></span>

## <a name="respond-with-a-random-answer"></a><span data-ttu-id="46e7e-143">Antworten mit einer zufälligen Antwort</span><span class="sxs-lookup"><span data-stu-id="46e7e-143">Respond with a random answer</span></span>

<span data-ttu-id="46e7e-144">Nachdem Sie die Frage wiederholt haben, können Sie den Code hinzufügen, um die zufällige Antwort zu generieren.</span><span class="sxs-lookup"><span data-stu-id="46e7e-144">After echoing the question, you can add the code to generate the random answer.</span></span> <span data-ttu-id="46e7e-145">Fügen Sie zunächst ein Array möglicher Antworten hinzu:</span><span class="sxs-lookup"><span data-stu-id="46e7e-145">Start by adding an array of possible answers:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="Answers":::

<span data-ttu-id="46e7e-146">Dieses Array umfasst zwölf positive, sechs zurückhaltende und sechs negative Antworten.</span><span class="sxs-lookup"><span data-stu-id="46e7e-146">This array has 12 answers that are affirmative, six that are non-committal, and six that are negative.</span></span> <span data-ttu-id="46e7e-147">Fügen Sie als Nächstes den folgenden Code hinzu, um eine zufällige Antwort aus dem Array zu generieren und anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="46e7e-147">Next, add the following code to generate and display a random answer from the array:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Program.cs" ID="GenerateAnswer":::

<span data-ttu-id="46e7e-148">Sie können die Anwendung noch mal ausführen, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="46e7e-148">You can run the application again to see the results.</span></span> <span data-ttu-id="46e7e-149">Es sollte nun etwa die folgende Ausgabe angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="46e7e-149">You should see something like the following output:</span></span>

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?

Should I use top level statements in all my programs?
Better not tell you now.
```

<span data-ttu-id="46e7e-150">Mit diesem Code werden die Fragen beantwortet, allerdings fügen Sie noch ein weiteres Feature hinzu.</span><span class="sxs-lookup"><span data-stu-id="46e7e-150">This code answers the questions, but let's add one more feature.</span></span> <span data-ttu-id="46e7e-151">Ihre Frage-App soll das Nachdenken vor dem Ausgeben der Antwort simulieren.</span><span class="sxs-lookup"><span data-stu-id="46e7e-151">You'd like your question app to simulate thinking about the answer.</span></span> <span data-ttu-id="46e7e-152">Dies erreichen Sie, indem Sie eine ASCII-Animation (American Standard Code for Information Interchange) hinzufügen und den restlichen Vorgang während der Bearbeitung anhalten.</span><span class="sxs-lookup"><span data-stu-id="46e7e-152">You can do that by adding a bit of ASCII animation, and pausing while working.</span></span>  <span data-ttu-id="46e7e-153">Fügen Sie den folgenden Code nach der Zeile hinzu, die die Frage wiederholt:</span><span class="sxs-lookup"><span data-stu-id="46e7e-153">Add the following code after the line that echoes the question:</span></span>

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="AnimationFirstPass":::

<span data-ttu-id="46e7e-154">Außerdem müssen Sie am Anfang der Quelldatei eine `using`-Anweisung hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="46e7e-154">You'll also need to add a `using` statement to the top of the source file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="46e7e-155">Die `using`-Anweisungen müssen sich vor allen anderen Anweisungen in der Datei befinden.</span><span class="sxs-lookup"><span data-stu-id="46e7e-155">The `using` statements must be before any other statements in the file.</span></span> <span data-ttu-id="46e7e-156">Andernfalls tritt ein Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="46e7e-156">Otherwise, it's a compiler error.</span></span> <span data-ttu-id="46e7e-157">Sie können das Programm noch mal ausführen und die Animation anzeigen.</span><span class="sxs-lookup"><span data-stu-id="46e7e-157">You can run the program again and see the animation.</span></span> <span data-ttu-id="46e7e-158">Dies ermöglicht eine bessere Nutzung des Programms.</span><span class="sxs-lookup"><span data-stu-id="46e7e-158">That makes a better experience.</span></span> <span data-ttu-id="46e7e-159">Experimentieren Sie hinsichtlich der Länge der Verzögerung, bis Sie mit dem Ergebnis zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="46e7e-159">Experiment with the length of the delay to match your taste.</span></span>

<span data-ttu-id="46e7e-160">Der vorangehende Code erstellt eine Reihe von Zeilen, die durch ein Leerzeichen voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="46e7e-160">The preceding code creates a set of spinning lines separated by a space.</span></span> <span data-ttu-id="46e7e-161">Durch das Hinzufügen des Schlüsselworts `await` wird der Compiler angewiesen, den Programmeinstiegspunkt als Methode zu generieren, die den `async`-Modifizierer aufweist und die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="46e7e-161">Adding the `await` keyword instructs the compiler to generate the program entry point as a method that has the `async` modifier, and returns a <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>.</span></span> <span data-ttu-id="46e7e-162">Dieses Programm gibt keinen Wert zurück, sodass der Programmeinstiegspunkt `Task` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="46e7e-162">This program does not return a value, so the program entry point returns a `Task`.</span></span> <span data-ttu-id="46e7e-163">Wenn das Programm einen ganzzahligen Wert zurückgibt, fügen Sie eine return-Anweisung am Ende der Anweisungen der obersten Ebene hinzu.</span><span class="sxs-lookup"><span data-stu-id="46e7e-163">If your program returns an integer value, you would add a return statement to the end of your top-level statements.</span></span> <span data-ttu-id="46e7e-164">Diese return-Anweisung gibt den ganzzahligen Wert an, der zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="46e7e-164">That return statement would specify the integer value to return.</span></span> <span data-ttu-id="46e7e-165">Wenn die Anweisungen der obersten Ebene einen `await`-Ausdruck enthalten, wird der Rückgabetyp zu einer <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="46e7e-165">If your top-level statements include an `await` expression, the return type becomes <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>.</span></span>

## <a name="refactoring-for-the-future"></a><span data-ttu-id="46e7e-166">Umgestaltung für die Zukunft</span><span class="sxs-lookup"><span data-stu-id="46e7e-166">Refactoring for the future</span></span>

<span data-ttu-id="46e7e-167">Ihr Programm sollte wie der folgende Code aussehen:</span><span class="sxs-lookup"><span data-stu-id="46e7e-167">Your program should look like the following code:</span></span>

```csharp
using System;
using System.Threading.Tasks;

Console.WriteLine();
foreach(var s in args)
{
    Console.Write(s);
    Console.Write(' ');
}
Console.WriteLine();

for (int i = 0; i < 20; i++)
{
    Console.Write("| -");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("/ \\");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("- |");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("\\ /");
    await Task.Delay(50);
    Console.Write("\b\b\b");
}
Console.WriteLine();

string[] answers =
{
    "It is certain.",       "Reply hazy, try again.",     "Don’t count on it.",
    "It is decidedly so.",  "Ask again later.",           "My reply is no.",
    "Without a doubt.",     "Better not tell you now.",   "My sources say no.",
    "Yes – definitely.",    "Cannot predict now.",        "Outlook not so good.",
    "You may rely on it.",  "Concentrate and ask again.", "Very doubtful.",
    "As I see it, yes.",
    "Most likely.",
    "Outlook good.",
    "Yes.",
    "Signs point to yes.",
};

var index = new Random().Next(answers.Length - 1);
Console.WriteLine(answers[index]);
```

<span data-ttu-id="46e7e-168">Der vorangehende Code ist nützlich.</span><span class="sxs-lookup"><span data-stu-id="46e7e-168">The preceding code is reasonable.</span></span> <span data-ttu-id="46e7e-169">Er funktioniert.</span><span class="sxs-lookup"><span data-stu-id="46e7e-169">It works.</span></span> <span data-ttu-id="46e7e-170">Er kann jedoch nicht erneut verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="46e7e-170">But it isn't reusable.</span></span> <span data-ttu-id="46e7e-171">Nachdem die Anwendung jetzt funktioniert, ist es an der Zeit, wiederverwendbare Teile zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="46e7e-171">Now that you have the application working, it's time to pull out reusable parts.</span></span>

<span data-ttu-id="46e7e-172">Eine Option hierfür ist der Code, der die Animation beim Warten während des Vorgangs anzeigt.</span><span class="sxs-lookup"><span data-stu-id="46e7e-172">One candidate is the code that displays the waiting animation.</span></span> <span data-ttu-id="46e7e-173">Aus diesem Codeausschnitt kann eine Methode werden:</span><span class="sxs-lookup"><span data-stu-id="46e7e-173">That snippet can become a method:</span></span>

<span data-ttu-id="46e7e-174">Erstellen Sie hierfür zunächst eine lokale Funktion in der Datei.</span><span class="sxs-lookup"><span data-stu-id="46e7e-174">You can start by creating a local function in your file.</span></span> <span data-ttu-id="46e7e-175">Ersetzen Sie die aktuelle Animation durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="46e7e-175">Replace the current animation with the following code:</span></span>

```csharp
await ShowConsoleAnimation();

static async Task ShowConsoleAnimation()
{
    for (int i = 0; i < 20; i++)
    {
        Console.Write("| -");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("/ \\");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("- |");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("\\ /");
        await Task.Delay(50);
        Console.Write("\b\b\b");
    }
    Console.WriteLine();
}
```

<span data-ttu-id="46e7e-176">Der vorangehende Code erstellt eine lokale Funktion in der Main-Methode.</span><span class="sxs-lookup"><span data-stu-id="46e7e-176">The preceding code creates a local function inside your main method.</span></span> <span data-ttu-id="46e7e-177">Diese ist immer noch nicht wiederverwendbar.</span><span class="sxs-lookup"><span data-stu-id="46e7e-177">That's still not reusable.</span></span> <span data-ttu-id="46e7e-178">Extrahieren Sie den Code daher in eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="46e7e-178">So, extract that code into a class.</span></span> <span data-ttu-id="46e7e-179">Erstellen Sie eine neue Datei namens *utilities.cs* , und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="46e7e-179">Create a new file named *utilities.cs* and add the following code:</span></span>

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="SnippetUtilities":::

<span data-ttu-id="46e7e-180">Anweisungen der obersten Ebene können nur in einer Datei enthalten sein, und diese Datei darf keine Namespaces oder Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="46e7e-180">Top-level statements can only be in one file, and that file cannot contain namespaces or types.</span></span>

<span data-ttu-id="46e7e-181">Zum Schluss können Sie den Animationscode bereinigen, um Duplizierungen zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="46e7e-181">Finally, you can clean the animation code to remove some duplication:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Utiliities.cs" ID="Animation":::

<span data-ttu-id="46e7e-182">Nun verfügen Sie über eine komplette Anwendung, und Sie haben die wiederverwendbaren Teile für die spätere Verwendung umgestaltet.</span><span class="sxs-lookup"><span data-stu-id="46e7e-182">Now you have a complete application, and you've refactored the reusable parts for later use.</span></span>

## <a name="summary"></a><span data-ttu-id="46e7e-183">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="46e7e-183">Summary</span></span>

<span data-ttu-id="46e7e-184">Anweisungen der obersten Ebene vereinfachen das Erstellen einfacher Programme, mit denen neue Algorithmen untersucht werden können.</span><span class="sxs-lookup"><span data-stu-id="46e7e-184">Top-level statements make it easier to create simple programs for use to explore new algorithms.</span></span> <span data-ttu-id="46e7e-185">Sie können mit Algorithmen experimentieren, indem Sie verschiedene Codeausschnitte ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="46e7e-185">You can experiment with algorithms by trying different snippets of code.</span></span> <span data-ttu-id="46e7e-186">Nachdem Sie gelernt haben, was funktioniert, können Sie den Code so umgestalten, dass er leichter verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="46e7e-186">Once you've learned what works, you can refactor the code to be more maintainable.</span></span>

<span data-ttu-id="46e7e-187">Anweisungen der obersten Ebene vereinfachen Programme, die auf Konsolenanwendungen basieren.</span><span class="sxs-lookup"><span data-stu-id="46e7e-187">Top-level statements simplify programs that are based on console applications.</span></span> <span data-ttu-id="46e7e-188">Hierzu gehören Azure-Funktionen, GitHub-Aktionen und andere kleine Hilfsprogramme.</span><span class="sxs-lookup"><span data-stu-id="46e7e-188">These include Azure functions, GitHub actions, and other small utilities.</span></span>
