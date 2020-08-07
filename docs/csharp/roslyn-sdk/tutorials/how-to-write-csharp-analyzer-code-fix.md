---
title: 'Tutorial: Schreiben Ihres ersten Analysetools und Codefixes'
description: Dieses Tutorial enthält Schritt-für-Schritt-Anleitungen zum Erstellen eines Analysetools und eines Codefixes mithilfe des .NET Compiler SDK (Roslyn-APIs).
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: e79907f364939462b7d0d5814c4752be23bcfdf3
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381592"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a><span data-ttu-id="f9b3f-103">Tutorial: Schreiben Ihres ersten Analysetools und Codefixes</span><span class="sxs-lookup"><span data-stu-id="f9b3f-103">Tutorial: Write your first analyzer and code fix</span></span>

<span data-ttu-id="f9b3f-104">Das .NET Compiler Platform SDK stellt die Tools zur Verfügung, die Sie zum Erstellen von benutzerdefinierten Warnungen mit C#- oder Visual Basic-Code als Ziel benötigen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-104">The .NET Compiler Platform SDK provides the tools you need to create custom warnings that target C# or Visual Basic code.</span></span> <span data-ttu-id="f9b3f-105">Ihr **Analysetool** enthält Code, der Verstöße gegen Ihre Regel erkennt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-105">Your **analyzer** contains code that recognizes violations of your rule.</span></span> <span data-ttu-id="f9b3f-106">Ihr **Codefix** enthält den Code, der den Verstoß behebt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-106">Your **code fix** contains the code that fixes the violation.</span></span> <span data-ttu-id="f9b3f-107">Die Regeln, die Sie implementieren, können sich auf alles Mögliche beziehen, von der Codestruktur über das Codeformat bis zu Benennungskonventionen usw.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-107">The rules you implement can be anything from code structure to coding style to naming conventions and more.</span></span> <span data-ttu-id="f9b3f-108">Die .NET Compiler Platform stellt das Framework zum Ausführen der Analyse bereit, während die Entwickler Code schreiben, mit allen Features der Visual Studio-Benutzeroberfläche für das Beheben von Codeproblemen: Anzeigen von Wellenlinien im Editor, Auffüllen der Fehlerliste von Visual Studio, Erstellen der "Glühbirnen"-Vorschläge und Darstellung der umfassenden Vorschau vorgeschlagener Fixe.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-108">The .NET Compiler Platform provides the framework for running analysis as developers are writing code, and all the Visual Studio UI features for fixing code: showing squiggles in the editor, populating the Visual Studio Error List, creating the "light bulb" suggestions and showing the rich preview of the suggested fixes.</span></span>

<span data-ttu-id="f9b3f-109">In diesem Tutorial lernen Sie die Erstellung eines **Analysetools** und eines begleitenden **Codefixes** unter Verwendung der Roslyn-APIs kennen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-109">In this tutorial, you'll explore the creation of an **analyzer** and an accompanying **code fix** using the Roslyn APIs.</span></span> <span data-ttu-id="f9b3f-110">Ein Analysetool ist eine Möglichkeit, Quellcodeanalyse auszuführen und dem Benutzer ein Problem zu melden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-110">An analyzer is a way to perform source code analysis and report a problem to the user.</span></span> <span data-ttu-id="f9b3f-111">Optional kann ein Analysetool auch einen Codefix bereitstellen, der eine Änderung am Quellcode des Benutzers darstellt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-111">Optionally, an analyzer can also provide a code fix that represents a modification to the user's source code.</span></span> <span data-ttu-id="f9b3f-112">In diesem Tutorial wird ein Analysetool erstellt, das Deklarationen von lokalen Variablen enthält, die mithilfe des `const`-Modifizierers deklariert werden könnten, es aber nicht sind.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-112">This tutorial creates an analyzer that finds local variable declarations that could be declared using the `const` modifier but are not.</span></span> <span data-ttu-id="f9b3f-113">Der begleitende Codefix ändert diese Deklarationen, indem er den `const`-Modifizierer hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-113">The accompanying code fix modifies those declarations to add the `const` modifier.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f9b3f-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f9b3f-114">Prerequisites</span></span>

> [!NOTE]
> <span data-ttu-id="f9b3f-115">Die aktuelle Visual Studio-Vorlage **Analyzer mit Codekorrektur (.NET Standard)** enthält einen bekannten Fehler, der in Visual Studio 2019, Version 16.7 behoben sein sollte.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-115">The current Visual Studio **Analyzer with code fix (.NET Standard)** template has a known bug in it and should be fixed in Visual Studio 2019 version 16.7.</span></span> <span data-ttu-id="f9b3f-116">Die Projekte in der Vorlage werden nur kompiliert, wenn die folgenden Änderungen vorgenommen werden:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-116">The projects in the template will not compile unless the following changes are made:</span></span>
>
> 1. <span data-ttu-id="f9b3f-117">Klicken Sie auf **Extras** > **Optionen** > **NuGet-Paket-Manager** > **Paketquellen**.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-117">Select **Tools** > **Options** > **NuGet Package Manager** > **Package Sources**</span></span>
>    - <span data-ttu-id="f9b3f-118">Klicken Sie auf das Pluszeichen, um eine neue Quelle hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-118">Select the plus button, to add a new source:</span></span>
>    - <span data-ttu-id="f9b3f-119">Legen Sie die **Quelle** auf `https://dotnet.myget.org/F/roslyn-analyzers/api/v3/index.json` fest, und wählen Sie **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-119">Set the **Source** to `https://dotnet.myget.org/F/roslyn-analyzers/api/v3/index.json` and select **Update**</span></span>
> 1. <span data-ttu-id="f9b3f-120">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **MakeConst.Vsix**, und wählen Sie **Projektdatei bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-120">From the **Solution Explorer**, right-click on the **MakeConst.Vsix** project, and select **Edit Project File**</span></span>
>    - <span data-ttu-id="f9b3f-121">Aktualisieren Sie den Knoten `<AssemblyName>`, um das Suffix `.Visx` hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-121">Update the `<AssemblyName>` node to add the `.Visx` suffix:</span></span>
>      - `<AssemblyName>MakeConst.Vsix</AssemblyName>`
>    - <span data-ttu-id="f9b3f-122">Aktualisieren Sie den Knoten `<ProjectReference>` in Zeile 41, um den `TargetFramework`-Wert zu ändern:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-122">Update the `<ProjectReference>` node on line 41 to alter the `TargetFramework` value:</span></span>
>      - `<ProjectReference Update="@(ProjectReference)" AdditionalProperties="TargetFramework=netstandard2.0" />`
> 1. <span data-ttu-id="f9b3f-123">Aktualisieren Sie die Datei *MakeConstUnitTests.cs* im Projekt *MakeConst.Test*:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-123">Update the *MakeConstUnitTests.cs* file, in the *MakeConst.Test* project:</span></span>
>    - <span data-ttu-id="f9b3f-124">Ändern Sie Zeile 9 in Folgendes, und beachten Sie die Namespaceänderung:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-124">Change line 9 to the following, notice namespace alteration:</span></span>
>      - `using Verify = Microsoft.CodeAnalysis.CSharp.Testing.MSTest.CodeFixVerifier<`
>    - <span data-ttu-id="f9b3f-125">Ändern Sie Zeile 24 in die folgende Methode:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-125">Change line 24 to the following method:</span></span>
>      - `await Verify.VerifyAnalyzerAsync(test);`
>    - <span data-ttu-id="f9b3f-126">Ändern Sie Zeile 62 in die folgende Methode:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-126">Change line 62 to the following method:</span></span>
>      - `await Verify.VerifyCodeFixAsync(test, expected, fixtest);`

- [<span data-ttu-id="f9b3f-127">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="f9b3f-127">Visual Studio 2017</span></span>](https://visualstudio.microsoft.com/vs/older-downloads/#visual-studio-2017-and-other-products)
- [<span data-ttu-id="f9b3f-128">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f9b3f-128">Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads)

<span data-ttu-id="f9b3f-129">Installieren Sie zunächst über den Visual Studio-Installer das **SDK für die .NET Compiler Platform**:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-129">You'll need to install the **.NET Compiler Platform SDK** via the Visual Studio Installer:</span></span>

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<span data-ttu-id="f9b3f-130">Das Erstellen und Überprüfen Ihres Analysetools erfolgt in mehreren Schritten:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-130">There are several steps to creating and validating your analyzer:</span></span>

1. <span data-ttu-id="f9b3f-131">Erstellen der Projektmappe</span><span class="sxs-lookup"><span data-stu-id="f9b3f-131">Create the solution.</span></span>
1. <span data-ttu-id="f9b3f-132">Registrieren von Name und Beschreibung des Analysetools</span><span class="sxs-lookup"><span data-stu-id="f9b3f-132">Register the analyzer name and description.</span></span>
1. <span data-ttu-id="f9b3f-133">Melden von Warnungen und Empfehlungen des Analysetools</span><span class="sxs-lookup"><span data-stu-id="f9b3f-133">Report analyzer warnings and recommendations.</span></span>
1. <span data-ttu-id="f9b3f-134">Implementieren des Codefixes zum Übernehmen der Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="f9b3f-134">Implement the code fix to accept recommendations.</span></span>
1. <span data-ttu-id="f9b3f-135">Verbessern der Analyse durch Komponententests</span><span class="sxs-lookup"><span data-stu-id="f9b3f-135">Improve the analysis through unit tests.</span></span>

## <a name="explore-the-analyzer-template"></a><span data-ttu-id="f9b3f-136">Kennenlernen der Vorlage für das Analysetool</span><span class="sxs-lookup"><span data-stu-id="f9b3f-136">Explore the analyzer template</span></span>

<span data-ttu-id="f9b3f-137">Ihr Analysetool meldet dem Benutzer alle lokalen Variablendeklarationen, die in lokale Konstanten konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-137">Your analyzer reports to the user any local variable declarations that can be converted to local constants.</span></span> <span data-ttu-id="f9b3f-138">Beachten Sie z. B. folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-138">For example, consider the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="f9b3f-139">Im Code oben ist `x` ein konstanter Wert zugewiesen, der nie geändert wird.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-139">In the code above, `x` is assigned a constant value and is never modified.</span></span> <span data-ttu-id="f9b3f-140">Er kann mithilfe des `const`-Modifizierers deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-140">It can be declared using the `const` modifier:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="f9b3f-141">Dies bringt die Analyse mit sich, mit der bestimmt wird, ob eine Variable zu einer Konstanten gemacht werden kann, wozu Syntaxanalyse, Konstantenanalyse des Initialisiererausdrucks und eine Datenflussanalyse erforderlich sind, um sicherzustellen, dass zu keinem Zeitpunkt in die Variable geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-141">The analysis to determine whether a variable can be made constant is involved, requiring syntactic analysis, constant analysis of the initializer expression and dataflow analysis to ensure that the variable is never written to.</span></span> <span data-ttu-id="f9b3f-142">Die .NET Compiler Platform stellt APIs zur Verfügung, die das Durchführen dieser Analyse erleichtern.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-142">The .NET Compiler Platform provides APIs that make it easier to perform this analysis.</span></span> <span data-ttu-id="f9b3f-143">Der erste Schritt ist die Erstellung eines neuen C#-Projekts **Analysetool mit Codefix**.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-143">The first step is to create a new C# **Analyzer with code fix** project.</span></span>

- <span data-ttu-id="f9b3f-144">Wählen Sie in Visual Studio **Datei > Neu > Projekt...** aus, um das Dialogfeld „Neues Projekt“ anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-144">In Visual Studio, choose **File > New > Project...** to display the New Project dialog.</span></span>
- <span data-ttu-id="f9b3f-145">Wählen Sie unter **Visual C# > Erweiterbarkeit** **Analyzer with code fix (.NET Standard)** (Analysetool mit Codefix (.NET Standard)) aus.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-145">Under **Visual C# > Extensibility**, choose **Analyzer with code fix (.NET Standard)**.</span></span>
- <span data-ttu-id="f9b3f-146">Benennen Sie Ihr Projekt "**MakeConst**", und klicken Sie auf „OK“.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-146">Name your project "**MakeConst**" and click OK.</span></span>

<span data-ttu-id="f9b3f-147">Die Vorlage für das Analysetool mit Codefix erstellt drei Projekte: Das erste enthält das Analysetool und den Codefix, das zweite ist ein Komponententestprojekt, und das dritte ist das VSIX-Projekt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-147">The analyzer with code fix template creates three projects: one contains the analyzer and code fix, the second is a unit test project, and the third is the VSIX project.</span></span> <span data-ttu-id="f9b3f-148">Das Standardstartprojekt ist das VSIX-Projekt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-148">The default startup project is the VSIX project.</span></span> <span data-ttu-id="f9b3f-149">Drücken Sie <kbd>F5</kbd>, um das VSIX-Projekt zu starten.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-149">Press <kbd>F5</kbd> to start the VSIX project.</span></span> <span data-ttu-id="f9b3f-150">Dadurch wird eine zweite Instanz von Visual Studio mit geladenem neuem Analysemodul gestartet.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-150">This starts a second instance of Visual Studio that has loaded your new analyzer.</span></span>

> [!TIP]
> <span data-ttu-id="f9b3f-151">Wenn Sie das Analysetool ausführen, wird eine zweite Instanz von Visual Studio gestartet.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-151">When you run your analyzer, you start a second copy of Visual Studio.</span></span> <span data-ttu-id="f9b3f-152">Diese zweite Kopie verwendet eine andere Registrierungsstruktur zum Speichern von Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-152">This second copy uses a different registry hive to store settings.</span></span> <span data-ttu-id="f9b3f-153">Dadurch können Sie in beiden Instanzen von Visual Studio verschiedene Anzeigeeinstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-153">That enables you to differentiate the visual settings in the two copies of Visual Studio.</span></span> <span data-ttu-id="f9b3f-154">Sie können für die Testinstanz von Visual Studio ein anderes Design auswählen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-154">You can pick a different theme for the experimental run of Visual Studio.</span></span> <span data-ttu-id="f9b3f-155">Achten Sie außerdem darauf, Ihre Einstellungen oder Ihre Anmeldung nicht mithilfe der Testinstanz von Visual Studio als mobiler Benutzer auf Ihr Visual Studio-Konto zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-155">In addition, don't roam your settings or login to your Visual Studio account using the experimental run of Visual Studio.</span></span> <span data-ttu-id="f9b3f-156">Auf diese Weise bleiben die unterschiedlichen Einstellungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-156">That keeps the settings different.</span></span>

<span data-ttu-id="f9b3f-157">Erstellen Sie in der zweiten Visual Studio-Instanz, die Sie gerade gestartet haben, ein neues Projekt für eine C#-Konsolenanwendung (wahlweise ein .NET Core- oder ein .NET Framework-Projekt – Analysetools arbeiten auf Quellebene.) Zeigen Sie auf das wellenförmig unterstrichene Token, dann wird der von einem Analysetool bereitgestellte Warnungstext angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-157">In the second Visual Studio instance that you just started, create a new C# Console Application project (either .NET Core or .NET Framework project will work -- analyzers work at the source level.) Hover over the token with a wavy underline, and the warning text provided by an analyzer appears.</span></span>

<span data-ttu-id="f9b3f-158">Die Vorlage erstellt ein Analysetool, das für jede Typdeklaration, deren Typname Kleinbuchstaben enthält, eine Warnung meldet, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-158">The template creates an analyzer that reports a warning on each type declaration where the type name contains lowercase letters, as shown in the following figure:</span></span>

![Analysetool beim Melden einer Warnung](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

<span data-ttu-id="f9b3f-160">Die Vorlage stellt darüber hinaus einen Codefix bereit, der jeden Typnamen, der Kleinbuchstaben enthält, in durchgängig Großbuchstaben ändert.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-160">The template also provides a code fix that changes any type name containing lower case characters to all upper case.</span></span> <span data-ttu-id="f9b3f-161">Sie können auf die zusammen mit der Warnung angezeigte Glühbirne klicken, um die vorgeschlagenen Änderungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-161">You can click on the light bulb displayed with the warning to see the suggested changes.</span></span> <span data-ttu-id="f9b3f-162">Wenn Sie die vorgeschlagenen Änderungen akzeptieren, werden der Typname und alle Verweise auf den betreffenden Typ in der Projektmappe aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-162">Accepting the suggested changes updates the type name and all references to that type in the solution.</span></span> <span data-ttu-id="f9b3f-163">Nachdem Sie jetzt das anfängliche Analysetool in Aktion gesehen haben, schließen Sie die zweite Visual Studio-Instanz, und kehren Sie zu Ihrem Analysetoolprojekt zurück.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-163">Now that you've seen the initial analyzer in action, close the second Visual Studio instance and return to your analyzer project.</span></span>

<span data-ttu-id="f9b3f-164">Sie brauchen keine zweite Instanz von Visual Studio zu starten und neuen Code zu erstellen, um jede Änderung an Ihrem Analysetool zu testen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-164">You don't have to start a second copy of Visual Studio and create new code to test every change in your analyzer.</span></span> <span data-ttu-id="f9b3f-165">Die Vorlage erstellt für Sie außerdem ein Komponententestprojekt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-165">The template also creates a unit test project for you.</span></span> <span data-ttu-id="f9b3f-166">Dieses Projekt enthält zwei Tests.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-166">That project contains two tests.</span></span> <span data-ttu-id="f9b3f-167">`TestMethod1` zeigt das typische Format eines Tests, der Code analysiert, ohne eine Diagnose auszulösen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-167">`TestMethod1` shows the typical format of a test that analyzes code without triggering a diagnostic.</span></span> <span data-ttu-id="f9b3f-168">`TestMethod2` zeigt das Format eines Tests, der eine Diagnose auslöst und dann einen vorgeschlagenen Codefix anwendet.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-168">`TestMethod2` shows the format of a test that triggers a diagnostic, and then applies a suggested code fix.</span></span> <span data-ttu-id="f9b3f-169">Beim Erstellen Ihres Analysetools und Codefixes werden Sie Tests für verschiedene Codestrukturen schreiben, um Ihre Arbeit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-169">As you build your analyzer and code fix, you'll write tests for different code structures to verify your work.</span></span> <span data-ttu-id="f9b3f-170">Komponententests für Analysetools sind viel schneller als interaktive Tests in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-170">Unit tests for analyzers are much quicker than testing them interactively with Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="f9b3f-171">Analysetool-Komponententests sind ein hervorragendes Werkzeug, wenn Sie wissen, welche Codekonstrukte Ihr Analysetool auslösen sollten und welche nicht.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-171">Analyzer unit tests are a great tool when you know what code constructs should and shouldn't trigger your analyzer.</span></span> <span data-ttu-id="f9b3f-172">Das Laden Ihres Analysetools in einer weiteren Visual Studio-Instanz ist ein tolles Hilfsmittel, um Konstrukte zu finden und zu untersuchen, die Ihnen möglicherweise noch nicht in den Sinn gekommen sind.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-172">Loading your analyzer in another copy of Visual Studio is a great tool to explore and find constructs you may not have thought about yet.</span></span>

## <a name="create-analyzer-registrations"></a><span data-ttu-id="f9b3f-173">Erstellen von Analysetoolregistrierungen</span><span class="sxs-lookup"><span data-stu-id="f9b3f-173">Create analyzer registrations</span></span>

<span data-ttu-id="f9b3f-174">Die Vorlage erstellt die anfängliche `DiagnosticAnalyzer`-Klasse in der Datei **MakeConstAnalyzer.cs**.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-174">The template creates the initial `DiagnosticAnalyzer` class, in the **MakeConstAnalyzer.cs** file.</span></span> <span data-ttu-id="f9b3f-175">Dieses anfängliche Analysetool zeigt zwei wichtige Eigenschaften jedes Analysetools.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-175">This initial analyzer shows two important properties of every analyzer.</span></span>

- <span data-ttu-id="f9b3f-176">Jedes Diagnoseanalysetool muss ein `[DiagnosticAnalyzer]`-Attribut bereitstellen, das die Sprache beschreibt, in der es arbeitet.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-176">Every diagnostic analyzer must provide a `[DiagnosticAnalyzer]` attribute that describes the language it operates on.</span></span>
- <span data-ttu-id="f9b3f-177">Jedes Diagnoseanalysetool muss aus der <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer>-Klasse abgeleitet sein.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-177">Every diagnostic analyzer must derive from the <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer> class.</span></span>

<span data-ttu-id="f9b3f-178">Die Vorlage zeigt außerdem die grundlegenden Features, die jedes Analysetool auszeichnen:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-178">The template also shows the basic features that are part of any analyzer:</span></span>

1. <span data-ttu-id="f9b3f-179">Registrieren von Aktionen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-179">Register actions.</span></span> <span data-ttu-id="f9b3f-180">Die Aktionen stellen Codeänderungen dar, die Ihr Analysetool auslösen sollten, um den Code auf Verstöße hin zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-180">The actions represent code changes that should trigger your analyzer to examine code for violations.</span></span> <span data-ttu-id="f9b3f-181">Wenn Visual Studio Codebearbeitungen erkennt, die mit einer registrierten Aktion übereinstimmen, ruft es die registrierte Methode Ihres Analysetools auf.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-181">When Visual Studio detects code edits that match a registered action, it calls your analyzer's registered method.</span></span>
1. <span data-ttu-id="f9b3f-182">Erstellen von Diagnosen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-182">Create diagnostics.</span></span> <span data-ttu-id="f9b3f-183">Wenn Ihr Analysemodul einen Verstoß erkennt, erstellt es ein Diagnoseobjekt, das von Visual Studio verwendet wird, um den Benutzer vom Verstoß zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-183">When your analyzer detects a violation, it creates a diagnostic object that Visual Studio uses to notify the user of the violation.</span></span>

<span data-ttu-id="f9b3f-184">Sie registrieren Aktionen in Ihrer Überschreibung der <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-184">You register actions in your override of <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f9b3f-185">In diesem Tutorial suchen Sie auf der Suche nach lokalen Deklarationen **Syntaxknoten** auf und sehen, welche von ihnen konstante Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-185">In this tutorial, you'll visit **syntax nodes** looking for local declarations, and see which of those have constant values.</span></span> <span data-ttu-id="f9b3f-186">Wenn eine Deklaration eine Konstante vorsehen könnte, erstellt und meldet Ihr Analysetool eine Diagnose.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-186">If a declaration could be constant, your analyzer will create and report a diagnostic.</span></span>

<span data-ttu-id="f9b3f-187">Der erste Schritt besteht darin, die Registrierungskonstanten und die `Initialize`-Methode zu aktualisieren, damit diese Konstanten Ihr „Make Const“-Analysetool anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-187">The first step is to update the registration constants and `Initialize` method so these constants indicate your "Make Const" analyzer.</span></span> <span data-ttu-id="f9b3f-188">Die meisten der Zeichenfolgenkonstanten sind in der Zeichenfolgen-Ressourcendatei definiert.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-188">Most of the string constants are defined in the string resource file.</span></span> <span data-ttu-id="f9b3f-189">Sie sollten sich zwecks einfacherer Lokalisierung auch an diese Praxis halten.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-189">You should follow that practice for easier localization.</span></span> <span data-ttu-id="f9b3f-190">Öffnen Sie die **Resources.resx**-Datei für das **MakeConst**-Analysetoolprojekt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-190">Open the **Resources.resx** file for the **MakeConst** analyzer project.</span></span> <span data-ttu-id="f9b3f-191">Dadurch wird der Ressourcen-Editor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-191">This displays the resource editor.</span></span> <span data-ttu-id="f9b3f-192">Aktualisieren Sie die Zeichenfolgenressourcen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-192">Update the string resources as follows:</span></span>

- <span data-ttu-id="f9b3f-193">Ändern Sie `AnalyzerTitle` in „Variable kann als Konstante umdeklariert werden“.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-193">Change `AnalyzerTitle` to "Variable can be made constant".</span></span>
- <span data-ttu-id="f9b3f-194">Ändern Sie `AnalyzerMessageFormat` in „Kann als Konstante deklariert werden“.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-194">Change `AnalyzerMessageFormat` to "Can be made constant".</span></span>
- <span data-ttu-id="f9b3f-195">Ändern Sie `AnalyzerDescription` in „Als Konstante deklarieren“.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-195">Change `AnalyzerDescription` to "Make Constant".</span></span>

<span data-ttu-id="f9b3f-196">Ändern Sie außerdem die **Zugriffsmodifizierer**-Dropdownliste in `public`.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-196">Also, change the **Access Modifier** drop-down to `public`.</span></span> <span data-ttu-id="f9b3f-197">Das vereinfacht die Verwendung dieser Konstanten in Komponententests.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-197">That makes it easier to use these constants in unit tests.</span></span> <span data-ttu-id="f9b3f-198">Wenn Sie fertig sind, sollte der Ressourcen-Editor wie in der folgenden Abbildung aussehen:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-198">When you have finished, the resource editor should appear as follow figure shows:</span></span>

![Zeichenfolgenressourcen aktualisieren](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

<span data-ttu-id="f9b3f-200">Die verbleibenden Änderungen finden sich in der Analysetooldatei.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-200">The remaining changes are in the analyzer file.</span></span> <span data-ttu-id="f9b3f-201">Öffnen Sie **MakeConstAnalyzer.cs** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-201">Open **MakeConstAnalyzer.cs** in Visual Studio.</span></span> <span data-ttu-id="f9b3f-202">Ändern Sie die registrierte Aktion von einer Aktion, die für Symbole aktiv ist, in eine, die mit Syntax agiert.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-202">Change the registered action from one that acts on symbols to one that acts on syntax.</span></span> <span data-ttu-id="f9b3f-203">Suchen Sie in der `MakeConstAnalyzerAnalyzer.Initialize`-Methode die Zeile, die die Aktion für Symbole registriert:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-203">In the `MakeConstAnalyzerAnalyzer.Initialize` method, find the line that registers the action on symbols:</span></span>

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

<span data-ttu-id="f9b3f-204">Ersetzen Sie sie durch die folgende Zeile:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-204">Replace it with the following line:</span></span>

[!code-csharp[Register the node action](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

<span data-ttu-id="f9b3f-205">Nach dieser Änderung können Sie die `AnalyzeSymbol`-Methode löschen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-205">After that change, you can delete the `AnalyzeSymbol` method.</span></span> <span data-ttu-id="f9b3f-206">Dieses Analysetool untersucht <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>-Anweisungen, keine <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType>-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-206">This analyzer examines <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, not <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType> statements.</span></span> <span data-ttu-id="f9b3f-207">Beachten Sie, dass `AnalyzeNode` mit roten Wellenlinien unterstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-207">Notice that `AnalyzeNode` has red squiggles under it.</span></span> <span data-ttu-id="f9b3f-208">Der Code, den Sie soeben hinzugefügt haben, verweist auf eine `AnalyzeNode`-Methode, die noch nicht deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-208">The code you just added references an `AnalyzeNode` method that hasn't been declared.</span></span> <span data-ttu-id="f9b3f-209">Deklarieren Sie diese Methode mithilfe des folgenden Codes:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-209">Declare that method using the following code:</span></span>

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

<span data-ttu-id="f9b3f-210">Ändern Sie in **MakeConstAnalyzer.cs** die `Category` in „Usage“, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-210">Change the `Category` to "Usage" in **MakeConstAnalyzer.cs** as shown in the following code:</span></span>

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a><span data-ttu-id="f9b3f-211">Suchen von lokalen Deklarationen, die „const“ lauten könnten</span><span class="sxs-lookup"><span data-stu-id="f9b3f-211">Find local declarations that could be const</span></span>

<span data-ttu-id="f9b3f-212">Es ist Zeit, die erste Version der `AnalyzeNode`-Methode zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-212">It's time to write the first version of the `AnalyzeNode` method.</span></span> <span data-ttu-id="f9b3f-213">Sie soll nach einer einzelnen lokalen Deklaration suchen, die `const` sein könnte, es aber nicht ist, wie der folgende Code:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-213">It should look for a single local declaration that could be `const` but is not, like the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="f9b3f-214">Der erste Schritt besteht darin, nach lokalen Deklarationen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-214">The first step is to find local declarations.</span></span> <span data-ttu-id="f9b3f-215">Fügen Sie in **MakeConstAnalyzer.cs** den folgenden Code zu `AnalyzeNode` hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-215">Add the following code to `AnalyzeNode` in **MakeConstAnalyzer.cs**:</span></span>

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

<span data-ttu-id="f9b3f-216">Diese Umwandlung funktioniert immer, da Ihr Analysetool für Änderungen an lokalen Deklarationen und nur an lokalen Deklarationen registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-216">This cast always succeeds because your analyzer registered for changes to local declarations, and only local declarations.</span></span> <span data-ttu-id="f9b3f-217">Kein anderer Knotentyp löst einen Aufruf Ihrer `AnalyzeNode`-Methode aus.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-217">No other node type triggers a call to your `AnalyzeNode` method.</span></span> <span data-ttu-id="f9b3f-218">Überprüfen Sie als Nächstes die Deklaration für alle `const`-Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-218">Next, check the declaration for any `const` modifiers.</span></span> <span data-ttu-id="f9b3f-219">Wenn Sie sie finden, geben Sie sofort zurück.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-219">If you find them, return immediately.</span></span> <span data-ttu-id="f9b3f-220">Der folgende Code sucht nach allen `const`-Modifizierern in der lokalen Deklaration:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-220">The following code looks for any `const` modifiers on the local declaration:</span></span>

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

<span data-ttu-id="f9b3f-221">Schließlich müssen Sie überprüfen, ob die Variable `const` sein könnte.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-221">Finally, you need to check that the variable could be `const`.</span></span> <span data-ttu-id="f9b3f-222">Das bedeutet, sicherzustellen, dass sie nach der Initialisierung nie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-222">That means making sure it is never assigned after it is initialized.</span></span>

<span data-ttu-id="f9b3f-223">Sie führen semantische Analysen mithilfe von <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext> durch.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-223">You'll perform some semantic analysis using the <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span></span> <span data-ttu-id="f9b3f-224">Sie verwenden das `context`-Argument, um festzustellen, ob die lokale Variablendeklaration als `const` festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-224">You use the `context` argument to determine whether the local variable declaration can be made `const`.</span></span> <span data-ttu-id="f9b3f-225">Ein <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> stellt sämtliche semantischen Informationen in einer einzelnen Quelldatei dar.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-225">A <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> represents all of semantic information in a single source file.</span></span> <span data-ttu-id="f9b3f-226">Mehr können Sie im Artikel über [semantische Modelle](../work-with-semantics.md) erfahren.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-226">You can learn more in the article that covers [semantic models](../work-with-semantics.md).</span></span> <span data-ttu-id="f9b3f-227">Sie verwenden das <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> zum Durchführen einer Datenflussanalyse für die lokale Deklarationsanweisung.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-227">You'll use the <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> to perform data flow analysis on the local declaration statement.</span></span> <span data-ttu-id="f9b3f-228">Anschließend nutzen Sie die Ergebnisse dieser Datenflussanalyse, um sicherzustellen, dass zu keiner Zeit irgendwo ein neuer Wert in die lokale Variable geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-228">Then, you use the results of this data flow analysis to ensure that the local variable isn't written with a new value anywhere else.</span></span> <span data-ttu-id="f9b3f-229">Rufen Sie die <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A>-Erweiterungsmethode auf, um das <xref:Microsoft.CodeAnalysis.ILocalSymbol> für die Variable abzurufen und zu sicherzustellen, dass sie nicht in der <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType>-Sammlung der Datenflussanalyse enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-229">Call the <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> extension method to retrieve the <xref:Microsoft.CodeAnalysis.ILocalSymbol> for the variable and check that it isn't contained with the <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> collection of the data flow analysis.</span></span> <span data-ttu-id="f9b3f-230">Fügen Sie am Ende der `AnalyzeNode`-Methode den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-230">Add the following code to the end of the `AnalyzeNode` method:</span></span>

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

<span data-ttu-id="f9b3f-231">Der Code, den Sie soeben hinzugefügt haben, stellt sicher, dass die Variable nicht verändert wird und daher als `const` deklariert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-231">The code just added ensures that the variable isn't modified, and can therefore be made `const`.</span></span> <span data-ttu-id="f9b3f-232">Es ist Zeit, die Diagnose zu stellen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-232">It's time to raise the diagnostic.</span></span> <span data-ttu-id="f9b3f-233">Fügen Sie in `AnalyzeNode` den folgenden Code als letzte Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-233">Add the following code as the last line in `AnalyzeNode`:</span></span>

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

<span data-ttu-id="f9b3f-234">Sie können Ihren Fortschritt überprüfen, indem Sie <kbd>F5</kbd> drücken, um Ihr Analysetool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-234">You can check your progress by pressing <kbd>F5</kbd> to run your analyzer.</span></span> <span data-ttu-id="f9b3f-235">Sie können die Konsolenanwendung laden, die Sie zuvor erstellt haben, und dann den folgenden Testcode hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-235">You can load the console application you created earlier and then add the following test code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="f9b3f-236">Die Glühbirne sollte angezeigt werden, und Ihr Analysetool sollte eine Diagnose melden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-236">The light bulb should appear, and your analyzer should report a diagnostic.</span></span> <span data-ttu-id="f9b3f-237">Allerdings verwendet die Glühbirne noch den aus der Vorlage erzeugten Codefix und informiert Sie, dass die Variable in Großbuchstaben geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-237">However, the light bulb still uses the template generated code fix, and tells you it can be made upper case.</span></span> <span data-ttu-id="f9b3f-238">Im nächsten Abschnitt erfahren Sie, wie der Codefix geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-238">The next section explains how to write the code fix.</span></span>

## <a name="write-the-code-fix"></a><span data-ttu-id="f9b3f-239">Schreiben des Codefixes</span><span class="sxs-lookup"><span data-stu-id="f9b3f-239">Write the code fix</span></span>

<span data-ttu-id="f9b3f-240">Ein Analysetool kann einen Codefix oder mehrere zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-240">An analyzer can provide one or more code fixes.</span></span> <span data-ttu-id="f9b3f-241">Ein Codefix definiert eine Bearbeitung, die das gemeldete Problem angeht.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-241">A code fix defines an edit that addresses the reported issue.</span></span> <span data-ttu-id="f9b3f-242">Für das Analysetool, das Sie erstellt haben, können Sie einen Codefix bereitstellen, der das Schlüsselwort „const“ einfügt:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-242">For the analyzer that you created, you can provide a code fix that inserts the const keyword:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="f9b3f-243">Der Benutzer wählt es im Editor in der Benutzeroberfläche der Glühbirne aus, und Visual Studio ändert den Code.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-243">The user chooses it from the light bulb UI in the editor and Visual Studio changes the code.</span></span>

<span data-ttu-id="f9b3f-244">Öffnen Sie die von der Vorlage hinzugefügte Datei **MakeConstCodeFixProvider.cs**.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-244">Open the **MakeConstCodeFixProvider.cs** file added by the template.</span></span>  <span data-ttu-id="f9b3f-245">Dieser Codefix ist bereits mit der Diagnose-ID verschaltet, die von Ihrem Diagnoseanalysetool erzeugt wird, er implementiert jedoch noch nicht die gewünschte Codetransformation.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-245">This code fix is already wired up to the Diagnostic ID produced by your diagnostic analyzer, but it doesn't yet implement the right code transform.</span></span> <span data-ttu-id="f9b3f-246">Zunächst sollten Sie einen Teil des Vorlagencodes entfernen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-246">First you should remove some of the template code.</span></span> <span data-ttu-id="f9b3f-247">Ändern Sie die Titelzeichenfolge in „Als Konstante deklarieren“:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-247">Change the title string to "Make constant":</span></span>

[!code-csharp[Update the CodeFix title](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

<span data-ttu-id="f9b3f-248">Löschen Sie als Nächstes die `MakeUppercaseAsync`-Methode.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-248">Next, delete the `MakeUppercaseAsync` method.</span></span> <span data-ttu-id="f9b3f-249">Sie trifft nicht mehr zu.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-249">It no longer applies.</span></span>

<span data-ttu-id="f9b3f-250">Alle Codefixanbieter werden von <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-250">All code fix providers derive from <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>.</span></span> <span data-ttu-id="f9b3f-251">Sie alle überschreiben <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType>, um verfügbare Codefixe zu melden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-251">They all override <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> to report available code fixes.</span></span> <span data-ttu-id="f9b3f-252">Ändern Sie in `RegisterCodeFixesAsync` den Typ des Vorgängerknotens, nach dem Sie suchen, in <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>, damit er mit der Diagnose übereinstimmt:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-252">In `RegisterCodeFixesAsync`, change the ancestor node type you're searching for to a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> to match the diagnostic:</span></span>

[!code-csharp[Find local declaration node](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

<span data-ttu-id="f9b3f-253">Ändern Sie dann die letzte Zeile, um einen Codefix zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-253">Next, change the last line to register a code fix.</span></span> <span data-ttu-id="f9b3f-254">Ihr Fix erstellt ein neues Dokument, das sich daraus ergibt, dass einer vorhandenen Deklaration der `const`-Modifizierer hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-254">Your fix will create a new document that results from adding the `const` modifier to an existing declaration:</span></span>

[!code-csharp[Register the new code fix](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

<span data-ttu-id="f9b3f-255">Sie werden rote Wellenlinien in dem soeben hinzugefügten Code unter dem Symbol `MakeConstAsync` bemerken.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-255">You'll notice red squiggles in the code you just added on the symbol `MakeConstAsync`.</span></span> <span data-ttu-id="f9b3f-256">Fügen Sie eine Deklaration für `MakeConstAsync` hinzu, wie etwa den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-256">Add a declaration for `MakeConstAsync` like the following code:</span></span>

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

<span data-ttu-id="f9b3f-257">Ihre neue `MakeConstAsync`-Methode transformiert das <xref:Microsoft.CodeAnalysis.Document>, das die Quelldatei des Benutzers darstellt, in ein neues <xref:Microsoft.CodeAnalysis.Document>, das jetzt eine `const`-Deklaration enthält.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-257">Your new `MakeConstAsync` method will transform the <xref:Microsoft.CodeAnalysis.Document> representing the user's source file into a new <xref:Microsoft.CodeAnalysis.Document> that now contains a `const` declaration.</span></span>

<span data-ttu-id="f9b3f-258">Sie erstellen ein neues `const`-Schlüsselworttoken, um es am Anfang der Deklarationsanweisung einzufügen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-258">You create a new `const` keyword token to insert at the front of the declaration statement.</span></span> <span data-ttu-id="f9b3f-259">Achten Sie darauf, zuerst alle führenden Trivia aus dem ersten Token der Deklarationsanweisung zu entfernen und sie an das `const`-Token anzufügen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-259">Be careful to first remove any leading trivia from the first token of the declaration statement and attach it to the `const` token.</span></span> <span data-ttu-id="f9b3f-260">Fügen Sie der `MakeConstAsync`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-260">Add the following code to the `MakeConstAsync` method:</span></span>

[!code-csharp[Create a new const keyword token](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

<span data-ttu-id="f9b3f-261">Fügen Sie als Nächstes der Deklaration das `const`-Token mithilfe des folgenden Codes hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-261">Next, add the `const` token to the declaration using the following code:</span></span>

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

<span data-ttu-id="f9b3f-262">Formatieren Sie anschließend die neue Deklaration gemäß den C#-Formatierungsregeln.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-262">Next, format the new declaration to match C# formatting rules.</span></span> <span data-ttu-id="f9b3f-263">Das Formatieren Ihrer Änderungen in Anlehnung an den vorhandenen Code macht einen besseren Eindruck.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-263">Formatting your changes to match existing code creates a better experience.</span></span> <span data-ttu-id="f9b3f-264">Fügen Sie unmittelbar hinter dem vorhandenen Code die folgende Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-264">Add the following statement immediately after the existing code:</span></span>

[!code-csharp[Format the new declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

<span data-ttu-id="f9b3f-265">Für diesen Code ist ein neuer Namespace erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-265">A new namespace is required for this code.</span></span> <span data-ttu-id="f9b3f-266">Fügen Sie am Anfang der Datei die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-266">Add the following `using` directive to the top of the file:</span></span>

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

<span data-ttu-id="f9b3f-267">Der letzte Schritt besteht im Ausführen Ihrer Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-267">The final step is to make your edit.</span></span> <span data-ttu-id="f9b3f-268">Dieser Prozess besteht aus drei Schritten:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-268">There are three steps to this process:</span></span>

1. <span data-ttu-id="f9b3f-269">Abrufen eines Handles zu dem vorhandenen Dokument.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-269">Get a handle to the existing document.</span></span>
1. <span data-ttu-id="f9b3f-270">Erstellen eines neuen Dokuments durch Ersetzen der vorhandenen Deklaration durch die neue Deklaration.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-270">Create a new document by replacing the existing declaration with the new declaration.</span></span>
1. <span data-ttu-id="f9b3f-271">Zurückgeben des neuen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-271">Return the new document.</span></span>

<span data-ttu-id="f9b3f-272">Fügen Sie den folgenden Code am Ende der `MakeConstAsync`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-272">Add the following code to the end of the `MakeConstAsync` method:</span></span>

[!code-csharp[replace the declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

<span data-ttu-id="f9b3f-273">Ihr Codefix ist nun bereit, ausprobiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-273">Your code fix is ready to try.</span></span>  <span data-ttu-id="f9b3f-274">Drücken Sie <kbd>F5</kbd>, um das Analysetoolprojekt in einer zweiten Instanz von Visual Studio auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-274">Press <kbd>F5</kbd> to run the analyzer project in a second instance of Visual Studio.</span></span> <span data-ttu-id="f9b3f-275">Erstellen Sie in der zweiten Visual Studio-Instanz ein neues Konsolenanwendungsprojekt in C#, und fügen Sie der Methode „Main“ einige lokale Variablendeklarationen hinzu, die mit konstanten Werten initialisiert sind.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-275">In the second Visual Studio instance, create a new C# Console Application project and add a few local variable declarations initialized with constant values to the Main method.</span></span> <span data-ttu-id="f9b3f-276">Sie sehen, dass sie als Warnungen gemeldet werden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-276">You'll see that they are reported as warnings as below.</span></span>

![Warnungen „Kann als ‚const‘ deklariert werden“](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

<span data-ttu-id="f9b3f-278">Sie haben große Fortschritte erzielt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-278">You've made a lot of progress.</span></span> <span data-ttu-id="f9b3f-279">Unter den Deklarationen, die in `const` umgewandelt werden können, werden Wellenlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-279">There are squiggles under the declarations that can be made `const`.</span></span> <span data-ttu-id="f9b3f-280">Aber die Arbeit ist noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-280">But there is still work to do.</span></span> <span data-ttu-id="f9b3f-281">Alles hier funktioniert, wenn Sie `const` den Deklarationen beginnend bei `i`, dann weiter mit `j` und schließlich `k` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-281">This works fine if you add `const` to the declarations starting with `i`, then `j` and finally `k`.</span></span> <span data-ttu-id="f9b3f-282">Wenn Sie den `const`-Modifizierer aber in einer anderen Reihenfolge zu i zuweisen, beginnend mit `k`, erzeugt Ihr Analysetool Fehler: `k` kann nicht `const` deklariert werden, sofern nicht `i` und `j` beide bereits `const` sind.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-282">But, if you add the `const` modifier in a different order, starting with `k`, your analyzer creates errors: `k` can't be declared `const`, unless `i` and `j` are both already `const`.</span></span> <span data-ttu-id="f9b3f-283">Sie müssen weitere Analysen durchführen, um sicherzustellen, dass Sie mit den verschiedenen Weisen umgehen können, in denen Variablen deklariert und initialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-283">You've got to do more analysis to ensure you handle the different ways variables can be declared and initialized.</span></span>

## <a name="build-data-driven-tests"></a><span data-ttu-id="f9b3f-284">Erstellen von datengesteuerten Tests</span><span class="sxs-lookup"><span data-stu-id="f9b3f-284">Build data driven tests</span></span>

<span data-ttu-id="f9b3f-285">Ihr Analysetool und der Codefix funktionieren beim einfachen Fall einer einzelnen Deklaration, die als „const“ deklariert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-285">Your analyzer and code fix work on a simple case of a single declaration that can be made const.</span></span> <span data-ttu-id="f9b3f-286">Es gibt eine Vielzahl von möglichen Deklarationsanweisungen, bei denen diese Implementierung zu Fehlern führt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-286">There are numerous possible declaration statements where this implementation makes mistakes.</span></span> <span data-ttu-id="f9b3f-287">Sie tragen diesen Fällen Rechnung, indem Sie mit der Komponententestbibliothek arbeiten, die von der Vorlage erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-287">You'll address these cases by working with the unit test library written by the template.</span></span> <span data-ttu-id="f9b3f-288">Das funktioniert viel schneller, als wiederholt eine zweite Instanz von Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-288">It's much faster than repeatedly opening a second copy of Visual Studio.</span></span>

<span data-ttu-id="f9b3f-289">Öffnen Sie die **MakeConstUnitTests.cs**-Datei im Komponententestprojekt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-289">Open the **MakeConstUnitTests.cs** file in the unit test project.</span></span> <span data-ttu-id="f9b3f-290">Die Vorlage hat zwei Tests erstellt, die den zwei allgemeinen Mustern für einen Komponententest für Analysetools und Codefixe folgen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-290">The template created two tests that follow the two common patterns for an analyzer and code fix unit test.</span></span> <span data-ttu-id="f9b3f-291">`TestMethod1` zeigt das Muster für einen Test, der sicherstellt, dass das Analysetool keine Diagnose meldet, wenn es das nicht sollte.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-291">`TestMethod1` shows the pattern for a test that ensures the analyzer doesn't report a diagnostic when it shouldn't.</span></span> <span data-ttu-id="f9b3f-292">`TestMethod2` zeigt das Muster für das Melden einer Diagnose und das Ausführen des Codefixes.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-292">`TestMethod2` shows the pattern for reporting a diagnostic and running the code fix.</span></span>

<span data-ttu-id="f9b3f-293">Der Code nahezu jedes Tests für Ihr Analysetool folgt einem dieser beiden Muster.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-293">The code for almost every test for your analyzer follows one of these two patterns.</span></span> <span data-ttu-id="f9b3f-294">Im ersten Schritt können Sie diese Tests als datengesteuerte Tests umarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-294">For the first step, you can rework these tests as data driven tests.</span></span> <span data-ttu-id="f9b3f-295">Anschließend wird es einfach, neue Tests zu erstellen, indem Sie neue Zeichenfolgenkonstanten hinzufügen, um verschiedene Testeingaben darzustellen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-295">Then, it will be easy to create new tests by adding new string constants to represent different test inputs.</span></span>

<span data-ttu-id="f9b3f-296">Aus Effizienzgründen besteht der erste Schritt in der Umgestaltung der beiden Tests in datengesteuerte Tests.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-296">For efficiency, the first step is to refactor the two tests into data driven tests.</span></span> <span data-ttu-id="f9b3f-297">Anschließend müssen Sie lediglich ein paar Zeichenfolgenkonstanten für jeden neuen Test definieren.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-297">Then, you only need to define a couple string constants for each new test.</span></span> <span data-ttu-id="f9b3f-298">Benennen Sie im Rahmen der Umgestaltung beide Methoden mit besseren Namen um.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-298">While you are refactoring, rename both methods to better names.</span></span> <span data-ttu-id="f9b3f-299">Ersetzen Sie `TestMethod1` durch diesen Test, der sicherstellt, dass keine Diagnose ausgelöst wird:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-299">Replace `TestMethod1` with this test that ensures no diagnostic is raised:</span></span>

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

<span data-ttu-id="f9b3f-300">Sie können für diesen Test eine neue Datenzeile erstellen, indem Sie jedes Codefragment definieren, das keine Warnung von Ihrer Diagnose auslösen soll.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-300">You can create a new data row for this test by defining any code fragment that should not cause your diagnostic to trigger a warning.</span></span> <span data-ttu-id="f9b3f-301">Diese Überladung von `VerifyCSharpDiagnostic` besteht den Test, wenn für das Quellcodefragment keine Diagnose ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-301">This overload of `VerifyCSharpDiagnostic` passes when there are no diagnostics triggered for the source code fragment.</span></span>

<span data-ttu-id="f9b3f-302">Ersetzen Sie als Nächstes `TestMethod2` durch diesen Test, der sicherstellt, dass für das Quellcodefragment eine Diagnose ausgelöst und ein Codefix angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-302">Next, replace `TestMethod2` with this test that ensures a diagnostic is raised and a code fix applied for the source code fragment:</span></span>

```csharp
[DataTestMethod]
[DataRow(LocalIntCouldBeConstant, LocalIntCouldBeConstantFixed, 10, 13)]
public void WhenDiagnosticIsRaisedFixUpdatesCode(
    string test,
    string fixTest,
    int line,
    int column)
{
    var expected = new DiagnosticResult
    {
        Id = MakeConstAnalyzer.DiagnosticId,
        Message = new LocalizableResourceString(nameof(MakeConst.Resources.AnalyzerMessageFormat), MakeConst.Resources.ResourceManager, typeof(MakeConst.Resources)).ToString(),
        Severity = DiagnosticSeverity.Warning,
        Locations =
            new[] {
                    new DiagnosticResultLocation("Test0.cs", line, column)
                }
    };

    VerifyCSharpDiagnostic(test, expected);

    VerifyCSharpFix(test, fixTest);
}
```

<span data-ttu-id="f9b3f-303">Im vorstehenden Code wurden außerdem ein paar Änderungen an dem Code vorgenommen, der das erwartete Diagnoseergebnis erzeugt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-303">The preceding code also made a couple changes to the code that builds the expected diagnostic result.</span></span> <span data-ttu-id="f9b3f-304">Er verwendet die im `MakeConst`-Analysetool registrierten öffentlichen Konstanten.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-304">It uses the public constants registered in the `MakeConst` analyzer.</span></span> <span data-ttu-id="f9b3f-305">Außerdem verwendet er zwei Zeichenfolgenkonstanten für die Eingabe und die feste Quelle.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-305">In addition, it uses two string constants for the input and fixed source.</span></span> <span data-ttu-id="f9b3f-306">Fügen Sie der `UnitTest`-Klasse die folgenden Zeichenfolgenkonstanten hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-306">Add the following string constants to the `UnitTest` class:</span></span>

[!code-csharp[string constants for fix test](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

<span data-ttu-id="f9b3f-307">Führen Sie diese zwei Tests aus, um sicherzustellen, dass sie bestanden werden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-307">Run these two tests to make sure they pass.</span></span> <span data-ttu-id="f9b3f-308">Öffnen Sie in Visual Studio den **Test-Explorer**, indem Sie **Test** > **Windows** > **Test-Explorer** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-308">In Visual Studio, open the **Test Explorer** by selecting **Test** > **Windows** > **Test Explorer**.</span></span> <span data-ttu-id="f9b3f-309">Wählen Sie dann den Link **Alle ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-309">Then select the **Run All** link.</span></span>

## <a name="create-tests-for-valid-declarations"></a><span data-ttu-id="f9b3f-310">Erstellen von Tests für gültige Deklarationen</span><span class="sxs-lookup"><span data-stu-id="f9b3f-310">Create tests for valid declarations</span></span>

<span data-ttu-id="f9b3f-311">Ganz allgemein sollten Analysetool so schnell wie möglich beendet werden und nur minimale Arbeit verrichten.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-311">As a general rule, analyzers should exit as quickly as possible, doing minimal work.</span></span> <span data-ttu-id="f9b3f-312">Visual Studio ruft registrierte Analysetools auf, während der Benutzer den Code bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-312">Visual Studio calls registered analyzers as the user edits code.</span></span> <span data-ttu-id="f9b3f-313">Reaktionsfähigkeit ist eine wichtige Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-313">Responsiveness is a key requirement.</span></span> <span data-ttu-id="f9b3f-314">Es gibt mehrere Testfälle für Code, der Ihre Diagnose nicht auslösen soll.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-314">There are several test cases for code that should not raise your diagnostic.</span></span> <span data-ttu-id="f9b3f-315">Ihr Analysetool verarbeitet bereits einen dieser Tests, den Fall, in dem eine Variable nach der Initialisierung zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-315">Your analyzer already handles one of those tests, the case where a variable is assigned after being initialized.</span></span> <span data-ttu-id="f9b3f-316">Fügen Sie Ihren Tests die folgende Zeichenfolgenkonstante hinzu, um diesem Fall darzustellen:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-316">Add the following string constant to your tests to represent that case:</span></span>

[!code-csharp[variable assigned](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

<span data-ttu-id="f9b3f-317">Fügen Sie anschließend eine Datenzeile für diesen Test hinzu, wie im Codeausschnitt unten zu sehen:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-317">Then, add a data row for this test as shown in the snippet below:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="f9b3f-318">Dieser Test wird ebenfalls bestanden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-318">This test passes as well.</span></span> <span data-ttu-id="f9b3f-319">Fügen Sie als Nächstes Konstanten für Bedingungen hinzu, die Sie noch nicht behandelt haben:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-319">Next, add constants for conditions you haven't handled yet:</span></span>

- <span data-ttu-id="f9b3f-320">Deklarationen, die bereits `const` sind, da sie bereits Konstanten sind:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-320">Declarations that are already `const`, because they are already const:</span></span>

   [!code-csharp[already const declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- <span data-ttu-id="f9b3f-321">Deklarationen, die keinen Initialisierer besitzen, weil es keinen zu verwendenden Wert gibt:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-321">Declarations that have no initializer, because there is no value to use:</span></span>

   [!code-csharp[declarations that have no initializer](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- <span data-ttu-id="f9b3f-322">Deklarationen, bei denen der Initialisierer keine Konstante ist, da sie zur Kompilierzeit keine Konstanten sein können:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-322">Declarations where the initializer is not a constant, because they can't be compile-time constants:</span></span>

   [!code-csharp[declarations where the initializer isn't const](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

<span data-ttu-id="f9b3f-323">Es kann sogar noch komplizierter sein, da C# mehrere Deklarationen in Form einer Anweisung zulässt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-323">It can be even more complicated because C# allows multiple declarations as one statement.</span></span> <span data-ttu-id="f9b3f-324">Betrachten Sie die folgende Zeichenfolgenkonstante aus einem Testfall:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-324">Consider the following test case string constant:</span></span>

[!code-csharp[multiple initializers](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

<span data-ttu-id="f9b3f-325">Die Variable `i` kann als Konstante deklariert werden, die Variable `j` jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-325">The variable `i` can be made constant, but the variable `j` cannot.</span></span> <span data-ttu-id="f9b3f-326">Daher kann aus dieser Anweisung keine const-Deklaration gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-326">Therefore, this statement cannot be made a const declaration.</span></span> <span data-ttu-id="f9b3f-327">Fügen Sie die `DataRow`-Deklarationen für alle diese Tests hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-327">Add the `DataRow` declarations for all these tests:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
    DataRow(VariableAssigned),
    DataRow(AlreadyConst),
    DataRow(NoInitializer),
    DataRow(InitializerNotConstant),
    DataRow(MultipleInitializers)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="f9b3f-328">Führen Sie Ihre Tests erneut aus – Sie werden feststellen, dass bei den neuen Testfällen Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-328">Run your tests again, and you'll see these new test cases fail.</span></span>

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a><span data-ttu-id="f9b3f-329">Aktualisieren Ihres Analysetools, damit korrekte Deklarationen ignoriert werden</span><span class="sxs-lookup"><span data-stu-id="f9b3f-329">Update your analyzer to ignore correct declarations</span></span>

<span data-ttu-id="f9b3f-330">Sie benötigen noch einige Verbesserungen an der `AnalyzeNode`-Methode Ihres Analysetools, um Code herauszufiltern, der den Bedingungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-330">You need some enhancements to your analyzer's `AnalyzeNode` method to filter out code that matches these conditions.</span></span> <span data-ttu-id="f9b3f-331">Es handelt sich bei allen um verwandte Bedingungen, daher lassen sich auch alle mit ähnlichen Änderungen beheben.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-331">They are all related conditions, so similar changes will fix all these conditions.</span></span> <span data-ttu-id="f9b3f-332">Nehmen Sie an `AnalyzeNode` die folgenden Änderungen vor:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-332">Make the following changes to `AnalyzeNode`:</span></span>

- <span data-ttu-id="f9b3f-333">Ihre semantische Analyse hat eine einzelne Variablendeklaration untersucht.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-333">Your semantic analysis examined a single variable declaration.</span></span> <span data-ttu-id="f9b3f-334">Dieser Code muss sich in einer `foreach`-Schleife befinden, die alle innerhalb der gleichen Anweisung deklarierten Variablen untersucht.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-334">This code needs to be in a `foreach` loop that examines all the variables declared in the same statement.</span></span>
- <span data-ttu-id="f9b3f-335">Jede deklarierte Variable muss über einen Initialisierer verfügen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-335">Each declared variable needs to have an initializer.</span></span>
- <span data-ttu-id="f9b3f-336">Der Initialisierer jeder deklarierten Variable muss zur Kompilierzeit eine Konstante sein.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-336">Each declared variable's initializer must be a compile-time constant.</span></span>

<span data-ttu-id="f9b3f-337">Ersetzen Sie in Ihrer `AnalyzeNode`-Methode die ursprüngliche semantische Analyse:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-337">In your `AnalyzeNode` method, replace the original semantic analysis:</span></span>

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

<span data-ttu-id="f9b3f-338">durch den folgenden Codeausschnitt:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-338">with the following code snippet:</span></span>

```csharp
// Ensure that all variables in the local declaration have initializers that
// are assigned with constant values.
foreach (var variable in localDeclaration.Declaration.Variables)
{
    var initializer = variable.Initializer;
    if (initializer == null)
    {
        return;
    }

    var constantValue = context.SemanticModel.GetConstantValue(initializer.Value);
    if (!constantValue.HasValue)
    {
        return;
    }
}

// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

foreach (var variable in localDeclaration.Declaration.Variables)
{
    // Retrieve the local symbol for each variable in the local declaration
    // and ensure that it is not written outside of the data flow analysis region.
    var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
    if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
    {
        return;
    }
}
```

<span data-ttu-id="f9b3f-339">Die erste `foreach`-Schleife untersucht jede Variablendeklaration mithilfe der Syntaxanalyse.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-339">The first `foreach` loop examines each variable declaration using syntactic analysis.</span></span> <span data-ttu-id="f9b3f-340">Die erste Prüfung stellt sicher, dass die Variable einen Initialisierer aufweist.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-340">The first check guarantees that the variable has an initializer.</span></span> <span data-ttu-id="f9b3f-341">Die zweite Prüfung stellt sicher, dass der Initialisierer eine Konstante ist.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-341">The second check guarantees that the initializer is a constant.</span></span> <span data-ttu-id="f9b3f-342">Die zweite Schleife enthält die ursprüngliche semantische Analyse.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-342">The second loop has the original semantic analysis.</span></span> <span data-ttu-id="f9b3f-343">Die semantischen Prüfungen befinden sich in einer separaten Schleife, da sie einen größeren Einfluss auf die Leistung haben.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-343">The semantic checks are in a separate loop because it has a greater impact on performance.</span></span> <span data-ttu-id="f9b3f-344">Führen Sie Ihre Tests erneut aus – sie sollten alle bestanden werden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-344">Run your tests again, and you should see them all pass.</span></span>

## <a name="add-the-final-polish"></a><span data-ttu-id="f9b3f-345">Der letzte Schliff</span><span class="sxs-lookup"><span data-stu-id="f9b3f-345">Add the final polish</span></span>

<span data-ttu-id="f9b3f-346">Sie haben es fast geschafft!</span><span class="sxs-lookup"><span data-stu-id="f9b3f-346">You're almost done.</span></span> <span data-ttu-id="f9b3f-347">Es gibt noch ein paar weitere Bedingungen, mit denen Ihr Analysetool umgehen muss.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-347">There are a few more conditions for your analyzer to handle.</span></span> <span data-ttu-id="f9b3f-348">Visual Studio ruft Analysetools auf, während der Benutzer Code schreibt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-348">Visual Studio calls analyzers while the user is writing code.</span></span> <span data-ttu-id="f9b3f-349">Es tritt häufig der Fall ein, dass Ihr Analysetool für Code aufgerufen wird, der sich nicht kompilieren lässt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-349">It's often the case that your analyzer will be called for code that doesn't compile.</span></span> <span data-ttu-id="f9b3f-350">Die Methode `AnalyzeNode` des Diagnoseanalysetools überprüft nicht, ob der Konstantenwert in den Variablentyp konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-350">The diagnostic analyzer's `AnalyzeNode` method does not check to see if the constant value is convertible to the variable type.</span></span> <span data-ttu-id="f9b3f-351">Daher konvertiert die aktuelle Implementierung eine falsche Deklaration wie int i = "abc"' unbedarft in eine lokale Konstante.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-351">So, the current implementation will happily convert an incorrect declaration such as int i = "abc"' to a local constant.</span></span> <span data-ttu-id="f9b3f-352">Fügen Sie für diese Bedingung eine Quellzeichenfolgenkonstante hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-352">Add a source string constant for that condition:</span></span>

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

<span data-ttu-id="f9b3f-353">Darüber hinaus werden Verweistypen nicht ordnungsgemäß behandelt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-353">In addition, reference types are not handled properly.</span></span> <span data-ttu-id="f9b3f-354">Der einzige Konstantenwert, die für einen Verweistyp zulässig ist, ist `null`, abgesehen von dem Fall <xref:System.String?displayProperty=nameWithType>, der Zeichenfolgenliterale zulässt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-354">The only constant value allowed for a reference type is `null`, except in this case of <xref:System.String?displayProperty=nameWithType>, which allows string literals.</span></span> <span data-ttu-id="f9b3f-355">Das heißt, `const string s = "abc"` ist zulässig, `const object s = "abc"` aber nicht.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-355">In other words, `const string s = "abc"` is legal, but `const object s = "abc"` is not.</span></span> <span data-ttu-id="f9b3f-356">Diese Bedingung wird mit diesem Codeausschnitt überprüft:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-356">This code snippet verifies that condition:</span></span>

[!code-csharp[Reference types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

<span data-ttu-id="f9b3f-357">Wenn Sie gründlich sein wollen, müssen Sie einen weiteren Test hinzufügen, um sicherzustellen, dass Sie für eine Zeichenfolge eine Konstantendeklaration erstellen können.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-357">To be thorough, you need to add another test to make sure that you can create a constant declaration for a string.</span></span> <span data-ttu-id="f9b3f-358">Der folgende Codeausschnitt definiert sowohl den Code, der die Diagnose auslöst, als auch den Code nach der Anwendung des Fixes:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-358">The following snippet defines both the code that raises the diagnostic, and the code after the fix has been applied:</span></span>

[!code-csharp[string reference types raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

<span data-ttu-id="f9b3f-359">Schließlich ergreift bei einer Variablen, die mit dem Schlüsselwort `var` deklariert ist, der Codefix die falsche Aktion und generiert eine `const var`-Deklaration, was von der Sprache C# nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-359">Finally, if a variable is declared with the `var` keyword, the code fix does the wrong thing and generates a `const var` declaration, which is not supported by the C# language.</span></span> <span data-ttu-id="f9b3f-360">Um diesen Fehler zu beheben, muss der Codefix das Schlüsselwort `var` durch den Namen des abgeleiteten Typs ersetzen:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-360">To fix this bug, the code fix must replace the `var` keyword with the inferred type's name:</span></span>

[!code-csharp[var references need to use the inferred types](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

<span data-ttu-id="f9b3f-361">Durch diese Änderungen werden die Datenzeilendeklarationen für beide Tests aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-361">These changes update the data row declarations for both tests.</span></span> <span data-ttu-id="f9b3f-362">Der folgende Code zeigt diese Tests mit allen Datenzeilenattributen:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-362">The following code shows these tests with all data row attributes:</span></span>

[!code-csharp[The finished tests](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

<span data-ttu-id="f9b3f-363">Glücklicherweise lassen sich alle oben aufgeführten Fehler mithilfe genau der Techniken beheben, die Sie gerade gelernt haben.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-363">Fortunately, all of the above bugs can be addressed using the same techniques that you just learned.</span></span>

<span data-ttu-id="f9b3f-364">Zum Beheben des ersten Fehlers öffnen Sie zuerst **DiagnosticAnalyzer.cs** und suchen die foreach-Schleife, in der jeder der Initialisierer der lokalen Deklaration überprüft wird, um sicherzustellen, dass allen konstante Werte zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-364">To fix the first bug, first open **DiagnosticAnalyzer.cs** and locate the foreach loop where each of the local declaration's initializers are checked to ensure that they're assigned with constant values.</span></span> <span data-ttu-id="f9b3f-365">Rufen Sie unmittelbar _vor_ der ersten foreach-Schleife `context.SemanticModel.GetTypeInfo()` auf, um Detailinformationen über den deklarierten Typ der lokalen Deklaration abzurufen:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-365">Immediately _before_ the first foreach loop, call `context.SemanticModel.GetTypeInfo()` to retrieve detailed information about the declared type of the local declaration:</span></span>

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

<span data-ttu-id="f9b3f-366">Überprüfen Sie anschließend innerhalb Ihrer `foreach`-Schleife jeden Initialisierer, um sicherzustellen, dass er in den Variablentyp konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-366">Then, inside your `foreach` loop, check each initializer to make sure it's convertible to the variable type.</span></span> <span data-ttu-id="f9b3f-367">Fügen Sie die folgende Überprüfung hinzu, nachdem sichergestellt wurde, dass der Initialisierer eine Konstante ist:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-367">Add the following check after ensuring that the initializer is a constant:</span></span>

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

<span data-ttu-id="f9b3f-368">Die nächste Änderung baut auf der letzten auf.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-368">The next change builds upon the last one.</span></span> <span data-ttu-id="f9b3f-369">Fügen Sie vor der schließenden geschweiften Klammer der ersten foreach-Schleife den folgenden Code hinzu, um den Typ der lokalen Deklaration zu überprüfen, wenn die Konstante eine Zeichenfolge oder NULL ist.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-369">Before the closing curly brace of the first foreach loop, add the following code to check the type of the local declaration when the constant is a string or null.</span></span>

```csharp
// Special cases:
//  * If the constant value is a string, the type of the local declaration
//    must be System.String.
//  * If the constant value is null, the type of the local declaration must
//    be a reference type.
if (constantValue.Value is string)
{
    if (variableType.SpecialType != SpecialType.System_String)
    {
        return;
    }
}
else if (variableType.IsReferenceType && constantValue.Value != null)
{
    return;
}
```

<span data-ttu-id="f9b3f-370">Sie müssen etwas mehr Code in Ihrem Codefixanbieter schreiben, um das Schlüsselwort `var` durch den korrekten Typnamen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-370">You must write a bit more code in your code fix provider to replace the `var` keyword with the correct type name.</span></span> <span data-ttu-id="f9b3f-371">Wechseln Sie zu **CodeFixProvider.cs** zurück.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-371">Return to **CodeFixProvider.cs**.</span></span> <span data-ttu-id="f9b3f-372">Der Code, den Sie hinzufügen, führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-372">The code you'll add does the following steps:</span></span>

- <span data-ttu-id="f9b3f-373">Überprüft, ob die Deklaration eine `var`-Deklaration ist, und wenn dies zutrifft:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-373">Check if the declaration is a `var` declaration, and if it is:</span></span>
- <span data-ttu-id="f9b3f-374">Erstellt einen neuen Typ für den abgeleiteten Typ.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-374">Create a new type for the inferred type.</span></span>
- <span data-ttu-id="f9b3f-375">Vergewissert sich, dass die Typdeklaration kein Alias ist.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-375">Make sure the type declaration is not an alias.</span></span> <span data-ttu-id="f9b3f-376">Ist das der Fall, ist eine Deklaration als `const var` zulässig.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-376">If so, it is legal to declare `const var`.</span></span>
- <span data-ttu-id="f9b3f-377">Stellt sicher, dass `var` kein Typname in diesem Programm ist.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-377">Make sure that `var` isn't a type name in this program.</span></span> <span data-ttu-id="f9b3f-378">(In dem Fall ist `const var` zulässig).</span><span class="sxs-lookup"><span data-stu-id="f9b3f-378">(If so, `const var` is legal).</span></span>
- <span data-ttu-id="f9b3f-379">Vereinfacht den vollständigen Typnamen</span><span class="sxs-lookup"><span data-stu-id="f9b3f-379">Simplify the full type name</span></span>

<span data-ttu-id="f9b3f-380">Das hört sich nach ziemlich viel Code an.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-380">That sounds like a lot of code.</span></span> <span data-ttu-id="f9b3f-381">Ist es aber nicht.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-381">It's not.</span></span> <span data-ttu-id="f9b3f-382">Ersetzen Sie die Zeile, in der `newLocal` deklariert und initialisiert wird, durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-382">Replace the line that declares and initializes `newLocal` with the following code.</span></span> <span data-ttu-id="f9b3f-383">Er gehört direkt hinter die Initialisierung von `newModifiers`:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-383">It goes immediately after the initialization of `newModifiers`:</span></span>

[!code-csharp[Replace Var designations](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

<span data-ttu-id="f9b3f-384">Sie müssen eine `using`-Anweisung hinzufügen, um den <xref:Microsoft.CodeAnalysis.Simplification.Simplifier>-Typ zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-384">You'll need to add one `using` directive to use the <xref:Microsoft.CodeAnalysis.Simplification.Simplifier> type:</span></span>

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

<span data-ttu-id="f9b3f-385">Führen Sie Ihre Tests aus – sie sollten alle bestanden werden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-385">Run your tests, and they should all pass.</span></span> <span data-ttu-id="f9b3f-386">Gratulieren Sie sich, indem Sie Ihr fertiges Analysetool ausführen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-386">Congratulate yourself by running your finished analyzer.</span></span> <span data-ttu-id="f9b3f-387">Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Analysetoolprojekt in einer zweiten Instanz von Visual Studio mit geladener Roslyn-Vorschauerweiterung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-387">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the analyzer project in a second instance of Visual Studio with the Roslyn Preview extension loaded.</span></span>

- <span data-ttu-id="f9b3f-388">Erstellen Sie in der zweiten Visual Studio-Instanz ein neues C#-Konsolenanwendungsprojekt, und fügen Sie `int x = "abc";` zur Methode „Main“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-388">In the second Visual Studio instance, create a new C# Console Application project and add `int x = "abc";` to the Main method.</span></span> <span data-ttu-id="f9b3f-389">Dank der ersten Fehlerbehebung sollte keine Warnung für diese lokale Variablendeklaration gemeldet werden (obwohl es erwartungsgemäß einen Compilerfehler gibt).</span><span class="sxs-lookup"><span data-stu-id="f9b3f-389">Thanks to the first bug fix, no warning should be reported for this local variable declaration (though there's a compiler error as expected).</span></span>
- <span data-ttu-id="f9b3f-390">Fügen Sie als Nächstes `object s = "abc";` zur Methode „Main“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-390">Next, add `object s = "abc";` to the Main method.</span></span> <span data-ttu-id="f9b3f-391">Aufgrund der zweiten Fehlerbehebung sollte keine Warnung gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-391">Because of the second bug fix, no warning should be reported.</span></span>
- <span data-ttu-id="f9b3f-392">Fügen Sie schließlich eine weitere lokale Variable hinzu, die das Schlüsselwort `var` verwendet.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-392">Finally, add another local variable that uses the `var` keyword.</span></span> <span data-ttu-id="f9b3f-393">Sie sehen, dass eine Warnung gemeldet und ein Vorschlag links unterhalb der Meldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-393">You'll see that a warning is reported and a suggestion appears beneath to the left.</span></span>
- <span data-ttu-id="f9b3f-394">Bewegen Sie den Textcursor des Editors über die Wellenlinien-Unterstreichung, und drücken Sie <kbd>STRG</kbd>+<kbd>.</kbd>,</span><span class="sxs-lookup"><span data-stu-id="f9b3f-394">Move the editor caret over the squiggly underline and press <kbd>Ctrl</kbd>+<kbd>.</kbd>.</span></span> <span data-ttu-id="f9b3f-395">um den vorgeschlagenen Codefix anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-395">to display the suggested code fix.</span></span> <span data-ttu-id="f9b3f-396">Beachten Sie beim Auswählen des Codefixes, dass das Schlüsselwort `var` jetzt ordnungsgemäß verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-396">Upon selecting your code fix, note that the `var` keyword is now handled correctly.</span></span>

<span data-ttu-id="f9b3f-397">Fügen Sie schließlich den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="f9b3f-397">Finally, add the following code:</span></span>

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

<span data-ttu-id="f9b3f-398">Nach diesen Änderungen erhalten Sie rote Wellenlinien nur unter den ersten zwei Variablen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-398">After these changes, you get red squiggles only on the first two variables.</span></span> <span data-ttu-id="f9b3f-399">Fügen Sie `const` sowohl zu `i` als auch zu `j` hinzu, und Sie erhalten eine neue Warnung zu `k`, da das nun als `const` deklariert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-399">Add `const` to both `i` and `j`, and you get a new warning on `k` because it can now be `const`.</span></span>

<span data-ttu-id="f9b3f-400">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="f9b3f-400">Congratulations!</span></span> <span data-ttu-id="f9b3f-401">Sie haben Ihre erste Erweiterung für die .NET Compiler Platform erstellt, die dynamische Codeanalyse durchführt, um ein Problem zu erkennen, und eine schnelle Problembehebung zu seiner Korrektur bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-401">You've created your first .NET Compiler Platform extension that performs on-the-fly code analysis to detect an issue and provides a quick fix to correct it.</span></span> <span data-ttu-id="f9b3f-402">Auf diesem Weg haben Sie viele der Code-APIs kennengelernt, die Teil der .NET Compiler Platform SDKs sind (Roslyn-APIs).</span><span class="sxs-lookup"><span data-stu-id="f9b3f-402">Along the way, you've learned many of the code APIs that are part of the .NET Compiler Platform SDK (Roslyn APIs).</span></span> <span data-ttu-id="f9b3f-403">Sie können Ihre Arbeit anhand des [fertiggestellten Beispiels](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) in unserem GitHub-Beispielrepository überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f9b3f-403">You can check your work against the [completed sample](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) in our samples GitHub repository.</span></span>

## <a name="other-resources"></a><span data-ttu-id="f9b3f-404">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f9b3f-404">Other resources</span></span>

- [<span data-ttu-id="f9b3f-405">Erste Schritte mit der Syntaxanalyse</span><span class="sxs-lookup"><span data-stu-id="f9b3f-405">Get started with syntax analysis</span></span>](../get-started/syntax-analysis.md)
- [<span data-ttu-id="f9b3f-406">Erste Schritte mit der semantischen Analyse</span><span class="sxs-lookup"><span data-stu-id="f9b3f-406">Get started with semantic analysis</span></span>](../get-started/semantic-analysis.md)
