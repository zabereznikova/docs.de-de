---
title: Erstellen einer .NET Standard-Klassenbibliothek in Visual Studio Code
description: Hier erfahren Sie, wie Sie eine .NET Standard-Klassenbibliothek mit Visual Studio Code erstellen.
ms.date: 05/29/2020
ms.openlocfilehash: 5720ac374d50ef27a07d463e57af1bd95a352d83
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446951"
---
# <a name="tutorial-create-a-net-standard-library-in-visual-studio-code"></a><span data-ttu-id="934e7-103">Tutorial: Erstellen einer .NET Standard-Bibliothek in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="934e7-103">Tutorial: Create a .NET Standard library in Visual Studio Code</span></span>

<span data-ttu-id="934e7-104">Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="934e7-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="934e7-105">Eine Klassenbibliothek, die sich auf .NET Standard 2.0 bezieht, ermöglicht das Aufrufen der Bibliothek aus jeder .NET-Implementierung, die diese Version von .NET Standard unterstützt.</span><span class="sxs-lookup"><span data-stu-id="934e7-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="934e7-106">Wenn Sie Ihre Klassenbibliothek fertigstellen, können Sie entscheiden, ob Sie diese als NuGet-Paket verteilen oder als Komponente in ein Paket mit mehreren Anwendungen einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="934e7-106">When you finish your class library, you can decide whether you want to distribute it as a NuGet package or include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="934e7-107">Eine Liste der .NET Standard-Versionen und der Plattformen, die sie unterstützen, finden Sie unter [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="934e7-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="934e7-108">In diesem Tutorial erstellen Sie eine einfache Hilfsprogrammbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="934e7-108">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="934e7-109">Sie implementieren sie als [Erweiterungsmethode](../../csharp/programming-guide/classes-and-structs/extension-methods.md), damit sie aufgerufen werden kann, als wäre sie ein Mitglied der <xref:System.String>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="934e7-109">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="934e7-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="934e7-110">Prerequisites</span></span>

1. <span data-ttu-id="934e7-111">[Visual Studio Code](https://code.visualstudio.com/) mit installierter [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="934e7-111">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="934e7-112">Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [Marketplace für VS Code-Erweiterungen](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="934e7-112">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="934e7-113">[.NET Core 3.1 SDK oder höher](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="934e7-113">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="934e7-114">Erstellen einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="934e7-114">Create a solution</span></span>

<span data-ttu-id="934e7-115">Beginnen Sie, indem Sie eine leere Projektmappe erstellen, um das Klassenbibliotheksprojekt darin zu speichern.</span><span class="sxs-lookup"><span data-stu-id="934e7-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="934e7-116">Eine Projektmappe dient als ein Container für mindestens ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="934e7-116">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="934e7-117">Sie fügen der gleichen Projektmappe weitere verwandte Projekte hinzu.</span><span class="sxs-lookup"><span data-stu-id="934e7-117">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="934e7-118">Öffnen Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="934e7-118">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="934e7-119">Klicken Sie im Hauptmenü auf **Datei** > **Ordner öffnen**/**Öffnen...** , erstellen Sie einen Ordner namens *ClassLibraryProjects*, und klicken Sie dann auf **Ordner auswählen**/**Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="934e7-119">Select **File** > **Open Folder**/**Open...** from the main menu, create a *ClassLibraryProjects* folder, and click **Select Folder**/**Open**.</span></span>

1. <span data-ttu-id="934e7-120">Öffnen Sie das **Terminal** in Visual Studio Code, indem Sie im Hauptmenü **Ansicht** > **Terminal** auswählen.</span><span class="sxs-lookup"><span data-stu-id="934e7-120">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="934e7-121">Das **Terminal** wird mit der Eingabeaufforderung im Ordner *ClassLibraryProjects* geöffnet.</span><span class="sxs-lookup"><span data-stu-id="934e7-121">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="934e7-122">Geben Sie im **Terminal** den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="934e7-122">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="934e7-123">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="934e7-123">The terminal output looks like the following example:</span></span>

   ```
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="934e7-124">Erstellen eines Klassenbibliotheksprojekts</span><span class="sxs-lookup"><span data-stu-id="934e7-124">Create a class library project</span></span>

<span data-ttu-id="934e7-125">Fügen Sie der Projektmappe ein neues .NET Standard-Klassenbibliotheksprojekt mit dem Namen „StringLibrary“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="934e7-125">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="934e7-126">Führen Sie im Terminal den folgenden Befehl aus, um das Bibliotheksprojekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="934e7-126">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="934e7-127">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="934e7-127">The terminal output looks like the following example:</span></span>

   ```
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restore completed in 328.13 ms for C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="934e7-128">Führen Sie den folgenden Befehl aus, um das Bibliotheksprojekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="934e7-128">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="934e7-129">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="934e7-129">The terminal output looks like the following example:</span></span>

   ```
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="934e7-130">Stellen Sie sicher, dass die Bibliothek die richtige Version von .NET Standard als Ziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="934e7-130">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="934e7-131">Öffnen Sie im **Explorer** die Datei *StringLibrary/StringLibrary.csproj*.</span><span class="sxs-lookup"><span data-stu-id="934e7-131">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="934e7-132">Das Element `TargetFramework` gibt an, dass das Projekt für .NET Standard 2.0 vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="934e7-132">The `TargetFramework` element shows that the project targets .NET Standard 2.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="934e7-133">Öffnen Sie die Datei *Class1.cs*, und ersetzen Sie den Code durch den folgenden:</span><span class="sxs-lookup"><span data-stu-id="934e7-133">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="934e7-134">Die Klassenbibliothek (`UtilityLibraries.StringLibrary`) enthält eine Methode namens `StartsWithUpper`.</span><span class="sxs-lookup"><span data-stu-id="934e7-134">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="934e7-135">Diese Methode gibt einen <xref:System.Boolean>-Wert zurück, der angibt, ob die aktuelle Zeichenfolgeninstanz mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="934e7-135">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="934e7-136">Der Unicode-Standard unterscheidet Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="934e7-136">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="934e7-137">Die Methode <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> gibt `true` zurück, wenn ein Zeichen ein Großbuchstabe ist.</span><span class="sxs-lookup"><span data-stu-id="934e7-137">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="934e7-138">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="934e7-138">Save the file.</span></span>

1. <span data-ttu-id="934e7-139">Führen Sie den folgenden Befehl aus, um die Projektmappe zu erstellen und zu überprüfen, ob das Projekt fehlerfrei kompiliert wird:</span><span class="sxs-lookup"><span data-stu-id="934e7-139">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="934e7-140">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="934e7-140">The terminal output looks like the following example:</span></span>

   ```
   Microsoft (R) Build Engine version 16.6.0 for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     You are using a preview version of .NET Core. See: https://aka.ms/dotnet-core-preview
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\netstandard2.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="934e7-141">Hinzufügen einer Konsolen-App zur Projektmappe</span><span class="sxs-lookup"><span data-stu-id="934e7-141">Add a console app to the solution</span></span>

<span data-ttu-id="934e7-142">Im Folgenden fügen Sie eine Konsolenanwendung hinzu, die die Klassenbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="934e7-142">Add a console application that uses the class library.</span></span> <span data-ttu-id="934e7-143">Die App fordert den Benutzer dazu auf, eine Zeichenfolge einzugeben, und meldet, ob die Zeichenfolge mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="934e7-143">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="934e7-144">Führen Sie im Terminal den folgenden Befehl aus, um das Konsolen-App-Projekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="934e7-144">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="934e7-145">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="934e7-145">The terminal output looks like the following example:</span></span>

   ```
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restore completed in 210.78 ms for C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="934e7-146">Führen Sie den folgenden Befehl aus, um das Konsolen-App-Projekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="934e7-146">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="934e7-147">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="934e7-147">The terminal output looks like the following example:</span></span>

   ```
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="934e7-148">Anfänglich besitzt das neue Konsolen-App-Projekt keinen Zugriff auf die Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="934e7-148">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="934e7-149">Erstellen Sie mit dem folgenden Befehl einen Projektverweis auf das Klassenbibliothek, um der App das Aufrufen von Methoden in der Klassenbibliothek zu erlauben:</span><span class="sxs-lookup"><span data-stu-id="934e7-149">To allow it to call methods in the class library, create a project reference to the class library project by running the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/Showcase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="934e7-150">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="934e7-150">The terminal output looks like the following example:</span></span>

   ```
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

1. <span data-ttu-id="934e7-151">Öffnen Sie die Datei *ShowCase/Program.cs*, und ersetzen Sie den gesamten Code durch den folgenden:</span><span class="sxs-lookup"><span data-stu-id="934e7-151">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="934e7-152">Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten.</span><span class="sxs-lookup"><span data-stu-id="934e7-152">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="934e7-153">Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="934e7-153">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="934e7-154">Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="934e7-154">The program prompts the user to enter a string.</span></span> <span data-ttu-id="934e7-155">Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="934e7-155">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="934e7-156">Wenn der Benutzer die EINGABETASTE drückt, ohne eine Zeichenfolge einzugeben, wird die Anwendung beendet und das Konsolenfenster geschlossen.</span><span class="sxs-lookup"><span data-stu-id="934e7-156">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="934e7-157">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="934e7-157">Save your changes.</span></span>

1. <span data-ttu-id="934e7-158">Führen Sie das Programm aus.</span><span class="sxs-lookup"><span data-stu-id="934e7-158">Run the program.</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="934e7-159">Testen Sie das Programm, indem Sie Zeichenfolgen eingeben und die <kbd>EINGABETASTE</kbd> drücken, und drücken Sie dann die <kbd>EINGABETASTE</kbd>, um das Programm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="934e7-159">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="934e7-160">Die Terminalausgabe sieht wie das folgende Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="934e7-160">The terminal output looks like the following example:</span></span>

   ```
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   A string that starts with a lowercase letter
   Input: A string that starts with a lowercase letter
   Begins with uppercase? : Yes
   ```

## <a name="additional-resources"></a><span data-ttu-id="934e7-161">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="934e7-161">Additional resources</span></span>

* [<span data-ttu-id="934e7-162">Entwickeln von Bibliotheken mit der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="934e7-162">Develop libraries with the .NET Core CLI</span></span>](libraries.md)

## <a name="next-steps"></a><span data-ttu-id="934e7-163">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="934e7-163">Next steps</span></span>

<span data-ttu-id="934e7-164">In diesem Tutorial haben Sie eine Projektmappe erstellt, ein Bibliotheksprojekt hinzugefügt und ein Konsolen-App-Projekt hinzugefügt, das die Bibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="934e7-164">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="934e7-165">Im nächsten Tutorial fügen Sie der Projektmappe ein Komponententestprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="934e7-165">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="934e7-166">Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="934e7-166">Test a .NET Standard library with .NET Core in Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
