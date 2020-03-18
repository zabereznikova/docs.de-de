---
title: 'Tutorial: Schreiben Ihres ersten Analysetools und Codefixes'
description: Dieses Tutorial enthält Schritt-für-Schritt-Anleitungen zum Erstellen eines Analysetools und eines Codefixes mithilfe des .NET Compiler SDK (Roslyn-APIs).
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: f6fc21c010f9b5fcd5e709ef822639c020a7c93b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240549"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a><span data-ttu-id="b01f1-103">Tutorial: Schreiben Ihres ersten Analysetools und Codefixes</span><span class="sxs-lookup"><span data-stu-id="b01f1-103">Tutorial: Write your first analyzer and code fix</span></span>

<span data-ttu-id="b01f1-104">Das .NET Compiler Platform SDK stellt die Tools zur Verfügung, die Sie zum Erstellen von benutzerdefinierten Warnungen mit C#- oder Visual Basic-Code als Ziel benötigen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-104">The .NET Compiler Platform SDK provides the tools you need to create custom warnings that target C# or Visual Basic code.</span></span> <span data-ttu-id="b01f1-105">Ihr **Analysetool** enthält Code, der Verstöße gegen Ihre Regel erkennt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-105">Your **analyzer** contains code that recognizes violations of your rule.</span></span> <span data-ttu-id="b01f1-106">Ihr **Codefix** enthält den Code, der den Verstoß behebt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-106">Your **code fix** contains the code that fixes the violation.</span></span> <span data-ttu-id="b01f1-107">Die Regeln, die Sie implementieren, können sich auf alles Mögliche beziehen, von der Codestruktur über das Codeformat bis zu Benennungskonventionen usw.</span><span class="sxs-lookup"><span data-stu-id="b01f1-107">The rules you implement can be anything from code structure to coding style to naming conventions and more.</span></span> <span data-ttu-id="b01f1-108">Die .NET Compiler Platform stellt das Framework zum Ausführen der Analyse bereit, während die Entwickler Code schreiben, mit allen Features der Visual Studio-Benutzeroberfläche für das Beheben von Codeproblemen: Anzeigen von Wellenlinien im Editor, Auffüllen der Fehlerliste von Visual Studio, Erstellen der "Glühbirnen"-Vorschläge und Darstellung der umfassenden Vorschau vorgeschlagener Fixe.</span><span class="sxs-lookup"><span data-stu-id="b01f1-108">The .NET Compiler Platform provides the framework for running analysis as developers are writing code, and all the Visual Studio UI features for fixing code: showing squiggles in the editor, populating the Visual Studio Error List, creating the "light bulb" suggestions and showing the rich preview of the suggested fixes.</span></span>

<span data-ttu-id="b01f1-109">In diesem Tutorial lernen Sie die Erstellung eines **Analysetools** und eines begleitenden **Codefixes** unter Verwendung der Roslyn-APIs kennen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-109">In this tutorial, you'll explore the creation of an **analyzer** and an accompanying **code fix** using the Roslyn APIs.</span></span> <span data-ttu-id="b01f1-110">Ein Analysetool ist eine Möglichkeit, Quellcodeanalyse auszuführen und dem Benutzer ein Problem zu melden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-110">An analyzer is a way to perform source code analysis and report a problem to the user.</span></span> <span data-ttu-id="b01f1-111">Optional kann ein Analysetool auch einen Codefix bereitstellen, der eine Änderung am Quellcode des Benutzers darstellt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-111">Optionally, an analyzer can also provide a code fix that represents a modification to the user's source code.</span></span> <span data-ttu-id="b01f1-112">In diesem Tutorial wird ein Analysetool erstellt, das Deklarationen von lokalen Variablen enthält, die mithilfe des `const`-Modifizierers deklariert werden könnten, es aber nicht sind.</span><span class="sxs-lookup"><span data-stu-id="b01f1-112">This tutorial creates an analyzer that finds local variable declarations that could be declared using the `const` modifier but are not.</span></span> <span data-ttu-id="b01f1-113">Der begleitende Codefix ändert diese Deklarationen, indem er den `const`-Modifizierer hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-113">The accompanying code fix modifies those declarations to add the `const` modifier.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b01f1-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b01f1-114">Prerequisites</span></span>

- [<span data-ttu-id="b01f1-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="b01f1-115">Visual Studio 2017</span></span>](https://visualstudio.microsoft.com/vs/older-downloads/#visual-studio-2017-and-other-products)
- [<span data-ttu-id="b01f1-116">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="b01f1-116">Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads)

<span data-ttu-id="b01f1-117">Installieren Sie zunächst über den Visual Studio-Installer das **SDK für die .NET Compiler Platform**:</span><span class="sxs-lookup"><span data-stu-id="b01f1-117">You'll need to install the **.NET Compiler Platform SDK** via the Visual Studio Installer:</span></span>

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<span data-ttu-id="b01f1-118">Das Erstellen und Überprüfen Ihres Analysetools erfolgt in mehreren Schritten:</span><span class="sxs-lookup"><span data-stu-id="b01f1-118">There are several steps to creating and validating your analyzer:</span></span>

1. <span data-ttu-id="b01f1-119">Erstellen der Projektmappe</span><span class="sxs-lookup"><span data-stu-id="b01f1-119">Create the solution.</span></span>
1. <span data-ttu-id="b01f1-120">Registrieren von Name und Beschreibung des Analysetools</span><span class="sxs-lookup"><span data-stu-id="b01f1-120">Register the analyzer name and description.</span></span>
1. <span data-ttu-id="b01f1-121">Melden von Warnungen und Empfehlungen des Analysetools</span><span class="sxs-lookup"><span data-stu-id="b01f1-121">Report analyzer warnings and recommendations.</span></span>
1. <span data-ttu-id="b01f1-122">Implementieren des Codefixes zum Übernehmen der Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="b01f1-122">Implement the code fix to accept recommendations.</span></span>
1. <span data-ttu-id="b01f1-123">Verbessern der Analyse durch Komponententests</span><span class="sxs-lookup"><span data-stu-id="b01f1-123">Improve the analysis through unit tests.</span></span>

## <a name="explore-the-analyzer-template"></a><span data-ttu-id="b01f1-124">Kennenlernen der Vorlage für das Analysetool</span><span class="sxs-lookup"><span data-stu-id="b01f1-124">Explore the analyzer template</span></span>

<span data-ttu-id="b01f1-125">Ihr Analysetool meldet dem Benutzer alle lokalen Variablendeklarationen, die in lokale Konstanten konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="b01f1-125">Your analyzer reports to the user any local variable declarations that can be converted to local constants.</span></span> <span data-ttu-id="b01f1-126">Beachten Sie z. B. folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="b01f1-126">For example, consider the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="b01f1-127">Im Code oben ist `x` ein konstanter Wert zugewiesen, der nie geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b01f1-127">In the code above, `x` is assigned a constant value and is never modified.</span></span> <span data-ttu-id="b01f1-128">Er kann mithilfe des `const`-Modifizierers deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="b01f1-128">It can be declared using the `const` modifier:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="b01f1-129">Dies bringt die Analyse mit sich, mit der bestimmt wird, ob eine Variable zu einer Konstanten gemacht werden kann, wozu Syntaxanalyse, Konstantenanalyse des Initialisiererausdrucks und eine Datenflussanalyse erforderlich sind, um sicherzustellen, dass zu keinem Zeitpunkt in die Variable geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="b01f1-129">The analysis to determine whether a variable can be made constant is involved, requiring syntactic analysis, constant analysis of the initializer expression and dataflow analysis to ensure that the variable is never written to.</span></span> <span data-ttu-id="b01f1-130">Die .NET Compiler Platform stellt APIs zur Verfügung, die das Durchführen dieser Analyse erleichtern.</span><span class="sxs-lookup"><span data-stu-id="b01f1-130">The .NET Compiler Platform provides APIs that make it easier to perform this analysis.</span></span> <span data-ttu-id="b01f1-131">Der erste Schritt ist die Erstellung eines neuen C#-Projekts **Analysetool mit Codefix**.</span><span class="sxs-lookup"><span data-stu-id="b01f1-131">The first step is to create a new C# **Analyzer with code fix** project.</span></span>

- <span data-ttu-id="b01f1-132">Wählen Sie in Visual Studio **Datei > Neu > Projekt...** aus, um das Dialogfeld „Neues Projekt“ anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-132">In Visual Studio, choose **File > New > Project...** to display the New Project dialog.</span></span>
- <span data-ttu-id="b01f1-133">Wählen Sie unter **Visual C# > Erweiterbarkeit** **Analyzer with code fix (.NET Standard)** (Analysetool mit Codefix (.NET Standard)) aus.</span><span class="sxs-lookup"><span data-stu-id="b01f1-133">Under **Visual C# > Extensibility**, choose **Analyzer with code fix (.NET Standard)**.</span></span>
- <span data-ttu-id="b01f1-134">Benennen Sie Ihr Projekt "**MakeConst**", und klicken Sie auf „OK“.</span><span class="sxs-lookup"><span data-stu-id="b01f1-134">Name your project "**MakeConst**" and click OK.</span></span>

<span data-ttu-id="b01f1-135">Die Vorlage für das Analysetool mit Codefix erstellt drei Projekte: Das erste enthält das Analysetool und den Codefix, das zweite ist ein Komponententestprojekt, und das dritte ist das VSIX-Projekt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-135">The analyzer with code fix template creates three projects: one contains the analyzer and code fix, the second is a unit test project, and the third is the VSIX project.</span></span> <span data-ttu-id="b01f1-136">Das Standardstartprojekt ist das VSIX-Projekt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-136">The default startup project is the VSIX project.</span></span> <span data-ttu-id="b01f1-137">Drücken Sie **F5**, um das VSIX-Projekt zu starten.</span><span class="sxs-lookup"><span data-stu-id="b01f1-137">Press **F5** to start the VSIX project.</span></span> <span data-ttu-id="b01f1-138">Dadurch wird eine zweite Instanz von Visual Studio mit geladenem neuem Analysemodul gestartet.</span><span class="sxs-lookup"><span data-stu-id="b01f1-138">This starts a second instance of Visual Studio that has loaded your new analyzer.</span></span>

> [!TIP]
> <span data-ttu-id="b01f1-139">Wenn Sie das Analysetool ausführen, wird eine zweite Instanz von Visual Studio gestartet.</span><span class="sxs-lookup"><span data-stu-id="b01f1-139">When you run your analyzer, you start a second copy of Visual Studio.</span></span> <span data-ttu-id="b01f1-140">Diese zweite Kopie verwendet eine andere Registrierungsstruktur zum Speichern von Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-140">This second copy uses a different registry hive to store settings.</span></span> <span data-ttu-id="b01f1-141">Dadurch können Sie in beiden Instanzen von Visual Studio verschiedene Anzeigeeinstellungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-141">That enables you to differentiate the visual settings in the two copies of Visual Studio.</span></span> <span data-ttu-id="b01f1-142">Sie können für die Testinstanz von Visual Studio ein anderes Design auswählen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-142">You can pick a different theme for the experimental run of Visual Studio.</span></span> <span data-ttu-id="b01f1-143">Achten Sie außerdem darauf, Ihre Einstellungen oder Ihre Anmeldung nicht mithilfe der Testinstanz von Visual Studio als mobiler Benutzer auf Ihr Visual Studio-Konto zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-143">In addition, don't roam your settings or login to your Visual Studio account using the experimental run of Visual Studio.</span></span> <span data-ttu-id="b01f1-144">Auf diese Weise bleiben die unterschiedlichen Einstellungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="b01f1-144">That keeps the settings different.</span></span>

<span data-ttu-id="b01f1-145">Erstellen Sie in der zweiten Visual Studio-Instanz, die Sie gerade gestartet haben, ein neues Projekt für eine C#-Konsolenanwendung (wahlweise ein .NET Core- oder ein .NET Framework-Projekt – Analysetools arbeiten auf Quellebene.) Zeigen Sie auf das wellenförmig unterstrichene Token, dann wird der von einem Analysetool bereitgestellte Warnungstext angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-145">In the second Visual Studio instance that you just started, create a new C# Console Application project (either .NET Core or .NET Framework project will work -- analyzers work at the source level.) Hover over the token with a wavy underline, and the warning text provided by an analyzer appears.</span></span>

<span data-ttu-id="b01f1-146">Die Vorlage erstellt ein Analysetool, das für jede Typdeklaration, deren Typname Kleinbuchstaben enthält, eine Warnung meldet, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="b01f1-146">The template creates an analyzer that reports a warning on each type declaration where the type name contains lowercase letters, as shown in the following figure:</span></span>

![Analysetool beim Melden einer Warnung](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

<span data-ttu-id="b01f1-148">Die Vorlage stellt darüber hinaus einen Codefix bereit, der jeden Typnamen, der Kleinbuchstaben enthält, in durchgängig Großbuchstaben ändert.</span><span class="sxs-lookup"><span data-stu-id="b01f1-148">The template also provides a code fix that changes any type name containing lower case characters to all upper case.</span></span> <span data-ttu-id="b01f1-149">Sie können auf die zusammen mit der Warnung angezeigte Glühbirne klicken, um die vorgeschlagenen Änderungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-149">You can click on the light bulb displayed with the warning to see the suggested changes.</span></span> <span data-ttu-id="b01f1-150">Wenn Sie die vorgeschlagenen Änderungen akzeptieren, werden der Typname und alle Verweise auf den betreffenden Typ in der Projektmappe aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b01f1-150">Accepting the suggested changes updates the type name and all references to that type in the solution.</span></span> <span data-ttu-id="b01f1-151">Nachdem Sie jetzt das anfängliche Analysetool in Aktion gesehen haben, schließen Sie die zweite Visual Studio-Instanz, und kehren Sie zu Ihrem Analysetoolprojekt zurück.</span><span class="sxs-lookup"><span data-stu-id="b01f1-151">Now that you've seen the initial analyzer in action, close the second Visual Studio instance and return to your analyzer project.</span></span>

<span data-ttu-id="b01f1-152">Sie brauchen keine zweite Instanz von Visual Studio zu starten und neuen Code zu erstellen, um jede Änderung an Ihrem Analysetool zu testen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-152">You don't have to start a second copy of Visual Studio and create new code to test every change in your analyzer.</span></span> <span data-ttu-id="b01f1-153">Die Vorlage erstellt für Sie außerdem ein Komponententestprojekt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-153">The template also creates a unit test project for you.</span></span> <span data-ttu-id="b01f1-154">Dieses Projekt enthält zwei Tests.</span><span class="sxs-lookup"><span data-stu-id="b01f1-154">That project contains two tests.</span></span> <span data-ttu-id="b01f1-155">`TestMethod1` zeigt das typische Format eines Tests, der Code analysiert, ohne eine Diagnose auszulösen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-155">`TestMethod1` shows the typical format of a test that analyzes code without triggering a diagnostic.</span></span> <span data-ttu-id="b01f1-156">`TestMethod2` zeigt das Format eines Tests, der eine Diagnose auslöst und dann einen vorgeschlagenen Codefix anwendet.</span><span class="sxs-lookup"><span data-stu-id="b01f1-156">`TestMethod2` shows the format of a test that triggers a diagnostic, and then applies a suggested code fix.</span></span> <span data-ttu-id="b01f1-157">Beim Erstellen Ihres Analysetools und Codefixes werden Sie Tests für verschiedene Codestrukturen schreiben, um Ihre Arbeit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-157">As you build your analyzer and code fix, you'll write tests for different code structures to verify your work.</span></span> <span data-ttu-id="b01f1-158">Komponententests für Analysetools sind viel schneller als interaktive Tests in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b01f1-158">Unit tests for analyzers are much quicker than testing them interactively with Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="b01f1-159">Analysetool-Komponententests sind ein hervorragendes Werkzeug, wenn Sie wissen, welche Codekonstrukte Ihr Analysetool auslösen sollten und welche nicht.</span><span class="sxs-lookup"><span data-stu-id="b01f1-159">Analyzer unit tests are a great tool when you know what code constructs should and shouldn't trigger your analyzer.</span></span> <span data-ttu-id="b01f1-160">Das Laden Ihres Analysetools in einer weiteren Visual Studio-Instanz ist ein tolles Hilfsmittel, um Konstrukte zu finden und zu untersuchen, die Ihnen möglicherweise noch nicht in den Sinn gekommen sind.</span><span class="sxs-lookup"><span data-stu-id="b01f1-160">Loading your analyzer in another copy of Visual Studio is a great tool to explore and find constructs you may not have thought about yet.</span></span>

## <a name="create-analyzer-registrations"></a><span data-ttu-id="b01f1-161">Erstellen von Analysetoolregistrierungen</span><span class="sxs-lookup"><span data-stu-id="b01f1-161">Create analyzer registrations</span></span>

<span data-ttu-id="b01f1-162">Die Vorlage erstellt die anfängliche `DiagnosticAnalyzer`-Klasse in der Datei **MakeConstAnalyzer.cs**.</span><span class="sxs-lookup"><span data-stu-id="b01f1-162">The template creates the initial `DiagnosticAnalyzer` class, in the **MakeConstAnalyzer.cs** file.</span></span> <span data-ttu-id="b01f1-163">Dieses anfängliche Analysetool zeigt zwei wichtige Eigenschaften jedes Analysetools.</span><span class="sxs-lookup"><span data-stu-id="b01f1-163">This initial analyzer shows two important properties of every analyzer.</span></span>

- <span data-ttu-id="b01f1-164">Jedes Diagnoseanalysetool muss ein `[DiagnosticAnalyzer]`-Attribut bereitstellen, das die Sprache beschreibt, in der es arbeitet.</span><span class="sxs-lookup"><span data-stu-id="b01f1-164">Every diagnostic analyzer must provide a `[DiagnosticAnalyzer]` attribute that describes the language it operates on.</span></span>
- <span data-ttu-id="b01f1-165">Jedes Diagnoseanalysetool muss aus der <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer>-Klasse abgeleitet sein.</span><span class="sxs-lookup"><span data-stu-id="b01f1-165">Every diagnostic analyzer must derive from the <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer> class.</span></span>

<span data-ttu-id="b01f1-166">Die Vorlage zeigt außerdem die grundlegenden Features, die jedes Analysetool auszeichnen:</span><span class="sxs-lookup"><span data-stu-id="b01f1-166">The template also shows the basic features that are part of any analyzer:</span></span>

1. <span data-ttu-id="b01f1-167">Registrieren von Aktionen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-167">Register actions.</span></span> <span data-ttu-id="b01f1-168">Die Aktionen stellen Codeänderungen dar, die Ihr Analysetool auslösen sollten, um den Code auf Verstöße hin zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-168">The actions represent code changes that should trigger your analyzer to examine code for violations.</span></span> <span data-ttu-id="b01f1-169">Wenn Visual Studio Codebearbeitungen erkennt, die mit einer registrierten Aktion übereinstimmen, ruft es die registrierte Methode Ihres Analysetools auf.</span><span class="sxs-lookup"><span data-stu-id="b01f1-169">When Visual Studio detects code edits that match a registered action, it calls your analyzer's registered method.</span></span>
1. <span data-ttu-id="b01f1-170">Erstellen von Diagnosen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-170">Create diagnostics.</span></span> <span data-ttu-id="b01f1-171">Wenn Ihr Analysemodul einen Verstoß erkennt, erstellt es ein Diagnoseobjekt, das von Visual Studio verwendet wird, um den Benutzer vom Verstoß zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-171">When your analyzer detects a violation, it creates a diagnostic object that Visual Studio uses to notify the user of the violation.</span></span>

<span data-ttu-id="b01f1-172">Sie registrieren Aktionen in Ihrer Überschreibung der <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="b01f1-172">You register actions in your override of <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b01f1-173">In diesem Tutorial suchen Sie auf der Suche nach lokalen Deklarationen **Syntaxknoten** auf und sehen, welche von ihnen konstante Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-173">In this tutorial, you'll visit **syntax nodes** looking for local declarations, and see which of those have constant values.</span></span> <span data-ttu-id="b01f1-174">Wenn eine Deklaration eine Konstante vorsehen könnte, erstellt und meldet Ihr Analysetool eine Diagnose.</span><span class="sxs-lookup"><span data-stu-id="b01f1-174">If a declaration could be constant, your analyzer will create and report a diagnostic.</span></span>

<span data-ttu-id="b01f1-175">Der erste Schritt besteht darin, die Registrierungskonstanten und die `Initialize`-Methode zu aktualisieren, damit diese Konstanten Ihr „Make Const“-Analysetool anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-175">The first step is to update the registration constants and `Initialize` method so these constants indicate your "Make Const" analyzer.</span></span> <span data-ttu-id="b01f1-176">Die meisten der Zeichenfolgenkonstanten sind in der Zeichenfolgen-Ressourcendatei definiert.</span><span class="sxs-lookup"><span data-stu-id="b01f1-176">Most of the string constants are defined in the string resource file.</span></span> <span data-ttu-id="b01f1-177">Sie sollten sich zwecks einfacherer Lokalisierung auch an diese Praxis halten.</span><span class="sxs-lookup"><span data-stu-id="b01f1-177">You should follow that practice for easier localization.</span></span> <span data-ttu-id="b01f1-178">Öffnen Sie die **Resources.resx**-Datei für das **MakeConst**-Analysetoolprojekt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-178">Open the **Resources.resx** file for the **MakeConst** analyzer project.</span></span> <span data-ttu-id="b01f1-179">Dadurch wird der Ressourcen-Editor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-179">This displays the resource editor.</span></span> <span data-ttu-id="b01f1-180">Aktualisieren Sie die Zeichenfolgenressourcen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b01f1-180">Update the string resources as follows:</span></span>

- <span data-ttu-id="b01f1-181">Ändern Sie `AnalyzerTitle` in „Variable kann als Konstante umdeklariert werden“.</span><span class="sxs-lookup"><span data-stu-id="b01f1-181">Change `AnalyzerTitle` to "Variable can be made constant".</span></span>
- <span data-ttu-id="b01f1-182">Ändern Sie `AnalyzerMessageFormat` in „Kann als Konstante deklariert werden“.</span><span class="sxs-lookup"><span data-stu-id="b01f1-182">Change `AnalyzerMessageFormat` to "Can be made constant".</span></span>
- <span data-ttu-id="b01f1-183">Ändern Sie `AnalyzerDescription` in „Als Konstante deklarieren“.</span><span class="sxs-lookup"><span data-stu-id="b01f1-183">Change `AnalyzerDescription` to "Make Constant".</span></span>

<span data-ttu-id="b01f1-184">Ändern Sie außerdem die **Zugriffsmodifizierer**-Dropdownliste in `public`.</span><span class="sxs-lookup"><span data-stu-id="b01f1-184">Also, change the **Access Modifier** drop-down to `public`.</span></span> <span data-ttu-id="b01f1-185">Das vereinfacht die Verwendung dieser Konstanten in Komponententests.</span><span class="sxs-lookup"><span data-stu-id="b01f1-185">That makes it easier to use these constants in unit tests.</span></span> <span data-ttu-id="b01f1-186">Wenn Sie fertig sind, sollte der Ressourcen-Editor wie in der folgenden Abbildung aussehen:</span><span class="sxs-lookup"><span data-stu-id="b01f1-186">When you have finished, the resource editor should appear as follow figure shows:</span></span>

![Zeichenfolgenressourcen aktualisieren](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

<span data-ttu-id="b01f1-188">Die verbleibenden Änderungen finden sich in der Analysetooldatei.</span><span class="sxs-lookup"><span data-stu-id="b01f1-188">The remaining changes are in the analyzer file.</span></span> <span data-ttu-id="b01f1-189">Öffnen Sie **MakeConstAnalyzer.cs** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b01f1-189">Open **MakeConstAnalyzer.cs** in Visual Studio.</span></span> <span data-ttu-id="b01f1-190">Ändern Sie die registrierte Aktion von einer Aktion, die für Symbole aktiv ist, in eine, die mit Syntax agiert.</span><span class="sxs-lookup"><span data-stu-id="b01f1-190">Change the registered action from one that acts on symbols to one that acts on syntax.</span></span> <span data-ttu-id="b01f1-191">Suchen Sie in der `MakeConstAnalyzerAnalyzer.Initialize`-Methode die Zeile, die die Aktion für Symbole registriert:</span><span class="sxs-lookup"><span data-stu-id="b01f1-191">In the `MakeConstAnalyzerAnalyzer.Initialize` method, find the line that registers the action on symbols:</span></span>

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

<span data-ttu-id="b01f1-192">Ersetzen Sie sie durch die folgende Zeile:</span><span class="sxs-lookup"><span data-stu-id="b01f1-192">Replace it with the following line:</span></span>

[!code-csharp[Register the node action](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

<span data-ttu-id="b01f1-193">Nach dieser Änderung können Sie die `AnalyzeSymbol`-Methode löschen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-193">After that change, you can delete the `AnalyzeSymbol` method.</span></span> <span data-ttu-id="b01f1-194">Dieses Analysetool untersucht <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>-Anweisungen, keine <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType>-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-194">This analyzer examines <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, not <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType> statements.</span></span> <span data-ttu-id="b01f1-195">Beachten Sie, dass `AnalyzeNode` mit roten Wellenlinien unterstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="b01f1-195">Notice that `AnalyzeNode` has red squiggles under it.</span></span> <span data-ttu-id="b01f1-196">Der Code, den Sie soeben hinzugefügt haben, verweist auf eine `AnalyzeNode`-Methode, die noch nicht deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="b01f1-196">The code you just added references an `AnalyzeNode` method that hasn't been declared.</span></span> <span data-ttu-id="b01f1-197">Deklarieren Sie diese Methode mithilfe des folgenden Codes:</span><span class="sxs-lookup"><span data-stu-id="b01f1-197">Declare that method using the following code:</span></span>

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

<span data-ttu-id="b01f1-198">Ändern Sie in **MakeConstAnalyzer.cs** die `Category` in „Usage“, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b01f1-198">Change the `Category` to "Usage" in **MakeConstAnalyzer.cs** as shown in the following code:</span></span>

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a><span data-ttu-id="b01f1-199">Suchen von lokalen Deklarationen, die „const“ lauten könnten</span><span class="sxs-lookup"><span data-stu-id="b01f1-199">Find local declarations that could be const</span></span>

<span data-ttu-id="b01f1-200">Es ist Zeit, die erste Version der `AnalyzeNode`-Methode zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="b01f1-200">It's time to write the first version of the `AnalyzeNode` method.</span></span> <span data-ttu-id="b01f1-201">Sie soll nach einer einzelnen lokalen Deklaration suchen, die `const` sein könnte, es aber nicht ist, wie der folgende Code:</span><span class="sxs-lookup"><span data-stu-id="b01f1-201">It should look for a single local declaration that could be `const` but is not, like the following code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="b01f1-202">Der erste Schritt besteht darin, nach lokalen Deklarationen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-202">The first step is to find local declarations.</span></span> <span data-ttu-id="b01f1-203">Fügen Sie in **MakeConstAnalyzer.cs** den folgenden Code zu `AnalyzeNode` hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-203">Add the following code to `AnalyzeNode` in **MakeConstAnalyzer.cs**:</span></span>

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

<span data-ttu-id="b01f1-204">Diese Umwandlung funktioniert immer, da Ihr Analysetool für Änderungen an lokalen Deklarationen und nur an lokalen Deklarationen registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="b01f1-204">This cast always succeeds because your analyzer registered for changes to local declarations, and only local declarations.</span></span> <span data-ttu-id="b01f1-205">Kein anderer Knotentyp löst einen Aufruf Ihrer `AnalyzeNode`-Methode aus.</span><span class="sxs-lookup"><span data-stu-id="b01f1-205">No other node type triggers a call to your `AnalyzeNode` method.</span></span> <span data-ttu-id="b01f1-206">Überprüfen Sie als Nächstes die Deklaration für alle `const`-Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="b01f1-206">Next, check the declaration for any `const` modifiers.</span></span> <span data-ttu-id="b01f1-207">Wenn Sie sie finden, geben Sie sofort zurück.</span><span class="sxs-lookup"><span data-stu-id="b01f1-207">If you find them, return immediately.</span></span> <span data-ttu-id="b01f1-208">Der folgende Code sucht nach allen `const`-Modifizierern in der lokalen Deklaration:</span><span class="sxs-lookup"><span data-stu-id="b01f1-208">The following code looks for any `const` modifiers on the local declaration:</span></span>

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

<span data-ttu-id="b01f1-209">Schließlich müssen Sie überprüfen, ob die Variable `const` sein könnte.</span><span class="sxs-lookup"><span data-stu-id="b01f1-209">Finally, you need to check that the variable could be `const`.</span></span> <span data-ttu-id="b01f1-210">Das bedeutet, sicherzustellen, dass sie nach der Initialisierung nie zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b01f1-210">That means making sure it is never assigned after it is initialized.</span></span>

<span data-ttu-id="b01f1-211">Sie führen semantische Analysen mithilfe von <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext> durch.</span><span class="sxs-lookup"><span data-stu-id="b01f1-211">You'll perform some semantic analysis using the <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>.</span></span> <span data-ttu-id="b01f1-212">Sie verwenden das `context`-Argument, um festzustellen, ob die lokale Variablendeklaration als `const` festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b01f1-212">You use the `context` argument to determine whether the local variable declaration can be made `const`.</span></span> <span data-ttu-id="b01f1-213">Ein <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> stellt sämtliche semantischen Informationen in einer einzelnen Quelldatei dar.</span><span class="sxs-lookup"><span data-stu-id="b01f1-213">A <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> represents of all semantic information in a single source file.</span></span> <span data-ttu-id="b01f1-214">Mehr können Sie im Artikel über [semantische Modelle](../work-with-semantics.md) erfahren.</span><span class="sxs-lookup"><span data-stu-id="b01f1-214">You can learn more in the article that covers [semantic models](../work-with-semantics.md).</span></span> <span data-ttu-id="b01f1-215">Sie verwenden das <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> zum Durchführen einer Datenflussanalyse für die lokale Deklarationsanweisung.</span><span class="sxs-lookup"><span data-stu-id="b01f1-215">You'll use the <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> to perform data flow analysis on the local declaration statement.</span></span> <span data-ttu-id="b01f1-216">Anschließend nutzen Sie die Ergebnisse dieser Datenflussanalyse, um sicherzustellen, dass zu keiner Zeit irgendwo ein neuer Wert in die lokale Variable geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="b01f1-216">Then, you use the results of this data flow analysis to ensure that the local variable isn't written with a new value anywhere else.</span></span> <span data-ttu-id="b01f1-217">Rufen Sie die <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A>-Erweiterungsmethode auf, um das <xref:Microsoft.CodeAnalysis.ILocalSymbol> für die Variable abzurufen und zu sicherzustellen, dass sie nicht in der <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType>-Sammlung der Datenflussanalyse enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b01f1-217">Call the <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> extension method to retrieve the <xref:Microsoft.CodeAnalysis.ILocalSymbol> for the variable and check that it isn't contained with the <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> collection of the data flow analysis.</span></span> <span data-ttu-id="b01f1-218">Fügen Sie am Ende der `AnalyzeNode`-Methode den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-218">Add the following code to the end of the `AnalyzeNode` method:</span></span>

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

<span data-ttu-id="b01f1-219">Der Code, den Sie soeben hinzugefügt haben, stellt sicher, dass die Variable nicht verändert wird und daher als `const` deklariert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b01f1-219">The code just added ensures that the variable isn't modified, and can therefore be made `const`.</span></span> <span data-ttu-id="b01f1-220">Es ist Zeit, die Diagnose zu stellen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-220">It's time to raise the diagnostic.</span></span> <span data-ttu-id="b01f1-221">Fügen Sie in `AnalyzeNode` den folgenden Code als letzte Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-221">Add the following code as the last line in `AnalyzeNode`:</span></span>

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

<span data-ttu-id="b01f1-222">Sie können Ihren Fortschritt überprüfen, indem Sie **F5** drücken, um Ihr Analysetool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-222">You can check your progress by pressing **F5** to run your analyzer.</span></span> <span data-ttu-id="b01f1-223">Sie können die Konsolenanwendung laden, die Sie zuvor erstellt haben, und dann den folgenden Testcode hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b01f1-223">You can load the console application you created earlier and then add the following test code:</span></span>

```csharp
int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="b01f1-224">Die Glühbirne sollte angezeigt werden, und Ihr Analysetool sollte eine Diagnose melden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-224">The light bulb should appear, and your analyzer should report a diagnostic.</span></span> <span data-ttu-id="b01f1-225">Allerdings verwendet die Glühbirne noch den aus der Vorlage erzeugten Codefix und informiert Sie, dass die Variable in Großbuchstaben geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="b01f1-225">However, the light bulb still uses the template generated code fix, and tells you it can be made upper case.</span></span> <span data-ttu-id="b01f1-226">Im nächsten Abschnitt erfahren Sie, wie der Codefix geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="b01f1-226">The next section explains how to write the code fix.</span></span>

## <a name="write-the-code-fix"></a><span data-ttu-id="b01f1-227">Schreiben des Codefixes</span><span class="sxs-lookup"><span data-stu-id="b01f1-227">Write the code fix</span></span>

<span data-ttu-id="b01f1-228">Ein Analysetool kann einen Codefix oder mehrere zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-228">An analyzer can provide one or more code fixes.</span></span> <span data-ttu-id="b01f1-229">Ein Codefix definiert eine Bearbeitung, die das gemeldete Problem angeht.</span><span class="sxs-lookup"><span data-stu-id="b01f1-229">A code fix defines an edit that addresses the reported issue.</span></span> <span data-ttu-id="b01f1-230">Für das Analysetool, das Sie erstellt haben, können Sie einen Codefix bereitstellen, der das Schlüsselwort „const“ einfügt:</span><span class="sxs-lookup"><span data-stu-id="b01f1-230">For the analyzer that you created, you can provide a code fix that inserts the const keyword:</span></span>

```csharp
const int x = 0;
Console.WriteLine(x);
```

<span data-ttu-id="b01f1-231">Der Benutzer wählt es im Editor in der Benutzeroberfläche der Glühbirne aus, und Visual Studio ändert den Code.</span><span class="sxs-lookup"><span data-stu-id="b01f1-231">The user chooses it from the light bulb UI in the editor and Visual Studio changes the code.</span></span>

<span data-ttu-id="b01f1-232">Öffnen Sie die von der Vorlage hinzugefügte Datei **MakeConstCodeFixProvider.cs**.</span><span class="sxs-lookup"><span data-stu-id="b01f1-232">Open the **MakeConstCodeFixProvider.cs** file added by the template.</span></span>  <span data-ttu-id="b01f1-233">Dieser Codefix ist bereits mit der Diagnose-ID verschaltet, die von Ihrem Diagnoseanalysetool erzeugt wird, er implementiert jedoch noch nicht die gewünschte Codetransformation.</span><span class="sxs-lookup"><span data-stu-id="b01f1-233">This code fix is already wired up to the Diagnostic ID produced by your diagnostic analyzer, but it doesn't yet implement the right code transform.</span></span> <span data-ttu-id="b01f1-234">Zunächst sollten Sie einen Teil des Vorlagencodes entfernen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-234">First you should remove some of the template code.</span></span> <span data-ttu-id="b01f1-235">Ändern Sie die Titelzeichenfolge in „Als Konstante deklarieren“:</span><span class="sxs-lookup"><span data-stu-id="b01f1-235">Change the title string to "Make constant":</span></span>

[!code-csharp[Update the CodeFix title](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

<span data-ttu-id="b01f1-236">Löschen Sie als Nächstes die `MakeUppercaseAsync`-Methode.</span><span class="sxs-lookup"><span data-stu-id="b01f1-236">Next, delete the `MakeUppercaseAsync` method.</span></span> <span data-ttu-id="b01f1-237">Sie trifft nicht mehr zu.</span><span class="sxs-lookup"><span data-stu-id="b01f1-237">It no longer applies.</span></span>

<span data-ttu-id="b01f1-238">Alle Codefixanbieter werden von <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="b01f1-238">All code fix providers derive from <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider>.</span></span> <span data-ttu-id="b01f1-239">Sie alle überschreiben <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType>, um verfügbare Codefixe zu melden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-239">They all override <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> to report available code fixes.</span></span> <span data-ttu-id="b01f1-240">Ändern Sie in `RegisterCodeFixesAsync` den Typ des Vorgängerknotens, nach dem Sie suchen, in <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>, damit er mit der Diagnose übereinstimmt:</span><span class="sxs-lookup"><span data-stu-id="b01f1-240">In `RegisterCodeFixesAsync`, change the ancestor node type you're searching for to a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> to match the diagnostic:</span></span>

[!code-csharp[Find local declaration node](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

<span data-ttu-id="b01f1-241">Ändern Sie dann die letzte Zeile, um einen Codefix zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="b01f1-241">Next, change the last line to register a code fix.</span></span> <span data-ttu-id="b01f1-242">Ihr Fix erstellt ein neues Dokument, das sich daraus ergibt, dass einer vorhandenen Deklaration der `const`-Modifizierer hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="b01f1-242">Your fix will create a new document that results from adding the `const` modifier to an existing declaration:</span></span>

[!code-csharp[Register the new code fix](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

<span data-ttu-id="b01f1-243">Sie werden rote Wellenlinien in dem soeben hinzugefügten Code unter dem Symbol `MakeConstAsync` bemerken.</span><span class="sxs-lookup"><span data-stu-id="b01f1-243">You'll notice red squiggles in the code you just added on the symbol `MakeConstAsync`.</span></span> <span data-ttu-id="b01f1-244">Fügen Sie eine Deklaration für `MakeConstAsync` hinzu, wie etwa den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="b01f1-244">Add a declaration for `MakeConstAsync` like the following code:</span></span>

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

<span data-ttu-id="b01f1-245">Ihre neue `MakeConstAsync`-Methode transformiert das <xref:Microsoft.CodeAnalysis.Document>, das die Quelldatei des Benutzers darstellt, in ein neues <xref:Microsoft.CodeAnalysis.Document>, das jetzt eine `const`-Deklaration enthält.</span><span class="sxs-lookup"><span data-stu-id="b01f1-245">Your new `MakeConstAsync` method will transform the <xref:Microsoft.CodeAnalysis.Document> representing the user's source file into a new <xref:Microsoft.CodeAnalysis.Document> that now contains a `const` declaration.</span></span>

<span data-ttu-id="b01f1-246">Sie erstellen ein neues `const`-Schlüsselworttoken, um es am Anfang der Deklarationsanweisung einzufügen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-246">You create a new `const` keyword token to insert at the front of the declaration statement.</span></span> <span data-ttu-id="b01f1-247">Achten Sie darauf, zuerst alle führenden Trivia aus dem ersten Token der Deklarationsanweisung zu entfernen und sie an das `const`-Token anzufügen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-247">Be careful to first remove any leading trivia from the first token of the declaration statement and attach it to the `const` token.</span></span> <span data-ttu-id="b01f1-248">Fügen Sie der `MakeConstAsync`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-248">Add the following code to the `MakeConstAsync` method:</span></span>

[!code-csharp[Create a new const keyword token](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

<span data-ttu-id="b01f1-249">Fügen Sie als Nächstes der Deklaration das `const`-Token mithilfe des folgenden Codes hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-249">Next, add the `const` token to the declaration using the following code:</span></span>

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

<span data-ttu-id="b01f1-250">Formatieren Sie anschließend die neue Deklaration gemäß den C#-Formatierungsregeln.</span><span class="sxs-lookup"><span data-stu-id="b01f1-250">Next, format the new declaration to match C# formatting rules.</span></span> <span data-ttu-id="b01f1-251">Das Formatieren Ihrer Änderungen in Anlehnung an den vorhandenen Code macht einen besseren Eindruck.</span><span class="sxs-lookup"><span data-stu-id="b01f1-251">Formatting your changes to match existing code creates a better experience.</span></span> <span data-ttu-id="b01f1-252">Fügen Sie unmittelbar hinter dem vorhandenen Code die folgende Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-252">Add the following statement immediately after the existing code:</span></span>

[!code-csharp[Format the new declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

<span data-ttu-id="b01f1-253">Für diesen Code ist ein neuer Namespace erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b01f1-253">A new namespace is required for this code.</span></span> <span data-ttu-id="b01f1-254">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-254">Add the following `using` statement to the top of the file:</span></span>

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

<span data-ttu-id="b01f1-255">Der letzte Schritt besteht im Ausführen Ihrer Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="b01f1-255">The final step is to make your edit.</span></span> <span data-ttu-id="b01f1-256">Dieser Prozess besteht aus drei Schritten:</span><span class="sxs-lookup"><span data-stu-id="b01f1-256">There are three steps to this process:</span></span>

1. <span data-ttu-id="b01f1-257">Abrufen eines Handles zu dem vorhandenen Dokument.</span><span class="sxs-lookup"><span data-stu-id="b01f1-257">Get a handle to the existing document.</span></span>
1. <span data-ttu-id="b01f1-258">Erstellen eines neuen Dokuments durch Ersetzen der vorhandenen Deklaration durch die neue Deklaration.</span><span class="sxs-lookup"><span data-stu-id="b01f1-258">Create a new document by replacing the existing declaration with the new declaration.</span></span>
1. <span data-ttu-id="b01f1-259">Zurückgeben des neuen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="b01f1-259">Return the new document.</span></span>

<span data-ttu-id="b01f1-260">Fügen Sie den folgenden Code am Ende der `MakeConstAsync`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-260">Add the following code to the end of the `MakeConstAsync` method:</span></span>

[!code-csharp[replace the declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

<span data-ttu-id="b01f1-261">Ihr Codefix ist nun bereit, ausprobiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-261">Your code fix is ready to try.</span></span>  <span data-ttu-id="b01f1-262">Drücken Sie F5, um das Analysetoolprojekt in einer zweiten Instanz von Visual Studio auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-262">Press F5 to run the analyzer project in a second instance of Visual Studio.</span></span> <span data-ttu-id="b01f1-263">Erstellen Sie in der zweiten Visual Studio-Instanz ein neues Konsolenanwendungsprojekt in C#, und fügen Sie der Methode „Main“ einige lokale Variablendeklarationen hinzu, die mit konstanten Werten initialisiert sind.</span><span class="sxs-lookup"><span data-stu-id="b01f1-263">In the second Visual Studio instance, create a new C# Console Application project and add a few local variable declarations initialized with constant values to the Main method.</span></span> <span data-ttu-id="b01f1-264">Sie sehen, dass sie als Warnungen gemeldet werden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-264">You'll see that they are reported as warnings as below.</span></span>

![Warnungen „Kann als ‚const‘ deklariert werden“](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

<span data-ttu-id="b01f1-266">Sie haben große Fortschritte erzielt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-266">You've made a lot of progress.</span></span> <span data-ttu-id="b01f1-267">Unter den Deklarationen, die in `const` umgewandelt werden können, werden Wellenlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-267">There are squiggles under the declarations that can be made `const`.</span></span> <span data-ttu-id="b01f1-268">Aber die Arbeit ist noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-268">But there is still work to do.</span></span> <span data-ttu-id="b01f1-269">Alles hier funktioniert, wenn Sie `const` den Deklarationen beginnend bei `i`, dann weiter mit `j` und schließlich `k` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-269">This works fine if you add `const` to the declarations starting with `i`, then `j` and finally `k`.</span></span> <span data-ttu-id="b01f1-270">Wenn Sie den `const`-Modifizierer aber in einer anderen Reihenfolge zu i zuweisen, beginnend mit `k`, erzeugt Ihr Analysetool Fehler: `k` kann nicht `const` deklariert werden, sofern nicht `i` und `j` beide bereits `const` sind.</span><span class="sxs-lookup"><span data-stu-id="b01f1-270">But, if you add the `const` modifier in a different order, starting with `k`, your analyzer creates errors: `k` can't be declared `const`, unless `i` and `j` are both already `const`.</span></span> <span data-ttu-id="b01f1-271">Sie müssen weitere Analysen durchführen, um sicherzustellen, dass Sie mit den verschiedenen Weisen umgehen können, in denen Variablen deklariert und initialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="b01f1-271">You've got to do more analysis to ensure you handle the different ways variables can be declared and initialized.</span></span>

## <a name="build-data-driven-tests"></a><span data-ttu-id="b01f1-272">Erstellen von datengesteuerten Tests</span><span class="sxs-lookup"><span data-stu-id="b01f1-272">Build data driven tests</span></span>

<span data-ttu-id="b01f1-273">Ihr Analysetool und der Codefix funktionieren beim einfachen Fall einer einzelnen Deklaration, die als „const“ deklariert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b01f1-273">Your analyzer and code fix work on a simple case of a single declaration that can be made const.</span></span> <span data-ttu-id="b01f1-274">Es gibt eine Vielzahl von möglichen Deklarationsanweisungen, bei denen diese Implementierung zu Fehlern führt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-274">There are numerous possible declaration statements where this implementation makes mistakes.</span></span> <span data-ttu-id="b01f1-275">Sie tragen diesen Fällen Rechnung, indem Sie mit der Komponententestbibliothek arbeiten, die von der Vorlage erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b01f1-275">You'll address these cases by working with the unit test library written by the template.</span></span> <span data-ttu-id="b01f1-276">Das funktioniert viel schneller, als wiederholt eine zweite Instanz von Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-276">It's much faster than repeatedly opening a second copy of Visual Studio.</span></span>

<span data-ttu-id="b01f1-277">Öffnen Sie die **MakeConstUnitTests.cs**-Datei im Komponententestprojekt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-277">Open the **MakeConstUnitTests.cs** file in the unit test project.</span></span> <span data-ttu-id="b01f1-278">Die Vorlage hat zwei Tests erstellt, die den zwei allgemeinen Mustern für einen Komponententest für Analysetools und Codefixe folgen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-278">The template created two tests that follow the two common patterns for an analyzer and code fix unit test.</span></span> <span data-ttu-id="b01f1-279">`TestMethod1` zeigt das Muster für einen Test, der sicherstellt, dass das Analysetool keine Diagnose meldet, wenn es das nicht sollte.</span><span class="sxs-lookup"><span data-stu-id="b01f1-279">`TestMethod1` shows the pattern for a test that ensures the analyzer doesn't report a diagnostic when it shouldn't.</span></span> <span data-ttu-id="b01f1-280">`TestMethod2` zeigt das Muster für das Melden einer Diagnose und das Ausführen des Codefixes.</span><span class="sxs-lookup"><span data-stu-id="b01f1-280">`TestMethod2` shows the pattern for reporting a diagnostic and running the code fix.</span></span>

<span data-ttu-id="b01f1-281">Der Code nahezu jedes Tests für Ihr Analysetool folgt einem dieser beiden Muster.</span><span class="sxs-lookup"><span data-stu-id="b01f1-281">The code for almost every test for your analyzer follows one of these two patterns.</span></span> <span data-ttu-id="b01f1-282">Im ersten Schritt können Sie diese Tests als datengesteuerte Tests umarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b01f1-282">For the first step, you can rework these tests as data driven tests.</span></span> <span data-ttu-id="b01f1-283">Anschließend wird es einfach, neue Tests zu erstellen, indem Sie neue Zeichenfolgenkonstanten hinzufügen, um verschiedene Testeingaben darzustellen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-283">Then, it will be easy to create new tests by adding new string constants to represent different test inputs.</span></span>

<span data-ttu-id="b01f1-284">Aus Effizienzgründen besteht der erste Schritt in der Umgestaltung der beiden Tests in datengesteuerte Tests.</span><span class="sxs-lookup"><span data-stu-id="b01f1-284">For efficiency, the first step is to refactor the two tests into data driven tests.</span></span> <span data-ttu-id="b01f1-285">Anschließend müssen Sie lediglich ein paar Zeichenfolgenkonstanten für jeden neuen Test definieren.</span><span class="sxs-lookup"><span data-stu-id="b01f1-285">Then, you only need to define a couple string constants for each new test.</span></span> <span data-ttu-id="b01f1-286">Benennen Sie im Rahmen der Umgestaltung beide Methoden mit besseren Namen um.</span><span class="sxs-lookup"><span data-stu-id="b01f1-286">While your refactoring, rename both methods to better names.</span></span> <span data-ttu-id="b01f1-287">Ersetzen Sie `TestMethod1` durch diesen Test, der sicherstellt, dass keine Diagnose ausgelöst wird:</span><span class="sxs-lookup"><span data-stu-id="b01f1-287">Replace `TestMethod1` with this test that ensures no diagnostic is raised:</span></span>

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

<span data-ttu-id="b01f1-288">Sie können für diesen Test eine neue Datenzeile erstellen, indem Sie jedes Codefragment definieren, das keine Warnung von Ihrer Diagnose auslösen soll.</span><span class="sxs-lookup"><span data-stu-id="b01f1-288">You can create a new data row for this test by defining any code fragment that should not cause your diagnostic to trigger a warning.</span></span> <span data-ttu-id="b01f1-289">Diese Überladung von `VerifyCSharpDiagnostic` besteht den Test, wenn für das Quellcodefragment keine Diagnose ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b01f1-289">This overload of `VerifyCSharpDiagnostic` passes when there are no diagnostics triggered for the source code fragment.</span></span>

<span data-ttu-id="b01f1-290">Ersetzen Sie als Nächstes `TestMethod2` durch diesen Test, der sicherstellt, dass für das Quellcodefragment eine Diagnose ausgelöst und ein Codefix angewendet wird:</span><span class="sxs-lookup"><span data-stu-id="b01f1-290">Next, replace `TestMethod2` with this test that ensures a diagnostic is raised and a code fix applied for the source code fragment:</span></span>

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

<span data-ttu-id="b01f1-291">Im vorstehenden Code wurden außerdem ein paar Änderungen an dem Code vorgenommen, der das erwartete Diagnoseergebnis erzeugt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-291">The preceding code also made a couple changes to the code that builds the expected diagnostic result.</span></span> <span data-ttu-id="b01f1-292">Er verwendet die im `MakeConst`-Analysetool registrierten öffentlichen Konstanten.</span><span class="sxs-lookup"><span data-stu-id="b01f1-292">It uses the public constants registered in the `MakeConst` analyzer.</span></span> <span data-ttu-id="b01f1-293">Außerdem verwendet er zwei Zeichenfolgenkonstanten für die Eingabe und die feste Quelle.</span><span class="sxs-lookup"><span data-stu-id="b01f1-293">In addition, it uses two string constants for the input and fixed source.</span></span> <span data-ttu-id="b01f1-294">Fügen Sie der `UnitTest`-Klasse die folgenden Zeichenfolgenkonstanten hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-294">Add the following string constants to the `UnitTest` class:</span></span>

[!code-csharp[string constants for fix test](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

<span data-ttu-id="b01f1-295">Führen Sie diese zwei Tests aus, um sicherzustellen, dass sie bestanden werden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-295">Run these two tests to make sure they pass.</span></span> <span data-ttu-id="b01f1-296">Öffnen Sie in Visual Studio den **Test-Explorer**, indem Sie **Test** > **Windows** > **Test-Explorer** auswählen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-296">In Visual Studio, open the **Test Explorer** by selecting **Test** > **Windows** > **Test Explorer**.</span></span>  <span data-ttu-id="b01f1-297">Aktivieren Sie dann den Link **Run All** (Alle ausführen).</span><span class="sxs-lookup"><span data-stu-id="b01f1-297">The press the **Run All** link.</span></span>

## <a name="create-tests-for-valid-declarations"></a><span data-ttu-id="b01f1-298">Erstellen von Tests für gültige Deklarationen</span><span class="sxs-lookup"><span data-stu-id="b01f1-298">Create tests for valid declarations</span></span>

<span data-ttu-id="b01f1-299">Ganz allgemein sollten Analysetool so schnell wie möglich beendet werden und nur minimale Arbeit verrichten.</span><span class="sxs-lookup"><span data-stu-id="b01f1-299">As a general rule, analyzers should exit as quickly as possible, doing minimal work.</span></span> <span data-ttu-id="b01f1-300">Visual Studio ruft registrierte Analysetools auf, während der Benutzer den Code bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="b01f1-300">Visual Studio calls registered analyzers as the user edits code.</span></span> <span data-ttu-id="b01f1-301">Reaktionsfähigkeit ist eine wichtige Anforderung.</span><span class="sxs-lookup"><span data-stu-id="b01f1-301">Responsiveness is a key requirement.</span></span> <span data-ttu-id="b01f1-302">Es gibt mehrere Testfälle für Code, der Ihre Diagnose nicht auslösen soll.</span><span class="sxs-lookup"><span data-stu-id="b01f1-302">There are several test cases for code that should not raise your diagnostic.</span></span> <span data-ttu-id="b01f1-303">Ihr Analysetool verarbeitet bereits einen dieser Tests, den Fall, in dem eine Variable nach der Initialisierung zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b01f1-303">Your analyzer already handles one of those tests, the case where a variable is assigned after being initialized.</span></span> <span data-ttu-id="b01f1-304">Fügen Sie Ihren Tests die folgende Zeichenfolgenkonstante hinzu, um diesem Fall darzustellen:</span><span class="sxs-lookup"><span data-stu-id="b01f1-304">Add the following string constant to your tests to represent that case:</span></span>

[!code-csharp[variable assigned](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

<span data-ttu-id="b01f1-305">Fügen Sie anschließend eine Datenzeile für diesen Test hinzu, wie im Codeausschnitt unten zu sehen:</span><span class="sxs-lookup"><span data-stu-id="b01f1-305">Then, add a data row for this test as shown in the snippet below:</span></span>

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

<span data-ttu-id="b01f1-306">Dieser Test wird ebenfalls bestanden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-306">This test passes as well.</span></span> <span data-ttu-id="b01f1-307">Fügen Sie als Nächstes Konstanten für Bedingungen hinzu, die Sie noch nicht behandelt haben:</span><span class="sxs-lookup"><span data-stu-id="b01f1-307">Next, add constants for conditions you haven't handled yet:</span></span>

- <span data-ttu-id="b01f1-308">Deklarationen, die bereits `const` sind, da sie bereits Konstanten sind:</span><span class="sxs-lookup"><span data-stu-id="b01f1-308">Declarations that are already `const`, because they are already const:</span></span>

   [!code-csharp[already const declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- <span data-ttu-id="b01f1-309">Deklarationen, die keinen Initialisierer besitzen, weil es keinen zu verwendenden Wert gibt:</span><span class="sxs-lookup"><span data-stu-id="b01f1-309">Declarations that have no initializer, because there is no value to use:</span></span>

   [!code-csharp[declarations that have no initializer](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- <span data-ttu-id="b01f1-310">Deklarationen, bei denen der Initialisierer keine Konstante ist, da sie zur Kompilierzeit keine Konstanten sein können:</span><span class="sxs-lookup"><span data-stu-id="b01f1-310">Declarations where the initializer is not a constant, because they can't be compile-time constants:</span></span>

   [!code-csharp[declarations where the initializer isn't const](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

<span data-ttu-id="b01f1-311">Es kann sogar noch komplizierter sein, da C# mehrere Deklarationen in Form einer Anweisung zulässt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-311">It can be even more complicated because C# allows multiple declarations as one statement.</span></span> <span data-ttu-id="b01f1-312">Betrachten Sie die folgende Zeichenfolgenkonstante aus einem Testfall:</span><span class="sxs-lookup"><span data-stu-id="b01f1-312">Consider the following test case string constant:</span></span>

[!code-csharp[multiple initializers](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

<span data-ttu-id="b01f1-313">Die Variable `i` kann als Konstante deklariert werden, die Variable `j` jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="b01f1-313">The variable `i` can be made constant, but the variable `j` cannot.</span></span> <span data-ttu-id="b01f1-314">Daher kann aus dieser Anweisung keine const-Deklaration gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-314">Therefore, this statement cannot be made a const declaration.</span></span> <span data-ttu-id="b01f1-315">Fügen Sie die `DataRow`-Deklarationen für alle diese Tests hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-315">Add the `DataRow` declarations for all these tests:</span></span>

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

<span data-ttu-id="b01f1-316">Führen Sie Ihre Tests erneut aus – Sie werden feststellen, dass bei den neuen Testfällen Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="b01f1-316">Run your tests again, and you'll see these new test cases fail.</span></span>

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a><span data-ttu-id="b01f1-317">Aktualisieren Ihres Analysetools, damit korrekte Deklarationen ignoriert werden</span><span class="sxs-lookup"><span data-stu-id="b01f1-317">Update your analyzer to ignore correct declarations</span></span>

<span data-ttu-id="b01f1-318">Sie benötigen noch einige Verbesserungen an der `AnalyzeNode`-Methode Ihres Analysetools, um Code herauszufiltern, der den Bedingungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="b01f1-318">You need some enhancements to your analyzer's `AnalyzeNode` method to filter out code that matches these conditions.</span></span> <span data-ttu-id="b01f1-319">Es handelt sich bei allen um verwandte Bedingungen, daher lassen sich auch alle mit ähnlichen Änderungen beheben.</span><span class="sxs-lookup"><span data-stu-id="b01f1-319">They are all related conditions, so similar changes will fix all these conditions.</span></span> <span data-ttu-id="b01f1-320">Nehmen Sie an `AnalyzeNode` die folgenden Änderungen vor:</span><span class="sxs-lookup"><span data-stu-id="b01f1-320">Make the following changes to `AnalyzeNode`:</span></span>

- <span data-ttu-id="b01f1-321">Ihre semantische Analyse hat eine einzelne Variablendeklaration untersucht.</span><span class="sxs-lookup"><span data-stu-id="b01f1-321">Your semantic analysis examined a single variable declaration.</span></span> <span data-ttu-id="b01f1-322">Dieser Code muss sich in einer `foreach`-Schleife befinden, die alle innerhalb der gleichen Anweisung deklarierten Variablen untersucht.</span><span class="sxs-lookup"><span data-stu-id="b01f1-322">This code needs to be in a `foreach` loop that examines all the variables declared in the same statement.</span></span>
- <span data-ttu-id="b01f1-323">Jede deklarierte Variable muss über einen Initialisierer verfügen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-323">Each declared variable needs to have an initializer.</span></span>
- <span data-ttu-id="b01f1-324">Der Initialisierer jeder deklarierten Variable muss zur Kompilierzeit eine Konstante sein.</span><span class="sxs-lookup"><span data-stu-id="b01f1-324">Each declared variable's initializer must be a compile-time constant.</span></span>

<span data-ttu-id="b01f1-325">Ersetzen Sie in Ihrer `AnalyzeNode`-Methode die ursprüngliche semantische Analyse:</span><span class="sxs-lookup"><span data-stu-id="b01f1-325">In your `AnalyzeNode` method, replace the original semantic analysis:</span></span>

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

<span data-ttu-id="b01f1-326">durch den folgenden Codeausschnitt:</span><span class="sxs-lookup"><span data-stu-id="b01f1-326">with the following code snippet:</span></span>

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

<span data-ttu-id="b01f1-327">Die erste `foreach`-Schleife untersucht jede Variablendeklaration mithilfe der Syntaxanalyse.</span><span class="sxs-lookup"><span data-stu-id="b01f1-327">The first `foreach` loop examines each variable declaration using syntactic analysis.</span></span> <span data-ttu-id="b01f1-328">Die erste Prüfung stellt sicher, dass die Variable einen Initialisierer aufweist.</span><span class="sxs-lookup"><span data-stu-id="b01f1-328">The first check guarantees that the variable has an initializer.</span></span> <span data-ttu-id="b01f1-329">Die zweite Prüfung stellt sicher, dass der Initialisierer eine Konstante ist.</span><span class="sxs-lookup"><span data-stu-id="b01f1-329">The second check guarantees that the initializer is a constant.</span></span> <span data-ttu-id="b01f1-330">Die zweite Schleife enthält die ursprüngliche semantische Analyse.</span><span class="sxs-lookup"><span data-stu-id="b01f1-330">The second loop has the original semantic analysis.</span></span> <span data-ttu-id="b01f1-331">Die semantischen Prüfungen befinden sich in einer separaten Schleife, da sie einen größeren Einfluss auf die Leistung haben.</span><span class="sxs-lookup"><span data-stu-id="b01f1-331">The semantic checks are in a separate loop because it has a greater impact on performance.</span></span> <span data-ttu-id="b01f1-332">Führen Sie Ihre Tests erneut aus – sie sollten alle bestanden werden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-332">Run your tests again, and you should see them all pass.</span></span>

## <a name="add-the-final-polish"></a><span data-ttu-id="b01f1-333">Der letzte Schliff</span><span class="sxs-lookup"><span data-stu-id="b01f1-333">Add the final polish</span></span>

<span data-ttu-id="b01f1-334">Sie haben es fast geschafft!</span><span class="sxs-lookup"><span data-stu-id="b01f1-334">You're almost done.</span></span> <span data-ttu-id="b01f1-335">Es gibt noch ein paar weitere Bedingungen, mit denen Ihr Analysetool umgehen muss.</span><span class="sxs-lookup"><span data-stu-id="b01f1-335">There are a few more conditions for your analyzer to handle.</span></span> <span data-ttu-id="b01f1-336">Visual Studio ruft Analysetools auf, während der Benutzer Code schreibt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-336">Visual Studio calls analyzers while the user is writing code.</span></span> <span data-ttu-id="b01f1-337">Es tritt häufig der Fall ein, dass Ihr Analysetool für Code aufgerufen wird, der sich nicht kompilieren lässt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-337">It's often the case that your analyzer will be called for code that doesn't compile.</span></span> <span data-ttu-id="b01f1-338">Die Methode `AnalyzeNode` des Diagnoseanalysetools überprüft nicht, ob der Konstantenwert in den Variablentyp konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b01f1-338">The diagnostic analyzer's `AnalyzeNode` method does not check to see if the constant value is convertible to the variable type.</span></span> <span data-ttu-id="b01f1-339">Daher konvertiert die aktuelle Implementierung eine falsche Deklaration wie int i = "abc"' unbedarft in eine lokale Konstante.</span><span class="sxs-lookup"><span data-stu-id="b01f1-339">So, the current implementation will happily convert an incorrect declaration such as int i = "abc"' to a local constant.</span></span> <span data-ttu-id="b01f1-340">Fügen Sie für diese Bedingung eine Quellzeichenfolgenkonstante hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-340">Add a source string constant for that condition:</span></span>

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

<span data-ttu-id="b01f1-341">Darüber hinaus werden Verweistypen nicht ordnungsgemäß behandelt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-341">In addition, reference types are not handled properly.</span></span> <span data-ttu-id="b01f1-342">Der einzige Konstantenwert, die für einen Verweistyp zulässig ist, ist `null`, abgesehen von dem Fall <xref:System.String?displayProperty=nameWithType>, der Zeichenfolgenliterale zulässt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-342">The only constant value allowed for a reference type is `null`, except in this case of <xref:System.String?displayProperty=nameWithType>, which allows string literals.</span></span> <span data-ttu-id="b01f1-343">Das heißt, `const string s = "abc"` ist zulässig, `const object s = "abc"` aber nicht.</span><span class="sxs-lookup"><span data-stu-id="b01f1-343">In other words, `const string s = "abc"` is legal, but `const object s = "abc"` is not.</span></span> <span data-ttu-id="b01f1-344">Diese Bedingung wird mit diesem Codeausschnitt überprüft:</span><span class="sxs-lookup"><span data-stu-id="b01f1-344">This code snippet verifies that condition:</span></span>

[!code-csharp[Reference types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

<span data-ttu-id="b01f1-345">Wenn Sie gründlich sein wollen, müssen Sie einen weiteren Test hinzufügen, um sicherzustellen, dass Sie für eine Zeichenfolge eine Konstantendeklaration erstellen können.</span><span class="sxs-lookup"><span data-stu-id="b01f1-345">To be thorough, you need to add another test to make sure that you can create a constant declaration for a string.</span></span> <span data-ttu-id="b01f1-346">Der folgende Codeausschnitt definiert sowohl den Code, der die Diagnose auslöst, als auch den Code nach der Anwendung des Fixes:</span><span class="sxs-lookup"><span data-stu-id="b01f1-346">The following snippet defines both the code that raises the diagnostic, and the code after the fix has been applied:</span></span>

[!code-csharp[string reference types raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

<span data-ttu-id="b01f1-347">Schließlich ergreift bei einer Variablen, die mit dem Schlüsselwort `var` deklariert ist, der Codefix die falsche Aktion und generiert eine `const var`-Deklaration, was von der Sprache C# nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b01f1-347">Finally, if a variable is declared with the `var` keyword, the code fix does the wrong thing and generates a `const var` declaration, which is not supported by the C# language.</span></span> <span data-ttu-id="b01f1-348">Um diesen Fehler zu beheben, muss der Codefix das Schlüsselwort `var` durch den Namen des abgeleiteten Typs ersetzen:</span><span class="sxs-lookup"><span data-stu-id="b01f1-348">To fix this bug, the code fix must replace the `var` keyword with the inferred type's name:</span></span>

[!code-csharp[var references need to use the inferred types](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

<span data-ttu-id="b01f1-349">Durch diese Änderungen werden die Datenzeilendeklarationen für beide Tests aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b01f1-349">These changes update the data row declarations for both tests.</span></span> <span data-ttu-id="b01f1-350">Der folgende Code zeigt diese Tests mit allen Datenzeilenattributen:</span><span class="sxs-lookup"><span data-stu-id="b01f1-350">The following code shows these tests with all data row attributes:</span></span>

[!code-csharp[The finished tests](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

<span data-ttu-id="b01f1-351">Glücklicherweise lassen sich alle oben aufgeführten Fehler mithilfe genau der Techniken beheben, die Sie gerade gelernt haben.</span><span class="sxs-lookup"><span data-stu-id="b01f1-351">Fortunately, all of the above bugs can be addressed using the same techniques that you just learned.</span></span>

<span data-ttu-id="b01f1-352">Zum Beheben des ersten Fehlers öffnen Sie zuerst **DiagnosticAnalyzer.cs** und suchen die foreach-Schleife, in der jeder der Initialisierer der lokalen Deklaration überprüft wird, um sicherzustellen, dass allen konstante Werte zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-352">To fix the first bug, first open **DiagnosticAnalyzer.cs** and locate the foreach loop where each of the local declaration's initializers are checked to ensure that they're assigned with constant values.</span></span> <span data-ttu-id="b01f1-353">Rufen Sie unmittelbar _vor_ der ersten foreach-Schleife `context.SemanticModel.GetTypeInfo()` auf, um Detailinformationen über den deklarierten Typ der lokalen Deklaration abzurufen:</span><span class="sxs-lookup"><span data-stu-id="b01f1-353">Immediately _before_ the first foreach loop, call `context.SemanticModel.GetTypeInfo()` to retrieve detailed information about the declared type of the local declaration:</span></span>

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

<span data-ttu-id="b01f1-354">Überprüfen Sie anschließend innerhalb Ihrer `foreach`-Schleife jeden Initialisierer, um sicherzustellen, dass er in den Variablentyp konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b01f1-354">Then, inside your `foreach` loop, check each initializer to make sure it's convertible to the variable type.</span></span> <span data-ttu-id="b01f1-355">Fügen Sie die folgende Überprüfung hinzu, nachdem sichergestellt wurde, dass der Initialisierer eine Konstante ist:</span><span class="sxs-lookup"><span data-stu-id="b01f1-355">Add the following check after ensuring that the initializer is a constant:</span></span>

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

<span data-ttu-id="b01f1-356">Die nächste Änderung baut auf der letzten auf.</span><span class="sxs-lookup"><span data-stu-id="b01f1-356">The next change builds upon the last one.</span></span> <span data-ttu-id="b01f1-357">Fügen Sie vor der schließenden geschweiften Klammer der ersten foreach-Schleife den folgenden Code hinzu, um den Typ der lokalen Deklaration zu überprüfen, wenn die Konstante eine Zeichenfolge oder NULL ist.</span><span class="sxs-lookup"><span data-stu-id="b01f1-357">Before the closing curly brace of the first foreach loop, add the following code to check the type of the local declaration when the constant is a string or null.</span></span>

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

<span data-ttu-id="b01f1-358">Sie müssen etwas mehr Code in Ihrem Codefixanbieter schreiben, um das Schlüsselwort „var“ durch den korrekten Typnamen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-358">You must write a bit more code in your code fix provider to replace the var' keyword with the correct type name.</span></span> <span data-ttu-id="b01f1-359">Wechseln Sie zu **CodeFixProvider.cs** zurück.</span><span class="sxs-lookup"><span data-stu-id="b01f1-359">Return to **CodeFixProvider.cs**.</span></span> <span data-ttu-id="b01f1-360">Der Code, den Sie hinzufügen, führt die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b01f1-360">The code you'll add does the following steps:</span></span>

- <span data-ttu-id="b01f1-361">Überprüft, ob die Deklaration eine `var`-Deklaration ist, und wenn dies zutrifft:</span><span class="sxs-lookup"><span data-stu-id="b01f1-361">Check if the declaration is a `var` declaration, and if it is:</span></span>
- <span data-ttu-id="b01f1-362">Erstellt einen neuen Typ für den abgeleiteten Typ.</span><span class="sxs-lookup"><span data-stu-id="b01f1-362">Create a new type for the inferred type.</span></span>
- <span data-ttu-id="b01f1-363">Vergewissert sich, dass die Typdeklaration kein Alias ist.</span><span class="sxs-lookup"><span data-stu-id="b01f1-363">Make sure the type declaration is not an alias.</span></span> <span data-ttu-id="b01f1-364">Ist das der Fall, ist eine Deklaration als `const var` zulässig.</span><span class="sxs-lookup"><span data-stu-id="b01f1-364">If so, it is legal to declare `const var`.</span></span>
- <span data-ttu-id="b01f1-365">Stellt sicher, dass `var` kein Typname in diesem Programm ist.</span><span class="sxs-lookup"><span data-stu-id="b01f1-365">Make sure that `var` isn't a type name in this program.</span></span> <span data-ttu-id="b01f1-366">(In dem Fall ist `const var` zulässig).</span><span class="sxs-lookup"><span data-stu-id="b01f1-366">(If so, `const var` is legal).</span></span>
- <span data-ttu-id="b01f1-367">Vereinfacht den vollständigen Typnamen</span><span class="sxs-lookup"><span data-stu-id="b01f1-367">Simplify the full type name</span></span>

<span data-ttu-id="b01f1-368">Das hört sich nach ziemlich viel Code an.</span><span class="sxs-lookup"><span data-stu-id="b01f1-368">That sounds like a lot of code.</span></span> <span data-ttu-id="b01f1-369">Ist es aber nicht.</span><span class="sxs-lookup"><span data-stu-id="b01f1-369">It's not.</span></span> <span data-ttu-id="b01f1-370">Ersetzen Sie die Zeile, in der `newLocal` deklariert und initialisiert wird, durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="b01f1-370">Replace the line that declares and initializes `newLocal` with the following code.</span></span> <span data-ttu-id="b01f1-371">Er gehört direkt hinter die Initialisierung von `newModifiers`:</span><span class="sxs-lookup"><span data-stu-id="b01f1-371">It goes immediately after the initialization of `newModifiers`:</span></span>

[!code-csharp[Replace Var designations](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

<span data-ttu-id="b01f1-372">Sie müssen eine `using`-Anweisung hinzufügen, um den <xref:Microsoft.CodeAnalysis.Simplification.Simplifier>-Typ zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="b01f1-372">You'll need to add one `using` statement to use the <xref:Microsoft.CodeAnalysis.Simplification.Simplifier> type:</span></span>

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

<span data-ttu-id="b01f1-373">Führen Sie Ihre Tests aus – sie sollten alle bestanden werden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-373">Run your tests, and they should all pass.</span></span> <span data-ttu-id="b01f1-374">Gratulieren Sie sich, indem Sie Ihr fertiges Analysetool ausführen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-374">Congratulate yourself by running your finished analyzer.</span></span> <span data-ttu-id="b01f1-375">Drücken Sie STRG+F5, um das Analysetoolprojekt in einer zweiten Instanz von Visual Studio mit geladener Roslyn-Vorschauerweiterung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-375">Press Ctrl+F5 to run the analyzer project in a second instance of Visual Studio with the Roslyn Preview extension loaded.</span></span>

- <span data-ttu-id="b01f1-376">Erstellen Sie in der zweiten Visual Studio-Instanz ein neues C#-Konsolenanwendungsprojekt, und fügen Sie `int x = "abc";` zur Methode „Main“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="b01f1-376">In the second Visual Studio instance, create a new C# Console Application project and add `int x = "abc";` to the Main method.</span></span> <span data-ttu-id="b01f1-377">Dank der ersten Fehlerbehebung sollte keine Warnung für diese lokale Variablendeklaration gemeldet werden (obwohl es erwartungsgemäß einen Compilerfehler gibt).</span><span class="sxs-lookup"><span data-stu-id="b01f1-377">Thanks to the first bug fix, no warning should be reported for this local variable declaration (though there's a compiler error as expected).</span></span>
- <span data-ttu-id="b01f1-378">Fügen Sie als Nächstes `object s = "abc";` zur Methode „Main“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="b01f1-378">Next, add `object s = "abc";` to the Main method.</span></span> <span data-ttu-id="b01f1-379">Aufgrund der zweiten Fehlerbehebung sollte keine Warnung gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="b01f1-379">Because of the second bug fix, no warning should be reported.</span></span>
- <span data-ttu-id="b01f1-380">Fügen Sie schließlich eine weitere lokale Variable hinzu, die das Schlüsselwort `var` verwendet.</span><span class="sxs-lookup"><span data-stu-id="b01f1-380">Finally, add another local variable that uses the `var` keyword.</span></span> <span data-ttu-id="b01f1-381">Sie sehen, dass eine Warnung gemeldet und ein Vorschlag links unterhalb der Meldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b01f1-381">You'll see that a warning is reported and a suggestion appears beneath to the left.</span></span>
- <span data-ttu-id="b01f1-382">Bewegen Sie den Textcursor des Editors über die Wellenlinien-Unterstreichung, und drücken Sie STRG+.,</span><span class="sxs-lookup"><span data-stu-id="b01f1-382">Move the editor caret over the squiggly underline and press Ctrl+.</span></span> <span data-ttu-id="b01f1-383">um den vorgeschlagenen Codefix anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-383">to display the suggested code fix.</span></span> <span data-ttu-id="b01f1-384">Beachten Sie beim Auswählen des Codefixes, dass das Schlüsselwort „var“ jetzt ordnungsgemäß behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="b01f1-384">Upon selecting your code fix, note that the var' keyword is now handled correctly.</span></span>

<span data-ttu-id="b01f1-385">Fügen Sie schließlich den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b01f1-385">Finally, add the following code:</span></span>

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

<span data-ttu-id="b01f1-386">Nach diesen Änderungen erhalten Sie rote Wellenlinien nur unter den ersten zwei Variablen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-386">After these changes, you get red squiggles only on the first two variables.</span></span> <span data-ttu-id="b01f1-387">Fügen Sie `const` sowohl zu `i` als auch zu `j` hinzu, und Sie erhalten eine neue Warnung zu `k`, da das nun als `const` deklariert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b01f1-387">Add `const` to both `i` and `j`, and you get a new warning on `k` because it can now be `const`.</span></span>

<span data-ttu-id="b01f1-388">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="b01f1-388">Congratulations!</span></span> <span data-ttu-id="b01f1-389">Sie haben Ihre erste Erweiterung für die .NET Compiler Platform erstellt, die dynamische Codeanalyse durchführt, um ein Problem zu erkennen, und eine schnelle Problembehebung zu seiner Korrektur bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b01f1-389">You've created your first .NET Compiler Platform extension that performs on-the-fly code analysis to detect an issue and provides a quick fix to correct it.</span></span> <span data-ttu-id="b01f1-390">Auf diesem Weg haben Sie viele der Code-APIs kennengelernt, die Teil der .NET Compiler Platform SDKs sind (Roslyn-APIs).</span><span class="sxs-lookup"><span data-stu-id="b01f1-390">Along the way, you've learned many of the code APIs that are part of the .NET Compiler Platform SDK (Roslyn APIs).</span></span> <span data-ttu-id="b01f1-391">Sie können Ihre Arbeit anhand des [fertiggestellten Beispiels](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) in unserem GitHub-Beispielrepository überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b01f1-391">You can check your work against the [completed sample](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) in our samples GitHub repository.</span></span>

## <a name="other-resources"></a><span data-ttu-id="b01f1-392">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b01f1-392">Other resources</span></span>

- [<span data-ttu-id="b01f1-393">Erste Schritte mit der Syntaxanalyse</span><span class="sxs-lookup"><span data-stu-id="b01f1-393">Get started with syntax analysis</span></span>](../get-started/syntax-analysis.md)
- [<span data-ttu-id="b01f1-394">Erste Schritte mit der semantischen Analyse</span><span class="sxs-lookup"><span data-stu-id="b01f1-394">Get started with semantic analysis</span></span>](../get-started/semantic-analysis.md)
