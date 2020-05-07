---
title: Erste Schritte mit C# und Visual Studio Code
description: Erfahren Sie, wie Sie Ihre erste .NET Core-Anwendung in C# mithilfe von Visual Studio Code erstellen und debuggen.
author: kendrahavens
ms.date: 04/23/2020
ms.openlocfilehash: 3dd7c4602fbb27e29bad977f8d3df34b6061bc23
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506889"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="90fea-103">Erste Schritte mit C# und Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="90fea-103">Get started with C# and Visual Studio Code</span></span>

<span data-ttu-id="90fea-104">.NET Core ist eine schnelle und modulare Plattform zum Erstellen von Anwendungen, die unter Windows, Linux und macOS ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="90fea-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="90fea-105">Verwenden Sie Visual Studio Code mit der C#-Erweiterung, um von leistungsfähigen Bearbeitungsfunktionen mit vollständiger Unterstützung für C# IntelliSense (intelligente Codevervollständigung) und Debugging zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="90fea-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="90fea-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="90fea-106">Prerequisites</span></span>

1. <span data-ttu-id="90fea-107">Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="90fea-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="90fea-108">Installieren Sie das [.NET Core SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="90fea-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>
3. <span data-ttu-id="90fea-109">Installieren Sie die [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) für Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="90fea-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="90fea-110">Weitere Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) (Marketplace für VS Code-Erweiterungen).</span><span class="sxs-lookup"><span data-stu-id="90fea-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="90fea-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="90fea-111">Hello World</span></span>

<span data-ttu-id="90fea-112">Beginnen wir mit einem einfachen Hallo-Welt-Programm in .NET Core:</span><span class="sxs-lookup"><span data-stu-id="90fea-112">Get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="90fea-113">Öffnen Sie ein Projekt:</span><span class="sxs-lookup"><span data-stu-id="90fea-113">Open a project:</span></span>

    - <span data-ttu-id="90fea-114">Öffnen Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="90fea-114">Open Visual Studio Code.</span></span>
    - <span data-ttu-id="90fea-115">Klicken Sie im Hauptmenü auf **Datei** > **Ordner öffnen**.</span><span class="sxs-lookup"><span data-stu-id="90fea-115">Select **File** > **Open Folder** from the main menu.</span></span>
    - <span data-ttu-id="90fea-116">Erstellen Sie einen Ordner mit dem Namen *HelloWorld*, und klicken Sie auf **Ordner auswählen**.</span><span class="sxs-lookup"><span data-stu-id="90fea-116">Create a folder named *HelloWorld*, and click **Select Folder**.</span></span> <span data-ttu-id="90fea-117">Der Name des Ordners wird standardmäßig zum Projektnamen und Namespacenamen.</span><span class="sxs-lookup"><span data-stu-id="90fea-117">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="90fea-118">Sie fügen später in diesem Tutorial Code hinzu, der erwartet, dass der Projektnamespace `HelloWorld` ist.</span><span class="sxs-lookup"><span data-stu-id="90fea-118">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="90fea-119">Initialisieren Sie ein C#-Projekt:</span><span class="sxs-lookup"><span data-stu-id="90fea-119">Initialize a C# project:</span></span>

    - <span data-ttu-id="90fea-120">Öffnen Sie das Terminal von Visual Studio Code, indem Sie im Hauptmenü auf **Ansicht** > **Terminal** klicken.</span><span class="sxs-lookup"><span data-stu-id="90fea-120">Open the Terminal from Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>
    - <span data-ttu-id="90fea-121">Geben Sie im Terminalfenster `dotnet new console` ein.</span><span class="sxs-lookup"><span data-stu-id="90fea-121">In the terminal window, enter `dotnet new console`.</span></span>

      <span data-ttu-id="90fea-122">Durch diesen Befehl wird eine Datei *Program.cs* in Ihrem Ordner erstellt, die ein bereits geschriebenes einfaches „Hello World“-Programm enthält. Zusätzlich wird eine C#-Projektdatei namens *HelloWorld.csproj* erstellt.</span><span class="sxs-lookup"><span data-stu-id="90fea-122">This command creates a *Program.cs* file in your folder with a simple "Hello World" program already written, along with a C# project file named *HelloWorld.csproj*.</span></span>

      ![Der Befehl „dotnet new“](media/with-visual-studio-code/dotnet-new-command.png)

1. <span data-ttu-id="90fea-124">Führen Sie das „Hello World“-Programm aus:</span><span class="sxs-lookup"><span data-stu-id="90fea-124">Run the "Hello World" program:</span></span>

    - <span data-ttu-id="90fea-125">Geben Sie im Terminalfenster `dotnet run` ein.</span><span class="sxs-lookup"><span data-stu-id="90fea-125">In the terminal window, enter `dotnet run`.</span></span>

      ![Der Befehl „dotnet run“](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="debug"></a><span data-ttu-id="90fea-127">Debug</span><span class="sxs-lookup"><span data-stu-id="90fea-127">Debug</span></span>

1. <span data-ttu-id="90fea-128">Öffnen Sie *Program.cs*, indem Sie darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="90fea-128">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="90fea-129">Wenn Sie eine C#-Datei zum ersten Mal in Visual Studio Code öffnen, wird [OmniSharp](https://www.omnisharp.net/) im Editor geladen.</span><span class="sxs-lookup"><span data-stu-id="90fea-129">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![Öffnen der Datei „Program.cs“](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="90fea-131">Visual Studio Code fordert Sie auf, die fehlenden Objekte zum Erstellen und Debuggen Ihrer App hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="90fea-131">Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="90fea-132">Wählen Sie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="90fea-132">Select **Yes**.</span></span>

    ![Aufforderung bei fehlenden Objekten](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="90fea-134">Um die Debugansicht zu öffnen, klicken Sie im Menü auf der linken Seite auf das Debugsymbol.</span><span class="sxs-lookup"><span data-stu-id="90fea-134">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Öffnen Sie die Registerkarte „Debuggen“ in Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

1. <span data-ttu-id="90fea-136">Suchen Sie den grünen Pfeil am oberen Rand des Fensters.</span><span class="sxs-lookup"><span data-stu-id="90fea-136">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="90fea-137">Stellen Sie sicher, dass in der Dropdownliste daneben die Option **.NET Core Launch (Console)** (.NET Core-Start (Konsole)) ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="90fea-137">Make sure the drop-down next to it has **.NET Core Launch (console)** selected.</span></span>

    ![Auswählen von .NET Core in Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

1. <span data-ttu-id="90fea-139">Fügen Sie einen Breakpoint zu Ihrem Projekt hinzu, indem Sie auf den **Rand des Editors** klicken. Dieser befindet sich links neben den Zeilennummern im Editor, neben Zeile 9. Alternativ können Sie den Textcursor im Editor in Zeile 9 bewegen und die Taste <kbd>F9</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="90fea-139">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![Festlegen eines Haltepunkts](media/with-visual-studio-code/set-breakpoint-vs-code.png)

1. <span data-ttu-id="90fea-141">Drücken Sie <kbd>F5</kbd>, oder klicken Sie auf den grünen Pfeil, um das Debuggen zu starten.</span><span class="sxs-lookup"><span data-stu-id="90fea-141">To start debugging, press <kbd>F5</kbd> or select the green arrow.</span></span> <span data-ttu-id="90fea-142">Der Debugger hält die Ausführung des Programms an, wenn der Haltepunkt erreicht wird, den Sie im vorherigen Schritt festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="90fea-142">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    - <span data-ttu-id="90fea-143">Während des Debuggens können Sie Ihre lokalen Variablen im oberen linken Bereich oder in der Debugkonsole anzeigen.</span><span class="sxs-lookup"><span data-stu-id="90fea-143">While debugging, you can view your local variables in the top-left pane or use the debug console.</span></span>

1. <span data-ttu-id="90fea-144">Wählen Sie im oberen Bereich den blauen Pfeil aus, um das Debuggen fortzusetzen, oder klicken Sie auf das rote Quadrat, um das Debuggen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="90fea-144">Select the blue arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

    ![Ausführen und Debuggen in Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> <span data-ttu-id="90fea-146">Weitere Informationen und Tipps zur Problembehandlung beim .NET Core-Debuggen mit OmniSharp in Visual Studio Code finden Sie unter [Instructions for setting up the .NET Core debugger (Anleitung zum Einrichten des .NET Core-Debuggers)](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="90fea-146">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="add-a-class"></a><span data-ttu-id="90fea-147">Hinzufügen einer Klasse</span><span class="sxs-lookup"><span data-stu-id="90fea-147">Add a class</span></span>

1. <span data-ttu-id="90fea-148">Klicken Sie im Visual Studio Code-Explorer mit der rechten Maustaste unter *Program.cs*, und klicken Sie dann auf **Neue Datei**, um eine neue Klasse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="90fea-148">To add a new class, right-click in the VSCode Explorer below *Program.cs* and select **New File**.</span></span> <span data-ttu-id="90fea-149">Dadurch wird dem Ordner, den Sie in Visual Studio Code geöffnet haben, eine neue Datei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="90fea-149">This adds a new file to the folder you have open in VSCode.</span></span>
1. <span data-ttu-id="90fea-150">Nennen Sie die Datei *MyClass.cs*.</span><span class="sxs-lookup"><span data-stu-id="90fea-150">Name your file *MyClass.cs*.</span></span> <span data-ttu-id="90fea-151">Sie müssen sie mit der `.cs`-Erweiterung speichern, damit sie als Csharp-Datei erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="90fea-151">You must save it with a `.cs` extension at the end for it to be recognized as a csharp file.</span></span>
1. <span data-ttu-id="90fea-152">Fügen Sie den folgenden Code hinzu, um Ihre erste Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="90fea-152">Add the following code to create your first class.</span></span>

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

1. <span data-ttu-id="90fea-153">Rufen Sie die neue Klasse über die `Main`-Methode auf, indem Sie den Code in *Program.cs* durch folgenden Code ersetzen:</span><span class="sxs-lookup"><span data-stu-id="90fea-153">Call your new class from your `Main` method by replacing the code in *Program.cs* with the following code:</span></span>

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

1. <span data-ttu-id="90fea-154">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="90fea-154">Save your changes.</span></span>

1. <span data-ttu-id="90fea-155">Führen Sie das Programm erneut aus.</span><span class="sxs-lookup"><span data-stu-id="90fea-155">Run the program again.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="90fea-156">Die neue Meldung wird mit der angefügten Zeichenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="90fea-156">The new message appears with the appended string.</span></span>

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a><span data-ttu-id="90fea-157">FAQ</span><span class="sxs-lookup"><span data-stu-id="90fea-157">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="90fea-158">Mir fehlen für das Erstellen und Debuggen von C# in Visual Studio Code die erforderlichen Objekte.</span><span class="sxs-lookup"><span data-stu-id="90fea-158">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="90fea-159">Mein Debugger gibt an: „Keine Konfiguration.“</span><span class="sxs-lookup"><span data-stu-id="90fea-159">My debugger says "No Configuration."</span></span>

<span data-ttu-id="90fea-160">Die C#-Erweiterung in Visual Studio Code kann Objekte zum Erstellen und Debuggen für Sie generieren.</span><span class="sxs-lookup"><span data-stu-id="90fea-160">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="90fea-161">Wenn Sie ein C#-Projekt zum ersten Mal öffnen, fordert Visual Studio Code Sie zur Generierung dieser Objekte auf.</span><span class="sxs-lookup"><span data-stu-id="90fea-161">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="90fea-162">Wenn Sie zu diesem Zeitpunkt keine Objekte generiert haben, können Sie diesen Befehl weiterhin ausführen, indem Sie die Befehlspalette ( **„Ansicht“ > „Befehlspalette“** ) öffnen und „>.NET: Objekte zum Erstellen und Debuggen generieren“ eingeben.</span><span class="sxs-lookup"><span data-stu-id="90fea-162">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="90fea-163">Durch diese Auswahl werden die erforderlichen Konfigurationsdateien *.vscode*, *launch.json* und *tasks.json* generiert.</span><span class="sxs-lookup"><span data-stu-id="90fea-163">Selecting this generates the *.vscode*, *launch.json*, and *tasks.json* configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="90fea-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90fea-164">See also</span></span>

- [<span data-ttu-id="90fea-165">Einrichten von Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="90fea-165">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)
- [<span data-ttu-id="90fea-166">Debuggen in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="90fea-166">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
