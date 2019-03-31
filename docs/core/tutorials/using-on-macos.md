---
title: Erste Schritte mit .NET Core unter macOS
description: Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe mithilfe von Visual Studio Code.
author: bleroy
ms.date: 03/23/2017
ms.custom: seodec18
ms.openlocfilehash: e5ac6fa04a2a5001146936de56acafeec7dd895d
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409496"
---
# <a name="get-started-with-net-core-on-macos"></a><span data-ttu-id="cdf96-103">Erste Schritte mit .NET Core unter macOS</span><span class="sxs-lookup"><span data-stu-id="cdf96-103">Get started with .NET Core on macOS</span></span>

<span data-ttu-id="cdf96-104">Dieses Dokument bietet einen Überblick über die Schritte und den Workflow zum Erstellen einer .NET Core-Projektmappe für macOS.</span><span class="sxs-lookup"><span data-stu-id="cdf96-104">This document provides the steps and workflow to create a .NET Core solution for macOS.</span></span> <span data-ttu-id="cdf96-105">Erfahren Sie, wie Projekte und Unittests erstellt, die Debuggingtools verwendet und Bibliotheken von Drittanbietern über [NuGet](https://www.nuget.org/) eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="cdf96-105">Learn how to create projects, unit tests, use the debugging tools, and incorporate third-party libraries via [NuGet](https://www.nuget.org/).</span></span>

> [!NOTE]
> <span data-ttu-id="cdf96-106">In diesem Artikel wird [Visual Studio Code](https://code.visualstudio.com) unter macOS verwendet.</span><span class="sxs-lookup"><span data-stu-id="cdf96-106">This article uses [Visual Studio Code](https://code.visualstudio.com) on macOS.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cdf96-107">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="cdf96-107">Prerequisites</span></span>

<span data-ttu-id="cdf96-108">Installieren Sie das [.NET Core SDK](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="cdf96-108">Install the [.NET Core SDK](https://www.microsoft.com/net/core).</span></span> <span data-ttu-id="cdf96-109">Das .NET Core SDK umfasst die neueste Version von .NET Core-Framework und -Runtime.</span><span class="sxs-lookup"><span data-stu-id="cdf96-109">The .NET Core SDK includes the latest release of the .NET Core framework and runtime.</span></span>

<span data-ttu-id="cdf96-110">Installieren Sie [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="cdf96-110">Install [Visual Studio Code](https://code.visualstudio.com).</span></span> <span data-ttu-id="cdf96-111">Im Rahmen dieses Artikels installieren Sie auch Visual Studio Code-Erweiterungen, die den .NET Core-Entwicklungsprozess verbessern.</span><span class="sxs-lookup"><span data-stu-id="cdf96-111">During the course of this article, you also install Visual Studio Code extensions that improve the .NET Core development experience.</span></span>

<span data-ttu-id="cdf96-112">Installieren Sie die C#-Erweiterung für Visual Studio Code, indem Sie Visual Studio Code öffnen und <kbd>F1</kbd> drücken, um die Visual Studio Code-Palette zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cdf96-112">Install the Visual Studio Code C# extension by opening Visual Studio Code and pressing <kbd>F1</kbd> to open the Visual Studio Code palette.</span></span> <span data-ttu-id="cdf96-113">Geben Sie **ext install** ein, um die Liste mit Erweiterungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cdf96-113">Type **ext install** to see the list of extensions.</span></span> <span data-ttu-id="cdf96-114">Wählen Sie die C#-Erweiterung aus.</span><span class="sxs-lookup"><span data-stu-id="cdf96-114">Select the C# extension.</span></span> <span data-ttu-id="cdf96-115">Starten Sie Visual Studio Code neu, um die Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cdf96-115">Restart Visual Studio Code to activate the extension.</span></span> <span data-ttu-id="cdf96-116">Weitere Informationen finden Sie unter [Dokumentation zur C#-Erweiterung von Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="cdf96-116">For more information, see the [Visual Studio Code C# Extension documentation](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="cdf96-117">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="cdf96-117">Get started</span></span>

<span data-ttu-id="cdf96-118">In diesem Tutorial erstellen Sie drei Projekte: ein Bibliotheksprojekt, Tests für dieses Bibliotheksprojekt sowie eine Konsolenanwendung, die die Bibliothek nutzt.</span><span class="sxs-lookup"><span data-stu-id="cdf96-118">In this tutorial, you create three projects: a library project, tests for that library project, and a console application that makes use of the library.</span></span> <span data-ttu-id="cdf96-119">Sie können die Quelle für dieses Thema im Repository „dotnet/samples“ auf GitHub [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/core/getting-started/golden).</span><span class="sxs-lookup"><span data-stu-id="cdf96-119">You can [view or download the source](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) for this topic at the dotnet/samples repository on GitHub.</span></span> <span data-ttu-id="cdf96-120">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="cdf96-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="cdf96-121">Starten Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="cdf96-121">Start Visual Studio Code.</span></span> <span data-ttu-id="cdf96-122">Drücken Sie <kbd>STRG</kbd>+<kbd>\`</kbd> (das Zeichen für das invertierte Hochkomma oder das Graviszeichen), oder wählen Sie **Anzeigen > Integriertes Terminal** aus dem Menü aus, um ein eingebettetes Terminal in Visual Studio Code zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cdf96-122">Press <kbd>Ctrl</kbd>+<kbd>\`</kbd> (the backquote or backtick character) or select **View > Integrated Terminal** from the menu to open an embedded terminal in Visual Studio Code.</span></span> <span data-ttu-id="cdf96-123">Sie können noch immer eine externe Shell mit dem Explorer-Befehl **In Eingabeaufforderung öffnen** (**In Terminal öffnen** unter Mac oder Linux) öffnen, wenn Sie lieber außerhalb von Visual Studio Code arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="cdf96-123">You can still open an external shell with the Explorer **Open in Command Prompt** command (**Open in Terminal** on Mac or Linux) if you prefer to work outside of Visual Studio Code.</span></span>

<span data-ttu-id="cdf96-124">Beginnen Sie, indem Sie eine Projektmappendatei erstellen, die als Container für mindestens ein .NET Core-Projekt dient.</span><span class="sxs-lookup"><span data-stu-id="cdf96-124">Begin by creating a solution file, which serves as a container for one or more .NET Core projects.</span></span> <span data-ttu-id="cdf96-125">Erstellen Sie im Terminal einen *golden*-Ordner, und öffnen Sie den Ordner.</span><span class="sxs-lookup"><span data-stu-id="cdf96-125">In the terminal, create a *golden* folder and open the folder.</span></span> <span data-ttu-id="cdf96-126">Dieser Ordner ist der Stamm der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="cdf96-126">This folder is the root of your solution.</span></span> <span data-ttu-id="cdf96-127">Führen Sie den [`dotnet new`](../tools/dotnet-new.md)-Befehl aus, um eine neue Projektmappe, *golden.sln*, zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="cdf96-127">Run the [`dotnet new`](../tools/dotnet-new.md) command to create a new solution, *golden.sln*:</span></span>

```console
dotnet new sln
```

<span data-ttu-id="cdf96-128">Führen Sie aus dem *golden*-Ordner den folgenden Befehl aus, um ein Bibliotheksprojekt zu erstellen, das zwei Dateien im *library*-Ordner erstellt: *library.csproj* and *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="cdf96-128">From the *golden* folder, execute the following command to create a library project, which produces two files,*library.csproj* and *Class1.cs*, in the *library* folder:</span></span>

```console
dotnet new classlib -o library
```

<span data-ttu-id="cdf96-129">Führen Sie den [`dotnet sln`](../tools/dotnet-sln.md)-Befehl aus, um das neu erstellte *library.csproj*-Projekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="cdf96-129">Execute the [`dotnet sln`](../tools/dotnet-sln.md) command to add the newly created *library.csproj* project to the solution:</span></span>

```console
dotnet sln add library/library.csproj
```

<span data-ttu-id="cdf96-130">Die *library.csproj*-Datei enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="cdf96-130">The *library.csproj* file contains the following information:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="cdf96-131">Unsere Bibliotheksmethode serialisieren und deserialisieren Objekte im JSON-Format.</span><span class="sxs-lookup"><span data-stu-id="cdf96-131">Our library methods serialize and deserialize objects in JSON format.</span></span> <span data-ttu-id="cdf96-132">Um die JSON-Serialisierung und Deserialisierung zu unterstützen, fügen Sie einen Verweis zum `Newtonsoft.Json`-NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="cdf96-132">To support JSON serialization and deserialization, add a reference to the `Newtonsoft.Json` NuGet package.</span></span> <span data-ttu-id="cdf96-133">Der `dotnet add`-Befehl fügt neue Elemente zu einem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="cdf96-133">The `dotnet add` command adds new items to a project.</span></span> <span data-ttu-id="cdf96-134">Um einen Verweis auf ein NuGet-Paket hinzuzufügen, führen Sie den [`dotnet add package`](../tools/dotnet-add-package.md)-Befehl aus, und geben den Namen des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="cdf96-134">To add a reference to a NuGet package, use the [`dotnet add package`](../tools/dotnet-add-package.md) command and specify the name of the package:</span></span>

```console
dotnet add library package Newtonsoft.Json
```

<span data-ttu-id="cdf96-135">Dadurch werden `Newtonsoft.Json` und dessen Abhängigkeiten zum Klassenbibliotheksprojekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cdf96-135">This adds `Newtonsoft.Json` and its dependencies to the library project.</span></span> <span data-ttu-id="cdf96-136">Alternativ können Sie die *library.csproj*-Datei manuell bearbeiten, und den folgenden Knoten hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="cdf96-136">Alternatively, manually edit the *library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="10.0.1" />
</ItemGroup>
```

<span data-ttu-id="cdf96-137">Führen Sie [`dotnet restore`](../tools/dotnet-restore.md) aus ([siehe Hinweis](#dotnet-restore-note)), wodurch Abhängigkeiten wiederhergestellt werden und ein *obj*-Ordner mit drei Dateien innerhalb von *library* erstellt wird, einschließlich einer *project.assets.json*-Datei:</span><span class="sxs-lookup"><span data-stu-id="cdf96-137">Execute [`dotnet restore`](../tools/dotnet-restore.md), ([see note](#dotnet-restore-note)) which restores dependencies and creates an *obj* folder inside *library* with three files in it, including a *project.assets.json* file:</span></span>

```console
dotnet restore
```

<span data-ttu-id="cdf96-138">Benennen Sie im Ordner *library* die Datei *Class1.cs* in *Thing.cs* um.</span><span class="sxs-lookup"><span data-stu-id="cdf96-138">In the *library* folder, rename the file *Class1.cs* to *Thing.cs*.</span></span> <span data-ttu-id="cdf96-139">Ersetzen Sie den Code durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cdf96-139">Replace the code with the following:</span></span>

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

<span data-ttu-id="cdf96-140">Die `Thing`-Klasse enthält eine öffentliche Methode, `Get`, die die Summe zweier Zahlen durch Konvertierung der Summe in eine Zeichenfolge zurückgibt, die anschließend in eine ganze Zahl serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="cdf96-140">The `Thing` class contains one public method, `Get`, which returns the sum of two numbers but does so by converting the sum into a string and then deserializing it into an integer.</span></span> <span data-ttu-id="cdf96-141">Hierbei werden verschiedene moderne C#-Features wie etwa [`using static`-Anweisungen](../../csharp/language-reference/keywords/using-static.md), [Ausdruckskörpermember](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members) und [Zeichenfolgeninterpolation](../../csharp/language-reference/tokens/interpolated.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="cdf96-141">This makes use of a number of modern C# features, such as [`using static` directives](../../csharp/language-reference/keywords/using-static.md), [expression-bodied members](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), and [string interpolation](../../csharp/language-reference/tokens/interpolated.md).</span></span>

<span data-ttu-id="cdf96-142">Erstellen Sie die Bibliothek mithilfe des [`dotnet build`](../tools/dotnet-build.md)-Befehls.</span><span class="sxs-lookup"><span data-stu-id="cdf96-142">Build the library with the [`dotnet build`](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="cdf96-143">Dadurch wird eine integrierte *library.dll*-Datei unter *golden/library/bin/Debug/netstandard1.4* erstellt.</span><span class="sxs-lookup"><span data-stu-id="cdf96-143">This produces a *library.dll* file under *golden/library/bin/Debug/netstandard1.4*:</span></span>

```console
dotnet build
```

## <a name="create-the-test-project"></a><span data-ttu-id="cdf96-144">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="cdf96-144">Create the test project</span></span>

<span data-ttu-id="cdf96-145">Erstellen Sie eine Testprojekt für die Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="cdf96-145">Build a test project for the library.</span></span> <span data-ttu-id="cdf96-146">Erstellen Sie aus dem *golden*-Ordner ein neues Testprojekt:</span><span class="sxs-lookup"><span data-stu-id="cdf96-146">From the *golden* folder, create a new test project:</span></span>

```console
dotnet new xunit -o test-library
```

<span data-ttu-id="cdf96-147">Fügen sie das Testprojekt zur Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="cdf96-147">Add the test project to the solution:</span></span>

```console
dotnet sln add test-library/test-library.csproj
```

<span data-ttu-id="cdf96-148">Fügen Sie der von Ihnen im letzten Abschnitt erstellten Bibliothek einen Projektverweis hinzu, damit der Compiler das Bibliotheksprojekt finden und verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="cdf96-148">Add a project reference the library you created in the previous section so that the compiler can find and use the library project.</span></span> <span data-ttu-id="cdf96-149">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="cdf96-149">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add test-library/test-library.csproj reference library/library.csproj
```

<span data-ttu-id="cdf96-150">Alternativ können Sie die *test-library.csproj*-Datei manuell bearbeiten, und den folgenden Knoten hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="cdf96-150">Alternatively, manually edit the *test-library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

<span data-ttu-id="cdf96-151">Nachdem Sie die Abhängigkeiten ordnungsgemäß konfiguriert haben, erstellen Sie nun die Tests für Ihre Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="cdf96-151">Now that the dependencies have been properly configured, create the tests for your library.</span></span> <span data-ttu-id="cdf96-152">Öffnen Sie *UnitTest1.cs*, und ersetzen Sie den Inhalt durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="cdf96-152">Open *UnitTest1.cs* and replace its contents with the following code:</span></span>

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

<span data-ttu-id="cdf96-153">Beachten Sie, dass der Wert 42 nicht 19+23 (oder 42) entspricht, wenn Sie zum ersten Mal den Komponententest (`Assert.NotEqual`) erstellen, was fehlschlagen wird.</span><span class="sxs-lookup"><span data-stu-id="cdf96-153">Note that you assert the value 42 is not equal to 19+23 (or 42) when you first create the unit test (`Assert.NotEqual`), which will fail.</span></span> <span data-ttu-id="cdf96-154">Ein wichtiger Schritt beim Erstellen von Komponententests ist die Erstellung des Tests, der zuerst einmal fehlschlägt, um seine Logik zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="cdf96-154">An important step in building unit tests is to create the test to fail once first to confirm its logic.</span></span>

<span data-ttu-id="cdf96-155">Führen Sie im *golden*-Ordner die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="cdf96-155">From the *golden* folder, execute the following commands:</span></span>

```console
dotnet restore 
dotnet test test-library/test-library.csproj
```

<span data-ttu-id="cdf96-156">Diese Befehle finden rekursiv alle Projekte, deren Abhängigkeiten wiederhergestellt werden sollen, erstellen sie und aktivieren den xUnit-Textlauf, um die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cdf96-156">These commands will recursively find all projects to restore dependencies, build them, and activate the xUnit test runner to run the tests.</span></span> <span data-ttu-id="cdf96-157">Der einzelne Text schlägt wie erwartet fehl.</span><span class="sxs-lookup"><span data-stu-id="cdf96-157">The single test fails, as you expect.</span></span>

<span data-ttu-id="cdf96-158">Bearbeiten Sie die Datei *UnitTest1.cs*, und ändern Sie die Assertion von `Assert.NotEqual` zu `Assert.Equal`.</span><span class="sxs-lookup"><span data-stu-id="cdf96-158">Edit the *UnitTest1.cs* file and change the assertion from `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="cdf96-159">Führen Sie den folgenden Befehl aus dem *golden*-Ordner aus, um den Test erneut auszuführen, der diesmal erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cdf96-159">Execute the following command from the *golden* folder to re-run the test, which passes this time:</span></span>

```console
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a><span data-ttu-id="cdf96-160">Schreiben der Konsolen-App</span><span class="sxs-lookup"><span data-stu-id="cdf96-160">Create the console app</span></span>

<span data-ttu-id="cdf96-161">Die Konsolen-App, die Sie mithilfe der folgenden Schritte erstellen, ist vom Bibliotheksprojekt abhängig, das Sie zuvor erstellt haben, und ruft seine Bibliotheksmethode auf, wenn es ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cdf96-161">The console app you create over the following steps takes a dependency on the library project you created earlier and calls its library method when it runs.</span></span> <span data-ttu-id="cdf96-162">Mithilfe dieses Entwicklungsmusters sehen Sie, wie Sie wiederverwendbare Bibliotheken für mehrere Projekte erstellen können.</span><span class="sxs-lookup"><span data-stu-id="cdf96-162">Using this pattern of development, you see how to create reusable libraries for multiple projects.</span></span>

<span data-ttu-id="cdf96-163">Erstellen Sie eine neue Konsolenanwendung aus dem *golden*-Ordner:</span><span class="sxs-lookup"><span data-stu-id="cdf96-163">Create a new console application from the *golden* folder:</span></span>

```console
dotnet new console -o app
```

<span data-ttu-id="cdf96-164">Fügen Sie das Konsolen-App-Projekt zur Projektmappe hinzu:</span><span class="sxs-lookup"><span data-stu-id="cdf96-164">Add the console app project to the solution:</span></span>

```console
dotnet sln add app/app.csproj
```

<span data-ttu-id="cdf96-165">Erstellen Sie die Abhängigkeit von der Bibliothek, indem Sie den `dotnet add reference`-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="cdf96-165">Create the dependency on the library by running the `dotnet add reference` command:</span></span>

```console
dotnet add app/app.csproj reference library/library.csproj
```

<span data-ttu-id="cdf96-166">Führen Sie `dotnet restore` aus ([siehe Hinweis](#dotnet-restore-note)), um die Abhängigkeiten der drei Projekte in der Projektmappe wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="cdf96-166">Run `dotnet restore` ([see note](#dotnet-restore-note)) to restore the dependencies of the three projects in the solution.</span></span> <span data-ttu-id="cdf96-167">Öffnen Sie *Program.cs*, und ersetzen Sie den Inhalt der `Main`-Methode durch diese Zeile:</span><span class="sxs-lookup"><span data-stu-id="cdf96-167">Open *Program.cs* and replace the contents of the `Main` method with the following line:</span></span>

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

<span data-ttu-id="cdf96-168">Fügen Sie ganz oben in der *Program.cs*-Datei zwei `using`-Direktiven hinzu:</span><span class="sxs-lookup"><span data-stu-id="cdf96-168">Add two `using` directives to the top of the *Program.cs* file:</span></span>

```csharp
using static System.Console;
using Library;
```

<span data-ttu-id="cdf96-169">Führen Sie den folgenden `dotnet run`-Befehl aus, um die ausführbare Datei auszuführen, wobei die `-p`-Option für `dotnet run` das Projekt für die Hauptanwendung angibt.</span><span class="sxs-lookup"><span data-stu-id="cdf96-169">Execute the following `dotnet run` command to run the executable, where the `-p` option to `dotnet run` specifies the project for the main application.</span></span> <span data-ttu-id="cdf96-170">Die App erzeugt die Zeichenfolge „Die Antwort ist 42“.</span><span class="sxs-lookup"><span data-stu-id="cdf96-170">The app produces the string "The answer is 42".</span></span>

```console
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a><span data-ttu-id="cdf96-171">Debuggen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="cdf96-171">Debug the application</span></span>

<span data-ttu-id="cdf96-172">Legen Sie bei der Anweisung `WriteLine` in der `Main`-Methode einen Haltepunkt fest.</span><span class="sxs-lookup"><span data-stu-id="cdf96-172">Set a breakpoint at the `WriteLine` statement in the `Main` method.</span></span> <span data-ttu-id="cdf96-173">Dies erreichen Sie, indem Sie entweder die <kbd>F9</kbd>-Taste drücken, wenn sich der Cursor auf der `WriteLine`-Zeile befindet, oder indem Sie auf den linken Rand der Zeile klicken, wo Sie den Haltepunkt festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="cdf96-173">Do this by either pressing the <kbd>F9</kbd> key when the cursor is over the `WriteLine` line or by clicking the mouse in the left margin on the line where you want to set the breakpoint.</span></span> <span data-ttu-id="cdf96-174">Es erscheint ein Roter Kreis im Rand neben der Codezeile.</span><span class="sxs-lookup"><span data-stu-id="cdf96-174">A red circle will appear in the margin next to the line of code.</span></span> <span data-ttu-id="cdf96-175">Wenn der Haltepunkt erreicht ist, wird die Ausführung des Codes angehalten, *bevor* die Haltepunktzeile ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cdf96-175">When the breakpoint is reached, code execution will stop *before* the breakpoint line is executed.</span></span>

<span data-ttu-id="cdf96-176">Öffnen Sie die Registerkarte „Debugger“, indem Sie das Debugger-Symbol in der Visual Studio Code-Symbolleiste auswählen, **Anzeigen > Debuggen** aus der Menüleiste auswählen oder den Tastaturkurzbefehl <kbd>STRG</kbd>+<kbd>UMSCHALT</kbd>+<kbd>D</kbd> verwenden:</span><span class="sxs-lookup"><span data-stu-id="cdf96-176">Open the debugger tab by selecting the Debug icon in the Visual Studio Code toolbar, selecting **View > Debug** from the menu bar, or using the keyboard shortcut <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>:</span></span>

![Visual Studio Code-Debugger](./media/using-on-macos/visual-studio-code-debugger.png)

<span data-ttu-id="cdf96-178">Klicken Sie auf die Schaltfläche „Wiedergabe“, um die Anwendung unter dem Debugger zu starten.</span><span class="sxs-lookup"><span data-stu-id="cdf96-178">Press the Play button to start the application under the debugger.</span></span> <span data-ttu-id="cdf96-179">Die App startet mit der Ausführung und läuft bis zum Haltepunkt, wo sie anhält.</span><span class="sxs-lookup"><span data-stu-id="cdf96-179">The app begins execution and runs to the breakpoint, where it stops.</span></span> <span data-ttu-id="cdf96-180">Führen Sie die `Get`-Methode schrittweise aus, und stellen Sie sicher, dass Sie die richtigen Argumente eingefügt haben.</span><span class="sxs-lookup"><span data-stu-id="cdf96-180">Step into the `Get` method and make sure that you have passed in the correct arguments.</span></span> <span data-ttu-id="cdf96-181">Bestätigen Sie, dass die Antwort 42 ist.</span><span class="sxs-lookup"><span data-stu-id="cdf96-181">Confirm that the answer is 42.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]