---
title: Erste Schritte mit C# und Visual Studio Code (C#-Handbuch)
description: Erfahren Sie, wie Sie Ihre erste .NET Core-Anwendung in C# mithilfe von Visual Studio Code erstellen und debuggen.
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.openlocfilehash: 8958c39ba16cadbfab95e35fa36e8e85ce0a4ab8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="8959e-103">Erste Schritte mit C# und Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8959e-103">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="8959e-104">.NET Core ist eine schnelle und modulare Plattform zum Erstellen von Anwendungen, die unter Windows, Linux und macOS ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8959e-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="8959e-105">Verwenden Sie Visual Studio Code mit der C#-Erweiterung, um von leistungsfähigen Bearbeitungsfunktionen mit vollständiger Unterstützung für C# IntelliSense (intelligente Codevervollständigung) und Debugging zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="8959e-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8959e-106">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="8959e-106">Prerequisites</span></span>

1. <span data-ttu-id="8959e-107">Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="8959e-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="8959e-108">Installieren Sie das [.NET Core SDK](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="8959e-108">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="8959e-109">Installieren Sie die [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) für Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8959e-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="8959e-110">Weitere Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) (Marketplace für VS Code-Erweiterungen).</span><span class="sxs-lookup"><span data-stu-id="8959e-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="8959e-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="8959e-111">Hello World</span></span>

<span data-ttu-id="8959e-112">Beginnen wir mit einem einfachen „Hello World“-Programm in .NET Core:</span><span class="sxs-lookup"><span data-stu-id="8959e-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="8959e-113">Öffnen Sie ein Projekt:</span><span class="sxs-lookup"><span data-stu-id="8959e-113">Open a project:</span></span>

    * <span data-ttu-id="8959e-114">Öffnen Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8959e-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="8959e-115">Klicken Sie im linken Menü auf das Explorer-Symbol, und klicken Sie dann auf **Ordner öffnen**.</span><span class="sxs-lookup"><span data-stu-id="8959e-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="8959e-116">Klicken Sie im Hauptmenü auf **Datei** > **Open Folder** (Ordner öffnen), um den Ordner zu öffnen, in dem Sie Ihr C#-Projekt speichern möchten, und klicken Sie auf **Ordner auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8959e-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="8959e-117">Für dieses Beispiel wird ein Ordner namens *HelloWorld* für das Projekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="8959e-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. <span data-ttu-id="8959e-119">Initialisieren Sie ein C#-Projekt:</span><span class="sxs-lookup"><span data-stu-id="8959e-119">Initialize a C# project:</span></span>
    * <span data-ttu-id="8959e-120">Öffnen Sie das integrierte Terminal von Visual Studio Code, indem Sie im Hauptmenü auf **Ansicht** > **Integriertes Terminal** klicken.</span><span class="sxs-lookup"><span data-stu-id="8959e-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="8959e-121">Geben Sie im Terminalfenster `dotnet new console` ein.</span><span class="sxs-lookup"><span data-stu-id="8959e-121">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="8959e-122">Durch diesen Befehl wird eine `Program.cs`-Datei in Ihrem Ordner erstellt, die ein bereits geschriebenes einfaches „Hallo Welt“-Programm enthält. Zusätzlich wird eine C#-Projektdatei namens `HelloWorld.csproj` erstellt.</span><span class="sxs-lookup"><span data-stu-id="8959e-122">This command creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

      ![Der Befehl „dotnet new“](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="8959e-124">Lösen Sie die Buildobjekte auf:</span><span class="sxs-lookup"><span data-stu-id="8959e-124">Resolve the build assets:</span></span>

    * <span data-ttu-id="8959e-125">Geben Sie für **.NET Core 1.x** den Befehl `dotnet restore` ein.</span><span class="sxs-lookup"><span data-stu-id="8959e-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="8959e-126">Durch Ausführen von `dotnet restore` erhalten Sie Zugriff auf die erforderlichen .NET Core-Pakete, die Sie zum Erstellen Ihres Projekts benötigen.</span><span class="sxs-lookup"><span data-stu-id="8959e-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![Der Befehl „dotnet restore“](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="8959e-128">Führen Sie das „Hello World“-Programm aus:</span><span class="sxs-lookup"><span data-stu-id="8959e-128">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="8959e-129">Geben Sie `dotnet run` ein.</span><span class="sxs-lookup"><span data-stu-id="8959e-129">Type `dotnet run`.</span></span> 

      ![Der Befehl „dotnet run“](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="8959e-131">Um weitere Unterstützung beim Setup zu erhalten, können Sie sich auch ein kurzes Videotutorial zu [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) oder [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) ansehen.</span><span class="sxs-lookup"><span data-stu-id="8959e-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="8959e-132">Debug</span><span class="sxs-lookup"><span data-stu-id="8959e-132">Debug</span></span>

1. <span data-ttu-id="8959e-133">Öffnen Sie *Program.cs*, indem Sie darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="8959e-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="8959e-134">Wenn Sie eine C#-Datei zum ersten Mal in Visual Studio Code öffnen, wird [OmniSharp](http://www.omnisharp.net/) im Editor geladen.</span><span class="sxs-lookup"><span data-stu-id="8959e-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) loads in the editor.</span></span>

    ![Öffnen der Datei „Program.cs“](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="8959e-136">Visual Studio Code fordert Sie dazu auf, die fehlenden Objekte zum Erstellen und Debuggen Ihrer App hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8959e-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="8959e-137">Wählen Sie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8959e-137">Select **Yes**.</span></span> 

    ![Aufforderung bei fehlenden Objekten](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="8959e-139">Um die Debugansicht zu öffnen, klicken Sie im Menü auf der linken Seite auf das Debugsymbol.</span><span class="sxs-lookup"><span data-stu-id="8959e-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Öffnen der Registerkarte „Debuggen“](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="8959e-141">Suchen Sie den grünen Pfeil am oberen Rand des Fensters.</span><span class="sxs-lookup"><span data-stu-id="8959e-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="8959e-142">Stellen Sie sicher, dass in der Dropdownliste die Option `.NET Core Launch (console)` ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="8959e-142">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

    ![Auswählen von .NET Core](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="8959e-144">Fügen Sie einen Breakpoint zu Ihrem Projekt hinzu, indem Sie neben Zeile 9 auf den **Rand des Editors** (der Bereich links neben den Zeilennummern im Editor) klicken.</span><span class="sxs-lookup"><span data-stu-id="8959e-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9.</span></span>

    ![Festlegen eines Haltepunkts](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="8959e-146">Drücken Sie <kbd>F5</kbd>, oder klicken Sie auf den grünen Pfeil, um das Debuggen zu starten.</span><span class="sxs-lookup"><span data-stu-id="8959e-146">To start debugging, select <kbd>F5</kbd> or the green arrow.</span></span> <span data-ttu-id="8959e-147">Der Debugger hält die Ausführung des Programms an, wenn der Haltepunkt erreicht wird, den Sie im vorherigen Schritt festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="8959e-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="8959e-148">Während des Debuggens können Sie Ihre lokalen Variablen im oberen linken Bereich oder in der Debugkonsole anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8959e-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

    ![Ausführen und Debuggen](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="8959e-150">Wählen Sie im oberen Bereich den grünen Pfeil aus, um das Debuggen fortzusetzen, oder klicken Sie auf das rote Quadrat, um das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="8959e-150">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="8959e-151">Weitere Informationen und Tipps zur Problembehandlung beim .NET Core-Debuggen mit OmniSharp in Visual Studio Code finden Sie unter [Instructions for setting up the .NET Core debugger (Anleitung zum Einrichten des .NET Core-Debuggers)](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="8959e-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8959e-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8959e-152">See also</span></span>
<span data-ttu-id="8959e-153">[Einrichten von Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span><span class="sxs-lookup"><span data-stu-id="8959e-153">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
[<span data-ttu-id="8959e-154">Debuggen in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8959e-154">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
