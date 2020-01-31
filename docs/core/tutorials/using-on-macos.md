---
title: 'Tutorial: Erstellen einer .NET Core-Lösung unter macOS mit Visual Studio Code'
description: Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe mithilfe von Visual Studio Code.
ms.date: 12/19/2019
ms.openlocfilehash: e3c210d4391c0e3c9c3455ecf23dd138abdb4363
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741538"
---
# <a name="tutorial-create-a-net-core-solution-in-macos-using-visual-studio-code"></a><span data-ttu-id="fa338-103">Tutorial: Erstellen einer .NET Core-Lösung unter macOS mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="fa338-103">Tutorial: Create a .NET Core solution in macOS using Visual Studio Code</span></span>

<span data-ttu-id="fa338-104">Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe für macOS.</span><span class="sxs-lookup"><span data-stu-id="fa338-104">This document provides the steps and workflow to create a .NET Core solution for macOS.</span></span> <span data-ttu-id="fa338-105">Erfahren Sie, wie Projekte und Unittests erstellt, die Debuggingtools verwendet und Bibliotheken von Drittanbietern über [NuGet](https://www.nuget.org/) eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="fa338-105">Learn how to create projects, unit tests, use the debugging tools, and incorporate third-party libraries via [NuGet](https://www.nuget.org/).</span></span>

> [!NOTE]
> <span data-ttu-id="fa338-106">In diesem Artikel wird [Visual Studio Code](https://code.visualstudio.com) unter macOS verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa338-106">This article uses [Visual Studio Code](https://code.visualstudio.com) on macOS.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa338-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="fa338-107">Prerequisites</span></span>

<span data-ttu-id="fa338-108">Installieren Sie das [.NET Core SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="fa338-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="fa338-109">Das .NET Core SDK umfasst die neueste Version von .NET Core-Framework und -Runtime.</span><span class="sxs-lookup"><span data-stu-id="fa338-109">The .NET Core SDK includes the latest release of the .NET Core framework and runtime.</span></span>

<span data-ttu-id="fa338-110">Installieren Sie [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="fa338-110">Install [Visual Studio Code](https://code.visualstudio.com).</span></span> <span data-ttu-id="fa338-111">Im Rahmen dieses Artikels installieren Sie auch Visual Studio Code-Erweiterungen, die den .NET Core-Entwicklungsprozess verbessern.</span><span class="sxs-lookup"><span data-stu-id="fa338-111">During the course of this article, you also install Visual Studio Code extensions that improve the .NET Core development experience.</span></span>

<span data-ttu-id="fa338-112">Installieren Sie die C#-Erweiterung für Visual Studio Code, indem Sie Visual Studio Code öffnen und <kbd>Fn</kbd>+<kbd>F1</kbd> drücken, um die Visual Studio Code-Palette zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fa338-112">Install the Visual Studio Code C# extension by opening Visual Studio Code and pressing <kbd>Fn</kbd>+<kbd>F1</kbd> to open the Visual Studio Code palette.</span></span> <span data-ttu-id="fa338-113">Geben Sie **ext install** ein, um die Liste mit Erweiterungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fa338-113">Type **ext install** to see the list of extensions.</span></span> <span data-ttu-id="fa338-114">Wählen Sie die C#-Erweiterung aus.</span><span class="sxs-lookup"><span data-stu-id="fa338-114">Select the C# extension.</span></span> <span data-ttu-id="fa338-115">Starten Sie Visual Studio Code neu, um die Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fa338-115">Restart Visual Studio Code to activate the extension.</span></span> <span data-ttu-id="fa338-116">Weitere Informationen finden Sie unter [Dokumentation zur C#-Erweiterung von Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="fa338-116">For more information, see the [Visual Studio Code C# Extension documentation](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="fa338-117">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="fa338-117">Get started</span></span>

<span data-ttu-id="fa338-118">In diesem Tutorial erstellen Sie drei Projekte: ein Bibliotheksprojekt, Tests für dieses Bibliotheksprojekt sowie eine Konsolenanwendung, die die Bibliothek nutzt.</span><span class="sxs-lookup"><span data-stu-id="fa338-118">In this tutorial, you create three projects: a library project, tests for that library project, and a console application that makes use of the library.</span></span> <span data-ttu-id="fa338-119">Sie können die Quelle für diesen Artikel im Repository „dotnet/samples“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/core/getting-started/golden).</span><span class="sxs-lookup"><span data-stu-id="fa338-119">You can [view or download the source](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) for this article at the dotnet/samples repository on GitHub.</span></span> <span data-ttu-id="fa338-120">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="fa338-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="fa338-121">Starten Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fa338-121">Start Visual Studio Code.</span></span> <span data-ttu-id="fa338-122">Drücken Sie <kbd>STRG</kbd><kbd>\`</kbd> (das Zeichen für das invertierte Hochkomma oder das Graviszeichen), oder wählen Sie **Anzeigen** > **Terminal** aus dem Menü aus, um ein eingebettetes Terminal in Visual Studio Code zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fa338-122">Press <kbd>Ctrl</kbd><kbd>\`</kbd> (the backquote or backtick character) or select **View** > **Terminal** from the menu to open an embedded terminal in Visual Studio Code.</span></span> <span data-ttu-id="fa338-123">Sie können noch immer eine externe Shell mit dem Explorer-Befehl **In Eingabeaufforderung öffnen** (**In Terminal öffnen** unter macOS oder Linux) öffnen, wenn Sie lieber außerhalb von Visual Studio Code arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="fa338-123">You can still open an external shell with the Explorer **Open in Command Prompt** command (**Open in Terminal** on macOS or Linux) if you prefer to work outside of Visual Studio Code.</span></span>

<span data-ttu-id="fa338-124">Beginnen Sie, indem Sie eine Projektmappendatei erstellen, die als Container für mindestens ein .NET Core-Projekt dient.</span><span class="sxs-lookup"><span data-stu-id="fa338-124">Begin by creating a solution file, which serves as a container for one or more .NET Core projects.</span></span> <span data-ttu-id="fa338-125">Führen Sie im Terminal den Befehl [`dotnet new`](../tools/dotnet-new.md) aus, um eine neue Projektmappe *golden.sln* in einem neuen Ordner namens *golden* zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="fa338-125">In the terminal, run the [`dotnet new`](../tools/dotnet-new.md) command to create a new solution *golden.sln* inside a new folder named *golden*:</span></span>

```dotnetcli
dotnet new sln -o golden
```

<span data-ttu-id="fa338-126">Navigieren Sie zum neuen Ordner *golden*, und führen Sie den folgenden Befehl aus, um ein Bibliotheksprojekt zu erstellen, das zwei Dateien im Ordner *library* erstellt: *library.csproj* und *Class1.cs*:</span><span class="sxs-lookup"><span data-stu-id="fa338-126">Navigate to the new *golden* folder and execute the following command to create a library project, which produces two files,*library.csproj* and *Class1.cs*, in the *library* folder:</span></span>

```dotnetcli
dotnet new classlib -o library
```

<span data-ttu-id="fa338-127">Führen Sie den [`dotnet sln`](../tools/dotnet-sln.md)-Befehl aus, um das neu erstellte *library.csproj*-Projekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="fa338-127">Execute the [`dotnet sln`](../tools/dotnet-sln.md) command to add the newly created *library.csproj* project to the solution:</span></span>

```dotnetcli
dotnet sln add library/library.csproj
```

<span data-ttu-id="fa338-128">Die *library.csproj*-Datei enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="fa338-128">The *library.csproj* file contains the following information:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="fa338-129">Unsere Bibliotheksmethode serialisieren und deserialisieren Objekte im JSON-Format.</span><span class="sxs-lookup"><span data-stu-id="fa338-129">Our library methods serialize and deserialize objects in JSON format.</span></span> <span data-ttu-id="fa338-130">Um die JSON-Serialisierung und Deserialisierung zu unterstützen, fügen Sie einen Verweis zum `Newtonsoft.Json`-NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="fa338-130">To support JSON serialization and deserialization, add a reference to the `Newtonsoft.Json` NuGet package.</span></span> <span data-ttu-id="fa338-131">Der `dotnet add`-Befehl fügt neue Elemente zu einem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="fa338-131">The `dotnet add` command adds new items to a project.</span></span> <span data-ttu-id="fa338-132">Um einen Verweis auf ein NuGet-Paket hinzuzufügen, führen Sie den [`dotnet add package`](../tools/dotnet-add-package.md)-Befehl aus, und geben den Namen des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="fa338-132">To add a reference to a NuGet package, use the [`dotnet add package`](../tools/dotnet-add-package.md) command and specify the name of the package:</span></span>

```dotnetcli
dotnet add library package Newtonsoft.Json
```

<span data-ttu-id="fa338-133">Dadurch werden `Newtonsoft.Json` und dessen Abhängigkeiten zum Klassenbibliotheksprojekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fa338-133">This adds `Newtonsoft.Json` and its dependencies to the library project.</span></span> <span data-ttu-id="fa338-134">Alternativ können Sie die *library.csproj*-Datei manuell bearbeiten, und den folgenden Knoten hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="fa338-134">Alternatively, manually edit the *library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

<span data-ttu-id="fa338-135">Führen Sie [`dotnet restore`](../tools/dotnet-restore.md) aus ([siehe Hinweis](#dotnet-restore-note)), wodurch Abhängigkeiten wiederhergestellt werden und ein *obj*-Ordner mit drei Dateien innerhalb von *library* erstellt wird, einschließlich einer *project.assets.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="fa338-135">Execute [`dotnet restore`](../tools/dotnet-restore.md), ([see note](#dotnet-restore-note)) which restores dependencies and creates an *obj* folder inside *library* with three files in it, including a *project.assets.json* file:</span></span>

```dotnetcli
dotnet restore
```

<span data-ttu-id="fa338-136">Benennen Sie im Ordner *library* die Datei *Class1.cs* in *Thing.cs* um.</span><span class="sxs-lookup"><span data-stu-id="fa338-136">In the *library* folder, rename the file *Class1.cs* to *Thing.cs*.</span></span> <span data-ttu-id="fa338-137">Ersetzen Sie den Code durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fa338-137">Replace the code with the following:</span></span>

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

<span data-ttu-id="fa338-138">Die `Thing`-Klasse enthält eine öffentliche Methode, `Get`, die die Summe zweier Zahlen durch Konvertierung der Summe in eine Zeichenfolge zurückgibt, die anschließend in eine ganze Zahl serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="fa338-138">The `Thing` class contains one public method, `Get`, which returns the sum of two numbers but does so by converting the sum into a string and then deserializing it into an integer.</span></span> <span data-ttu-id="fa338-139">Hierbei werden verschiedene moderne C#-Features wie etwa [`using static`-Anweisungen](../../csharp/language-reference/keywords/using-static.md), [Ausdruckskörpermember](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members) und [Zeichenfolgeninterpolation](../../csharp/language-reference/tokens/interpolated.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa338-139">This makes use of a number of modern C# features, such as [`using static` directives](../../csharp/language-reference/keywords/using-static.md), [expression-bodied members](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), and [string interpolation](../../csharp/language-reference/tokens/interpolated.md).</span></span>

<span data-ttu-id="fa338-140">Erstellen Sie die Bibliothek mithilfe des [`dotnet build`](../tools/dotnet-build.md)-Befehls.</span><span class="sxs-lookup"><span data-stu-id="fa338-140">Build the library with the [`dotnet build`](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="fa338-141">Dadurch wird eine integrierte *library.dll*-Datei unter *golden/library/bin/Debug/netstandard1.4* erstellt.</span><span class="sxs-lookup"><span data-stu-id="fa338-141">This produces a *library.dll* file under *golden/library/bin/Debug/netstandard1.4*:</span></span>

```dotnetcli
dotnet build
```

## <a name="create-the-test-project"></a><span data-ttu-id="fa338-142">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="fa338-142">Create the test project</span></span>

<span data-ttu-id="fa338-143">Erstellen Sie eine Testprojekt für die Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="fa338-143">Build a test project for the library.</span></span> <span data-ttu-id="fa338-144">Erstellen Sie aus dem *golden*-Ordner ein neues Testprojekt:</span><span class="sxs-lookup"><span data-stu-id="fa338-144">From the *golden* folder, create a new test project:</span></span>

```dotnetcli
dotnet new xunit -o test-library
```

<span data-ttu-id="fa338-145">Fügen sie das Testprojekt zur Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="fa338-145">Add the test project to the solution:</span></span>

```dotnetcli
dotnet sln add test-library/test-library.csproj
```

<span data-ttu-id="fa338-146">Fügen Sie der von Ihnen im letzten Abschnitt erstellten Bibliothek einen Projektverweis hinzu, damit der Compiler das Bibliotheksprojekt finden und verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="fa338-146">Add a project reference the library you created in the previous section so that the compiler can find and use the library project.</span></span> <span data-ttu-id="fa338-147">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="fa338-147">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add test-library/test-library.csproj reference library/library.csproj
```

<span data-ttu-id="fa338-148">Alternativ können Sie die *test-library.csproj*-Datei manuell bearbeiten, und den folgenden Knoten hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="fa338-148">Alternatively, manually edit the *test-library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

<span data-ttu-id="fa338-149">Nachdem Sie die Abhängigkeiten ordnungsgemäß konfiguriert haben, erstellen Sie nun die Tests für Ihre Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="fa338-149">Now that the dependencies have been properly configured, create the tests for your library.</span></span> <span data-ttu-id="fa338-150">Öffnen Sie *UnitTest1.cs*, und ersetzen Sie den Inhalt durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="fa338-150">Open *UnitTest1.cs* and replace its contents with the following code:</span></span>

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing()
        {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

<span data-ttu-id="fa338-151">Beachten Sie, dass der Wert 42 nicht 19+23 (oder 42) entspricht, wenn Sie zum ersten Mal den Komponententest (`Assert.NotEqual`) erstellen, was fehlschlagen wird.</span><span class="sxs-lookup"><span data-stu-id="fa338-151">Note that you assert the value 42 is not equal to 19+23 (or 42) when you first create the unit test (`Assert.NotEqual`), which will fail.</span></span> <span data-ttu-id="fa338-152">Ein wichtiger Schritt beim Erstellen von Komponententests ist die Erstellung des Tests, der zuerst einmal fehlschlägt, um seine Logik zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="fa338-152">An important step in building unit tests is to create the test to fail once first to confirm its logic.</span></span>

<span data-ttu-id="fa338-153">Führen Sie im *golden*-Ordner die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="fa338-153">From the *golden* folder, execute the following commands:</span></span>

```dotnetcli
dotnet restore 
dotnet test test-library/test-library.csproj
```

<span data-ttu-id="fa338-154">Diese Befehle finden rekursiv alle Projekte, deren Abhängigkeiten wiederhergestellt werden sollen, erstellen sie und aktivieren den xUnit-Textlauf, um die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fa338-154">These commands will recursively find all projects to restore dependencies, build them, and activate the xUnit test runner to run the tests.</span></span> <span data-ttu-id="fa338-155">Der einzelne Text schlägt wie erwartet fehl.</span><span class="sxs-lookup"><span data-stu-id="fa338-155">The single test fails, as you expect.</span></span>

<span data-ttu-id="fa338-156">Bearbeiten Sie die Datei *UnitTest1.cs*, und ändern Sie die Assertion von `Assert.NotEqual` zu `Assert.Equal`.</span><span class="sxs-lookup"><span data-stu-id="fa338-156">Edit the *UnitTest1.cs* file and change the assertion from `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="fa338-157">Führen Sie den folgenden Befehl aus dem *golden*-Ordner aus, um den Test erneut auszuführen, der diesmal erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fa338-157">Execute the following command from the *golden* folder to re-run the test, which passes this time:</span></span>

```dotnetcli
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a><span data-ttu-id="fa338-158">Schreiben der Konsolen-App</span><span class="sxs-lookup"><span data-stu-id="fa338-158">Create the console app</span></span>

<span data-ttu-id="fa338-159">Die Konsolen-App, die Sie mithilfe der folgenden Schritte erstellen, ist vom Bibliotheksprojekt abhängig, das Sie zuvor erstellt haben, und ruft seine Bibliotheksmethode auf, wenn es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fa338-159">The console app you create over the following steps takes a dependency on the library project you created earlier and calls its library method when it runs.</span></span> <span data-ttu-id="fa338-160">Mithilfe dieses Entwicklungsmusters sehen Sie, wie Sie wiederverwendbare Bibliotheken für mehrere Projekte erstellen können.</span><span class="sxs-lookup"><span data-stu-id="fa338-160">Using this pattern of development, you see how to create reusable libraries for multiple projects.</span></span>

<span data-ttu-id="fa338-161">Erstellen Sie eine neue Konsolenanwendung aus dem *golden*-Ordner:</span><span class="sxs-lookup"><span data-stu-id="fa338-161">Create a new console application from the *golden* folder:</span></span>

```dotnetcli
dotnet new console -o app
```

<span data-ttu-id="fa338-162">Fügen Sie das Konsolen-App-Projekt zur Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="fa338-162">Add the console app project to the solution:</span></span>

```dotnetcli
dotnet sln add app/app.csproj
```

<span data-ttu-id="fa338-163">Erstellen Sie die Abhängigkeit von der Bibliothek, indem Sie den `dotnet add reference`-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="fa338-163">Create the dependency on the library by running the `dotnet add reference` command:</span></span>

```dotnetcli
dotnet add app/app.csproj reference library/library.csproj
```

<span data-ttu-id="fa338-164">Führen Sie `dotnet restore` aus ([siehe Hinweis](#dotnet-restore-note)), um die Abhängigkeiten der drei Projekte in der Projektmappe wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="fa338-164">Run `dotnet restore` ([see note](#dotnet-restore-note)) to restore the dependencies of the three projects in the solution.</span></span> <span data-ttu-id="fa338-165">Öffnen Sie *Program.cs*, und ersetzen Sie den Inhalt der `Main`-Methode durch diese Zeile:</span><span class="sxs-lookup"><span data-stu-id="fa338-165">Open *Program.cs* and replace the contents of the `Main` method with the following line:</span></span>

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

<span data-ttu-id="fa338-166">Fügen Sie ganz oben in der *Program.cs*-Datei zwei `using`-Direktiven hinzu:</span><span class="sxs-lookup"><span data-stu-id="fa338-166">Add two `using` directives to the top of the *Program.cs* file:</span></span>

```csharp
using static System.Console;
using Library;
```

<span data-ttu-id="fa338-167">Führen Sie den folgenden `dotnet run`-Befehl aus, um die ausführbare Datei auszuführen, wobei die `-p`-Option für `dotnet run` das Projekt für die Hauptanwendung angibt.</span><span class="sxs-lookup"><span data-stu-id="fa338-167">Execute the following `dotnet run` command to run the executable, where the `-p` option to `dotnet run` specifies the project for the main application.</span></span> <span data-ttu-id="fa338-168">Die App erzeugt die Zeichenfolge „Die Antwort ist 42“.</span><span class="sxs-lookup"><span data-stu-id="fa338-168">The app produces the string "The answer is 42".</span></span>

```dotnetcli
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a><span data-ttu-id="fa338-169">Debuggen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="fa338-169">Debug the application</span></span>

<span data-ttu-id="fa338-170">Legen Sie bei der Anweisung `WriteLine` in der `Main`-Methode einen Haltepunkt fest.</span><span class="sxs-lookup"><span data-stu-id="fa338-170">Set a breakpoint at the `WriteLine` statement in the `Main` method.</span></span> <span data-ttu-id="fa338-171">Sie erreichen dies, indem Sie entweder die <kbd>Fn</kbd>+<kbd>F9</kbd>-Taste drücken, wenn sich der Cursor in der `WriteLine`-Zeile befindet, oder indem Sie auf den linken Rand der Zeile klicken, in der Sie den Breakpoint festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="fa338-171">Do this by either pressing the <kbd>Fn</kbd>+<kbd>F9</kbd> key when the cursor is over the `WriteLine` line or by clicking the mouse in the left margin on the line where you want to set the breakpoint.</span></span> <span data-ttu-id="fa338-172">Es erscheint ein Roter Kreis im Rand neben der Codezeile.</span><span class="sxs-lookup"><span data-stu-id="fa338-172">A red circle will appear in the margin next to the line of code.</span></span> <span data-ttu-id="fa338-173">Wenn der Haltepunkt erreicht ist, wird die Ausführung des Codes angehalten, *bevor* die Haltepunktzeile ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fa338-173">When the breakpoint is reached, code execution will stop *before* the breakpoint line is executed.</span></span>

<span data-ttu-id="fa338-174">Öffnen Sie die Registerkarte „Debugger“, indem Sie das Symbol zum Debuggen in der Visual Studio Code-Symbolleiste auswählen. Wählen Sie **Anzeigen** > **Debuggen** aus der Menüleiste aus, oder verwenden Sie die Tastenkombination<kbd>&#8679;</kbd><kbd>&#8984;</kbd><kbd>D</kbd>:</span><span class="sxs-lookup"><span data-stu-id="fa338-174">Open the debugger tab by selecting the Debug icon in the Visual Studio Code toolbar, selecting **View** > **Debug** from the menu bar, or using the keyboard shortcut <kbd>&#8679;</kbd><kbd>&#8984;</kbd><kbd>D</kbd>:</span></span>

![Visual Studio Code-Debugger](./media/using-on-macos/visual-studio-code-debugger.png)

<span data-ttu-id="fa338-176">Klicken Sie auf die Schaltfläche „Wiedergabe“, um die Anwendung unter dem Debugger zu starten.</span><span class="sxs-lookup"><span data-stu-id="fa338-176">Press the Play button to start the application under the debugger.</span></span> <span data-ttu-id="fa338-177">Sie haben in diesem Projekt sowohl ein Testprojekt als auch eine Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="fa338-177">You've created both a test project and an application in this project.</span></span> <span data-ttu-id="fa338-178">Der Debugger fragt, welches Projekt gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fa338-178">The debugger asks which project you want to start.</span></span> <span data-ttu-id="fa338-179">Wählen Sie das Projekt „App“ aus.</span><span class="sxs-lookup"><span data-stu-id="fa338-179">Select the "app" project.</span></span> <span data-ttu-id="fa338-180">Die App startet mit der Ausführung und läuft bis zum Haltepunkt, wo sie anhält.</span><span class="sxs-lookup"><span data-stu-id="fa338-180">The app begins execution and runs to the breakpoint, where it stops.</span></span> <span data-ttu-id="fa338-181">Führen Sie die `Get`-Methode schrittweise aus, und stellen Sie sicher, dass Sie die richtigen Argumente eingefügt haben.</span><span class="sxs-lookup"><span data-stu-id="fa338-181">Step into the `Get` method and make sure that you have passed in the correct arguments.</span></span> <span data-ttu-id="fa338-182">Bestätigen Sie, dass die Antwort 42 ist.</span><span class="sxs-lookup"><span data-stu-id="fa338-182">Confirm that the answer is 42.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
