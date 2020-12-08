---
title: Erstellen einer .NET-Klassenbibliothek in Visual Studio Code
description: Hier erfahren Sie, wie Sie eine .NET-Klassenbibliothek mit Visual Studio Code erstellen.
ms.date: 11/18/2020
ms.openlocfilehash: 4473163b76060623b364d7dabf7366c3575e3dcd
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599498"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio-code"></a><span data-ttu-id="207c8-103">Tutorial: Erstellen einer .NET-Klassenbibliothek in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="207c8-103">Tutorial: Create a .NET class library using Visual Studio Code</span></span>

<span data-ttu-id="207c8-104">In diesem Tutorial erstellen Sie eine einfache Hilfsprogrammbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="207c8-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span>

<span data-ttu-id="207c8-105">Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="207c8-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="207c8-106">Wenn die Bibliothek auf .NET Standard 2.0 ausgelegt ist, kann sie von jeder .NET-Implementierung (einschließlich .NET Framework) aufgerufen werden, die .NET Standard 2.0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="207c8-106">If the library targets .NET Standard 2.0, it can be called by any .NET implementation (including .NET Framework) that supports .NET Standard 2.0.</span></span> <span data-ttu-id="207c8-107">Wenn die Bibliothek auf .NET 5 ausgelegt ist, kann sie von jeder Anwendung aufgerufen werden, die auf .NET 5 ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="207c8-107">If the library targets .NET 5, it can be called by any application that targets .NET 5.</span></span> <span data-ttu-id="207c8-108">In diesem Tutorial erfahren Sie, wie Sie .NET 5 als Zielversion verwenden.</span><span class="sxs-lookup"><span data-stu-id="207c8-108">This tutorial shows how to target .NET 5.</span></span>

<span data-ttu-id="207c8-109">Wenn Sie Ihre Klassenbibliothek erstellen, können Sie sie als Komponente eines Drittanbieters oder als gebündelte Komponente mit einer oder mehreren Anwendungen verteilen.</span><span class="sxs-lookup"><span data-stu-id="207c8-109">When you create a class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="207c8-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="207c8-110">Prerequisites</span></span>

1. <span data-ttu-id="207c8-111">[Visual Studio Code](https://code.visualstudio.com/) mit installierter [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="207c8-111">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="207c8-112">Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [Marketplace für VS Code-Erweiterungen](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="207c8-112">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="207c8-113">Das [.NET 5.0 SDK oder höher](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="207c8-113">The [.NET 5.0 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="207c8-114">Erstellen einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="207c8-114">Create a solution</span></span>

<span data-ttu-id="207c8-115">Beginnen Sie, indem Sie eine leere Projektmappe erstellen, um das Klassenbibliotheksprojekt darin zu speichern.</span><span class="sxs-lookup"><span data-stu-id="207c8-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="207c8-116">Eine Projektmappe dient als ein Container für mindestens ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="207c8-116">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="207c8-117">Sie fügen der gleichen Projektmappe weitere verwandte Projekte hinzu.</span><span class="sxs-lookup"><span data-stu-id="207c8-117">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="207c8-118">Starten Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="207c8-118">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="207c8-119">Wählen Sie im Hauptmenü **Datei** > **Ordner öffnen** (**Öffnen...** unter macOS) aus.</span><span class="sxs-lookup"><span data-stu-id="207c8-119">Select **File** > **Open Folder** (**Open...** on macOS) from the main menu</span></span>

1. <span data-ttu-id="207c8-120">Erstellen Sie im Dialogfeld **Ordner öffnen** den Ordner *ClassLibraryProjects*, und klicken Sie auf **Ordner auswählen** (**Öffnen** unter macOS).</span><span class="sxs-lookup"><span data-stu-id="207c8-120">In the **Open Folder** dialog, create a *ClassLibraryProjects* folder and click **Select Folder** (**Open** on macOS).</span></span>

1. <span data-ttu-id="207c8-121">Öffnen Sie das **Terminal** in Visual Studio Code, indem Sie im Hauptmenü **Ansicht** > **Terminal** auswählen.</span><span class="sxs-lookup"><span data-stu-id="207c8-121">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="207c8-122">Das **Terminal** wird mit der Eingabeaufforderung im Ordner *ClassLibraryProjects* geöffnet.</span><span class="sxs-lookup"><span data-stu-id="207c8-122">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="207c8-123">Geben Sie im **Terminal** den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="207c8-123">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="207c8-124">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="207c8-124">The terminal output looks like the following example:</span></span>

   ```output
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="207c8-125">Erstellen eines Klassenbibliotheksprojekts</span><span class="sxs-lookup"><span data-stu-id="207c8-125">Create a class library project</span></span>

<span data-ttu-id="207c8-126">Fügen Sie ein neues .NET-Klassenbibliotheksprojekt namens „StringLibrary“ zur Projektmappe hinzu.</span><span class="sxs-lookup"><span data-stu-id="207c8-126">Add a new .NET class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="207c8-127">Führen Sie im Terminal den folgenden Befehl aus, um das Bibliotheksprojekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="207c8-127">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="207c8-128">Der Befehl `-o` oder `--output` gibt den Speicherort für die generierte Ausgabe an.</span><span class="sxs-lookup"><span data-stu-id="207c8-128">The `-o` or `--output` command specifies the location to place the generated output.</span></span>

   <span data-ttu-id="207c8-129">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="207c8-129">The terminal output looks like the following example:</span></span>

   ```output
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj (in 328 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="207c8-130">Führen Sie den folgenden Befehl aus, um das Bibliotheksprojekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="207c8-130">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="207c8-131">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="207c8-131">The terminal output looks like the following example:</span></span>

   ```output
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="207c8-132">Stellen Sie sicher, dass die Bibliothek auf .NET 5 ausgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="207c8-132">Check to make sure that the library targets .NET 5.</span></span> <span data-ttu-id="207c8-133">Öffnen Sie im **Explorer** die Datei *StringLibrary/StringLibrary.csproj*.</span><span class="sxs-lookup"><span data-stu-id="207c8-133">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="207c8-134">Das Element `TargetFramework` gibt an, dass das Projekt für .NET 5.0 vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="207c8-134">The `TargetFramework` element shows that the project targets .NET 5.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>net5.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="207c8-135">Öffnen Sie die Datei *Class1.cs*, und ersetzen Sie den Code durch den folgenden:</span><span class="sxs-lookup"><span data-stu-id="207c8-135">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="207c8-136">Die Klassenbibliothek (`UtilityLibraries.StringLibrary`) enthält eine Methode namens `StartsWithUpper`.</span><span class="sxs-lookup"><span data-stu-id="207c8-136">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="207c8-137">Diese Methode gibt einen <xref:System.Boolean>-Wert zurück, der angibt, ob die aktuelle Zeichenfolgeninstanz mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="207c8-137">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="207c8-138">Der Unicode-Standard unterscheidet Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="207c8-138">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="207c8-139">Die Methode <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> gibt `true` zurück, wenn ein Zeichen ein Großbuchstabe ist.</span><span class="sxs-lookup"><span data-stu-id="207c8-139">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="207c8-140">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="207c8-140">Save the file.</span></span>

1. <span data-ttu-id="207c8-141">Führen Sie den folgenden Befehl aus, um die Projektmappe zu erstellen und zu überprüfen, ob das Projekt fehlerfrei kompiliert wird:</span><span class="sxs-lookup"><span data-stu-id="207c8-141">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="207c8-142">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="207c8-142">The terminal output looks like the following example:</span></span>

   ```output
   Microsoft (R) Build Engine version 16.7.0+b89cb5fde for .NET
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\net5.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="207c8-143">Hinzufügen einer Konsolen-App zur Projektmappe</span><span class="sxs-lookup"><span data-stu-id="207c8-143">Add a console app to the solution</span></span>

<span data-ttu-id="207c8-144">Im Folgenden fügen Sie eine Konsolenanwendung hinzu, die die Klassenbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="207c8-144">Add a console application that uses the class library.</span></span> <span data-ttu-id="207c8-145">Die App fordert den Benutzer dazu auf, eine Zeichenfolge einzugeben, und meldet, ob die Zeichenfolge mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="207c8-145">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="207c8-146">Führen Sie im Terminal den folgenden Befehl aus, um das Konsolen-App-Projekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="207c8-146">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="207c8-147">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="207c8-147">The terminal output looks like the following example:</span></span>

   ```output
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj (in 210 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="207c8-148">Führen Sie den folgenden Befehl aus, um das Konsolen-App-Projekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="207c8-148">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="207c8-149">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="207c8-149">The terminal output looks like the following example:</span></span>

   ```output
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="207c8-150">Öffnen Sie die Datei *ShowCase/Program.cs*, und ersetzen Sie den gesamten Code durch den folgenden:</span><span class="sxs-lookup"><span data-stu-id="207c8-150">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="207c8-151">Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten.</span><span class="sxs-lookup"><span data-stu-id="207c8-151">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="207c8-152">Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="207c8-152">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="207c8-153">Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="207c8-153">The program prompts the user to enter a string.</span></span> <span data-ttu-id="207c8-154">Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="207c8-154">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="207c8-155">Wenn der Benutzer die <kbd>EINGABETASTE</kbd> drückt, ohne eine Zeichenfolge einzugeben, wird die Anwendung beendet und das Konsolenfenster geschlossen.</span><span class="sxs-lookup"><span data-stu-id="207c8-155">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="207c8-156">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="207c8-156">Save your changes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="207c8-157">Hinzufügen eines Projektverweises</span><span class="sxs-lookup"><span data-stu-id="207c8-157">Add a project reference</span></span>

<span data-ttu-id="207c8-158">Anfänglich besitzt das neue Konsolen-App-Projekt keinen Zugriff auf die Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="207c8-158">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="207c8-159">Damit es Methoden in der Klassenbibliothek aufrufen kann, erstellen Sie einen Projektverweis auf das Klassenbibliotheksprojekt.</span><span class="sxs-lookup"><span data-stu-id="207c8-159">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="207c8-160">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="207c8-160">Run the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/ShowCase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="207c8-161">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="207c8-161">The terminal output looks like the following example:</span></span>

   ```output
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a><span data-ttu-id="207c8-162">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="207c8-162">Run the app</span></span>

1. <span data-ttu-id="207c8-163">Führen Sie die folgenden Befehle im Terminal aus:</span><span class="sxs-lookup"><span data-stu-id="207c8-163">Run the following command in the terminal:</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="207c8-164">Testen Sie das Programm, indem Sie Zeichenfolgen eingeben und die <kbd>EINGABETASTE</kbd> drücken, und drücken Sie dann die <kbd>EINGABETASTE</kbd>, um das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="207c8-164">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="207c8-165">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="207c8-165">The terminal output looks like the following example:</span></span>

   ```output
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   a string that starts with a lowercase letter
   Input: a string that starts with a lowercase letter
   Begins with uppercase? : No
   ```

## <a name="additional-resources"></a><span data-ttu-id="207c8-166">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="207c8-166">Additional resources</span></span>

* [<span data-ttu-id="207c8-167">Entwickeln von Bibliotheken mit der .NET-CLI</span><span class="sxs-lookup"><span data-stu-id="207c8-167">Develop libraries with the .NET CLI</span></span>](libraries.md)
* <span data-ttu-id="207c8-168">[.NET Standard-Versionen und die von ihnen unterstützten Plattformen](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="207c8-168">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="207c8-169">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="207c8-169">Next steps</span></span>

<span data-ttu-id="207c8-170">In diesem Tutorial haben Sie eine Projektmappe erstellt, ein Bibliotheksprojekt hinzugefügt und ein Konsolen-App-Projekt hinzugefügt, das die Bibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="207c8-170">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="207c8-171">Im nächsten Tutorial fügen Sie der Projektmappe ein Komponententestprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="207c8-171">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="207c8-172">Testen einer .NET-Klassenbibliothek mit .NET mithilfe von Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="207c8-172">Test a .NET class library with .NET using Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
