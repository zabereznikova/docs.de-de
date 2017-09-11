---
title: Komponententests in .NET Core mit dotnet test und xUnit
description: "In diesem interaktiven Tutorial wird Schritt für Schritt eine Beispielprojektmappe erstellt. Außerdem erfahren Sie mehr über Komponententests in .NET Core."
author: ardalis
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.translationtype: HT
ms.sourcegitcommit: 867f9eb286fa7ff5ef3e9167c1ab944c81161216
ms.openlocfilehash: d989ee731d7ffd0439bac69afe1458e2aa10733a
ms.contentlocale: de-de
ms.lasthandoff: 08/17/2017

---
# <a name="unit-testing-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="3312a-103">Komponententests in .NET Core mit dotnet test und xUnit</span><span class="sxs-lookup"><span data-stu-id="3312a-103">Unit testing in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="3312a-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Komponententests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="3312a-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="3312a-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="3312a-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/) before you begin.</span></span> <span data-ttu-id="3312a-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="3312a-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="3312a-107">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="3312a-107">Creating the source project</span></span>

<span data-ttu-id="3312a-108">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="3312a-108">Open a shell window.</span></span> <span data-ttu-id="3312a-109">Erstellen Sie ein Verzeichnis namens *unit-testing-using-dotnet-test*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3312a-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="3312a-110">Erstellen Sie in diesem neuen Verzeichnis ein *PrimeService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="3312a-110">Inside this new directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="3312a-111">Nachfolgend wird die bisherige Verzeichnisstruktur dargestellt:</span><span class="sxs-lookup"><span data-stu-id="3312a-111">The directory structure thus far is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
```

<span data-ttu-id="3312a-112">Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3312a-112">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="3312a-113">Benennen Sie *Class1.cs* in *PrimeService.cs* um.</span><span class="sxs-lookup"><span data-stu-id="3312a-113">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="3312a-114">Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="3312a-114">To use test-driven development (TDD), you'll create a failing implementation of the `PrimeService` class:</span></span>

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

## <a name="creating-the-test-project"></a><span data-ttu-id="3312a-115">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="3312a-115">Creating the test project</span></span>

<span data-ttu-id="3312a-116">Wechseln Sie wieder in das *unit-testing-using-dotnet-test*-Verzeichnis, und erstellen Sie das *PrimeService.Tests*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="3312a-116">Change the directory back to the *unit-testing-using-dotnet-test* directory and create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="3312a-117">Die Verzeichnisstruktur wird nachfolgend gezeigt:</span><span class="sxs-lookup"><span data-stu-id="3312a-117">The directory structure is shown below:</span></span>

```
/unit-testing-using-dotnet-test
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="3312a-118">Stellen Sie das *PrimeService.Tests*-Verzeichnis als aktuelles Verzeichnis ein, und erstellen Sie ein neues Projekt mit [`dotnet new xunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="3312a-118">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new xunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="3312a-119">Dies erstellt ein Testprojekt, das xUnit als Testbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="3312a-119">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="3312a-120">Die generierte Vorlage konfiguriert das Testprogramm in *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="3312a-120">The generated template configures the test runner in the *PrimeServiceTests.csproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="3312a-121">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3312a-121">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="3312a-122">`dotnet new` hat im vorherigen Schritt xUnit und xUnit Runner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3312a-122">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="3312a-123">Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als eine andere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="3312a-123">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="3312a-124">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="3312a-124">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="3312a-125">Sie können stattdessen auch die *PrimeService.Tests.csproj*-Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="3312a-125">Another option is to edit the *PrimeService.Tests.csproj* file.</span></span> <span data-ttu-id="3312a-126">Fügen Sie direkt unter dem ersten `<ItemGroup>`-Knoten einen weiteren `<ItemGroup>`-Knoten mit einem Verweis auf das Bibliotheksprojekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="3312a-126">Directly under the first `<ItemGroup>` node, add another `<ItemGroup>` node with a reference to the library project:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

<span data-ttu-id="3312a-127">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="3312a-127">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="3312a-128">Das endgültige Layout der Projektmappe wird unten gezeigt:</span><span class="sxs-lookup"><span data-stu-id="3312a-128">The final solution layout is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="3312a-129">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="3312a-129">Creating the first test</span></span>

<span data-ttu-id="3312a-130">Führen Sie vor dem Erstellen der Bibliothek oder der Tests [`dotnet restore`](../tools/dotnet-restore.md) im *PrimeService.Tests*-Verzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="3312a-130">Before building the library or the tests, execute [`dotnet restore`](../tools/dotnet-restore.md) in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="3312a-131">Dieser Befehl stellt alle erforderlichen NuGet-Pakete für jedes Projekt wieder her.</span><span class="sxs-lookup"><span data-stu-id="3312a-131">This command restores all the necessary NuGet packages for each project.</span></span>

<span data-ttu-id="3312a-132">Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="3312a-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="3312a-133">Entfernen Sie *UnitTest1.cs* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue C#-Datei namens *PrimeService_IsPrimeShould.cs* mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="3312a-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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

            Assert.False(result, $"1 should not be prime");
        }
    }
}
```

<span data-ttu-id="3312a-134">Das Attribut `[Fact]` kennzeichnet eine Methode als einzelnen Test.</span><span class="sxs-lookup"><span data-stu-id="3312a-134">The `[Fact]` attribute denotes a method as a single test.</span></span> <span data-ttu-id="3312a-135">Führen Sie [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3312a-135">Execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="3312a-136">Der xUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests.</span><span class="sxs-lookup"><span data-stu-id="3312a-136">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="3312a-137">`dotnet test` startet den Test Runner und stellt ein Befehlszeilenargument für den Test Runner bereit, das die Assembly mit Ihren Tests angibt.</span><span class="sxs-lookup"><span data-stu-id="3312a-137">`dotnet test` starts the test runner and provides a command-line argument to the test runner indicating the assembly that contains your tests.</span></span>

<span data-ttu-id="3312a-138">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="3312a-138">Your test fails.</span></span> <span data-ttu-id="3312a-139">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="3312a-139">You haven't created the implementation yet.</span></span> <span data-ttu-id="3312a-140">Schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse, damit dieser Test erfolgreich verläuft:</span><span class="sxs-lookup"><span data-stu-id="3312a-140">Write the simplest code in the `PrimeService` class to make this test pass:</span></span>

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

<span data-ttu-id="3312a-141">Führen Sie `dotnet test` im *PrimeService.Tests*-Verzeichnis erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3312a-141">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="3312a-142">Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="3312a-142">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="3312a-143">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3312a-143">After building both projects, it runs this single test.</span></span> <span data-ttu-id="3312a-144">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="3312a-144">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="3312a-145">Hinzufügen weiterer Features</span><span class="sxs-lookup"><span data-stu-id="3312a-145">Adding more features</span></span>

<span data-ttu-id="3312a-146">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="3312a-146">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="3312a-147">Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="3312a-147">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="3312a-148">Sie könnten diese neuen Tests mit dem Attribut `[Fact]` hinzufügen, aber das wird schnell recht mühsam.</span><span class="sxs-lookup"><span data-stu-id="3312a-148">You could add those as new tests with the `[Fact]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="3312a-149">Es gibt andere xUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.</span><span class="sxs-lookup"><span data-stu-id="3312a-149">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="3312a-150">Ein `[Theory]`-Attribut stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="3312a-150">A `[Theory]` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="3312a-151">Sie können das Attribut `[InlineData]` verwenden, um Werte für diese Eingaben anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3312a-151">You can use the `[InlineData]` attribute to specify values for those inputs.</span></span> 
 
<span data-ttu-id="3312a-152">Statt neue Tests zu erstellen, nutzen Sie diese beiden Attribute zum Erstellen einer einzigen Theorie. Damit werden mehrere Werte kleiner als 2 (die kleinste Primzahl) getestet:</span><span class="sxs-lookup"><span data-stu-id="3312a-152">Instead of creating new tests, leverage these two attributes to create a single theory that tests several values less than two, which is the lowest prime number:</span></span>

<span data-ttu-id="3312a-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span><span class="sxs-lookup"><span data-stu-id="3312a-153">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span></span>

<span data-ttu-id="3312a-154">Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="3312a-154">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="3312a-155">Sie müssen die `if`-Klausel am Anfang der Methode ändern, damit alle Tests erfolgreich sind:</span><span class="sxs-lookup"><span data-stu-id="3312a-155">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="3312a-156">Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3312a-156">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="3312a-157">Am Ende verfügen Sie über die [endgültige Version der Tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="3312a-157">You'll end up with the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="3312a-158">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="3312a-158">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="3312a-159">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests nahtlos funktioniert, und Sie können sich in Sachen Zeit und Aufwand auf die Lösung der Ziele der Anwendung konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="3312a-159">You've structured the solution so that adding new packages and tests is seamless, and you can concentrate most of your time and effort on solving the goals of the applicaiton.</span></span>

