---
title: Komponententests für Visual Basic in .NET Core mit „dotnet test“ und MSTest
description: Erfahren Sie mehr über die Konzepte von Komponententests in .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Visual Basic-Beispielprojektmappe mithilfe von MSTest erstellen.
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.openlocfilehash: 14c145ffc227078378897feeb75db0df8da4be6f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714251"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-mstest"></a><span data-ttu-id="e1b38-103">Komponententests für Visual Basic .NET Core-Bibliotheken mithilfe von „dotnet test“ und MSTest</span><span class="sxs-lookup"><span data-stu-id="e1b38-103">Unit testing Visual Basic .NET Core libraries using dotnet test and MSTest</span></span>

<span data-ttu-id="e1b38-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="e1b38-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="e1b38-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-mstest/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="e1b38-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-mstest/) before you begin.</span></span> <span data-ttu-id="e1b38-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="e1b38-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="e1b38-107">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="e1b38-107">Creating the source project</span></span>

<span data-ttu-id="e1b38-108">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="e1b38-108">Open a shell window.</span></span> <span data-ttu-id="e1b38-109">Erstellen Sie ein Verzeichnis namens *unit-testing-vb-mstest*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e1b38-109">Create a directory called *unit-testing-vb-mstest* to hold the solution.</span></span>
<span data-ttu-id="e1b38-110">Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1b38-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="e1b38-111">Diese Übung vereinfacht die Verwaltung des Klassenbibliotheks- und Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="e1b38-111">This practice makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="e1b38-112">Erstellen Sie im Projektmappenverzeichnis ein *PrimeService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e1b38-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="e1b38-113">Soweit verfügen Sie über die bisherige Verzeichnis- und Dateistruktur:</span><span class="sxs-lookup"><span data-stu-id="e1b38-113">You have the following directory and file structure thus far:</span></span>

```console
/unit-testing-vb-mstest
    unit-testing-vb-mstest.sln
    /PrimeService
```

<span data-ttu-id="e1b38-114">Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1b38-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="e1b38-115">Benennen Sie *Class1.VB* in *PrimeService.VB* um.</span><span class="sxs-lookup"><span data-stu-id="e1b38-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="e1b38-116">Sie erstellen eine fehlerhafte Implementierung der `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="e1b38-116">You create a failing implementation of the `PrimeService` class:</span></span>

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="e1b38-117">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-vb-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="e1b38-117">Change the directory back to the *unit-testing-vb-using-mstest* directory.</span></span> <span data-ttu-id="e1b38-118">Führen Sie [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e1b38-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="e1b38-119">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="e1b38-119">Creating the test project</span></span>

<span data-ttu-id="e1b38-120">Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="e1b38-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="e1b38-121">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="e1b38-121">The following outline shows the directory structure:</span></span>

```console
/unit-testing-vb-mstest
    unit-testing-vb-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="e1b38-122">Machen Sie das *PrimeService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new mstest -lang VB`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="e1b38-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="e1b38-123">Dieser Befehl erstellt ein Testprojekt, das NUnit als Testbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1b38-123">This command creates a test project that uses MSTest as the test library.</span></span> <span data-ttu-id="e1b38-124">Die generierte Vorlage konfiguriert Test Runner in *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="e1b38-124">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="e1b38-125">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e1b38-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="e1b38-126">`dotnet new` hat im vorherigen Schritt MSTest und MSTest Runner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e1b38-126">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="e1b38-127">Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1b38-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="e1b38-128">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="e1b38-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="e1b38-129">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="e1b38-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="e1b38-130">Sie verfügen über das folgende endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="e1b38-130">You have the following final solution layout:</span></span>

```console
/unit-testing-vb-mstest
    unit-testing-vb-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="e1b38-131">Führen Sie [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-vb-mstest* aus.</span><span class="sxs-lookup"><span data-stu-id="e1b38-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-mstest* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="e1b38-132">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="e1b38-132">Creating the first test</span></span>

<span data-ttu-id="e1b38-133">Sie schreiben einen fehlerhaften Test, lassen ihn bestehen und wiederholen dann den Prozess.</span><span class="sxs-lookup"><span data-stu-id="e1b38-133">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="e1b38-134">Entfernen Sie *UnitTest1.vb* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue Visual Basic-Datei namens *PrimeService_IsPrimeShould.VB*.</span><span class="sxs-lookup"><span data-stu-id="e1b38-134">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="e1b38-135">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="e1b38-135">Add the following code:</span></span>

```vb
Imports Microsoft.VisualStudio.TestTools.UnitTesting

Namespace PrimeService.Tests
    <TestClass>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <TestMethod>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.IsFalse(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="e1b38-136">Das `<TestClass>`-Attribut gibt eine Klasse an, die Tests enthält.</span><span class="sxs-lookup"><span data-stu-id="e1b38-136">The `<TestClass>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="e1b38-137">Das `<TestMethod>`-Attribut kennzeichnet eine Methode, die von Test Runner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e1b38-137">The `<TestMethod>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="e1b38-138">Führen Sie im Verzeichnis *unit-testing-vb-mstest*[`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e1b38-138">From the *unit-testing-vb-mstest*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="e1b38-139">Der MSTest Test Runner verfügt über den Programmeinstiegspunkt zum Ausführen der Tests.</span><span class="sxs-lookup"><span data-stu-id="e1b38-139">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="e1b38-140">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="e1b38-140">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="e1b38-141">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="e1b38-141">Your test fails.</span></span> <span data-ttu-id="e1b38-142">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="e1b38-142">You haven't created the implementation yet.</span></span> <span data-ttu-id="e1b38-143">Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="e1b38-143">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first.")
End Function
```

<span data-ttu-id="e1b38-144">Führen Sie im Verzeichnis *unit-testing-vb-mstest* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="e1b38-144">In the *unit-testing-vb-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="e1b38-145">Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="e1b38-145">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="e1b38-146">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e1b38-146">After building both projects, it runs this single test.</span></span> <span data-ttu-id="e1b38-147">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e1b38-147">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="e1b38-148">Hinzufügen weiterer Features</span><span class="sxs-lookup"><span data-stu-id="e1b38-148">Adding more features</span></span>

<span data-ttu-id="e1b38-149">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="e1b38-149">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="e1b38-150">Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="e1b38-150">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="e1b38-151">Sie könnten diese neuen Fälle als neue Tests mit dem Attribut `<TestMethod>` hinzufügen, aber das wird schnell recht mühsam.</span><span class="sxs-lookup"><span data-stu-id="e1b38-151">You could add those cases as new tests with the `<TestMethod>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="e1b38-152">Es gibt andere MSTest-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.</span><span class="sxs-lookup"><span data-stu-id="e1b38-152">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="e1b38-153">Ein `<DataTestMethod>`-Attribut stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1b38-153">A `<DataTestMethod>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="e1b38-154">Sie können das Attribut `<DataRow>` verwenden, um Werte für diese Eingaben anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e1b38-154">You can use the `<DataRow>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="e1b38-155">Statt neue Tests zu erstellen, wenden Sie diese beiden Attribute zum Erstellen einer einzelnen Theorie an.</span><span class="sxs-lookup"><span data-stu-id="e1b38-155">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="e1b38-156">Bei der Theorie handelt es sich um eine Methode, die mehrere Werte unter zwei als niedrigste Primzahl testet:</span><span class="sxs-lookup"><span data-stu-id="e1b38-156">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="e1b38-157">Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="e1b38-157">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="e1b38-158">Sie müssen die `if`-Klausel am Anfang der Methode ändern, damit alle Tests erfolgreich sind:</span><span class="sxs-lookup"><span data-stu-id="e1b38-158">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="e1b38-159">Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e1b38-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="e1b38-160">Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="e1b38-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="e1b38-161">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="e1b38-161">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="e1b38-162">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="e1b38-162">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="e1b38-163">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="e1b38-163">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
