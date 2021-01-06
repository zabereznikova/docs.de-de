---
title: Erstellen einer .NET-Klassenbibliothek mit Visual Studio
description: Hier erfahren Sie, wie Sie eine .NET-Klassenbibliothek mit Visual Studio erstellen.
ms.date: 08/07/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet,contperf-fy21q1
ms.openlocfilehash: 2d9b02a155c950b77565a66417948568f5fa039f
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513119"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio"></a><span data-ttu-id="73196-103">Tutorial: Erstellen einer .NET-Klassenbibliothek mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73196-103">Tutorial: Create a .NET class library using Visual Studio</span></span>

<span data-ttu-id="73196-104">In diesem Tutorial erstellen Sie eine einfache Klassenbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="73196-104">In this tutorial, you create a simple class library that contains a single string-handling method.</span></span>

<span data-ttu-id="73196-105">Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="73196-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="73196-106">Wenn die Bibliothek auf .NET Standard 2.0 ausgelegt ist, kann sie von jeder .NET-Implementierung (einschließlich .NET Framework) aufgerufen werden, die .NET Standard 2.0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="73196-106">If the library targets .NET Standard 2.0, it can be called by any .NET implementation (including .NET Framework) that supports .NET Standard 2.0.</span></span> <span data-ttu-id="73196-107">Wenn die Bibliothek auf .NET 5 ausgelegt ist, kann sie von jeder Anwendung aufgerufen werden, die auf .NET 5 ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="73196-107">If the library targets .NET 5, it can be called by any application that targets .NET 5.</span></span> <span data-ttu-id="73196-108">In diesem Tutorial erfahren Sie, wie Sie .NET 5 als Zielversion verwenden.</span><span class="sxs-lookup"><span data-stu-id="73196-108">This tutorial shows how to target .NET 5.</span></span>

<span data-ttu-id="73196-109">Wenn Sie eine Klassenbibliothek erstellen, können Sie diese als NuGet-Paket oder als mit der zugehörigen Anwendung gebündelte Komponente ausliefern.</span><span class="sxs-lookup"><span data-stu-id="73196-109">When you create a class library, you can distribute it as a NuGet package or as a component bundled with the application that uses it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73196-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="73196-110">Prerequisites</span></span>

- <span data-ttu-id="73196-111">[Visual Studio 2019 Version 16.8 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload **Plattformübergreifende .NET Core-Entwicklung**.</span><span class="sxs-lookup"><span data-stu-id="73196-111">[Visual Studio 2019 version 16.8 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="73196-112">Das .NET 5.0 SDK wird automatisch installiert, wenn Sie diese Workload auswählen.</span><span class="sxs-lookup"><span data-stu-id="73196-112">The .NET 5.0 SDK is automatically installed when you select this workload.</span></span> <span data-ttu-id="73196-113">In diesem Tutorial wird davon ausgegangen, dass Sie die Option **Show all .NET Core templates in the New project** (Alle .NET Core-Vorlagen im Dialogfeld „Neues Projekt“ anzeigen) wie im [Tutorial: Erstellen einer .NET-Konsolenanwendung mit Visual Studio](with-visual-studio.md) gezeigt aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="73196-113">This tutorial assumes you have enabled **Show all .NET Core templates in the New project**, as shown in [Tutorial: Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="73196-114">Erstellen einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="73196-114">Create a solution</span></span>

<span data-ttu-id="73196-115">Beginnen Sie, indem Sie eine leere Projektmappe erstellen, um das Klassenbibliotheksprojekt darin zu speichern.</span><span class="sxs-lookup"><span data-stu-id="73196-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="73196-116">Eine Visual Studio-Projektmappe dient als ein Container für mindestens ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="73196-116">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="73196-117">Sie fügen der gleichen Projektmappe weitere verwandte Projekte hinzu.</span><span class="sxs-lookup"><span data-stu-id="73196-117">You'll add additional, related projects to the same solution.</span></span>

<span data-ttu-id="73196-118">So erstellen Sie eine leere Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="73196-118">To create the blank solution:</span></span>

1. <span data-ttu-id="73196-119">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="73196-119">Start Visual Studio.</span></span>

2. <span data-ttu-id="73196-120">Wählen Sie im Startfenster **Neues Projekt erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-120">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="73196-121">Geben Sie auf der Seite **Neues Projekt erstellen** die Angabe **Projektmappe** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="73196-121">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="73196-122">Wählen Sie die Vorlage **Leere Projektmappe** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73196-122">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   :::image type="content" source="media/library-with-visual-studio/blank-solution.png" alt-text="Vorlage „Leere Projektmappe“ in Visual Studio":::

4. <span data-ttu-id="73196-124">Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **ClassLibraryProjects** ein.</span><span class="sxs-lookup"><span data-stu-id="73196-124">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="73196-125">Wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-125">Then choose **Create**.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="73196-126">Erstellen eines Klassenbibliotheksprojekts</span><span class="sxs-lookup"><span data-stu-id="73196-126">Create a class library project</span></span>

1. <span data-ttu-id="73196-127">Fügen Sie ein neues .NET-Klassenbibliotheksprojekt namens „StringLibrary“ zur Projektmappe hinzu.</span><span class="sxs-lookup"><span data-stu-id="73196-127">Add a new .NET class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="73196-128">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-128">Right-click on the solution in **Solution Explorer** and select **Add** > **New Project**.</span></span>

   1. <span data-ttu-id="73196-129">Geben Sie auf der Seite **Neues Projekt hinzufügen** **library** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="73196-129">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="73196-130">Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-130">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="73196-131">Wählen Sie die Vorlage **Klassenbibliothek** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73196-131">Choose the **Class Library** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="73196-132">Geben Sie im auf der Seite **Neues Projekt konfigurieren** im Feld **Projektname** den Namen **StringLibrary** ein, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73196-132">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box, and then choose **Next**.</span></span>

   1. <span data-ttu-id="73196-133">Wählen Sie auf der Seite **Zusätzliche Informationen** die Option **.NET 5.0 (aktuell)** aus, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="73196-133">On the **Additional information** page, select **.NET 5.0 (Current)**, and then choose **Create**.</span></span>

1. <span data-ttu-id="73196-134">Stellen Sie sicher, dass die Bibliothek die richtige Version von .NET als Ziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="73196-134">Check to make sure that the library targets the correct version of .NET.</span></span> <span data-ttu-id="73196-135">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Bibliotheksprojekt, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="73196-135">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="73196-136">Das Textfeld **Zielframework** zeigt dann, dass .NET 5.0 als Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="73196-136">The **Target Framework** text box shows that the project targets .NET 5.0.</span></span>

1. <span data-ttu-id="73196-137">Wenn Sie Visual Basic verwenden, löschen Sie den Text im Textfeld **Stammnamespace**.</span><span class="sxs-lookup"><span data-stu-id="73196-137">If you're using Visual Basic, clear the text in the **Root namespace** text box.</span></span>

   :::image type="content" source="./media/library-with-visual-studio/vb/library-project-properties.png" alt-text="Projekteigenschaften für die Klassenbibliothek":::

   <span data-ttu-id="73196-139">Für jedes Projekt erstellt Visual Basic automatisch einen Namespace, der dem Projektnamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="73196-139">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="73196-140">In diesem Tutorial definieren Sie einen Namespace der obersten Ebene mithilfe des Schlüsselworts [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) in der Codedatei.</span><span class="sxs-lookup"><span data-stu-id="73196-140">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="73196-141">Ersetzen Sie den Code im Codefenster für *Class1.cs* oder *Class1.vb* durch den folgenden Code, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="73196-141">Replace the code in the code window for *Class1.cs*  or *Class1.vb* with the following code, and save the file.</span></span> <span data-ttu-id="73196-142">Wenn die gewünschte Sprache nicht angezeigt wird, ändern Sie die Sprachauswahl am oberen Rand der Seite.</span><span class="sxs-lookup"><span data-stu-id="73196-142">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   <span data-ttu-id="73196-143">Die Klassenbibliothek (`UtilityLibraries.StringLibrary`) enthält eine Methode namens `StartsWithUpper`.</span><span class="sxs-lookup"><span data-stu-id="73196-143">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="73196-144">Diese Methode gibt einen <xref:System.Boolean>-Wert zurück, der angibt, ob die aktuelle Zeichenfolgeninstanz mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="73196-144">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="73196-145">Der Unicode-Standard unterscheidet Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="73196-145">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="73196-146">Die Methode <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> gibt `true` zurück, wenn ein Zeichen ein Großbuchstabe ist.</span><span class="sxs-lookup"><span data-stu-id="73196-146">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

   <span data-ttu-id="73196-147">Die Methode `StartsWithUpper` wird als [Erweiterungsmethode](../../csharp/programming-guide/classes-and-structs/extension-methods.md) implementiert, damit sie wie ein Member der Klasse <xref:System.String> aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="73196-147">`StartsWithUpper` is implemented as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

1. <span data-ttu-id="73196-148">Klicken Sie auf der Menüleiste auf **Erstellen** > **Projektmappe erstellen**, oder drücken Sie <kbd>STRG</kbd>+<kbd>UMSCHALT</kbd>+<kbd>B</kbd>, um zu bestätigen, dass das Projekt ohne Fehler kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="73196-148">On the menu bar, select **Build** > **Build Solution** or press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd> to verify that the project compiles without error.</span></span>

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="73196-149">Hinzufügen einer Konsolen-App zur Projektmappe</span><span class="sxs-lookup"><span data-stu-id="73196-149">Add a console app to the solution</span></span>

<span data-ttu-id="73196-150">Im Folgenden fügen Sie eine Konsolenanwendung hinzu, die die Klassenbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="73196-150">Add a console application that uses the class library.</span></span> <span data-ttu-id="73196-151">Die App fordert den Benutzer dazu auf, eine Zeichenfolge einzugeben, und meldet, ob die Zeichenfolge mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="73196-151">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="73196-152">Fügen Sie der Projektmappe eine neue .NET-Konsolenanwendung mit dem Namen „ShowCase“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="73196-152">Add a new .NET console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="73196-153">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-153">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="73196-154">Geben Sie auf der Seite **Neues Projekt hinzufügen** die Angabe **Konsole** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="73196-154">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="73196-155">Wählen Sie **C#** oder **Visual Basic** in der Liste der Sprachen und dann in der Liste der Plattformen **Alle Plattformen** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-155">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="73196-156">Wählen Sie die Vorlage **Konsolenanwendung** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="73196-156">Choose the **Console Application** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="73196-157">Geben Sie **ShowCase** auf der Seite **Neues Projekt konfigurieren** in das Feld **Projektname** ein.</span><span class="sxs-lookup"><span data-stu-id="73196-157">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="73196-158">Wählen Sie anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-158">Then choose **Next**.</span></span>

   1. <span data-ttu-id="73196-159">Wählen Sie auf der Seite **Zusätzliche Informationen** im Feld **Zielframework** die Option **.NET 5.0 (aktuell)** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-159">On the **Additional information** page, select **.NET 5.0 (Current)** in the **Target Framework** box.</span></span> <span data-ttu-id="73196-160">Wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-160">Then choose **Create**.</span></span>

1. <span data-ttu-id="73196-161">Ersetzen Sie im Codefenster für die Datei *Program.cs* oder *Program.vb* den gesamten Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="73196-161">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   <span data-ttu-id="73196-162">Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten.</span><span class="sxs-lookup"><span data-stu-id="73196-162">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="73196-163">Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="73196-163">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="73196-164">Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="73196-164">The program prompts the user to enter a string.</span></span> <span data-ttu-id="73196-165">Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="73196-165">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="73196-166">Wenn der Benutzer die <kbd>EINGABETASTE</kbd> drückt, ohne eine Zeichenfolge einzugeben, wird die Anwendung beendet und das Konsolenfenster geschlossen.</span><span class="sxs-lookup"><span data-stu-id="73196-166">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="73196-167">Hinzufügen eines Projektverweises</span><span class="sxs-lookup"><span data-stu-id="73196-167">Add a project reference</span></span>

<span data-ttu-id="73196-168">Anfänglich besitzt das neue Konsolen-App-Projekt keinen Zugriff auf die Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="73196-168">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="73196-169">Damit es Methoden in der Klassenbibliothek aufrufen kann, erstellen Sie einen Projektverweis auf das Klassenbibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="73196-169">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="73196-170">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des `ShowCase`-Projekts, und wählen Sie **Projektverweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-170">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node, and select **Add Project Reference**.</span></span>

   :::image type="content" source="media/library-with-visual-studio/add-reference-context-menu.png" alt-text="Kontextmenü „Verweis hinzufügen“ in Visual Studio":::

1. <span data-ttu-id="73196-172">Wählen Sie im Dialogfeld **Verweis-Manager** das Projekt **StringLibrary** und dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-172">In the **Reference Manager** dialog, select the **StringLibrary** project, and select **OK**.</span></span>

   :::image type="content" source="media/library-with-visual-studio/manage-project-references.png" alt-text="Dialogfeld „Verweis-Manager“ mit ausgewählter StringLibrary":::

## <a name="run-the-app"></a><span data-ttu-id="73196-174">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="73196-174">Run the app</span></span>

1. <span data-ttu-id="73196-175">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das **ShowCase**-Projekt, und wählen Sie **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="73196-175">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   :::image type="content" source="media/library-with-visual-studio/set-startup-project-context-menu.png" alt-text="Visual Studio-Projektkontextmenü zum Festlegen des Startprojekts":::

1. <span data-ttu-id="73196-177">Drücken Sie <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Programm ohne Debuggen zu kompilieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="73196-177">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to compile and run the program without debugging.</span></span>

   :::image type="content" source="media/library-with-visual-studio/visual-studio-project-toolbar.png" alt-text="Visual Studio-Projektsymbolleiste mit Schaltfläche „Debuggen“":::

1. <span data-ttu-id="73196-179">Testen Sie das Programm, indem Sie Zeichenfolgen eingeben und die <kbd>EINGABETASTE</kbd> drücken, und drücken Sie dann die <kbd>EINGABETASTE</kbd>, um das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="73196-179">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Konsolenfenster, in dem ShowCase ausgeführt wird":::

## <a name="additional-resources"></a><span data-ttu-id="73196-181">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="73196-181">Additional resources</span></span>

* [<span data-ttu-id="73196-182">Entwickeln von Bibliotheken mit der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="73196-182">Develop libraries with the .NET CLI</span></span>](libraries.md)
* <span data-ttu-id="73196-183">[.NET Standard-Versionen und die von ihnen unterstützten Plattformen](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="73196-183">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="73196-184">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="73196-184">Next steps</span></span>

<span data-ttu-id="73196-185">In diesem Tutorial haben Sie eine Klassenbibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="73196-185">In this tutorial, you created a class library.</span></span> <span data-ttu-id="73196-186">Im nächsten Tutorial erfahren Sie, wie Sie Komponententests für die Klassenbibliothek ausführen.</span><span class="sxs-lookup"><span data-stu-id="73196-186">In the next tutorial, you learn how to unit test the class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="73196-187">Durchführen eines Komponententests für eine .NET-Klassenbibliothek mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73196-187">Unit test a .NET class library using Visual Studio</span></span>](testing-library-with-visual-studio.md)

<span data-ttu-id="73196-188">Alternativ können Sie die automatisierten Komponententests auch überspringen und sich damit beschäftigen, wie die Bibliothek durch Erstellen eines NuGet-Pakets freigegeben werden kann:</span><span class="sxs-lookup"><span data-stu-id="73196-188">Or you can skip automated unit testing and learn how to share the library by creating a NuGet package:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="73196-189">Erstellen und Veröffentlichen eines Pakets mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73196-189">Create and publish a package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio)

<span data-ttu-id="73196-190">Stattdessen können Sie sich auch über das Veröffentlichen einer Konsolen-App informieren.</span><span class="sxs-lookup"><span data-stu-id="73196-190">Or learn how to publish a console app.</span></span> <span data-ttu-id="73196-191">Wenn Sie die Konsolen-App aus der Projektmappe veröffentlichen, die Sie in diesem Tutorial erstellt haben, wird die Klassenbibliothek als *DLL*-Datei veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="73196-191">If you publish the console app from the solution you created in this tutorial, the class library goes with it as a *.dll* file.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="73196-192">Veröffentlichen einer .NET-Konsolenanwendung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73196-192">Publish a .NET console application using Visual Studio</span></span>](publishing-with-visual-studio.md)
