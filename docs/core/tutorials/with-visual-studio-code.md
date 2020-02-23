---
title: Erste Schritte mit C# und Visual Studio Code
description: Erfahren Sie, wie Sie Ihre erste .NET Core-Anwendung in C# mithilfe von Visual Studio Code erstellen und debuggen.
author: kendrahavens
ms.date: 12/05/2018
ms.openlocfilehash: acd1c300545bc6c107552576180afd7dec6b7382
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503519"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="01dd2-103">Erste Schritte mit C# und Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="01dd2-103">Get started with C# and Visual Studio Code</span></span>

<span data-ttu-id="01dd2-104">.NET Core ist eine schnelle und modulare Plattform zum Erstellen von Anwendungen, die unter Windows, Linux und macOS ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="01dd2-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="01dd2-105">Verwenden Sie Visual Studio Code mit der C#-Erweiterung, um von leistungsfähigen Bearbeitungsfunktionen mit vollständiger Unterstützung für C# IntelliSense (intelligente Codevervollständigung) und Debugging zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="01dd2-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="01dd2-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="01dd2-106">Prerequisites</span></span>

1. <span data-ttu-id="01dd2-107">Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="01dd2-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="01dd2-108">Installieren Sie das [.NET Core SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="01dd2-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>
3. <span data-ttu-id="01dd2-109">Installieren Sie die [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) für Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="01dd2-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="01dd2-110">Weitere Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) (Marketplace für VS Code-Erweiterungen).</span><span class="sxs-lookup"><span data-stu-id="01dd2-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="01dd2-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="01dd2-111">Hello World</span></span>

<span data-ttu-id="01dd2-112">Beginnen wir mit einem einfachen „Hello World“-Programm in .NET Core:</span><span class="sxs-lookup"><span data-stu-id="01dd2-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="01dd2-113">Öffnen Sie ein Projekt:</span><span class="sxs-lookup"><span data-stu-id="01dd2-113">Open a project:</span></span>

    - <span data-ttu-id="01dd2-114">Öffnen Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="01dd2-114">Open Visual Studio Code.</span></span>
    - <span data-ttu-id="01dd2-115">Klicken Sie im linken Menü auf das Explorer-Symbol, und klicken Sie dann auf **Ordner öffnen**.</span><span class="sxs-lookup"><span data-stu-id="01dd2-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    - <span data-ttu-id="01dd2-116">Klicken Sie im Hauptmenü auf **Datei** > **Open Folder** (Ordner öffnen), um den Ordner zu öffnen, in dem Sie Ihr C#-Projekt speichern möchten, und klicken Sie auf **Ordner auswählen**.</span><span class="sxs-lookup"><span data-stu-id="01dd2-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="01dd2-117">Für dieses Beispiel wird ein Ordner namens *HelloWorld* für das Projekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="01dd2-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![Visual Studio Code, Ordner öffnen](media/with-visual-studio-code/vs-code-open-folder.png)

2. <span data-ttu-id="01dd2-119">Initialisieren Sie ein C#-Projekt:</span><span class="sxs-lookup"><span data-stu-id="01dd2-119">Initialize a C# project:</span></span>

    - <span data-ttu-id="01dd2-120">Öffnen Sie das integrierte Terminal von Visual Studio Code, indem Sie im Hauptmenü auf **Ansicht** > **Integriertes Terminal** klicken.</span><span class="sxs-lookup"><span data-stu-id="01dd2-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    - <span data-ttu-id="01dd2-121">Geben Sie im Terminalfenster `dotnet new console` ein.</span><span class="sxs-lookup"><span data-stu-id="01dd2-121">In the terminal window, type `dotnet new console`.</span></span>
    - <span data-ttu-id="01dd2-122">Durch diesen Befehl wird eine Datei *Program.cs* in Ihrem Ordner erstellt, die ein bereits geschriebenes einfaches „Hello World“-Programm enthält. Zusätzlich wird eine C#-Projektdatei namens *HelloWorld.csproj* erstellt.</span><span class="sxs-lookup"><span data-stu-id="01dd2-122">This command creates a *Program.cs* file in your folder with a simple "Hello World" program already written, along with a C# project file named *HelloWorld.csproj*.</span></span>

      ![Der Befehl „dotnet new“](media/with-visual-studio-code/dotnet-new-command.png)

3. <span data-ttu-id="01dd2-124">Lösen Sie die Buildobjekte auf:</span><span class="sxs-lookup"><span data-stu-id="01dd2-124">Resolve the build assets:</span></span>

    - <span data-ttu-id="01dd2-125">Geben Sie für **.NET Core 1.x** den Befehl `dotnet restore` ein.</span><span class="sxs-lookup"><span data-stu-id="01dd2-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="01dd2-126">Durch Ausführen von `dotnet restore` erhalten Sie Zugriff auf die erforderlichen .NET Core-Pakete, die Sie zum Erstellen Ihres Projekts benötigen.</span><span class="sxs-lookup"><span data-stu-id="01dd2-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![Der Befehl „dotnet restore“](media/with-visual-studio-code/dotnet-restore-command.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="01dd2-128">Führen Sie das „Hello World“-Programm aus:</span><span class="sxs-lookup"><span data-stu-id="01dd2-128">Run the "Hello World" program:</span></span>

    - <span data-ttu-id="01dd2-129">Geben Sie `dotnet run` ein.</span><span class="sxs-lookup"><span data-stu-id="01dd2-129">Type `dotnet run`.</span></span>

      ![Der Befehl „dotnet run“](media/with-visual-studio-code/dotnet-run-command.png)

<span data-ttu-id="01dd2-131">Um weitere Unterstützung beim Setup zu erhalten, können Sie sich auch ein kurzes Videotutorial zu [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) oder [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) ansehen.</span><span class="sxs-lookup"><span data-stu-id="01dd2-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="01dd2-132">Debug</span><span class="sxs-lookup"><span data-stu-id="01dd2-132">Debug</span></span>

1. <span data-ttu-id="01dd2-133">Öffnen Sie *Program.cs*, indem Sie darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="01dd2-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="01dd2-134">Wenn Sie eine C#-Datei zum ersten Mal in Visual Studio Code öffnen, wird [OmniSharp](https://www.omnisharp.net/) im Editor geladen.</span><span class="sxs-lookup"><span data-stu-id="01dd2-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![Öffnen der Datei „Program.cs“](media/with-visual-studio-code/open-program-cs.png)

2. <span data-ttu-id="01dd2-136">Visual Studio Code fordert Sie dazu auf, die fehlenden Objekte zum Erstellen und Debuggen Ihrer App hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="01dd2-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="01dd2-137">Wählen Sie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="01dd2-137">Select **Yes**.</span></span>

    ![Aufforderung bei fehlenden Objekten](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="01dd2-139">Um die Debugansicht zu öffnen, klicken Sie im Menü auf der linken Seite auf das Debugsymbol.</span><span class="sxs-lookup"><span data-stu-id="01dd2-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Öffnen Sie die Registerkarte „Debuggen“ in Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

4. <span data-ttu-id="01dd2-141">Suchen Sie den grünen Pfeil am oberen Rand des Fensters.</span><span class="sxs-lookup"><span data-stu-id="01dd2-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="01dd2-142">Stellen Sie sicher, dass in der Dropdownliste daneben die Option **.NET Core Launch (Console)** (.NET Core-Start (Konsole)) ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="01dd2-142">Make sure the drop-down next to it has **.NET Core Launch (console)** selected.</span></span>

    ![Auswählen von .NET Core in Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

5. <span data-ttu-id="01dd2-144">Fügen Sie einen Breakpoint zu Ihrem Projekt hinzu, indem Sie auf den **Rand des Editors** klicken. Dieser befindet sich links neben den Zeilennummern im Editor, neben Zeile 9. Alternativ können Sie den Textcursor im Editor in Zeile 9 bewegen und die Taste <kbd>F9</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="01dd2-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![Festlegen eines Haltepunkts](media/with-visual-studio-code/set-breakpoint-vs-code.png)

6. <span data-ttu-id="01dd2-146">Drücken Sie <kbd>F5</kbd>, oder klicken Sie auf den grünen Pfeil, um das Debuggen zu starten.</span><span class="sxs-lookup"><span data-stu-id="01dd2-146">To start debugging, press <kbd>F5</kbd> or select the green arrow.</span></span> <span data-ttu-id="01dd2-147">Der Debugger hält die Ausführung des Programms an, wenn der Haltepunkt erreicht wird, den Sie im vorherigen Schritt festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="01dd2-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    - <span data-ttu-id="01dd2-148">Während des Debuggens können Sie Ihre lokalen Variablen im oberen linken Bereich oder in der Debugkonsole anzeigen.</span><span class="sxs-lookup"><span data-stu-id="01dd2-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

7. <span data-ttu-id="01dd2-149">Wählen Sie im oberen Bereich den blauen Pfeil aus, um das Debuggen fortzusetzen, oder klicken Sie auf das rote Quadrat, um das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="01dd2-149">Select the blue arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

    ![Ausführen und Debuggen in Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> <span data-ttu-id="01dd2-151">Weitere Informationen und Tipps zur Problembehandlung beim .NET Core-Debuggen mit OmniSharp in Visual Studio Code finden Sie unter [Instructions for setting up the .NET Core debugger (Anleitung zum Einrichten des .NET Core-Debuggers)](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="01dd2-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="add-a-class"></a><span data-ttu-id="01dd2-152">Hinzufügen einer Klasse</span><span class="sxs-lookup"><span data-stu-id="01dd2-152">Add a class</span></span>

1. <span data-ttu-id="01dd2-153">Um eine neue Klasse hinzuzufügen, klicken Sie mit der rechten Maustaste auf den VSCode-Explorer, und wählen Sie **Neue Datei** aus.</span><span class="sxs-lookup"><span data-stu-id="01dd2-153">To add a new class, right click in the VSCode Explorer and select **New File**.</span></span> <span data-ttu-id="01dd2-154">Dadurch wird dem Ordner, den Sie in Visual Studio Code geöffnet haben, eine neue Datei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="01dd2-154">This adds a new file to the folder you have open in VSCode.</span></span>
2. <span data-ttu-id="01dd2-155">Nennen Sie die Datei *MyClass.cs*.</span><span class="sxs-lookup"><span data-stu-id="01dd2-155">Name your file *MyClass.cs*.</span></span> <span data-ttu-id="01dd2-156">Sie müssen sie mit der `.cs`-Erweiterung speichern, damit sie als Csharp-Datei erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="01dd2-156">You must save it with a `.cs` extension at the end for it to be recognized as a csharp file.</span></span>
3. <span data-ttu-id="01dd2-157">Fügen Sie den folgenden Code zum Erstellen Ihrer ersten Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="01dd2-157">Add the code below to create your first class.</span></span> <span data-ttu-id="01dd2-158">Achten Sie darauf, den richtigen Namespace einzubeziehen, damit Sie aus Ihrer Datei *Program.cs* darauf verweisen können:</span><span class="sxs-lookup"><span data-stu-id="01dd2-158">Make sure to include the correct namespace so you can reference it from your *Program.cs* file:</span></span>

    ``` csharp
    using System;

    namespace HelloWorld
    {
        public class MyClass
        {
            public string ReturnMessage()
            {
                return "Happy coding!";
            }
        }
    }
    ```

4. <span data-ttu-id="01dd2-159">Rufen Sie die neue Klasse aus Ihrer Main-Methode in *Program.cs* auf, indem Sie den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="01dd2-159">Call your new class from your main method in *Program.cs* by adding the code below:</span></span>

    ```csharp
    using System;
    
    namespace HelloWorld
    {
        class Program
        {
            static void Main(string[] args)
            {
                var c1 = new MyClass();
                Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
            }
        }
    }
    ```

5. <span data-ttu-id="01dd2-160">Speichern Sie die Änderungen, und führen Sie das Programm erneut aus.</span><span class="sxs-lookup"><span data-stu-id="01dd2-160">Save your changes and run your program again.</span></span> <span data-ttu-id="01dd2-161">Die neue Nachricht sollte mit der angefügten Zeichenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="01dd2-161">The new message should appear with the appended string.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="01dd2-162">Sie erhalten die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="01dd2-162">You get the following output:</span></span>

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a><span data-ttu-id="01dd2-163">FAQ</span><span class="sxs-lookup"><span data-stu-id="01dd2-163">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="01dd2-164">Mir fehlen für das Erstellen und Debuggen von C# in Visual Studio Code die erforderlichen Objekte.</span><span class="sxs-lookup"><span data-stu-id="01dd2-164">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="01dd2-165">Mein Debugger gibt an: „Keine Konfiguration.“</span><span class="sxs-lookup"><span data-stu-id="01dd2-165">My debugger says "No Configuration."</span></span>

<span data-ttu-id="01dd2-166">Die C#-Erweiterung in Visual Studio Code kann Objekte zum Erstellen und Debuggen für Sie generieren.</span><span class="sxs-lookup"><span data-stu-id="01dd2-166">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="01dd2-167">Wenn Sie ein C#-Projekt zum ersten Mal öffnen, fordert Visual Studio Code Sie zur Generierung dieser Objekte auf.</span><span class="sxs-lookup"><span data-stu-id="01dd2-167">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="01dd2-168">Wenn Sie zu diesem Zeitpunkt keine Objekte generiert haben, können Sie diesen Befehl weiterhin ausführen, indem Sie die Befehlspalette ( **„Ansicht“ > „Befehlspalette“** ) öffnen und „>.NET: Objekte zum Erstellen und Debuggen generieren“ eingeben.</span><span class="sxs-lookup"><span data-stu-id="01dd2-168">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="01dd2-169">Durch diese Auswahl werden die erforderlichen Konfigurationsdateien *.vscode*, *launch.json* und *tasks.json* generiert.</span><span class="sxs-lookup"><span data-stu-id="01dd2-169">Selecting this generates the *.vscode*, *launch.json*, and *tasks.json* configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="01dd2-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01dd2-170">See also</span></span>

- [<span data-ttu-id="01dd2-171">Einrichten von Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="01dd2-171">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)
- [<span data-ttu-id="01dd2-172">Debuggen in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="01dd2-172">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
