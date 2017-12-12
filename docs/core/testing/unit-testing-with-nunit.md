---
title: "Unittests für C# mit NUnit und .NET Core"
description: "Erfahren Sie mehr über die Konzepte von Unittests in C# und .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und NUnit erstellen."
keywords: NUnit, .NET, .NET Core
author: rprouse
ms.date: 12/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.openlocfilehash: ad410497adc641e89bd9845ed69c063692ad2f73
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a><span data-ttu-id="148d4-104">Unittests für C# mit NUnit und .NET Core</span><span class="sxs-lookup"><span data-stu-id="148d4-104">Unit testing C# with NUnit and .NET Core</span></span>

<span data-ttu-id="148d4-105">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="148d4-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="148d4-106">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="148d4-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/) before you begin.</span></span> <span data-ttu-id="148d4-107">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="148d4-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="148d4-108">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="148d4-108">Creating the source project</span></span>

<span data-ttu-id="148d4-109">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="148d4-109">Open a shell window.</span></span> <span data-ttu-id="148d4-110">Erstellen Sie ein Verzeichnis namens *unit-testing-using-nunit*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="148d4-110">Create a directory called *unit-testing-using-nunit* to hold the solution.</span></span> <span data-ttu-id="148d4-111">Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappendatei für die Klassenbibliothek und das Testprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="148d4-111">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="148d4-112">Erstellen Sie als Nächstes ein *PrimeService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="148d4-112">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="148d4-113">Die folgende Gliederung zeigt die Verzeichnis- und Dateistruktur:</span><span class="sxs-lookup"><span data-stu-id="148d4-113">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

<span data-ttu-id="148d4-114">Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="148d4-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="148d4-115">Benennen Sie *Class1.cs* in *PrimeService.cs* um.</span><span class="sxs-lookup"><span data-stu-id="148d4-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="148d4-116">Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="148d4-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="148d4-117">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="148d4-117">Change the directory back to the *unit-testing-using-nunit* directory.</span></span> <span data-ttu-id="148d4-118">Führen Sie [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="148d4-118">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="148d4-119">Installieren der NUnit-Projektvorlage</span><span class="sxs-lookup"><span data-stu-id="148d4-119">Install the NUnit project template</span></span>

<span data-ttu-id="148d4-120">Vor dem Erstellen eines Testprojekts müssen Sie die NUnit-Projektvorlage installieren.</span><span class="sxs-lookup"><span data-stu-id="148d4-120">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="148d4-121">Dies muss auf jedem Entwicklercomputer, auf dem Sie neue NUnit-Projekte erstellen, nur einmal erfolgen.</span><span class="sxs-lookup"><span data-stu-id="148d4-121">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="148d4-122">Führen Sie [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) aus, um die NUnit-Vorlagen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="148d4-122">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

```
dotnet new -i NUnit3.DotNetNew.Template
```

### <a name="creating-the-test-project"></a><span data-ttu-id="148d4-123">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="148d4-123">Creating the test project</span></span>

<span data-ttu-id="148d4-124">Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="148d4-124">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="148d4-125">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="148d4-125">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="148d4-126">Machen Sie das *PrimeService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new nunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="148d4-126">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new nunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="148d4-127">Der neue dotnet-Befehl erstellt ein Testprojekt, das NUnit als Testbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="148d4-127">The dotnet new command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="148d4-128">Die generierte Vorlage konfiguriert das Testprogramm in der Datei *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="148d4-128">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="148d4-129">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="148d4-129">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="148d4-130">Mithilfe von `dotnet new` im vorherigen Schritt wurden das Microsoft-Test-SDK, das NUnit-Testframework und der NUnit-Testadapter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="148d4-130">`dotnet new` in the previous step added the Microsoft test SDK, the NUnit test framework, and the NUnit test adapter.</span></span> <span data-ttu-id="148d4-131">Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="148d4-131">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="148d4-132">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="148d4-132">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="148d4-133">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="148d4-133">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="148d4-134">Die folgende Gliederung zeigt das endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="148d4-134">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="148d4-135">Führen Sie [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-using-dotnet-test* aus.</span><span class="sxs-lookup"><span data-stu-id="148d4-135">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="148d4-136">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="148d4-136">Creating the first test</span></span>

<span data-ttu-id="148d4-137">Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="148d4-137">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="148d4-138">Entfernen Sie *UnitTest1.cs* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue C#-Datei namens *PrimeService_IsPrimeShould.cs* mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="148d4-138">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Test]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="148d4-139">Das `[TestFixture]`-Attribut gibt eine Klasse an, die Unittests enthält.</span><span class="sxs-lookup"><span data-stu-id="148d4-139">The `[TestFixture]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="148d4-140">Das `[Test]`-Attribut gibt an, dass es sich bei einer Methode um eine Testmethode handelt.</span><span class="sxs-lookup"><span data-stu-id="148d4-140">The `[Test]` attribute indicates a method is a test method.</span></span>

<span data-ttu-id="148d4-141">Speichern Sie diese Datei und führen Sie [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="148d4-141">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="148d4-142">Der NUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests.</span><span class="sxs-lookup"><span data-stu-id="148d4-142">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="148d4-143">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="148d4-143">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="148d4-144">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="148d4-144">Your test fails.</span></span> <span data-ttu-id="148d4-145">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="148d4-145">You haven't created the implementation yet.</span></span> <span data-ttu-id="148d4-146">Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="148d4-146">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="148d4-147">Führen Sie im Verzeichnis *unit-testing-using-nunit* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="148d4-147">In the *unit-testing-using-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="148d4-148">Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="148d4-148">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="148d4-149">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="148d4-149">After building both projects, it runs this single test.</span></span> <span data-ttu-id="148d4-150">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="148d4-150">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="148d4-151">Hinzufügen weiterer Features</span><span class="sxs-lookup"><span data-stu-id="148d4-151">Adding more features</span></span>

<span data-ttu-id="148d4-152">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="148d4-152">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="148d4-153">Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="148d4-153">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="148d4-154">Sie könnten diese neuen Tests mit dem Attribut `[Test]` hinzufügen, aber das wird schnell recht mühsam.</span><span class="sxs-lookup"><span data-stu-id="148d4-154">You could add new tests with the `[Test]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="148d4-155">Es gibt andere NUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.</span><span class="sxs-lookup"><span data-stu-id="148d4-155">There are other NUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="148d4-156">Ein `[TestCase]`-Attribut wird verwendet, um eine Reihe von Tests zu erstellen, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="148d4-156">A `[TestCase]` attribute is used to create a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="148d4-157">Sie können das Attribut `[TestCase]` verwenden, um Werte für diese Eingaben anzugeben.</span><span class="sxs-lookup"><span data-stu-id="148d4-157">You can use the `[TestCase]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="148d4-158">Statt neue Tests zu erstellen, wenden Sie dieses Attribut zum Erstellen eines einzelnen datengesteuerten Tests an.</span><span class="sxs-lookup"><span data-stu-id="148d4-158">Instead of creating new tests, apply this attribute to create a single data driven test.</span></span> <span data-ttu-id="148d4-159">Bei dem datengesteuerten Test handelt es sich um eine Methode, die mehrere Werte unter zwei als niedrigste Primzahl testet:</span><span class="sxs-lookup"><span data-stu-id="148d4-159">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="148d4-160">Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="148d4-160">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="148d4-161">Sie müssen die `if`-Klausel am Anfang der Methode ändern, damit alle Tests erfolgreich sind:</span><span class="sxs-lookup"><span data-stu-id="148d4-161">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="148d4-162">Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="148d4-162">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="148d4-163">Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="148d4-163">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="148d4-164">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="148d4-164">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="148d4-165">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="148d4-165">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="148d4-166">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="148d4-166">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
