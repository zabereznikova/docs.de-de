---
title: "Komponententests für C# mit MSTest und .NET Core"
description: "Erfahren Sie mehr über die Konzepte von Komponententests in C# und .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und MSTest erstellen."
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.openlocfilehash: 2915c2f4b18b9e9d03915c2f17cfc96d4f401c09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="a4060-104">Komponententests für C# mit MSTest und .NET Core</span><span class="sxs-lookup"><span data-stu-id="a4060-104">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="a4060-105">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="a4060-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="a4060-106">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="a4060-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="a4060-107">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="a4060-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="a4060-108">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="a4060-108">Creating the source project</span></span>

<span data-ttu-id="a4060-109">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="a4060-109">Open a shell window.</span></span> <span data-ttu-id="a4060-110">Erstellen Sie ein Verzeichnis namens *unit-testing-using-dotnet-test*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a4060-110">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="a4060-111">Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappendatei für die Klassenbibliothek und das Testprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4060-111">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="a4060-112">Erstellen Sie als Nächstes ein *PrimeService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a4060-112">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="a4060-113">Die folgende Gliederung zeigt die Verzeichnis- und Dateistruktur:</span><span class="sxs-lookup"><span data-stu-id="a4060-113">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="a4060-114">Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4060-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="a4060-115">Benennen Sie *Class1.cs* in *PrimeService.cs* um.</span><span class="sxs-lookup"><span data-stu-id="a4060-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="a4060-116">Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="a4060-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="a4060-117">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="a4060-117">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="a4060-118">Führen Sie [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a4060-118">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span> 

### <a name="creating-the-test-project"></a><span data-ttu-id="a4060-119">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="a4060-119">Creating the test project</span></span>

<span data-ttu-id="a4060-120">Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="a4060-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="a4060-121">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="a4060-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="a4060-122">Machen Sie das *PrimeService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new mstest`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="a4060-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="a4060-123">Der neue dotnet-Befehl erstellt ein Testprojekt, das MSTest als Testbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4060-123">The dotnet new command creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="a4060-124">Die generierte Vorlage konfiguriert das Testprogramm in der Datei *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="a4060-124">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="a4060-125">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a4060-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="a4060-126">`dotnet new` hat im vorherigen Schritt MSTest-SDK, MSTest-Testframework und MSTest-Runner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a4060-126">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="a4060-127">Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="a4060-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="a4060-128">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="a4060-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="a4060-129">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="a4060-129">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="a4060-130">Die folgende Gliederung zeigt das endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="a4060-130">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="a4060-131">Führen Sie [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-using-dotnet-test* aus.</span><span class="sxs-lookup"><span data-stu-id="a4060-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="a4060-132">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="a4060-132">Creating the first test</span></span>

<span data-ttu-id="a4060-133">Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="a4060-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="a4060-134">Entfernen Sie *UnitTest1.cs* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue C#-Datei namens *PrimeService_IsPrimeShould.cs* mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="a4060-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="a4060-135">Das `[TestClass]`-Attribut gibt eine Klasse an, die Unittests enthält.</span><span class="sxs-lookup"><span data-stu-id="a4060-135">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="a4060-136">Das `[TestMethod]`-Attribut gibt an, dass es sich bei einer Methode um eine Testmethode handelt.</span><span class="sxs-lookup"><span data-stu-id="a4060-136">The `[TestMethod]` attribute indicates a method is a test method.</span></span> 

<span data-ttu-id="a4060-137">Speichern Sie diese Datei und führen Sie [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a4060-137">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="a4060-138">Der MSTest Test Runner verfügt über den Programmeinstiegspunkt zum Ausführen der Tests.</span><span class="sxs-lookup"><span data-stu-id="a4060-138">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="a4060-139">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="a4060-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="a4060-140">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="a4060-140">Your test fails.</span></span> <span data-ttu-id="a4060-141">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="a4060-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="a4060-142">Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="a4060-142">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="a4060-143">Führen Sie im Verzeichnis *unit-testing-using-mstest* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="a4060-143">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="a4060-144">Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="a4060-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="a4060-145">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a4060-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="a4060-146">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="a4060-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="a4060-147">Hinzufügen weiterer Features</span><span class="sxs-lookup"><span data-stu-id="a4060-147">Adding more features</span></span>

<span data-ttu-id="a4060-148">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="a4060-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="a4060-149">Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="a4060-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="a4060-150">Sie könnten diese neuen Tests mit dem Attribut `[TestMethod]` hinzufügen, aber das wird schnell recht mühsam.</span><span class="sxs-lookup"><span data-stu-id="a4060-150">You could add new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="a4060-151">Es gibt andere MSTest-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.</span><span class="sxs-lookup"><span data-stu-id="a4060-151">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="a4060-152">Ein `[DataTestMethod]`-Attribut stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="a4060-152">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="a4060-153">Sie können das Attribut `[DataRow]` verwenden, um Werte für diese Eingaben anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a4060-153">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="a4060-154">Statt neue Tests zu erstellen, wenden Sie diese beiden Attribute zum Erstellen eines einzelnen datengesteuerten Tests an.</span><span class="sxs-lookup"><span data-stu-id="a4060-154">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="a4060-155">Bei dem datengesteuerten Test handelt es sich um eine Methode, die mehrere Werte unter zwei als niedrigste Primzahl testet:</span><span class="sxs-lookup"><span data-stu-id="a4060-155">The data driven test is a method that tests several values less than two, which is the lowest prime number: :</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="a4060-156">Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="a4060-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="a4060-157">Sie müssen die `if`-Klausel am Anfang der Methode ändern, damit alle Tests erfolgreich sind:</span><span class="sxs-lookup"><span data-stu-id="a4060-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="a4060-158">Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a4060-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="a4060-159">Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="a4060-159">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="a4060-160">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="a4060-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="a4060-161">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="a4060-161">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="a4060-162">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="a4060-162">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
