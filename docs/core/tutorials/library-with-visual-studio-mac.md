---
title: Erstellen einer .NET Standard-Klassenbibliothek in Visual Studio für Mac
description: Erfahren Sie, wie Sie eine .NET Standard-Klassenbibliothek mit Visual Studio für Mac erstellen.
ms.date: 06/08/2020
ms.openlocfilehash: 8e1e4ca3bc1b12d889b847d80318f3d6cd1bbe46
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416002"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-for-mac"></a><span data-ttu-id="2de3d-103">Tutorial: Erstellen einer .NET-Standard-Bibliothek in Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="2de3d-103">Tutorial: Create a .NET Standard library using Visual Studio for Mac</span></span>

<span data-ttu-id="2de3d-104">In diesem Tutorial erstellen Sie eine einfache Klassenbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="2de3d-104">In this tutorial, you create a class library that contains a single string-handling method.</span></span> <span data-ttu-id="2de3d-105">Sie implementieren sie als [Erweiterungsmethode](../../csharp/programming-guide/classes-and-structs/extension-methods.md), damit sie aufgerufen werden kann, als wäre sie ein Mitglied der <xref:System.String>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2de3d-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="2de3d-106">Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="2de3d-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="2de3d-107">Eine Klassenbibliothek, die auf .NET Standard 2.1 abzielt, kann von einer Anwendung genutzt werden, die auf jede .NET-Implementierung abzielt, die Version 2.1 von .NET Standard unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2de3d-107">A class library that targets .NET Standard 2.1 can be used by an application that targets any .NET implementation that supports version 2.1 of .NET Standard.</span></span> <span data-ttu-id="2de3d-108">Wenn Sie Ihre Klassenbibliothek fertig gestellt haben, können Sie sie als Komponente eines Drittanbieters oder als gebündelte Komponente mit einer oder mehreren Anwendungen verteilen.</span><span class="sxs-lookup"><span data-stu-id="2de3d-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="2de3d-109">Ihr Feedback ist uns sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="2de3d-109">Your feedback is highly valued.</span></span> <span data-ttu-id="2de3d-110">Es gibt zwei Möglichkeiten, wie Sie Feedback für das Entwicklungsteam von Visual Studio für Mac bereitstellen können:</span><span class="sxs-lookup"><span data-stu-id="2de3d-110">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> - <span data-ttu-id="2de3d-111">Klicken Sie in Visual Studio für Mac auf **Hilfe** > **Ein Problem melden** im Menü oder auf **Ein Problem melden** auf der Willkommensseite. Dadurch wird ein Fenster für das Einreichen eines Fehlerberichts geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2de3d-111">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="2de3d-112">Sie können Ihr Feedback im Portal der [Entwicklercommunity](https://developercommunity.visualstudio.com/spaces/41/index.html) verfolgen.</span><span class="sxs-lookup"><span data-stu-id="2de3d-112">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html) portal.</span></span>
> - <span data-ttu-id="2de3d-113">Um einen Vorschlag zu machen, wählen Sie **Hilfe** > **Vorschlag senden** im Menü oder **Vorschlag senden** auf der Willkommensseite aus. Dadurch gelangen Sie zur Webseite [Visual Studio für Mac-Entwicklercommunity](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="2de3d-113">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2de3d-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2de3d-114">Prerequisites</span></span>

* <span data-ttu-id="2de3d-115">[Installieren von Visual Studio für Mac Version 8.6 oder höher](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="2de3d-115">[Install Visual Studio for Mac version 8.6 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="2de3d-116">Wählen Sie die Option zum Installieren von .NET Core aus.</span><span class="sxs-lookup"><span data-stu-id="2de3d-116">Select the option to install .NET Core.</span></span> <span data-ttu-id="2de3d-117">Die Installation von Xamarin ist für die Entwicklung mit .NET Core optional.</span><span class="sxs-lookup"><span data-stu-id="2de3d-117">Installing Xamarin is optional for .NET Core development.</span></span> <span data-ttu-id="2de3d-118">Weitere Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="2de3d-118">For more information, see the following resources:</span></span>

  * <span data-ttu-id="2de3d-119">[Tutorial: Installieren von Visual Studio für Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="2de3d-119">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="2de3d-120">[Unterstützte macOS-Versionen](../install/dependencies.md?pivots=os-macos)</span><span class="sxs-lookup"><span data-stu-id="2de3d-120">[Supported macOS versions](../install/dependencies.md?pivots=os-macos).</span></span>
  * <span data-ttu-id="2de3d-121">[Von Visual Studio für Mac unterstützte .NET Core-Versionen](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="2de3d-121">[.NET Core versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-a-solution-with-a-class-library-project"></a><span data-ttu-id="2de3d-122">Erstellen einer Projektmappe mit einem Klassenbibliotheksprojekt</span><span class="sxs-lookup"><span data-stu-id="2de3d-122">Create a solution with a class library project</span></span>

<span data-ttu-id="2de3d-123">Eine Visual Studio-Projektmappe dient als ein Container für mindestens ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="2de3d-123">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="2de3d-124">Erstellen Sie eine Projektmappe und darin ein Klassenbibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="2de3d-124">Create a solution and a class library project in the solution.</span></span> <span data-ttu-id="2de3d-125">Sie fügen später der gleichen Projektmappe weitere verwandte Projekte hinzu.</span><span class="sxs-lookup"><span data-stu-id="2de3d-125">You'll add additional, related projects to the same solution later.</span></span>

1. <span data-ttu-id="2de3d-126">Starten Sie Visual Studio für Mac.</span><span class="sxs-lookup"><span data-stu-id="2de3d-126">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="2de3d-127">Wählen Sie im Startfenster **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="2de3d-127">In the start window, select **New Project**.</span></span>

1. <span data-ttu-id="2de3d-128">Wählen Sie im Dialogfeld **Neues Projekt** unter dem Knoten **Multi-Plattform** erst **Bibliothek** und dann die Vorlage **.NET Standard-Bibliothek** aus. Wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="2de3d-128">In the **New Project** dialog under the **Multi-Platform** node, select **Library**, then select the **.NET Standard Library** template, and select **Next**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Dialogfeld "Neues Projekt"":::

1. <span data-ttu-id="2de3d-130">Wählen Sie im Dialogfeld **Neue .NET Standard-Bibliothek konfigurieren** die Option „.NET Standard 2.1“ und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="2de3d-130">In the **Configure your new .NET Standard Library** dialog, choose ".NET Standard 2.1", and select **Next**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/choose-net-std-21.png" alt-text="Wählen Sie .NET Standard 2.1":::

1. <span data-ttu-id="2de3d-132">Nennen Sie die Projektmappe „StringLibrary“ und die Projektmappe „ClassLibraryProjects“.</span><span class="sxs-lookup"><span data-stu-id="2de3d-132">Name the project "StringLibrary" and the solution "ClassLibraryProjects".</span></span> <span data-ttu-id="2de3d-133">Lassen Sie **Projektverzeichnis im Projektmappenverzeichnis erstellen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2de3d-133">Leave **Create a project directory within the solution directory** selected.</span></span> <span data-ttu-id="2de3d-134">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="2de3d-134">Select **Create**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project-options.png" alt-text="Visual Studio für Mac, Optionen im Dialogfeld „Neues Projekt“":::

1. <span data-ttu-id="2de3d-136">Wählen Sie im Hauptmenü **Ansicht** > **Pads** > **Projektmappe** und dann das Andocksymbol aus, um das Pad geöffnet zu halten.</span><span class="sxs-lookup"><span data-stu-id="2de3d-136">From the main menu, select **View** > **Pads** > **Solution**, and select the dock icon to keep the pad open.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/solution-dock-icon.png" alt-text="Andocksymbol für Pad „Projektmappe“":::

1. <span data-ttu-id="2de3d-138">Erweitern Sie im Pad **Projektmappe** den `StringLibrary`-Knoten, um die von der Vorlage bereitgestellte Klassendatei *Class1.cs* anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2de3d-138">In the **Solution** pad, expand the `StringLibrary` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="2de3d-139">Klicken Sie bei gedrückter <kbd>CTRL-TASTE</kbd> auf die Datei. Wählen Sie im Kontextmenü **Umbenennen** aus, und benennen Sie die Datei in *StringLibrary.cs* um.</span><span class="sxs-lookup"><span data-stu-id="2de3d-139"><kbd>ctrl</kbd>-click the file, select **Rename** from the context menu, and rename the file to *StringLibrary.cs*.</span></span> <span data-ttu-id="2de3d-140">Öffnen Sie die Datei und ersetzen Sie den Inhalt durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="2de3d-140">Open the file and replace the contents with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

1. <span data-ttu-id="2de3d-141">Drücken Sie <kbd>⌘</kbd><kbd>S</kbd> (<kbd>BEFEHL</kbd>+<kbd>S</kbd>), um die Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2de3d-141">Press <kbd>⌘</kbd><kbd>S</kbd> (<kbd>command</kbd>+<kbd>S</kbd>) to save the file.</span></span>

1. <span data-ttu-id="2de3d-142">Wählen Sie am unteren Rand des IDE-Fensters **Fehler** aus, um den Bereich **Fehler** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2de3d-142">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="2de3d-143">Wählen Sie die Schaltfläche **Buildausgabe** aus.</span><span class="sxs-lookup"><span data-stu-id="2de3d-143">Select the **Build Output** button.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-error-button.png" alt-text="Unterer Rand der IDE mit Schaltfläche „Fehler“ in Visual Studio für Mac":::

1. <span data-ttu-id="2de3d-145">Klicken Sie im Menü auf **Build** > **Build All** (Erstellen > Alle erstellen).</span><span class="sxs-lookup"><span data-stu-id="2de3d-145">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="2de3d-146">Die Projektmappe wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="2de3d-146">The solution builds.</span></span> <span data-ttu-id="2de3d-147">Im Bereich „Buildausgabe“ wird angezeigt, dass der Build erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2de3d-147">The build output panel shows that the build is successful.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-build-panel.png" alt-text="Visual Studio für Mac, Buildausgabebereich im Bereich „Fehler“ mit Meldung, dass der Build erfolgreich war":::

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="2de3d-149">Hinzufügen einer Konsolen-App zur Projektmappe</span><span class="sxs-lookup"><span data-stu-id="2de3d-149">Add a console app to the solution</span></span>

<span data-ttu-id="2de3d-150">Im Folgenden fügen Sie eine Konsolenanwendung hinzu, die die Klassenbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="2de3d-150">Add a console application that uses the class library.</span></span> <span data-ttu-id="2de3d-151">Die App fordert den Benutzer dazu auf, eine Zeichenfolge einzugeben, und meldet, ob die Zeichenfolge mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="2de3d-151">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="2de3d-152">Klicken Sie im Pad **Projektmappe** bei gedrückter <kbd>CTRL-TASTE</kbd> auf die Projektmappe `ClassLibraryProjects`.</span><span class="sxs-lookup"><span data-stu-id="2de3d-152">In the **Solution** pad, <kbd>ctrl</kbd>-click the `ClassLibraryProjects` solution.</span></span> <span data-ttu-id="2de3d-153">Fügen Sie ein neues **Konsolenanwendungsprojekt** hinzu, indem Sie die Vorlage aus den Vorlagen unter **Web und Konsole** > **App** und dann **Weiter** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2de3d-153">Add a new **Console Application** project by selecting the template from the **Web and Console** > **App** templates, and select **Next**.</span></span>

1. <span data-ttu-id="2de3d-154">Wählen Sie **.NET Core 3.1** als **Zielframework** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="2de3d-154">Select **.NET Core 3.1** as the **Target Framework** and select **Next**.</span></span>

1. <span data-ttu-id="2de3d-155">Geben Sie dem Projekt den Namen **ShowCase**.</span><span class="sxs-lookup"><span data-stu-id="2de3d-155">Name the project **ShowCase**.</span></span> <span data-ttu-id="2de3d-156">Wählen Sie **Erstellen** aus, um das Projekt in der Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2de3d-156">Select **Create** to create the project in the solution.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/add-showcase-project.png" alt-text="Projekt „ShowCase“ hinzufügen":::

1. <span data-ttu-id="2de3d-158">Öffnen Sie die Datei *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="2de3d-158">Open the *Program.cs* file.</span></span> <span data-ttu-id="2de3d-159">Ersetzen Sie den Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="2de3d-159">Replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="2de3d-160">Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="2de3d-160">The program prompts the user to enter a string.</span></span> <span data-ttu-id="2de3d-161">Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="2de3d-161">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="2de3d-162">Wenn der Benutzer die <kbd>EINGABETASTE</kbd> drückt, ohne eine Zeichenfolge einzugeben, wird die Anwendung beendet und das Konsolenfenster geschlossen.</span><span class="sxs-lookup"><span data-stu-id="2de3d-162">If the user presses the <kbd>enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

   <span data-ttu-id="2de3d-163">Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten.</span><span class="sxs-lookup"><span data-stu-id="2de3d-163">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="2de3d-164">Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="2de3d-164">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="2de3d-165">Hinzufügen eines Projektverweises</span><span class="sxs-lookup"><span data-stu-id="2de3d-165">Add a project reference</span></span>

<span data-ttu-id="2de3d-166">Anfänglich besitzt das neue Konsolen-App-Projekt keinen Zugriff auf die Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="2de3d-166">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="2de3d-167">Damit es Methoden in der Klassenbibliothek aufrufen kann, erstellen Sie einen Projektverweis auf das Klassenbibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="2de3d-167">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="2de3d-168">Klicken Sie im Pad **Projektmappe** bei gedrückter <kbd>CTRL-TASTE</kbd> im neuen Projekt **ShowCase** auf den Knoten **Abhängigkeiten**.</span><span class="sxs-lookup"><span data-stu-id="2de3d-168">In the **Solutions** pad, <kbd>ctrl</kbd>-click the **Dependencies** node of the new **ShowCase** project.</span></span> <span data-ttu-id="2de3d-169">Wählen Sie im Kontextmenü **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="2de3d-169">In the context menu, select **Add Reference**.</span></span>

1. <span data-ttu-id="2de3d-170">Wählen Sie im Dialogfeld **Verweise** das Projekt **StringLibrary** und dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="2de3d-170">In the **References** dialog, select **StringLibrary** and select **OK**.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="2de3d-171">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="2de3d-171">Run the app</span></span>

1. <span data-ttu-id="2de3d-172">Klicken Sie bei gedrückter <kbd>CTRL-TASTE</kbd> auf das Projekt ShowCase, und wählen Sie im Kontextmenü **Projekt ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="2de3d-172"><kbd>ctrl</kbd>-click on the ShowCase project and select **Run project** from the context menu.</span></span>

1. <span data-ttu-id="2de3d-173">Testen Sie das Programm, indem Sie Zeichenfolgen eingeben und die <kbd>EINGABETASTE</kbd> drücken. Drücken Sie dann die <kbd>EINGABETASTE</kbd>, um das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="2de3d-173">Try out the program by entering strings and pressing <kbd>enter</kbd>, then press <kbd>enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-console-window.png" alt-text="Visual Studio für Mac-Konsolenfenster, das Ihre App bei der Ausführung zeigt":::

## <a name="additional-resources"></a><span data-ttu-id="2de3d-175">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="2de3d-175">Additional resources</span></span>

* [<span data-ttu-id="2de3d-176">Entwickeln von Bibliotheken mit der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="2de3d-176">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="2de3d-177">[.NET Standard-Versionen und die von ihnen unterstützten Plattformen](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="2de3d-177">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>
* [<span data-ttu-id="2de3d-178">Versionsanmerkungen für Visual Studio 2019 für Mac</span><span class="sxs-lookup"><span data-stu-id="2de3d-178">Visual Studio 2019 for Mac Release Notes</span></span>](/visualstudio/releasenotes/vs2019-mac-relnotes)

## <a name="next-steps"></a><span data-ttu-id="2de3d-179">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2de3d-179">Next steps</span></span>

<span data-ttu-id="2de3d-180">In diesem Tutorial haben Sie eine Projektmappe und ein Bibliotheksprojekt erstellt sowie ein Konsolen-App-Projekt hinzugefügt, das die Bibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="2de3d-180">In this tutorial, you created a solution and a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="2de3d-181">Im nächsten Tutorial fügen Sie der Projektmappe ein Komponententestprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="2de3d-181">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2de3d-182">Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="2de3d-182">Test a .NET Standard library with .NET Core using Visual Studio for Mac</span></span>](testing-library-with-visual-studio-mac.md)
