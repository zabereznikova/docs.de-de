---
title: Verwenden einer .NET Standard-Bibliothek in Visual Studio
description: Erstellen Sie eine .NET Core-Anwendung, die Member einer anderen Klassenbibliothek mit Visual Studio 2019 aufruft.
ms.date: 12/20/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4eb75f23359334ea483cba1498f1804c4b24c80c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920458"
---
# <a name="consume-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="a31c4-103">Verwenden einer .NET Standard-Bibliothek in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a31c4-103">Consume a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="a31c4-104">Nachdem Sie eine .NET Standard-Klassenbibliothek erstellt und getestet sowie eine Releaseversion der Bibliothek erstellt haben, besteht der nächste Schritt darin, diese für Aufrufer verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="a31c4-104">Once you've created a .NET Standard class library, tested it, and built a release version of the library, the next step is to make it available to callers.</span></span> <span data-ttu-id="a31c4-105">Dazu gibt es zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="a31c4-105">You can do this in two ways:</span></span>

- <span data-ttu-id="a31c4-106">Wenn die Bibliothek von einer einzelnen Projektmappe verwendet wird (wenn es sich z.B. um eine Komponente in einer großen Einzelanwendung handelt), können Sie die Bibliothek als Projekt in Ihre Projektmappe einfügen.</span><span class="sxs-lookup"><span data-stu-id="a31c4-106">If the library will be used by a single solution (for example, if it's a component in a single large application), you can include it as a project in your solution.</span></span>
- <span data-ttu-id="a31c4-107">Wenn die Bibliothek öffentlich verfügbar sein soll, können Sie sie als NuGet-Paket verteilen.</span><span class="sxs-lookup"><span data-stu-id="a31c4-107">If the library will be publicly available, you can distribute it as a NuGet package.</span></span>

<span data-ttu-id="a31c4-108">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="a31c4-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="a31c4-109">Fügen Sie der Projektmappe eine Konsolen-App hinzu, die auf ein .NET Standard-Bibliotheksprojekt verweist.</span><span class="sxs-lookup"><span data-stu-id="a31c4-109">Add a console app to your solution that references a .NET Standard library project.</span></span>
> - <span data-ttu-id="a31c4-110">Erstellen Sie ein NuGet-Paket, das ein .NET Standard-Bibliotheksprojekt enthält.</span><span class="sxs-lookup"><span data-stu-id="a31c4-110">Create a NuGet package that contains a .NET Standard library project.</span></span>

## <a name="add-a-console-app-to-your-solution"></a><span data-ttu-id="a31c4-111">Hinzufügen einer Konsolen-App zur Projektmappe</span><span class="sxs-lookup"><span data-stu-id="a31c4-111">Add a console app to your solution</span></span>

<span data-ttu-id="a31c4-112">Ebenso wie Sie unter [Testen einer .NET Standard-Bibliothek in Visual Studio](testing-library-with-visual-studio.md) Komponententests in dieselbe Projektmappe wie Ihre Klassenbibliothek einbezogen haben, können Sie Ihre Anwendung als Teil dieser Projektmappe einschließen.</span><span class="sxs-lookup"><span data-stu-id="a31c4-112">Just as you included unit tests in the same solution as your class library in [Test a .NET Standard library in Visual Studio](testing-library-with-visual-studio.md), you can include your application as part of that solution.</span></span> <span data-ttu-id="a31c4-113">Angenommen, Sie können Ihre Klassenbibliothek in einer Konsolenanwendung verwenden, die den Benutzer zur Eingabe einer Zeichenfolge auffordert und meldet, ob das erste Zeichen ein Großbuchstabe ist:</span><span class="sxs-lookup"><span data-stu-id="a31c4-113">For example, you can use your class library in a console application that prompts the user to enter a string and reports whether its first character is uppercase:</span></span>

1. <span data-ttu-id="a31c4-114">Öffnen Sie die `ClassLibraryProjects`-Projektmappe, die Sie im Artikel [Erstellen einer .NET Standard-Bibliothek in Visual Studio](library-with-visual-studio.md) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a31c4-114">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="a31c4-115">Fügen Sie der Projektmappe eine neue .NET Core-Konsolenanwendung mit dem Namen „ShowCase“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="a31c4-115">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="a31c4-116">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="a31c4-116">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="a31c4-117">Geben Sie auf der Seite **Neues Projekt hinzufügen** die Angabe **Konsole** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="a31c4-117">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="a31c4-118">Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.</span><span class="sxs-lookup"><span data-stu-id="a31c4-118">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="a31c4-119">Wählen Sie die Vorlage **Konsolen-App (.NET Core)** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="a31c4-119">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="a31c4-120">Geben Sie **ShowCase** auf der Seite **Neues Projekt konfigurieren** in das Feld **Projektname** ein.</span><span class="sxs-lookup"><span data-stu-id="a31c4-120">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="a31c4-121">Wählen Sie anschließend **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="a31c4-121">Then, choose **Create**.</span></span>

1. <span data-ttu-id="a31c4-122">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **ShowCase**-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="a31c4-122">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Visual Studio-Projektkontextmenü zum Festlegen des Startprojekts](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="a31c4-124">Zunächst hat Ihr Projekt keinen Zugriff auf unsere Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="a31c4-124">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="a31c4-125">Damit es Methoden in Ihrer Klassenbibliothek aufrufen kann, erstellen Sie einen Verweis auf die Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="a31c4-125">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="a31c4-126">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten `ShowCase`Abhängigkeiten**des**-Projekts, und wählen Sie **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="a31c4-126">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![Kontextmenü „Verweis hinzufügen“ in Visual Studio](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="a31c4-128">Wählen Sie im Dialogfeld **Verweis-Manager** **StringLibrary**, Ihr Klassenbibliotheksprojekt, aus, und klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="a31c4-128">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![Dialogfeld „Verweis-Manager“ mit ausgewählter StringLibrary](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="a31c4-130">Ersetzen Sie im Codefenster für die Datei *Program.cs* oder *Program.vb* den gesamten Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="a31c4-130">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code:</span></span>

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   <span data-ttu-id="a31c4-131">Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten.</span><span class="sxs-lookup"><span data-stu-id="a31c4-131">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="a31c4-132">Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="a31c4-132">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="a31c4-133">Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="a31c4-133">The program prompts the user to enter a string.</span></span> <span data-ttu-id="a31c4-134">Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="a31c4-134">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="a31c4-135">Wenn der Benutzer die EINGABETASTE drückt, ohne eine Zeichenfolge einzugeben, wird die Anwendung beendet und das Konsolenfenster geschlossen.</span><span class="sxs-lookup"><span data-stu-id="a31c4-135">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="a31c4-136">Ändern Sie ggf. die Symbolleiste, um das**Debugrelease** des `ShowCase`-Projekts zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a31c4-136">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="a31c4-137">Kompilieren Sie das Programm, und führen Sie es anschließend aus, indem Sie auf den grünen Pfeil auf der Schaltfläche **ShowCase** klicken.</span><span class="sxs-lookup"><span data-stu-id="a31c4-137">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![Visual Studio-Projektsymbolleiste mit Schaltfläche „Debuggen“](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

<span data-ttu-id="a31c4-139">Sie können die Anwendung, die diese Bibliothek verwendet, debuggen und veröffentlichen, indem Sie die Schritte unter [Debuggen Ihrer C# oder Visual Basic .NET Core Hello World-Anwendung mit Visual Studio](debugging-with-visual-studio.md) und [Veröffentlichen Ihrer .NET Core Hello World-Anwendung mit Visual Studio](publishing-with-visual-studio.md) ausführen.</span><span class="sxs-lookup"><span data-stu-id="a31c4-139">You can debug and publish the application that uses this library by following the steps in [Debug your C# or Visual Basic .NET Core Hello World application using Visual Studio](debugging-with-visual-studio.md) and [Publish your .NET Core Hello World application with Visual Studio](publishing-with-visual-studio.md).</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="a31c4-140">Erstellen eines NuGet-Pakets</span><span class="sxs-lookup"><span data-stu-id="a31c4-140">Create a NuGet package</span></span>

<span data-ttu-id="a31c4-141">Sie können Ihre Klassenbibliothek allgemein verfügbar machen, indem Sie sie als NuGet-Paket veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a31c4-141">You can make your class library widely available by publishing it as a NuGet package.</span></span> <span data-ttu-id="a31c4-142">Visual Studio bietet keine Unterstützung für das Erstellen von NuGet-Paketen.</span><span class="sxs-lookup"><span data-stu-id="a31c4-142">Visual Studio doesn't support the creation of NuGet packages.</span></span> <span data-ttu-id="a31c4-143">Um ein solches Paket zu erstellen, müssen Sie die .NET Core-CLI-Befehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="a31c4-143">To create one, you need to use the .NET Core CLI commands:</span></span>

1. <span data-ttu-id="a31c4-144">Öffnen Sie ein Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="a31c4-144">Open a console window.</span></span>

   <span data-ttu-id="a31c4-145">Geben Sie beispielsweise **Eingabeaufforderung** in das Suchfeld auf der Windows-Taskleiste ein.</span><span class="sxs-lookup"><span data-stu-id="a31c4-145">For example, enter **Command Prompt** in the search box on the Windows task bar.</span></span> <span data-ttu-id="a31c4-146">Wählen Sie die Desktop-App **Eingabeaufforderung** aus, oder drücken Sie die **EINGABETASTE**, wenn sie in den Suchergebnissen bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a31c4-146">Select the **Command Prompt** desktop app or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="a31c4-147">Navigieren Sie zum Projektverzeichnis Ihrer Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="a31c4-147">Navigate to your library's project directory.</span></span> <span data-ttu-id="a31c4-148">Das Verzeichnis enthält Ihren Quellcode und eine Projektdatei (*StringLibrary.csproj* oder *StringLibrary.vbproj*).</span><span class="sxs-lookup"><span data-stu-id="a31c4-148">The directory contains your source code and a project file, *StringLibrary.csproj* or *StringLibrary.vbproj*.</span></span>

1. <span data-ttu-id="a31c4-149">Führen Sie den Befehl [dotnet pack](../tools/dotnet-pack.md) aus, um ein Paket mit der Erweiterung *.nupkg* zu generieren:</span><span class="sxs-lookup"><span data-stu-id="a31c4-149">Run the [dotnet pack](../tools/dotnet-pack.md) command to generate a package with a *.nupkg* extension:</span></span>

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > <span data-ttu-id="a31c4-150">Wenn sich das Verzeichnis, das die Datei *dotnet.exe* enthält, nicht in Ihrem Pfad befindet, können Sie ihren Speicherort ermitteln, indem Sie im Konsolenfenster `where dotnet.exe` eingeben.</span><span class="sxs-lookup"><span data-stu-id="a31c4-150">If the directory that contains *dotnet.exe* is not in your PATH, you can find its location by entering `where dotnet.exe` in the console window.</span></span>

<span data-ttu-id="a31c4-151">Weitere Informationen zum Erstellen von NuGet-Paketen finden Sie unter [Erstellen eines NuGet-Pakets mit der .NET Core-CLI](../deploying/creating-nuget-packages.md).</span><span class="sxs-lookup"><span data-stu-id="a31c4-151">For more information on creating NuGet packages, see [How to create a NuGet package with the .NET Core CLI](../deploying/creating-nuget-packages.md).</span></span>
