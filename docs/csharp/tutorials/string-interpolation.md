---
title: "Zeichenfolgeninterpolation – C#"
description: Erfahren Sie, wie die Zeichenfolgeninterpolation in C# 6 funktioniert.
keywords: .NET, .NET Core, C#, Zeichenfolge
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.openlocfilehash: b6b3ce53a08cfacfacb19266b0be216a40633352
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="string-interpolation-in-c"></a><span data-ttu-id="a5ec7-104">Zeichenfolgeninterpolation in C#</span><span class="sxs-lookup"><span data-stu-id="a5ec7-104">String Interpolation in C#</span></span> #

<span data-ttu-id="a5ec7-105">Die Zeichenfolgeninterpolation ermöglicht, dass Platzhalter in einer Zeichenfolge durch den Wert einer Zeichenfolgenvariablen ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-105">String Interpolation is the way that placeholders in a string are replaced by the value of a string variable.</span></span> <span data-ttu-id="a5ec7-106">Vor C# 6 wurde dies mit `System.String.Format` realisiert.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-106">Before C# 6, the way to do this is with `System.String.Format`.</span></span> <span data-ttu-id="a5ec7-107">Dies funktioniert gut, aber da dabei nummerierte Platzhalter verwendet werden, kann es schwieriger zu lesen und detaillierter sein.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-107">This works okay, but since it uses numbered placeholders, it can be harder to read and more verbose.</span></span>

<span data-ttu-id="a5ec7-108">In anderen Programmiersprachen ist die Zeichenfolgeninterpolation bereits seit einer Weile integriert.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-108">Other programming languages have had string interpolation built into the language for a while.</span></span> <span data-ttu-id="a5ec7-109">Zum Beispiel in PHP:</span><span class="sxs-lookup"><span data-stu-id="a5ec7-109">For instance, in PHP:</span></span>

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

<span data-ttu-id="a5ec7-110">In C# 6 haben wir nun diesen Zeichenfolgeninterpolations-Stil.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-110">In C# 6, we finally have that style of string interpolation.</span></span> <span data-ttu-id="a5ec7-111">Sie können ein `$` vor einer Zeichenfolge verwenden, um anzugeben, dass sie Variablen/Ausdrücke durch deren Werte ersetzen soll.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-111">You can use a `$` before a string to indicate that it should substitute variables/expressions for their values.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a5ec7-112">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="a5ec7-112">Prerequisites</span></span>
<span data-ttu-id="a5ec7-113">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-113">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="a5ec7-114">Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="a5ec7-114">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="a5ec7-115">Sie können diese Anwendung unter Windows, Ubuntu Linux, macOS oder in einem Docker-Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-115">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="a5ec7-116">Sie müssen Ihren bevorzugten Code-Editor installieren.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-116">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="a5ec7-117">In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-117">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="a5ec7-118">Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-118">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="a5ec7-119">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="a5ec7-119">Create the Application</span></span>

<span data-ttu-id="a5ec7-120">Nachdem Sie alle Tools installiert haben, erstellen Sie eine neue .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-120">Now that you've installed all the tools, create a new .NET Core application.</span></span> <span data-ttu-id="a5ec7-121">Um den Befehlszeilengenerator zu verwenden, erstellen Sie ein Verzeichnis für Ihr Projekt, z.B. `interpolated`, und führen den folgenden Befehl in Ihrer bevorzugten Shell aus:</span><span class="sxs-lookup"><span data-stu-id="a5ec7-121">To use the command line generator, create a directory for your project, such as `interpolated`, and execute the following command in your favorite shell:</span></span>

```
dotnet new console
```

<span data-ttu-id="a5ec7-122">Dieser Befehl erstellt ein neues .NET Core-Projekt mit einer Projektdatei, *interpolated.csproj*, und einer Quellcodedatei, *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-122">This command will create a barebones .NET core project with a project file, *interpolated.csproj*, and a source code file, *Program.cs*.</span></span> <span data-ttu-id="a5ec7-123">Sie müssen `dotnet restore` ausführen, um die Abhängigkeiten wiederherzustellen, die zum Kompilieren dieses Projekts erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-123">You will need to execute `dotnet restore` to restore the dependencies needed to compile this project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="a5ec7-124">Verwenden Sie zum Ausführen des Programms `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-124">To execute the program, use `dotnet run`.</span></span> <span data-ttu-id="a5ec7-125">Es sollte „Hello, World“ auf der Konsole ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-125">You should see "Hello, World" output to the console.</span></span>



## <a name="intro-to-string-interpolation"></a><span data-ttu-id="a5ec7-126">Einführung zur Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="a5ec7-126">Intro to String Interpolation</span></span>

<span data-ttu-id="a5ec7-127">Mit `System.String.Format` geben Sie „Platzhalter“ in einer Zeichenfolge an, die von den Parametern ersetzt werden, die auf die Zeichenfolge folgen.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-127">With `System.String.Format`, you specify "placeholders" in a string that are replaced by the parameters following the string.</span></span> <span data-ttu-id="a5ec7-128">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a5ec7-128">For instance:</span></span>

[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

<span data-ttu-id="a5ec7-129">Damit wird „My name is Matt Groves“ ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-129">That will output "My name is Matt Groves".</span></span>

<span data-ttu-id="a5ec7-130">In C# 6 definieren Sie eine interpolierte Zeichenfolge, indem Sie ihr das `$`-Symbol voranstellen und dann die Variablen direkt in der Zeichenfolge verwenden, anstatt `String.Format` zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-130">In C# 6, instead of using `String.Format`, you define an interpolated string by prepending it with the `$` symbol, and then using the variables directly in the string.</span></span> <span data-ttu-id="a5ec7-131">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a5ec7-131">For instance:</span></span>

[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

<span data-ttu-id="a5ec7-132">Sie müssen nicht einfach Variablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-132">You don't have to use just variables.</span></span> <span data-ttu-id="a5ec7-133">Sie können jeden Ausdruck innerhalb der Klammern verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-133">You can use any expression within the brackets.</span></span> <span data-ttu-id="a5ec7-134">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a5ec7-134">For instance:</span></span>

[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

<span data-ttu-id="a5ec7-135">Die Ausgabe wäre:</span><span class="sxs-lookup"><span data-stu-id="a5ec7-135">Which would output:</span></span>

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a><span data-ttu-id="a5ec7-136">So funktioniert die Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="a5ec7-136">How string interpolation works</span></span>

<span data-ttu-id="a5ec7-137">Hinter den Kulissen wird diese Zeichenfolgeninterpolations-Syntax vom Compiler in String.Format übersetzt.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-137">Behind the scenes, this string interpolation syntax is translated into String.Format by the compiler.</span></span> <span data-ttu-id="a5ec7-138">So können Sie [das Gleiche tun, was Sie bereits mit String.Format getan haben](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="a5ec7-138">So, you can do the [same type of stuff you've done before with String.Format](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx).</span></span>

<span data-ttu-id="a5ec7-139">Sie können z.B. auffüllen und numerisch formatieren:</span><span class="sxs-lookup"><span data-stu-id="a5ec7-139">For instance, you can add padding and numeric formatting:</span></span>

[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

<span data-ttu-id="a5ec7-140">Der obige Code würde folgende Ausgabe ergeben:</span><span class="sxs-lookup"><span data-stu-id="a5ec7-140">The above would output something like:</span></span>

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

<span data-ttu-id="a5ec7-141">Wenn der Name einer Variablen nicht gefunden wird, wird ein Kompilierzeitfehler generiert.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-141">If a variable name is not found, then a compile time error will be generated.</span></span>

<span data-ttu-id="a5ec7-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a5ec7-142">For instance:</span></span>

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

<span data-ttu-id="a5ec7-143">Wenn Sie dies kompilieren, erhalten Sie Fehlermeldungen:</span><span class="sxs-lookup"><span data-stu-id="a5ec7-143">If you compile this, you'll get errors:</span></span>
 
* <span data-ttu-id="a5ec7-144">`Cannot use local variable 'adj' before it is declared` – die `adj`-Variable wurde erst *nach* der interpolierten Zeichenfolge deklariert.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-144">`Cannot use local variable 'adj' before it is declared` - the `adj` variable wasn't declared until *after* the interpolated string.</span></span>
* <span data-ttu-id="a5ec7-145">`The name 'otheranimal' does not exist in the current context` – eine Variable namens `otheranimal` wurde nie deklariert</span><span class="sxs-lookup"><span data-stu-id="a5ec7-145">`The name 'otheranimal' does not exist in the current context` - a variable called `otheranimal` was never even declared</span></span>

## <a name="localization-and-internationalization"></a><span data-ttu-id="a5ec7-146">Lokalisierung und Internationalisierung</span><span class="sxs-lookup"><span data-stu-id="a5ec7-146">Localization and Internationalization</span></span>

<span data-ttu-id="a5ec7-147">Eine interpolierte Zeichenfolge unterstützt `IFormattable` und `FormattableString`, was für die Internationalisierung nützlich sein kann.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-147">An interpolated string supports `IFormattable` and `FormattableString`, which can be useful for internationalization.</span></span>

<span data-ttu-id="a5ec7-148">Standardmäßig verwendet eine interpolierte Zeichenfolge die aktuelle Kultur.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-148">By default, an interpolated string uses the current culture.</span></span> <span data-ttu-id="a5ec7-149">Um eine andere Kultur zu verwenden, können Sie sie in `IFormattable` umwandeln.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-149">To use a different culture, you could cast it as `IFormattable`</span></span>

<span data-ttu-id="a5ec7-150">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a5ec7-150">For instance:</span></span>

[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

## <a name="conclusion"></a><span data-ttu-id="a5ec7-151">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="a5ec7-151">Conclusion</span></span> 

<span data-ttu-id="a5ec7-152">In diesem Tutorial haben Sie gelernt, wie Sie Zeichenfolgeninterpolations-Funktionen von C# 6 verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-152">In this tutorial, you learned how to use string interpolation features of C# 6.</span></span> <span data-ttu-id="a5ec7-153">Es ist im Grunde eine präzisere Methode, einfache `String.Format`-Anweisungen zu schreiben, mit einigen Einschränkungen für fortgeschrittenere Verwendungen.</span><span class="sxs-lookup"><span data-stu-id="a5ec7-153">It's basically a more concise way of writing simple `String.Format` statements, with some caveats for more advanced uses of it.</span></span>
