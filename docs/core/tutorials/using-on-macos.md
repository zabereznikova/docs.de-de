---
title: Erste Schritte mit .NET Core unter Mac OS
description: "Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe mithilfe von Visual Studio Code."
keywords: .NET, .NET Core, Mac, macOS, Visual Studio Code
author: bleroy
ms.author: mairaw
ms.date: 03/23/2017
ms.topic: get-started-article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8ad82148-dac8-4b31-9128-b0e9610f4d9b
ms.workload: dotnetcore
ms.openlocfilehash: 5a8f1fca7623763d43b977d0cc44396de249c62e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="getting-started-with-net-core-on-macos"></a><span data-ttu-id="52c5c-104">Erste Schritte mit .NET Core unter Mac OS</span><span class="sxs-lookup"><span data-stu-id="52c5c-104">Getting started with .NET Core on macOS</span></span>

<span data-ttu-id="52c5c-105">Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe für macOS.</span><span class="sxs-lookup"><span data-stu-id="52c5c-105">This document provides the steps and workflow to create a .NET Core solution for macOS.</span></span> <span data-ttu-id="52c5c-106">Erfahren Sie, wie Projekte und Unittests erstellt, die Debuggingtools verwendet und Bibliotheken von Drittanbietern über [NuGet](https://www.nuget.org/) eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="52c5c-106">Learn how to create projects, unit tests, use the debugging tools, and incorporate third-party libraries via [NuGet](https://www.nuget.org/).</span></span>

> [!NOTE]
> <span data-ttu-id="52c5c-107">In diesem Artikel wird [Visual Studio Code](http://code.visualstudio.com) unter macOS verwendet.</span><span class="sxs-lookup"><span data-stu-id="52c5c-107">This article uses [Visual Studio Code](http://code.visualstudio.com) on macOS.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="52c5c-108">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="52c5c-108">Prerequisites</span></span>

<span data-ttu-id="52c5c-109">Installieren Sie das [.NET Core SDK](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="52c5c-109">Install the [.NET Core SDK](https://www.microsoft.com/net/core).</span></span> <span data-ttu-id="52c5c-110">Das .NET Core SDK umfasst die neueste Version von .NET Core-Framework und -Runtime.</span><span class="sxs-lookup"><span data-stu-id="52c5c-110">The .NET Core SDK includes the latest release of the .NET Core framework and runtime.</span></span>

<span data-ttu-id="52c5c-111">Installieren Sie [Visual Studio Code](http://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="52c5c-111">Install [Visual Studio Code](http://code.visualstudio.com).</span></span> <span data-ttu-id="52c5c-112">Im Rahmen dieses Artikels installieren Sie auch Visual Studio Code-Erweiterungen, die den .NET Core-Entwicklungsprozess verbessern.</span><span class="sxs-lookup"><span data-stu-id="52c5c-112">During the course of this article, you also install Visual Studio Code extensions that improve the .NET Core development experience.</span></span>

<span data-ttu-id="52c5c-113">Installieren Sie die C#-Erweiterung für Visual Studio Code, indem Sie Visual Studio Code öffnen und <kbd>F1</kbd> drücken, um die Visual Studio Code-Palette zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="52c5c-113">Install the Visual Studio Code C# extension by opening Visual Studio Code and pressing <kbd>F1</kbd> to open the Visual Studio Code palette.</span></span> <span data-ttu-id="52c5c-114">Geben Sie **ext install** ein, um die Liste mit Erweiterungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="52c5c-114">Type **ext install** to see the list of extensions.</span></span> <span data-ttu-id="52c5c-115">Wählen Sie die C#-Erweiterung aus.</span><span class="sxs-lookup"><span data-stu-id="52c5c-115">Select the C# extension.</span></span> <span data-ttu-id="52c5c-116">Starten Sie Visual Studio Code neu, um die Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="52c5c-116">Restart Visual Studio Code to activate the extension.</span></span> <span data-ttu-id="52c5c-117">Weitere Informationen finden Sie unter [Dokumentation zur C#-Erweiterung von Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="52c5c-117">For more information, see the [Visual Studio Code C# Extension documentation](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="getting-started"></a><span data-ttu-id="52c5c-118">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="52c5c-118">Getting started</span></span>

<span data-ttu-id="52c5c-119">In diesem Tutorial erstellen Sie drei Projekte: ein Bibliotheksprojekt, Tests für dieses Bibliotheksprojekt sowie eine Konsolenanwendung, die die Bibliothek nutzt.</span><span class="sxs-lookup"><span data-stu-id="52c5c-119">In this tutorial, you create three projects: a library project, tests for that library project, and a console application that makes use of the library.</span></span> <span data-ttu-id="52c5c-120">Sie können die Quelle für dieses Thema im Repository „dotnet/docs“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden).</span><span class="sxs-lookup"><span data-stu-id="52c5c-120">You can [view or download the source](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden) for this topic at the dotnet/docs repository on GitHub.</span></span> <span data-ttu-id="52c5c-121">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="52c5c-121">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="52c5c-122">Starten Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="52c5c-122">Start Visual Studio Code.</span></span> <span data-ttu-id="52c5c-123">Drücken Sie <kbd>STRG</kbd>+<kbd>\\`</kbd> (das Zeichen für das invertierte Hochkomma oder das Graviszeichen), oder wählen Sie **Anzeigen > Integriertes Terminal** aus dem Menü aus, um ein eingebettetes Terminal in Visual Studio Code zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="52c5c-123">Press <kbd>Ctrl</kbd>+<kbd>\\`</kbd> (the backquote or backtick character) or select **View > Integrated Terminal** from the menu to open an embedded terminal in Visual Studio Code.</span></span> <span data-ttu-id="52c5c-124">Sie können noch immer eine externe Shell mit dem Explorer-Befehl **In Eingabeaufforderung öffnen** (**In Terminal öffnen** unter Mac oder Linux) öffnen, wenn Sie lieber außerhalb von Visual Studio Code arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="52c5c-124">You can still open an external shell with the Explorer **Open in Command Prompt** command (**Open in Terminal** on Mac or Linux) if you prefer to work outside of Visual Studio Code.</span></span>

<span data-ttu-id="52c5c-125">Beginnen Sie, indem Sie eine Projektmappendatei erstellen, die als Container für mindestens ein .NET Core-Projekt dient.</span><span class="sxs-lookup"><span data-stu-id="52c5c-125">Begin by creating a solution file, which serves as a container for one or more .NET Core projects.</span></span> <span data-ttu-id="52c5c-126">Erstellen Sie im Terminal einen *golden*-Ordner, und öffnen Sie den Ordner.</span><span class="sxs-lookup"><span data-stu-id="52c5c-126">In the terminal, create a *golden* folder and open the folder.</span></span> <span data-ttu-id="52c5c-127">Dieser Ordner ist der Stamm der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="52c5c-127">This folder is the root of your solution.</span></span> <span data-ttu-id="52c5c-128">Führen Sie den [`dotnet new`](../tools/dotnet-new.md)-Befehl aus, um eine neue Projektmappe, *golden.sln*, zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="52c5c-128">Run the [`dotnet new`](../tools/dotnet-new.md) command to create a new solution, *golden.sln*:</span></span>

```console
dotnet new sln
```

<span data-ttu-id="52c5c-129">Führen Sie aus dem *golden*-Ordner den folgenden Befehl aus, um ein Bibliotheksprojekt zu erstellen, das zwei Dateien im *library*-Ordner erstellt: *library.csproj* and *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="52c5c-129">From the *golden* folder, execute the following command to create a library project, which produces two files,*library.csproj* and *Class1.cs*, in the *library* folder:</span></span>

```console
dotnet new classlib -o library
```

<span data-ttu-id="52c5c-130">Führen Sie den [`dotnet sln`](../tools/dotnet-sln.md)-Befehl aus, um das neu erstellte *library.csproj*-Projekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="52c5c-130">Execute the [`dotnet sln`](../tools/dotnet-sln.md) command to add the newly created *library.csproj* project to the solution:</span></span>

```console
dotnet sln add library/library.csproj
```

<span data-ttu-id="52c5c-131">Die *library.csproj*-Datei enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="52c5c-131">The *library.csproj* file contains the following information:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="52c5c-132">Unsere Bibliotheksmethode serialisieren und deserialisieren Objekte im JSON-Format.</span><span class="sxs-lookup"><span data-stu-id="52c5c-132">Our library methods serialize and deserialize objects in JSON format.</span></span> <span data-ttu-id="52c5c-133">Um die JSON-Serialisierung und Deserialisierung zu unterstützen, fügen Sie einen Verweis zum `Newtonsoft.Json`-NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="52c5c-133">To support JSON serialization and deserialization, add a reference to the `Newtonsoft.Json` NuGet package.</span></span> <span data-ttu-id="52c5c-134">Der `dotnet add`-Befehl fügt neue Elemente zu einem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="52c5c-134">The `dotnet add` command adds new items to a project.</span></span> <span data-ttu-id="52c5c-135">Um einen Verweis auf ein NuGet-Paket hinzuzufügen, führen Sie den [`dotnet add package`](../tools/dotnet-add-package.md)-Befehl aus, und geben den Namen des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="52c5c-135">To add a reference to a NuGet package, use the [`dotnet add package`](../tools/dotnet-add-package.md) command and specify the name of the package:</span></span>

```console
dotnet add library package Newtonsoft.Json
```

<span data-ttu-id="52c5c-136">Dadurch werden `Newtonsoft.Json` und dessen Abhängigkeiten zum Klassenbibliotheksprojekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52c5c-136">This adds `Newtonsoft.Json` and its dependencies to the library project.</span></span> <span data-ttu-id="52c5c-137">Alternativ können Sie die *library.csproj*-Datei manuell bearbeiten, und den folgenden Knoten hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="52c5c-137">Alternatively, manually edit the *library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="10.0.1" />
</ItemGroup>
```

<span data-ttu-id="52c5c-138">Führen Sie [`dotnet restore`](../tools/dotnet-restore.md) aus ([siehe Hinweis](#dotnet-restore-note)), wodurch Abhängigkeiten wiederhergestellt werden und ein *obj*-Ordner mit drei Dateien innerhalb von *library* erstellt wird, einschließlich einer *project.assets.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="52c5c-138">Execute [`dotnet restore`](../tools/dotnet-restore.md), ([see note](#dotnet-restore-note)) which restores dependencies and creates an *obj* folder inside *library* with three files in it, including a *project.assets.json* file:</span></span>

```console
dotnet restore
```

<span data-ttu-id="52c5c-139">Benennen Sie im Ordner *library* die Datei *Class1.cs* in *Thing.cs* um.</span><span class="sxs-lookup"><span data-stu-id="52c5c-139">In the *library* folder, rename the file *Class1.cs* to *Thing.cs*.</span></span> <span data-ttu-id="52c5c-140">Ersetzen Sie den Code durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="52c5c-140">Replace the code with the following:</span></span>

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

<span data-ttu-id="52c5c-141">Die `Thing`-Klasse enthält eine öffentliche Methode, `Get`, die die Summe zweier Zahlen durch Konvertierung der Summe in eine Zeichenfolge zurückgibt, die anschließend in eine ganze Zahl serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="52c5c-141">The `Thing` class contains one public method, `Get`, which returns the sum of two numbers but does so by converting the sum into a string and then deserializing it into an integer.</span></span> <span data-ttu-id="52c5c-142">Hierbei werden verschiedene moderne C#-Features verwendet, wie etwa [`using static`-Direktiven](../../csharp/language-reference/keywords/using-static.md), [Ausdruckskörpermitglieder](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members) und [interpolierte Zeichenfolgen](../../csharp/language-reference/keywords/interpolated-strings.md).</span><span class="sxs-lookup"><span data-stu-id="52c5c-142">This makes use of a number of modern C# features, such as [`using static` directives](../../csharp/language-reference/keywords/using-static.md), [expression-bodied members](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), and [interpolated strings](../../csharp/language-reference/keywords/interpolated-strings.md).</span></span>

<span data-ttu-id="52c5c-143">Erstellen Sie die Bibliothek mithilfe des [`dotnet build`](../tools/dotnet-build.md)-Befehls.</span><span class="sxs-lookup"><span data-stu-id="52c5c-143">Build the library with the [`dotnet build`](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="52c5c-144">Dadurch wird eine integrierte *library.dll*-Datei unter *golden/library/bin/Debug/netstandard1.4* erstellt.</span><span class="sxs-lookup"><span data-stu-id="52c5c-144">This produces a *library.dll* file under *golden/library/bin/Debug/netstandard1.4*:</span></span>

```console
dotnet build
```

## <a name="create-the-test-project"></a><span data-ttu-id="52c5c-145">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="52c5c-145">Create the test project</span></span>

<span data-ttu-id="52c5c-146">Erstellen Sie eine Testprojekt für die Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="52c5c-146">Build a test project for the library.</span></span> <span data-ttu-id="52c5c-147">Erstellen Sie aus dem *golden*-Ordner ein neues Testprojekt:</span><span class="sxs-lookup"><span data-stu-id="52c5c-147">From the *golden* folder, create a new test project:</span></span>

```console
dotnet new xunit -o test-library
```

<span data-ttu-id="52c5c-148">Fügen sie das Testprojekt zur Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="52c5c-148">Add the test project to the solution:</span></span>

```console
dotnet sln add test-library/test-library.csproj
```

<span data-ttu-id="52c5c-149">Fügen Sie der von Ihnen im letzten Abschnitt erstellten Bibliothek einen Projektverweis hinzu, damit der Compiler das Bibliotheksprojekt finden und verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="52c5c-149">Add a project reference the library you created in the previous section so that the compiler can find and use the library project.</span></span> <span data-ttu-id="52c5c-150">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="52c5c-150">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add test-library/test-library.csproj reference library/library.csproj
```

<span data-ttu-id="52c5c-151">Alternativ können Sie die *test-library.csproj*-Datei manuell bearbeiten, und den folgenden Knoten hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="52c5c-151">Alternatively, manually edit the *test-library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

<span data-ttu-id="52c5c-152">Nachdem Sie die Abhängigkeiten ordnungsgemäß konfiguriert haben, erstellen Sie nun die Tests für Ihre Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="52c5c-152">Now that the dependencies have been properly configured, create the tests for your library.</span></span> <span data-ttu-id="52c5c-153">Öffnen Sie *UnitTest1.cs*, und ersetzen Sie den Inhalt durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="52c5c-153">Open *UnitTest1.cs* and replace its contents with the following code:</span></span>

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

<span data-ttu-id="52c5c-154">Beachten Sie, dass der Wert 42 nicht 19+23 (oder 42) entspricht, wenn Sie zum ersten Mal den Komponententest (`Assert.NotEqual`) erstellen, was fehlschlagen wird.</span><span class="sxs-lookup"><span data-stu-id="52c5c-154">Note that you assert the value 42 is not equal to 19+23 (or 42) when you first create the unit test (`Assert.NotEqual`), which will fail.</span></span> <span data-ttu-id="52c5c-155">Ein wichtiger Schritt beim Erstellen von Komponententests ist die Erstellung des Tests, der zuerst einmal fehlschlägt, um seine Logik zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="52c5c-155">An important step in building unit tests is to create the test to fail once first to confirm its logic.</span></span>

<span data-ttu-id="52c5c-156">Führen Sie im *golden*-Ordner die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="52c5c-156">From the *golden* folder, execute the following commands:</span></span>

```console
dotnet restore 
dotnet test test-library/test-library.csproj
```

<span data-ttu-id="52c5c-157">Diese Befehle finden rekursiv alle Projekte, deren Abhängigkeiten wiederhergestellt werden sollen, erstellen sie und aktivieren den xUnit-Textlauf, um die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="52c5c-157">These commands will recursively find all projects to restore dependencies, build them, and activate the xUnit test runner to run the tests.</span></span> <span data-ttu-id="52c5c-158">Der einzelne Text schlägt wie erwartet fehl.</span><span class="sxs-lookup"><span data-stu-id="52c5c-158">The single test fails, as you expect.</span></span>

<span data-ttu-id="52c5c-159">Bearbeiten Sie die Datei *UnitTest1.cs*, und ändern Sie die Assertion von `Assert.NotEqual` zu `Assert.Equal`.</span><span class="sxs-lookup"><span data-stu-id="52c5c-159">Edit the *UnitTest1.cs* file and change the assertion from `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="52c5c-160">Führen Sie den folgenden Befehl aus dem *golden*-Ordner aus, um den Test erneut auszuführen, der diesmal erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52c5c-160">Execute the following command from the *golden* folder to re-run the test, which passes this time:</span></span>

```console
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a><span data-ttu-id="52c5c-161">Schreiben der Konsolen-App</span><span class="sxs-lookup"><span data-stu-id="52c5c-161">Create the console app</span></span>

<span data-ttu-id="52c5c-162">Die Konsolen-App, die Sie mithilfe der folgenden Schritte erstellen, ist vom Bibliotheksprojekt abhängig, das Sie zuvor erstellt haben, und ruft seine Bibliotheksmethode auf, wenn es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52c5c-162">The console app you create over the following steps takes a dependency on the library project you created earlier and calls its library method when it runs.</span></span> <span data-ttu-id="52c5c-163">Mithilfe dieses Entwicklungsmusters sehen Sie, wie Sie wiederverwendbare Bibliotheken für mehrere Projekte erstellen können.</span><span class="sxs-lookup"><span data-stu-id="52c5c-163">Using this pattern of development, you see how to create reusable libraries for multiple projects.</span></span>

<span data-ttu-id="52c5c-164">Erstellen Sie eine neue Konsolenanwendung aus dem *golden*-Ordner:</span><span class="sxs-lookup"><span data-stu-id="52c5c-164">Create a new console application from the *golden* folder:</span></span>

```console
dotnet new console -o app
```

<span data-ttu-id="52c5c-165">Fügen Sie das Konsolen-App-Projekt zur Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="52c5c-165">Add the console app project to the solution:</span></span>

```console
dotnet sln add app/app.csproj
```

<span data-ttu-id="52c5c-166">Erstellen Sie die Abhängigkeit von der Bibliothek, indem Sie den `dotnet add reference`-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="52c5c-166">Create the dependency on the library by running the `dotnet add reference` command:</span></span>

```console
dotnet add app/app.csproj reference library/library.csproj
```

<span data-ttu-id="52c5c-167">Führen Sie `dotnet restore` aus ([siehe Hinweis](#dotnet-restore-note)), um die Abhängigkeiten der drei Projekte in der Projektmappe wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="52c5c-167">Run `dotnet restore` ([see note](#dotnet-restore-note)) to restore the dependencies of the three projects in the solution.</span></span> <span data-ttu-id="52c5c-168">Öffnen Sie *Program.cs*, und ersetzen Sie den Inhalt der `Main`-Methode durch diese Zeile:</span><span class="sxs-lookup"><span data-stu-id="52c5c-168">Open *Program.cs* and replace the contents of the `Main` method with the following line:</span></span>

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

<span data-ttu-id="52c5c-169">Fügen Sie ganz oben in der *Program.cs*-Datei zwei `using`-Direktiven hinzu:</span><span class="sxs-lookup"><span data-stu-id="52c5c-169">Add two `using` directives to the top of the *Program.cs* file:</span></span>

```csharp
using static System.Console;
using Library;
```

<span data-ttu-id="52c5c-170">Führen Sie den folgenden `dotnet run`-Befehl aus, um die ausführbare Datei auszuführen, wobei die `-p`-Option für `dotnet run` das Projekt für die Hauptanwendung angibt.</span><span class="sxs-lookup"><span data-stu-id="52c5c-170">Execute the following `dotnet run` command to run the executable, where the `-p` option to `dotnet run` specifies the project for the main application.</span></span> <span data-ttu-id="52c5c-171">Die App erzeugt die Zeichenfolge „Die Antwort ist 42“.</span><span class="sxs-lookup"><span data-stu-id="52c5c-171">The app produces the string "The answer is 42".</span></span>

```console
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a><span data-ttu-id="52c5c-172">Debuggen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="52c5c-172">Debug the application</span></span>

<span data-ttu-id="52c5c-173">Legen Sie bei der Anweisung `WriteLine` in der `Main`-Methode einen Haltepunkt fest.</span><span class="sxs-lookup"><span data-stu-id="52c5c-173">Set a breakpoint at the `WriteLine` statement in the `Main` method.</span></span> <span data-ttu-id="52c5c-174">Dies erreichen Sie, indem Sie entweder die <kbd>F9</kbd>-Taste drücken, wenn sich der Cursor auf der `WriteLine`-Zeile befindet, oder indem Sie auf den linken Rand der Zeile klicken, wo Sie den Haltepunkt festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="52c5c-174">Do this by either pressing the <kbd>F9</kbd> key when the cursor is over the `WriteLine` line or by clicking the mouse in the left margin on the line where you want to set the breakpoint.</span></span> <span data-ttu-id="52c5c-175">Es erscheint ein Roter Kreis im Rand neben der Codezeile.</span><span class="sxs-lookup"><span data-stu-id="52c5c-175">A red circle will appear in the margin next to the line of code.</span></span> <span data-ttu-id="52c5c-176">Wenn der Haltepunkt erreicht ist, wird die Ausführung des Codes angehalten, *bevor* die Haltepunktzeile ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="52c5c-176">When the breakpoint is reached, code execution will stop *before* the breakpoint line is executed.</span></span>

<span data-ttu-id="52c5c-177">Öffnen Sie die Registerkarte „Debugger“, indem Sie das Debugger-Symbol in der Visual Studio Code-Symbolleiste auswählen, **Anzeigen > Debuggen** aus der Menüleiste auswählen oder den Tastaturkurzbefehl <kbd>STRG</kbd>+<kbd>UMSCHALT</kbd>+<kbd>D</kbd> verwenden:</span><span class="sxs-lookup"><span data-stu-id="52c5c-177">Open the debugger tab by selecting the Debug icon in the Visual Studio Code toolbar, selecting **View > Debug** from the menu bar, or using the keyboard shortcut <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>:</span></span>

![Visual Studio Code-Debugger](./media/using-on-macos/vscodedebugger.png)

<span data-ttu-id="52c5c-179">Klicken Sie auf die Schaltfläche „Wiedergabe“, um die Anwendung unter dem Debugger zu starten.</span><span class="sxs-lookup"><span data-stu-id="52c5c-179">Press the Play button to start the application under the debugger.</span></span> <span data-ttu-id="52c5c-180">Die App startet mit der Ausführung und läuft bis zum Haltepunkt, wo sie anhält.</span><span class="sxs-lookup"><span data-stu-id="52c5c-180">The app begins execution and runs to the breakpoint, where it stops.</span></span> <span data-ttu-id="52c5c-181">Führen Sie die `Get`-Methode schrittweise aus, und stellen Sie sicher, dass Sie die richtigen Argumente eingefügt haben.</span><span class="sxs-lookup"><span data-stu-id="52c5c-181">Step into the `Get` method and make sure that you have passed in the correct arguments.</span></span> <span data-ttu-id="52c5c-182">Bestätigen Sie, dass die Antwort 42 ist.</span><span class="sxs-lookup"><span data-stu-id="52c5c-182">Confirm that the answer is 42.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]