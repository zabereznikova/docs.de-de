---
title: Komponententests für den C#-Code in .NET Core mit „dotnet test“ und xUnit
description: Erfahren Sie mehr über die Konzepte von Komponententests in C# und .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und xUnit erstellen.
author: ardalis
ms.author: wiwagn
ms.date: 11/29/2017
ms.topic: article
ms.prod: .net-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 382b5b5e8bafccbcaaa5ef247d894506c1b0b172
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2018
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="98ace-103">Komponententests für C# in .NET Core mit „dotnet test“ und xUnit</span><span class="sxs-lookup"><span data-stu-id="98ace-103">Unit testing C# in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="98ace-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="98ace-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="98ace-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="98ace-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="98ace-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="98ace-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="98ace-107">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="98ace-107">Creating the source project</span></span>

<span data-ttu-id="98ace-108">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="98ace-108">Open a shell window.</span></span> <span data-ttu-id="98ace-109">Erstellen Sie ein Verzeichnis namens *unit-testing-using-dotnet-test*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="98ace-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="98ace-110">Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="98ace-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="98ace-111">Eine Projektmappe vereinfacht die Verwaltung des Klassenbibliotheks- und des Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="98ace-111">Having a solution makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="98ace-112">Erstellen Sie im Projektmappenverzeichnis ein *PrimeService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="98ace-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="98ace-113">Die bisherige Verzeichnis- und Dateistruktur sollte folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="98ace-113">The directory and file structure thus far should be as follows:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

<span data-ttu-id="98ace-114">Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="98ace-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="98ace-115">Benennen Sie *Class1.cs* in *PrimeService.cs* um.</span><span class="sxs-lookup"><span data-stu-id="98ace-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="98ace-116">Erstellen Sie zunächst eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="98ace-116">To use test-driven development (TDD), you first create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first");
        }
    }
}
```

<span data-ttu-id="98ace-117">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-using-dotnet-test*.</span><span class="sxs-lookup"><span data-stu-id="98ace-117">Change the directory back to the *unit-testing-using-dotnet-test* directory.</span></span>

<span data-ttu-id="98ace-118">Führen Sie [dotnet sln](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="98ace-118">Run the [dotnet sln](../tools/dotnet-sln.md) command to add the class library project to the solution:</span></span>

```
dotnet sln add .\PrimeService\PrimeService.csproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="98ace-119">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="98ace-119">Creating the test project</span></span>

<span data-ttu-id="98ace-120">Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="98ace-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="98ace-121">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="98ace-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="98ace-122">Machen Sie das *PrimeService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new xunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="98ace-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="98ace-123">Dieser Befehl erstellt ein Testprojekt, das xUnit als Testbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="98ace-123">This command creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="98ace-124">Die generierte Vorlage konfiguriert den Test Runner in der Datei *PrimeServiceTests.csproj* ähnlich wie im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="98ace-124">The generated template configures the test runner in the *PrimeServiceTests.csproj* file similar to the following code:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="98ace-125">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98ace-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="98ace-126">`dotnet new` hat im vorherigen Schritt xUnit und xUnit Runner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98ace-126">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="98ace-127">Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als eine andere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="98ace-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="98ace-128">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="98ace-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="98ace-129">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="98ace-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="98ace-130">Im Folgenden wird das endgültige Projektmappenlayout gezeigt:</span><span class="sxs-lookup"><span data-stu-id="98ace-130">The following shows the final solution layout:</span></span>

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="98ace-131">Um das Testprojekt zur Projektmappe hinzuzufügen, führen Sie den Befehl [dotnet sln](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-using-dotnet-test* aus:</span><span class="sxs-lookup"><span data-stu-id="98ace-131">To add the test project to the solution, run the [dotnet sln](../tools/dotnet-sln.md) command in the *unit-testing-using-dotnet-test* directory:</span></span>

```
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="98ace-132">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="98ace-132">Creating the first test</span></span>

<span data-ttu-id="98ace-133">Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="98ace-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="98ace-134">Entfernen Sie *UnitTest1.cs* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue C#-Datei namens *PrimeService_IsPrimeShould.cs*.</span><span class="sxs-lookup"><span data-stu-id="98ace-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs*.</span></span> <span data-ttu-id="98ace-135">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="98ace-135">Add the following code:</span></span>

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="98ace-136">Das `[Fact]`-Attribut gibt eine Testmethode an, die von Test Runner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98ace-136">The `[Fact]` attribute indicates a test method that is run by the test runner.</span></span> <span data-ttu-id="98ace-137">Führen Sie im Verzeichnis *PrimeService.Tests* [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="98ace-137">From the *PrimeService.Tests* folder, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="98ace-138">Der xUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests.</span><span class="sxs-lookup"><span data-stu-id="98ace-138">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="98ace-139">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="98ace-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="98ace-140">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="98ace-140">Your test fails.</span></span> <span data-ttu-id="98ace-141">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="98ace-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="98ace-142">Damit dieser Test erfolgreich verläuft, schreiben Sie in der `PrimeService`-Klasse einen ganz einfachen Code.</span><span class="sxs-lookup"><span data-stu-id="98ace-142">Make this test by writing the simplest code in the `PrimeService` class that works.</span></span> <span data-ttu-id="98ace-143">Ersetzen Sie die vorhandene Implementierung der Methode `IsPrime` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="98ace-143">Replace the existing `IsPrime` method implementation with the following code:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first");
}
```

<span data-ttu-id="98ace-144">Führen Sie `dotnet test` im *PrimeService.Tests*-Verzeichnis erneut aus.</span><span class="sxs-lookup"><span data-stu-id="98ace-144">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="98ace-145">Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="98ace-145">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="98ace-146">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98ace-146">After building both projects, it runs this single test.</span></span> <span data-ttu-id="98ace-147">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="98ace-147">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="98ace-148">Hinzufügen weiterer Features</span><span class="sxs-lookup"><span data-stu-id="98ace-148">Adding more features</span></span>

<span data-ttu-id="98ace-149">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="98ace-149">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="98ace-150">Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="98ace-150">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="98ace-151">Sie könnten diese neuen Fälle als neue Tests mit dem Attribut `[Fact]` hinzufügen, aber das wird schnell recht mühsam.</span><span class="sxs-lookup"><span data-stu-id="98ace-151">You could add those cases as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="98ace-152">Es gibt andere xUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können:</span><span class="sxs-lookup"><span data-stu-id="98ace-152">There are other xUnit attributes that enable you to write a suite of similar tests:</span></span>

- <span data-ttu-id="98ace-153">`[Theory]` repräsentiert eine Reihe von Tests, die zwar denselben Code ausführen, aber unterschiedliche Eingabeargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="98ace-153">`[Theory]` represents a suite of tests that execute the same code but have different input arguments.</span></span>

- <span data-ttu-id="98ace-154">Das `[InlineData]`-Attribut gibt Werte für diese Eingaben an.</span><span class="sxs-lookup"><span data-stu-id="98ace-154">`[InlineData]` attribute specifies values for those inputs.</span></span>

<span data-ttu-id="98ace-155">Statt neue Tests zu erstellen, wenden Sie die zwei Attribute `[Theory]` und `[InlineData]` zum Erstellen einer einzelnen Theorie in der Datei *PrimeService_IsPrimeShould.cs* an.</span><span class="sxs-lookup"><span data-stu-id="98ace-155">Instead of creating new tests, apply these two attributes, `[Theory]` and `[InlineData]`, to create a single theory in the *PrimeService_IsPrimeShould.cs* file.</span></span> <span data-ttu-id="98ace-156">Bei der Theorie handelt es sich um eine Methode, die mehrere Werte unter zwei als niedrigste Primzahl testet:</span><span class="sxs-lookup"><span data-stu-id="98ace-156">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="98ace-157">Wenn Sie `dotnet test` erneut ausführen, sollten bei zwei dieser Tests Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="98ace-157">Run `dotnet test` again, and two of these tests should fail.</span></span> <span data-ttu-id="98ace-158">Damit alle Tests erfolgreich sind, müssen Sie in der Datei *PrimeService.cs* am Anfang der Methode `IsPrime` die `if`-Klausel ändern:</span><span class="sxs-lookup"><span data-stu-id="98ace-158">To make all of the tests pass, change the `if` clause at the beginning of the `IsPrime` method in the *PrimeService.cs* file:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="98ace-159">Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="98ace-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="98ace-160">Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="98ace-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="98ace-161">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="98ace-161">Additional resources</span></span>

[<span data-ttu-id="98ace-162">Testen von Controllerlogik in ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="98ace-162">Testing controller logic in ASP.NET Core</span></span>](/aspnet/core/mvc/controllers/testing)
