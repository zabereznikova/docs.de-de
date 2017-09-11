---
title: Unittests mit MSTest und .NET Core
description: Verwenden von MSTest mit .NET Core
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d1cb9f6667e1317e74d246988ef1257d0712c431
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="unit-testing-with-mstest-and-net-core"></a><span data-ttu-id="e04e1-104">Unittests mit MSTest und .NET Core</span><span class="sxs-lookup"><span data-stu-id="e04e1-104">Unit testing with MSTest and .NET Core</span></span>

<span data-ttu-id="e04e1-105">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="e04e1-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="e04e1-106">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="e04e1-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="e04e1-107">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="e04e1-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="e04e1-108">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="e04e1-108">Creating the source project</span></span>

<span data-ttu-id="e04e1-109">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="e04e1-109">Open a shell window.</span></span> <span data-ttu-id="e04e1-110">Erstellen Sie ein Verzeichnis namens *unit-testing-using-dotnet-test*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e04e1-110">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="e04e1-111">Erstellen Sie in diesem neuen Verzeichnis ein *PrimeService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e04e1-111">Inside this new directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="e04e1-112">Nachfolgend wird die bisherige Verzeichnisstruktur dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e04e1-112">The directory structure thus far is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
```

<span data-ttu-id="e04e1-113">Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e04e1-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="e04e1-114">Benennen Sie *Class1.cs* in *PrimeService.cs* um.</span><span class="sxs-lookup"><span data-stu-id="e04e1-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="e04e1-115">Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="e04e1-115">To use test-driven development (TDD), you'll create a failing implementation of the `PrimeService` class:</span></span>

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

### <a name="creating-the-test-project"></a><span data-ttu-id="e04e1-116">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="e04e1-116">Creating the test project</span></span>

<span data-ttu-id="e04e1-117">Ändern Sie das Verzeichnis wieder in das *unit-testing-using-mstest*-Verzeichnis, und erstellen Sie das *PrimeService.Tests*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e04e1-117">Change the directory back to the *unit-testing-using-mstest* directory and create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="e04e1-118">Die Verzeichnisstruktur wird nachfolgend gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e04e1-118">The directory structure is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="e04e1-119">Machen Sie das *PrimeService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new mstest`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="e04e1-119">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="e04e1-120">Dies erstellt ein Testprojekt, das MStest als Testbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="e04e1-120">This creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="e04e1-121">Die generierte Vorlage konfiguriert das Testprogramm in der Datei *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="e04e1-121">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.11" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11" />
</ItemGroup>
```

<span data-ttu-id="e04e1-122">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e04e1-122">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="e04e1-123">`dotnet new` hat im vorherigen Schritt MSTest-SDK, MSTest-Testframework und MSTest-Runner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e04e1-123">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="e04e1-124">Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="e04e1-124">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="e04e1-125">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="e04e1-125">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="e04e1-126">Sie können stattdessen auch die *PrimeService.Tests.csproj*-Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e04e1-126">Another option is to edit the *PrimeService.Tests.csproj* file.</span></span> <span data-ttu-id="e04e1-127">Fügen Sie direkt unter dem ersten `<ItemGroup>`-Knoten einen weiteren `<ItemGroup>`-Knoten mit einem Verweis auf das Bibliotheksprojekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="e04e1-127">Directly under the first `<ItemGroup>` node, add another `<ItemGroup>` node with a reference to the library project:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

<span data-ttu-id="e04e1-128">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="e04e1-128">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="e04e1-129">Das endgültige Layout der Projektmappe wird unten gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e04e1-129">The final solution layout is shown below:</span></span>

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="e04e1-130">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="e04e1-130">Creating the first test</span></span>

<span data-ttu-id="e04e1-131">Führen Sie vor dem Erstellen der Bibliothek oder der Tests [`dotnet restore`](../tools/dotnet-restore.md) im *PrimeService.Tests*-Verzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="e04e1-131">Before building the library or the tests, execute [`dotnet restore`](../tools/dotnet-restore.md) in the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="e04e1-132">Dieser Befehl stellt alle erforderlichen NuGet-Pakete für jedes Projekt wieder her.</span><span class="sxs-lookup"><span data-stu-id="e04e1-132">This command restores all the necessary NuGet packages for each project.</span></span>

<span data-ttu-id="e04e1-133">Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="e04e1-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="e04e1-134">Entfernen Sie *UnitTest1.cs* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue C#-Datei namens *PrimeService_IsPrimeShould.cs* mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="e04e1-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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

            Assert.IsFalse(result, $"1 should not be prime");
        }
    }
}
```

<span data-ttu-id="e04e1-135">Das `[TestClass]`-Attribut gibt eine Klasse an, die Unittests enthält.</span><span class="sxs-lookup"><span data-stu-id="e04e1-135">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="e04e1-136">Das Attribut `[TestMethod]` kennzeichnet eine Methode als einzelnen Test.</span><span class="sxs-lookup"><span data-stu-id="e04e1-136">The `[TestMethod]` attribute denotes a method as a single test.</span></span> 

<span data-ttu-id="e04e1-137">Speichern Sie diese Datei und führen Sie [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e04e1-137">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="e04e1-138">Der MSTest Test Runner verfügt über den Programmeinstiegspunkt zum Ausführen der Tests.</span><span class="sxs-lookup"><span data-stu-id="e04e1-138">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="e04e1-139">`dotnet test` startet den Test Runner und stellt ein Befehlszeilenargument für den Test Runner bereit, das die Assembly mit Ihren Tests angibt.</span><span class="sxs-lookup"><span data-stu-id="e04e1-139">`dotnet test` starts the test runner and provides a command-line argument to the test runner indicating the assembly that contains your tests.</span></span>

<span data-ttu-id="e04e1-140">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="e04e1-140">Your test fails.</span></span> <span data-ttu-id="e04e1-141">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="e04e1-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="e04e1-142">Schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse, damit dieser Test erfolgreich verläuft:</span><span class="sxs-lookup"><span data-stu-id="e04e1-142">Write the simplest code in the `PrimeService` class to make this test pass:</span></span>

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

<span data-ttu-id="e04e1-143">Führen Sie `dotnet test` im *PrimeService.Tests*-Verzeichnis erneut aus.</span><span class="sxs-lookup"><span data-stu-id="e04e1-143">In the *PrimeService.Tests* directory, run `dotnet test` again.</span></span> <span data-ttu-id="e04e1-144">Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="e04e1-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="e04e1-145">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e04e1-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="e04e1-146">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e04e1-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="e04e1-147">Hinzufügen weiterer Features</span><span class="sxs-lookup"><span data-stu-id="e04e1-147">Adding more features</span></span>

<span data-ttu-id="e04e1-148">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="e04e1-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="e04e1-149">Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="e04e1-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="e04e1-150">Sie könnten diese neuen Tests mit dem Attribut `[TestMethod]` hinzufügen, aber das wird schnell recht mühsam.</span><span class="sxs-lookup"><span data-stu-id="e04e1-150">You could add those as new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="e04e1-151">Es gibt andere MSTest-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.</span><span class="sxs-lookup"><span data-stu-id="e04e1-151">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="e04e1-152">Ein `[DataTestMethod]`-Attribut stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="e04e1-152">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="e04e1-153">Sie können das Attribut `[DataRow]` verwenden, um Werte für diese Eingaben anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e04e1-153">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span> 
 
<span data-ttu-id="e04e1-154">Statt neue Tests zu erstellen, nutzen Sie diese beiden Attribute zum Erstellen einer einzigen Datentestmethode, die mehrere Werte kleiner als zwei (die kleinste Primzahl) testet:</span><span class="sxs-lookup"><span data-stu-id="e04e1-154">Instead of creating new tests, leverage these two attributes to create a single data test method that tests several values less than two, which is the lowest prime number:</span></span>

<span data-ttu-id="e04e1-155">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span><span class="sxs-lookup"><span data-stu-id="e04e1-155">[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]</span></span>

<span data-ttu-id="e04e1-156">Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="e04e1-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="e04e1-157">Sie müssen die `if`-Klausel am Anfang der Methode ändern, damit alle Tests erfolgreich sind:</span><span class="sxs-lookup"><span data-stu-id="e04e1-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="e04e1-158">Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e04e1-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="e04e1-159">Am Ende verfügen Sie über die [endgültige Version der Tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="e04e1-159">You'll end up with the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="e04e1-160">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="e04e1-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="e04e1-161">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests nahtlos funktioniert, und Sie können sich in Sachen Zeit und Aufwand auf die Lösung der Ziele der Anwendung konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="e04e1-161">You've structured the solution so that adding new packages and tests is seamless, and you can concentrate most of your time and effort on solving the goals of the applicaiton.</span></span>

