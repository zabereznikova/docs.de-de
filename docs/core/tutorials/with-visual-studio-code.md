---
title: "Erste Schritte mit C# und Visual Studio Code – Leitfaden für C# | Microsoft-Dokumentation"
description: Erfahren Sie, wie Sie Ihre erste .NET Core-Anwendung in C# mithilfe von Visual Studio Code erstellen und debuggen.
keywords: "C#, erste Schritte, Erwerb, Installation, Visual Studio Code, plattformübergreifend"
author: kendrahavens
ms.author: mairaw
ms.date: 8/01/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.translationtype: HT
ms.sourcegitcommit: 3bd8800e7410ae4a3b89f5962af957789edd48b0
ms.openlocfilehash: a10fda5663f0a49069388ee8ee7a9ebb575cd549
ms.contentlocale: de-de
ms.lasthandoff: 08/03/2017

---

# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="c9da3-104">Erste Schritte mit C# und Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c9da3-104">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="c9da3-105">.NET Core ist eine schnelle und modulare Plattform zum Erstellen von Anwendungen, die unter Windows, Linux und macOS ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c9da3-105">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="c9da3-106">Verwenden Sie Visual Studio Code mit der C#-Erweiterung, um von leistungsfähigen Bearbeitungsfunktionen mit vollständiger Unterstützung für C# IntelliSense (intelligente Codevervollständigung) und Debugging zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="c9da3-106">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c9da3-107">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="c9da3-107">Prerequisites</span></span>

1. <span data-ttu-id="c9da3-108">Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="c9da3-108">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="c9da3-109">Installieren Sie das [.NET Core SDK](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="c9da3-109">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="c9da3-110">Installieren Sie die [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) aus dem Visual Studio Code Marketplace.</span><span class="sxs-lookup"><span data-stu-id="c9da3-110">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) from the Visual Studio Code Marketplace.</span></span>

## <a name="hello-world"></a><span data-ttu-id="c9da3-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="c9da3-111">Hello World</span></span>

<span data-ttu-id="c9da3-112">Beginnen wir mit einem einfachen „Hello World“-Programm in .NET Core:</span><span class="sxs-lookup"><span data-stu-id="c9da3-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="c9da3-113">Öffnen Sie ein Projekt:</span><span class="sxs-lookup"><span data-stu-id="c9da3-113">Open a project:</span></span>

    * <span data-ttu-id="c9da3-114">Öffnen Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="c9da3-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="c9da3-115">Klicken Sie im linken Menü auf das Explorer-Symbol, und klicken Sie dann auf **Ordner öffnen**.</span><span class="sxs-lookup"><span data-stu-id="c9da3-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="c9da3-116">Wählen Sie den Ordner, in dem Sie Ihr C#-Projekt speichern möchten, und klicken Sie auf **Ordner auswählen**.</span><span class="sxs-lookup"><span data-stu-id="c9da3-116">Select the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="c9da3-117">Für unser Beispiel erstellen wir einen Ordner namens „HelloWorld“ für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="c9da3-117">For our example, we'll create a folder for our project named 'HelloWorld'.</span></span> 

  ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

    * <span data-ttu-id="c9da3-119">Alternativ dazu können Sie aus dem Hauptmenü die Option **Datei** > **Ordner öffnen** auswählen, um Ihren Projektordner zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c9da3-119">Alternatively, you can select **File** > **Open Folder** from the main menu to open your project folder.</span></span>

2. <span data-ttu-id="c9da3-120">Initialisieren Sie ein C#-Projekt:</span><span class="sxs-lookup"><span data-stu-id="c9da3-120">Initialize a C# project:</span></span>
    * <span data-ttu-id="c9da3-121">Öffnen Sie das integrierte Terminal aus Visual Studio Code, indem Sie <kbd>STRG</kbd>+<kbd>\\`</kbd> (Backtick, rückwärts geneigtes Hochkomma) drücken.</span><span class="sxs-lookup"><span data-stu-id="c9da3-121">Open the Integrated Terminal from Visual Studio Code by typing <kbd>CTRL</kbd>+<kbd>\\`</kbd> (backtick).</span></span> <span data-ttu-id="c9da3-122">Alternativ dazu können Sie auch aus dem Hauptmenü die Optionen **Ansicht** > **Integriertes Terminal** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c9da3-122">Alternatively, you can select **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="c9da3-123">Geben Sie im Terminalfenster `dotnet new console` ein.</span><span class="sxs-lookup"><span data-stu-id="c9da3-123">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="c9da3-124">Dadurch wird eine `Program.cs`-Datei in Ihrem Ordner erstellt, die ein bereits geschriebenes einfaches „Hello World“-Programm enthält. Zusätzlich wird eine C#-Projektdatei namens `HelloWorld.csproj` erstellt.</span><span class="sxs-lookup"><span data-stu-id="c9da3-124">This creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

  ![Der Befehl „dotnet new“](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="c9da3-126">Lösen Sie die Buildobjekte auf:</span><span class="sxs-lookup"><span data-stu-id="c9da3-126">Resolve the build assets:</span></span>

    * <span data-ttu-id="c9da3-127">Geben Sie für **.NET Core 1.1** den Befehl `dotnet restore` ein.</span><span class="sxs-lookup"><span data-stu-id="c9da3-127">For **.NET Core 1.1**, type `dotnet restore`.</span></span> <span data-ttu-id="c9da3-128">Durch Ausführen von `dotnet restore` erhalten Sie Zugriff auf die erforderlichen .NET Core-Pakete, die Sie zum Erstellen Ihres Projekts benötigen.</span><span class="sxs-lookup"><span data-stu-id="c9da3-128">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

   ![Der Befehl „dotnet restore“](media/with-visual-studio-code/dotnetrestore.png)

    * <span data-ttu-id="c9da3-130">Für **.NET Core 2.0** ist dieser Schritt optional.</span><span class="sxs-lookup"><span data-stu-id="c9da3-130">For **.NET Core 2.0**, this step is optional.</span></span> <span data-ttu-id="c9da3-131">Der Befehl `dotnet restore` wird automatisch ausgeführt, wenn ein neues Projekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c9da3-131">The `dotnet restore` command executes automatically when a new project is created.</span></span>

4. <span data-ttu-id="c9da3-132">Führen Sie das „Hello World“-Programm aus:</span><span class="sxs-lookup"><span data-stu-id="c9da3-132">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="c9da3-133">Geben Sie `dotnet run` ein.</span><span class="sxs-lookup"><span data-stu-id="c9da3-133">Type `dotnet run`.</span></span> 

  ![Der Befehl „dotnet run“](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="c9da3-135">Um weitere Unterstützung beim Setup zu erhalten, können Sie sich auch ein kurzes Videotutorial zu [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) oder [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) ansehen.</span><span class="sxs-lookup"><span data-stu-id="c9da3-135">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="c9da3-136">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c9da3-136">Debug</span></span>
1. <span data-ttu-id="c9da3-137">Öffnen Sie *Program.cs*, indem Sie darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="c9da3-137">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="c9da3-138">Wenn Sie eine C#-Datei zum ersten Mal in Visual Studio Code öffnen, wird [OmniSharp](http://www.omnisharp.net/) in den Editor geladen.</span><span class="sxs-lookup"><span data-stu-id="c9da3-138">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) will load in the editor.</span></span>

  ![Öffnen der Datei „Program.cs“](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="c9da3-140">Visual Studio Code fordert Sie auf, die fehlenden Objekte zum Erstellen und Debuggen Ihrer App hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c9da3-140">Visual Studio Code will prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="c9da3-141">Wählen Sie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c9da3-141">Select **Yes**.</span></span> 

  ![Aufforderung bei fehlenden Objekten](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="c9da3-143">Um die Debugansicht zu öffnen, klicken Sie im Menü auf der linken Seite auf das Debugsymbol.</span><span class="sxs-lookup"><span data-stu-id="c9da3-143">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

  ![Öffnen der Registerkarte „Debuggen“](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="c9da3-145">Suchen Sie den grünen Pfeil am oberen Rand des Fensters.</span><span class="sxs-lookup"><span data-stu-id="c9da3-145">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="c9da3-146">Stellen Sie sicher, dass in der Dropdownliste die Option `.NET Core Launch (console)` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c9da3-146">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

  ![Auswählen von .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="c9da3-148">Fügen Sie einen Haltepunkt zu Ihrem Projekt hinzu, indem Sie neben Zeile 9 auf den **Rand des Editors** (der Bereich links neben den Zeilennummern im Editor) klicken.</span><span class="sxs-lookup"><span data-stu-id="c9da3-148">Add a breakpoint to your project by clicking on the **editor margin** (the space on the left of the line numbers in the editor) next to line 9.</span></span>

  ![Festlegen eines Haltepunkts](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="c9da3-150">Drücken Sie auf <kbd>F5</kbd>, oder klicken Sie auf den grünen Pfeil, um das Debuggen zu starten.</span><span class="sxs-lookup"><span data-stu-id="c9da3-150">Select <kbd>F5</kbd> or the green arrow to start debugging.</span></span> <span data-ttu-id="c9da3-151">Der Debugger hält die Ausführung des Programms an, wenn der Haltepunkt erreicht wird, den Sie im vorherigen Schritt festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="c9da3-151">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="c9da3-152">Während des Debuggens können Sie Ihre lokalen Variablen im oberen linken Bereich oder in der Debugkonsole anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c9da3-152">While debugging you can view your local variables in the top left pane or use the debug console.</span></span>

  ![Ausführen und Debuggen](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="c9da3-154">Wählen Sie im oberen Bereich den grünen Pfeil aus, um das Debuggen fortzusetzen, oder klicken Sie auf das rote Quadrat, um das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="c9da3-154">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="c9da3-155">Weitere Informationen und Tipps zur Problembehandlung beim .NET Core-Debuggen mit OmniSharp in Visual Studio Code finden Sie unter [Instructions for setting up the .NET Core debugger (Anleitung zum Einrichten des .NET Core-Debuggers)](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="c9da3-155">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c9da3-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9da3-156">See also</span></span>
<span data-ttu-id="c9da3-157">[Einrichten von Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span><span class="sxs-lookup"><span data-stu-id="c9da3-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
[<span data-ttu-id="c9da3-158">Debuggen in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c9da3-158">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)

