---
title: Unittests für C# mit NUnit und .NET Core
description: Erfahren Sie mehr über die Konzepte von Unittests in C# und .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und NUnit erstellen.
author: rprouse
ms.date: 12/01/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: db11adf265b2a08456a1bd42bc8a6847ba70a2ce
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a><span data-ttu-id="8b7d9-103">Unittests für C# mit NUnit und .NET Core</span><span class="sxs-lookup"><span data-stu-id="8b7d9-103">Unit testing C# with NUnit and .NET Core</span></span>

<span data-ttu-id="8b7d9-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="8b7d9-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) before you begin.</span></span> <span data-ttu-id="8b7d9-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="8b7d9-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="8b7d9-107">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="8b7d9-107">Creating the source project</span></span>

<span data-ttu-id="8b7d9-108">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-108">Open a shell window.</span></span> <span data-ttu-id="8b7d9-109">Erstellen Sie ein Verzeichnis namens *unit-testing-using-nunit*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-109">Create a directory called *unit-testing-using-nunit* to hold the solution.</span></span> <span data-ttu-id="8b7d9-110">Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappendatei für die Klassenbibliothek und das Testprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="8b7d9-111">Erstellen Sie als Nächstes ein *PrimeService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-111">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="8b7d9-112">Die folgende Gliederung zeigt die Verzeichnis- und Dateistruktur:</span><span class="sxs-lookup"><span data-stu-id="8b7d9-112">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

<span data-ttu-id="8b7d9-113">Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="8b7d9-114">Benennen Sie *Class1.cs* in *PrimeService.cs* um.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="8b7d9-115">Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="8b7d9-115">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="8b7d9-116">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-116">Change the directory back to the *unit-testing-using-nunit* directory.</span></span> <span data-ttu-id="8b7d9-117">Führen Sie [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-117">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="8b7d9-118">Installieren der NUnit-Projektvorlage</span><span class="sxs-lookup"><span data-stu-id="8b7d9-118">Install the NUnit project template</span></span>

<span data-ttu-id="8b7d9-119">Vor dem Erstellen eines Testprojekts müssen Sie die NUnit-Projektvorlage installieren.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-119">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="8b7d9-120">Dies muss auf jedem Entwicklercomputer, auf dem Sie neue NUnit-Projekte erstellen, nur einmal erfolgen.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-120">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="8b7d9-121">Führen Sie [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) aus, um die NUnit-Vorlagen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-121">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

```
dotnet new -i NUnit3.DotNetNew.Template
```

### <a name="creating-the-test-project"></a><span data-ttu-id="8b7d9-122">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="8b7d9-122">Creating the test project</span></span>

<span data-ttu-id="8b7d9-123">Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-123">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="8b7d9-124">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="8b7d9-124">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="8b7d9-125">Machen Sie das *PrimeService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new nunit`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="8b7d9-125">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new nunit`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="8b7d9-126">Der neue dotnet-Befehl erstellt ein Testprojekt, das NUnit als Testbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-126">The dotnet new command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="8b7d9-127">Die generierte Vorlage konfiguriert das Testprogramm in der Datei *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="8b7d9-127">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="8b7d9-128">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-128">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="8b7d9-129">Mithilfe von `dotnet new` im vorherigen Schritt wurden das Microsoft-Test-SDK, das NUnit-Testframework und der NUnit-Testadapter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-129">`dotnet new` in the previous step added the Microsoft test SDK, the NUnit test framework, and the NUnit test adapter.</span></span> <span data-ttu-id="8b7d9-130">Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-130">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="8b7d9-131">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="8b7d9-131">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="8b7d9-132">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-132">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="8b7d9-133">Die folgende Gliederung zeigt das endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="8b7d9-133">The following outline shows the final solution layout:</span></span>

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

<span data-ttu-id="8b7d9-134">Führen Sie [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-using-dotnet-test* aus.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-134">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="8b7d9-135">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="8b7d9-135">Creating the first test</span></span>

<span data-ttu-id="8b7d9-136">Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-136">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="8b7d9-137">Entfernen Sie *UnitTest1.cs* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue C#-Datei namens *PrimeService_IsPrimeShould.cs* mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="8b7d9-137">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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

<span data-ttu-id="8b7d9-138">Das `[TestFixture]`-Attribut gibt eine Klasse an, die Unittests enthält.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-138">The `[TestFixture]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="8b7d9-139">Das `[Test]`-Attribut gibt an, dass es sich bei einer Methode um eine Testmethode handelt.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-139">The `[Test]` attribute indicates a method is a test method.</span></span>

<span data-ttu-id="8b7d9-140">Speichern Sie diese Datei und führen Sie [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-140">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="8b7d9-141">Der NUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-141">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="8b7d9-142">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-142">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="8b7d9-143">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-143">Your test fails.</span></span> <span data-ttu-id="8b7d9-144">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-144">You haven't created the implementation yet.</span></span> <span data-ttu-id="8b7d9-145">Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="8b7d9-145">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="8b7d9-146">Führen Sie im Verzeichnis *unit-testing-using-nunit* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-146">In the *unit-testing-using-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="8b7d9-147">Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-147">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="8b7d9-148">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-148">After building both projects, it runs this single test.</span></span> <span data-ttu-id="8b7d9-149">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-149">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="8b7d9-150">Hinzufügen weiterer Features</span><span class="sxs-lookup"><span data-stu-id="8b7d9-150">Adding more features</span></span>

<span data-ttu-id="8b7d9-151">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-151">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="8b7d9-152">Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-152">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="8b7d9-153">Sie könnten diese neuen Tests mit dem Attribut `[Test]` hinzufügen, aber das wird schnell recht mühsam.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-153">You could add new tests with the `[Test]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="8b7d9-154">Es gibt andere NUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-154">There are other NUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="8b7d9-155">Ein `[TestCase]`-Attribut wird verwendet, um eine Reihe von Tests zu erstellen, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-155">A `[TestCase]` attribute is used to create a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="8b7d9-156">Sie können das Attribut `[TestCase]` verwenden, um Werte für diese Eingaben anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-156">You can use the `[TestCase]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="8b7d9-157">Statt neue Tests zu erstellen, wenden Sie dieses Attribut zum Erstellen eines einzelnen datengesteuerten Tests an.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-157">Instead of creating new tests, apply this attribute to create a single data driven test.</span></span> <span data-ttu-id="8b7d9-158">Bei dem datengesteuerten Test handelt es sich um eine Methode, die mehrere Werte unter zwei als niedrigste Primzahl testet:</span><span class="sxs-lookup"><span data-stu-id="8b7d9-158">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="8b7d9-159">Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-159">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="8b7d9-160">Sie müssen die `if`-Klausel am Anfang der Methode ändern, damit alle Tests erfolgreich sind:</span><span class="sxs-lookup"><span data-stu-id="8b7d9-160">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="8b7d9-161">Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-161">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="8b7d9-162">Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="8b7d9-162">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="8b7d9-163">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-163">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="8b7d9-164">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-164">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="8b7d9-165">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="8b7d9-165">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
