---
title: Erstellen einer .NET Standard-Klassenbibliothek in Visual Studio
description: Erfahren Sie, wie Sie eine .NET Standard-Klassenbibliothek mit Visual Studio erstellen.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: ef9c62b0378e1064d8cfd90a8c59aed74ea312b2
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701564"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio"></a><span data-ttu-id="950ce-103">Tutorial: Erstellen einer .NET-Standard-Bibliothek in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="950ce-103">Tutorial: Create a .NET Standard library using Visual Studio</span></span>

<span data-ttu-id="950ce-104">In diesem Tutorial erstellen Sie eine einfache Hilfsprogrammbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="950ce-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="950ce-105">Sie implementieren sie als [Erweiterungsmethode](../../csharp/programming-guide/classes-and-structs/extension-methods.md), damit sie aufgerufen werden kann, als wäre sie ein Mitglied der <xref:System.String>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="950ce-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="950ce-106">Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="950ce-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="950ce-107">Eine Klassenbibliothek, die sich auf .NET Standard 2.0 bezieht, ermöglicht das Aufrufen der Bibliothek aus jeder .NET-Implementierung, die diese Version von .NET Standard unterstützt.</span><span class="sxs-lookup"><span data-stu-id="950ce-107">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="950ce-108">Wenn Sie Ihre Klassenbibliothek fertig gestellt haben, können Sie sie als Komponente eines Drittanbieters oder als gebündelte Komponente mit einer oder mehreren Anwendungen verteilen.</span><span class="sxs-lookup"><span data-stu-id="950ce-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="950ce-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="950ce-109">Prerequisites</span></span>

- <span data-ttu-id="950ce-110">[Visual Studio 2019 Version 16.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload **Plattformübergreifende .NET Core-Entwicklung**.</span><span class="sxs-lookup"><span data-stu-id="950ce-110">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="950ce-111">Das .NET Core 3.1 SDK wird automatisch installiert, wenn Sie diese Workload auswählen.</span><span class="sxs-lookup"><span data-stu-id="950ce-111">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="950ce-112">Weitere Informationen finden Sie im Abschnitt [Installieren mit Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) des Artikels [Installieren des .NET Core SDK](../install/sdk.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="950ce-112">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="950ce-113">Erstellen einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="950ce-113">Create a solution</span></span>

<span data-ttu-id="950ce-114">Beginnen Sie, indem Sie eine leere Projektmappe erstellen, um das Klassenbibliotheksprojekt darin zu speichern.</span><span class="sxs-lookup"><span data-stu-id="950ce-114">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="950ce-115">Eine Visual Studio-Projektmappe dient als ein Container für mindestens ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="950ce-115">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="950ce-116">Sie fügen der gleichen Projektmappe weitere verwandte Projekte hinzu.</span><span class="sxs-lookup"><span data-stu-id="950ce-116">You'll add additional, related projects to the same solution.</span></span>

<span data-ttu-id="950ce-117">So erstellen Sie eine leere Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="950ce-117">To create the blank solution:</span></span>

1. <span data-ttu-id="950ce-118">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="950ce-118">Start Visual Studio.</span></span>

2. <span data-ttu-id="950ce-119">Wählen Sie im Startfenster **Neues Projekt erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-119">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="950ce-120">Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Projektmappe** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="950ce-120">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="950ce-121">Wählen Sie die Vorlage **Leere Projektmappe** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="950ce-121">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Vorlage „Leere Projektmappe“ in Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="950ce-123">Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **ClassLibraryProjects** ein.</span><span class="sxs-lookup"><span data-stu-id="950ce-123">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="950ce-124">Wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-124">Then choose **Create**.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="950ce-125">Erstellen eines Klassenbibliotheksprojekts</span><span class="sxs-lookup"><span data-stu-id="950ce-125">Create a class library project</span></span>

1. <span data-ttu-id="950ce-126">Fügen Sie der Projektmappe ein neues .NET Standard-Klassenbibliotheksprojekt mit dem Namen „StringLibrary“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="950ce-126">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="950ce-127">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-127">Right-click on the solution in **Solution Explorer** and select **Add** > **New Project**.</span></span>

   1. <span data-ttu-id="950ce-128">Geben Sie auf der Seite **Neues Projekt hinzufügen** **library** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="950ce-128">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="950ce-129">Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-129">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="950ce-130">Wählen Sie die Vorlage **Klassenbibliothek (.NET Standard)** aus, und wählen Sie dann **Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-130">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="950ce-131">Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **StringLibrary** ein.</span><span class="sxs-lookup"><span data-stu-id="950ce-131">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="950ce-132">Wählen Sie anschließend **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-132">Then, choose **Create**.</span></span>

1. <span data-ttu-id="950ce-133">Stellen Sie sicher, dass die Bibliothek die richtige Version von .NET Standard als Ziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="950ce-133">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="950ce-134">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Bibliotheksprojekt, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="950ce-134">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="950ce-135">Das Textfeld **Zielframework** zeigt dann, dass .NET Standard 2.0 als Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="950ce-135">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Projekteigenschaften für die Klassenbibliothek](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="950ce-137">Wenn Sie Visual Basic verwenden, löschen Sie den Text im Textfeld **Stammnamespace**.</span><span class="sxs-lookup"><span data-stu-id="950ce-137">If you're using Visual Basic, clear the text in the **Root namespace** text box.</span></span>

   ![Projekteigenschaften für die Klassenbibliothek](./media/library-with-visual-studio/vb/library-project-properties.png)

   <span data-ttu-id="950ce-139">Für jedes Projekt erstellt Visual Basic automatisch einen Namespace, der dem Projektnamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="950ce-139">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="950ce-140">In diesem Tutorial definieren Sie einen Namespace der obersten Ebene mithilfe des Schlüsselworts [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) in der Codedatei.</span><span class="sxs-lookup"><span data-stu-id="950ce-140">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="950ce-141">Ersetzen Sie den Code im Codefenster für *Class1.cs* oder *Class1.vb* durch den folgenden Code, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="950ce-141">Replace the code in the code window for *Class1.cs*  or *Class1.vb* with the following code, and save the file.</span></span> <span data-ttu-id="950ce-142">Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.</span><span class="sxs-lookup"><span data-stu-id="950ce-142">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   <span data-ttu-id="950ce-143">Die Klassenbibliothek (`UtilityLibraries.StringLibrary`) enthält eine Methode namens `StartsWithUpper`.</span><span class="sxs-lookup"><span data-stu-id="950ce-143">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="950ce-144">Diese Methode gibt einen <xref:System.Boolean>-Wert zurück, der angibt, ob die aktuelle Zeichenfolgeninstanz mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="950ce-144">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="950ce-145">Der Unicode-Standard unterscheidet Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="950ce-145">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="950ce-146">Die Methode <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> gibt `true` zurück, wenn ein Zeichen ein Großbuchstabe ist.</span><span class="sxs-lookup"><span data-stu-id="950ce-146">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="950ce-147">Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus, um zu bestätigen, dass das Projekt ohne Fehler kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="950ce-147">On the menu bar, select **Build** > **Build Solution** to verify that the project compiles without error.</span></span>

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="950ce-148">Hinzufügen einer Konsolen-App zur Projektmappe</span><span class="sxs-lookup"><span data-stu-id="950ce-148">Add a console app to the solution</span></span>

<span data-ttu-id="950ce-149">Im Folgenden fügen Sie eine Konsolenanwendung hinzu, die die Klassenbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="950ce-149">Add a console application that uses the class library.</span></span> <span data-ttu-id="950ce-150">Die App fordert den Benutzer dazu auf, eine Zeichenfolge einzugeben, und meldet, ob die Zeichenfolge mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="950ce-150">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="950ce-151">Fügen Sie der Projektmappe eine neue .NET Core-Konsolenanwendung mit dem Namen „ShowCase“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="950ce-151">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="950ce-152">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-152">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="950ce-153">Geben Sie auf der Seite **Neues Projekt hinzufügen** die Angabe **Konsole** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="950ce-153">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="950ce-154">Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-154">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="950ce-155">Wählen Sie die Vorlage **Konsolen-App (.NET Core)** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-155">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="950ce-156">Geben Sie **ShowCase** auf der Seite **Neues Projekt konfigurieren** in das Feld **Projektname** ein.</span><span class="sxs-lookup"><span data-stu-id="950ce-156">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="950ce-157">Wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-157">Then choose **Create**.</span></span>

1. <span data-ttu-id="950ce-158">Ersetzen Sie im Codefenster für die Datei *Program.cs* oder *Program.vb* den gesamten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="950ce-158">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   <span data-ttu-id="950ce-159">Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten.</span><span class="sxs-lookup"><span data-stu-id="950ce-159">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="950ce-160">Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="950ce-160">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="950ce-161">Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="950ce-161">The program prompts the user to enter a string.</span></span> <span data-ttu-id="950ce-162">Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="950ce-162">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="950ce-163">Wenn der Benutzer die <kbd>EINGABETASTE</kbd> drückt, ohne eine Zeichenfolge einzugeben, wird die Anwendung beendet und das Konsolenfenster geschlossen.</span><span class="sxs-lookup"><span data-stu-id="950ce-163">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="950ce-164">Hinzufügen eines Projektverweises</span><span class="sxs-lookup"><span data-stu-id="950ce-164">Add a project reference</span></span>

<span data-ttu-id="950ce-165">Anfänglich besitzt das neue Konsolen-App-Projekt keinen Zugriff auf die Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="950ce-165">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="950ce-166">Damit es Methoden in der Klassenbibliothek aufrufen kann, erstellen Sie einen Projektverweis auf das Klassenbibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="950ce-166">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="950ce-167">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des `ShowCase`-Projekts, und wählen Sie **Projektverweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-167">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node, and select **Add Project Reference**.</span></span>

   ![Kontextmenü „Verweis hinzufügen“ in Visual Studio](media/library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="950ce-169">Wählen Sie im Dialogfeld **Verweis-Manager** das Projekt **StringLibrary** und dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-169">In the **Reference Manager** dialog, select the **StringLibrary** project, and select **OK**.</span></span>

   ![Dialogfeld „Verweis-Manager“ mit ausgewählter StringLibrary](media/library-with-visual-studio/manage-project-references.png)

## <a name="run-the-app"></a><span data-ttu-id="950ce-171">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="950ce-171">Run the app</span></span>

1. <span data-ttu-id="950ce-172">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **ShowCase**-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="950ce-172">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Visual Studio-Projektkontextmenü zum Festlegen des Startprojekts](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="950ce-174">Drücken Sie <kbd>UMSCHALT</kbd>+<kbd>F5</kbd>, um das Programm ohne Debuggen zu kompilieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="950ce-174">Press <kbd>Shift</kbd>+<kbd>F5</kbd> to compile and run the program without debugging.</span></span>

   ![Visual Studio-Projektsymbolleiste mit Schaltfläche „Debuggen“](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. <span data-ttu-id="950ce-176">Testen Sie das Programm, indem Sie Zeichenfolgen eingeben und die <kbd>EINGABETASTE</kbd> drücken, und drücken Sie dann die <kbd>EINGABETASTE</kbd>, um das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="950ce-176">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Konsolenfenster, in dem ShowCase ausgeführt wird":::

## <a name="additional-resources"></a><span data-ttu-id="950ce-178">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="950ce-178">Additional resources</span></span>

* [<span data-ttu-id="950ce-179">Entwickeln von Bibliotheken mit der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="950ce-179">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="950ce-180">[.NET Standard-Versionen und die von ihnen unterstützten Plattformen](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="950ce-180">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="950ce-181">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="950ce-181">Next steps</span></span>

<span data-ttu-id="950ce-182">In diesem Tutorial haben Sie eine Projektmappe erstellt, ein Bibliotheksprojekt hinzugefügt und ein Konsolen-App-Projekt hinzugefügt, das die Bibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="950ce-182">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="950ce-183">Im nächsten Tutorial fügen Sie der Projektmappe ein Komponententestprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="950ce-183">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="950ce-184">Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="950ce-184">Test a .NET Standard library with .NET Core using Visual Studio</span></span>](testing-library-with-visual-studio.md)
