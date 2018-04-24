---
title: Unittests für Visual Basic in .NET Core mithilfe von „dotnet test“ und NUnit
description: Erfahren Sie mehr über die Konzepte von Komponententests in .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Visual Basic-Beispielprojektmappe mithilfe von NUnit erstellen.
author: rprouse
ms.date: 12/01/2017
ms.topic: article
dev_langs:
- vb
ms.prod: .net-core
ms.openlocfilehash: 9ddb6dc439e11b394bc71ac30b72310f122da498
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2018
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a><span data-ttu-id="92076-103">Unittests für Visual Basic .NET Core-Bibliotheken mithilfe von „dotnet test“ und NUnit</span><span class="sxs-lookup"><span data-stu-id="92076-103">Unit testing Visual Basic .NET Core libraries using dotnet test and NUnit</span></span>

<span data-ttu-id="92076-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="92076-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="92076-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="92076-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/) before you begin.</span></span> <span data-ttu-id="92076-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="92076-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="92076-107">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="92076-107">Creating the source project</span></span>

<span data-ttu-id="92076-108">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="92076-108">Open a shell window.</span></span> <span data-ttu-id="92076-109">Erstellen Sie ein Verzeichnis namens *unit-testing-vb-nunit*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="92076-109">Create a directory called *unit-testing-vb-nunit* to hold the solution.</span></span> <span data-ttu-id="92076-110">Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92076-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="92076-111">Diese Übung vereinfacht die Verwaltung des Klassenbibliotheks- und Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="92076-111">This practice makes it easier to manage both the class library and the unit test project.</span></span> <span data-ttu-id="92076-112">Erstellen Sie im Projektmappenverzeichnis ein *PrimeService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="92076-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="92076-113">Soweit verfügen Sie über die bisherige Verzeichnis- und Dateistruktur:</span><span class="sxs-lookup"><span data-stu-id="92076-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

<span data-ttu-id="92076-114">Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92076-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="92076-115">Benennen Sie *Class1.VB* in *PrimeService.VB* um.</span><span class="sxs-lookup"><span data-stu-id="92076-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="92076-116">Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="92076-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="92076-117">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-vb-using-stest*.</span><span class="sxs-lookup"><span data-stu-id="92076-117">Change the directory back to the *unit-testing-vb-using-stest* directory.</span></span> <span data-ttu-id="92076-118">Führen Sie [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="92076-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="92076-119">Installieren der NUnit-Projektvorlage</span><span class="sxs-lookup"><span data-stu-id="92076-119">Install the NUnit project template</span></span>

<span data-ttu-id="92076-120">Vor dem Erstellen eines Testprojekts müssen Sie die NUnit-Projektvorlage installieren.</span><span class="sxs-lookup"><span data-stu-id="92076-120">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="92076-121">Dies muss auf jedem Entwicklercomputer, auf dem Sie neue NUnit-Projekte erstellen, nur einmal erfolgen.</span><span class="sxs-lookup"><span data-stu-id="92076-121">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="92076-122">Führen Sie [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) aus, um die NUnit-Vorlagen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="92076-122">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a><span data-ttu-id="92076-123">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="92076-123">Creating the test project</span></span>

<span data-ttu-id="92076-124">Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="92076-124">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="92076-125">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="92076-125">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="92076-126">Machen Sie das *PrimeService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new nunit -lang VB`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="92076-126">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new nunit -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="92076-127">Dieser Befehl erstellt ein Testprojekt, das NUnit als Testbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="92076-127">This command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="92076-128">Die generierte Vorlage konfiguriert Test Runner in *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="92076-128">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="92076-129">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="92076-129">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="92076-130">Mithilfe von `dotnet new` wurden im vorhergehenden Schritt NUnit und der NUnit-Testadapter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="92076-130">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="92076-131">Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="92076-131">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="92076-132">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="92076-132">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="92076-133">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="92076-133">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="92076-134">Sie verfügen über das folgende endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="92076-134">You have the following final solution layout:</span></span>

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="92076-135">Führen Sie [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-vb-nunit* aus.</span><span class="sxs-lookup"><span data-stu-id="92076-135">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-nunit* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="92076-136">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="92076-136">Creating the first test</span></span>

<span data-ttu-id="92076-137">Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="92076-137">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="92076-138">Entfernen Sie *UnitTest1.vb* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue Visual Basic-Datei namens *PrimeService_IsPrimeShould.VB*.</span><span class="sxs-lookup"><span data-stu-id="92076-138">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="92076-139">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="92076-139">Add the following code:</span></span>

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="92076-140">Das `<TestFixture>`-Attribut gibt eine Klasse an, die Tests enthält.</span><span class="sxs-lookup"><span data-stu-id="92076-140">The `<TestFixture>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="92076-141">Das `<Test>`-Attribut kennzeichnet eine Methode, die von Test Runner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="92076-141">The `<Test>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="92076-142">Führen Sie im Verzeichnis *unit-testing-vb-nunit* [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="92076-142">From the *unit-testing-vb-nunit*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="92076-143">Der NUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests.</span><span class="sxs-lookup"><span data-stu-id="92076-143">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="92076-144">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="92076-144">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="92076-145">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="92076-145">Your test fails.</span></span> <span data-ttu-id="92076-146">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="92076-146">You haven't created the implementation yet.</span></span> <span data-ttu-id="92076-147">Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="92076-147">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

<span data-ttu-id="92076-148">Führen Sie im Verzeichnis *unit-testing-vb-nunit* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="92076-148">In the *unit-testing-vb-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="92076-149">Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="92076-149">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="92076-150">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="92076-150">After building both projects, it runs this single test.</span></span> <span data-ttu-id="92076-151">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="92076-151">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="92076-152">Hinzufügen weiterer Features</span><span class="sxs-lookup"><span data-stu-id="92076-152">Adding more features</span></span>

<span data-ttu-id="92076-153">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="92076-153">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="92076-154">Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="92076-154">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="92076-155">Sie könnten diese neuen Fälle als neue Tests mit dem Attribut `<Test>` hinzufügen, aber das wird schnell recht mühsam.</span><span class="sxs-lookup"><span data-stu-id="92076-155">You could add those cases as new tests with the `<Test>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="92076-156">Es gibt andere xUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.</span><span class="sxs-lookup"><span data-stu-id="92076-156">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="92076-157">Ein `<TestCase>`-Attribut stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="92076-157">A `<TestCase>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="92076-158">Sie können das Attribut `<TestCase>` verwenden, um Werte für diese Eingaben anzugeben.</span><span class="sxs-lookup"><span data-stu-id="92076-158">You can use the `<TestCase>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="92076-159">Statt neue Tests zu erstellen, wenden Sie diese beiden Attribute zum Erstellen einer Testserie an. Damit werden mehrere Werte kleiner als 2 (die kleinste Primzahl) getestet:</span><span class="sxs-lookup"><span data-stu-id="92076-159">Instead of creating new tests, apply these two attributes to create a series of tests that test several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="92076-160">Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="92076-160">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="92076-161">Sie müssen die `if`-Klausel am Anfang der Methode ändern, damit alle Tests erfolgreich sind:</span><span class="sxs-lookup"><span data-stu-id="92076-161">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="92076-162">Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="92076-162">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="92076-163">Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="92076-163">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="92076-164">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="92076-164">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="92076-165">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="92076-165">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="92076-166">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="92076-166">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
