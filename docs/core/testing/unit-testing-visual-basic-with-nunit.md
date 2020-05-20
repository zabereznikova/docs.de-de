---
title: Komponententests für Visual Basic in .NET Core mit „dotnet test“ und NUnit
description: Erfahren Sie mehr über die Konzepte von Komponententests in .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Visual Basic-Beispielprojektmappe mithilfe von NUnit erstellen.
author: rprouse
ms.date: 10/04/2018
ms.openlocfilehash: a33447457344b241b4c2376d777b0deb7f556874
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240921"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a><span data-ttu-id="de0a5-103">Unittests für Visual Basic .NET Core-Bibliotheken mithilfe von „dotnet test“ und NUnit</span><span class="sxs-lookup"><span data-stu-id="de0a5-103">Unit testing Visual Basic .NET Core libraries using dotnet test and NUnit</span></span>

<span data-ttu-id="de0a5-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="de0a5-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="de0a5-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="de0a5-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/) before you begin.</span></span> <span data-ttu-id="de0a5-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="de0a5-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a><span data-ttu-id="de0a5-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="de0a5-107">Prerequisites</span></span>

- <span data-ttu-id="de0a5-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) oder höhere Versionen.</span><span class="sxs-lookup"><span data-stu-id="de0a5-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="de0a5-109">Ein Text-Editor oder Code-Editor Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="de0a5-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="de0a5-110">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="de0a5-110">Creating the source project</span></span>

<span data-ttu-id="de0a5-111">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="de0a5-111">Open a shell window.</span></span> <span data-ttu-id="de0a5-112">Erstellen Sie ein Verzeichnis namens *unit-testing-vb-nunit*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="de0a5-112">Create a directory called *unit-testing-vb-nunit* to hold the solution.</span></span> <span data-ttu-id="de0a5-113">Führen Sie in diesem neuen Verzeichnis den folgenden Befehl aus, um eine neue Projektmappendatei für die Klassenbibliothek und das Testprojekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="de0a5-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```dotnetcli
dotnet new sln
```

<span data-ttu-id="de0a5-114">Erstellen Sie als Nächstes ein *PrimeService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="de0a5-114">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="de0a5-115">Die folgende Gliederung zeigt die bisherige Dateistruktur:</span><span class="sxs-lookup"><span data-stu-id="de0a5-115">The following outline shows the file structure so far:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

<span data-ttu-id="de0a5-116">Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie den folgenden Befehl aus, um das Quellprojekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="de0a5-116">Make *PrimeService* the current directory and run the following command to create the source project:</span></span>

```dotnetcli
dotnet new classlib -lang VB
```

<span data-ttu-id="de0a5-117">Benennen Sie *Class1.VB* in *PrimeService.VB* um.</span><span class="sxs-lookup"><span data-stu-id="de0a5-117">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="de0a5-118">Sie erstellen eine fehlerhafte Implementierung der `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="de0a5-118">You create a failing implementation of the `PrimeService` class:</span></span>

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first.")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="de0a5-119">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-vb-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="de0a5-119">Change the directory back to the *unit-testing-vb-using-mstest* directory.</span></span> <span data-ttu-id="de0a5-120">Führen Sie den folgenden Befehl aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="de0a5-120">Run the following command to add the class library project to the solution:</span></span>

```dotnetcli
dotnet sln add .\PrimeService\PrimeService.vbproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="de0a5-121">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="de0a5-121">Creating the test project</span></span>

<span data-ttu-id="de0a5-122">Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="de0a5-122">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="de0a5-123">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="de0a5-123">The following outline shows the directory structure:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="de0a5-124">Machen Sie das Verzeichnis *PrimeService.Tests* zum aktuellen Verzeichnis, und erstellen Sie mit dem folgenden Befehl ein neues Projekt:</span><span class="sxs-lookup"><span data-stu-id="de0a5-124">Make the *PrimeService.Tests* directory the current directory and create a new project using the following command:</span></span>

```dotnetcli
dotnet new nunit -lang VB
```

<span data-ttu-id="de0a5-125">Mit dem Befehl [dotnet new](../tools/dotnet-new.md) wird ein Testprojekt erstellt, in dem NUnit als Testbibliothek verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="de0a5-125">The [dotnet new](../tools/dotnet-new.md) command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="de0a5-126">Die generierte Vorlage konfiguriert Test Runner in der Datei *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="de0a5-126">The generated template configures the test runner in the *PrimeServiceTests.vbproj* file:</span></span>

[!code-xml[Packages](~/samples/snippets/core/testing/unit-testing-vb-nunit/vb/PrimeService.Tests/PrimeService.Tests.vbproj#Packages)]

<span data-ttu-id="de0a5-127">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="de0a5-127">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="de0a5-128">Mithilfe von `dotnet new` wurden im vorhergehenden Schritt NUnit und der NUnit-Testadapter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="de0a5-128">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="de0a5-129">Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als eine andere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="de0a5-129">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="de0a5-130">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="de0a5-130">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="de0a5-131">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="de0a5-131">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="de0a5-132">Sie verfügen über das folgende endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="de0a5-132">You have the following final solution layout:</span></span>

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.vbproj
```

<span data-ttu-id="de0a5-133">Führen Sie im Verzeichnis *unit-testing-vb-nunit* den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="de0a5-133">Execute the following command in the *unit-testing-vb-nunit* directory:</span></span>

```dotnetcli
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="de0a5-134">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="de0a5-134">Creating the first test</span></span>

<span data-ttu-id="de0a5-135">Sie schreiben einen fehlerhaften Test, lassen ihn bestehen und wiederholen dann den Prozess.</span><span class="sxs-lookup"><span data-stu-id="de0a5-135">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="de0a5-136">Benennen Sie im Verzeichnis *PrimeService.Tests* die Datei *UnitTest1.vb* in *PrimeService_IsPrimeShould.VB* um, und ersetzen Sie den gesamten Inhalt durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="de0a5-136">In the *PrimeService.Tests* directory, rename the *UnitTest1.vb* file to *PrimeService_IsPrimeShould.VB* and replace its entire contents with the following code:</span></span>

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="de0a5-137">Das `<TestFixture>`-Attribut gibt eine Klasse an, die Tests enthält.</span><span class="sxs-lookup"><span data-stu-id="de0a5-137">The `<TestFixture>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="de0a5-138">Das `<Test>`-Attribut kennzeichnet eine Methode, die von Test Runner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="de0a5-138">The `<Test>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="de0a5-139">Führen Sie im Verzeichnis *unit-testing-vb-nunit*[`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="de0a5-139">From the *unit-testing-vb-nunit*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="de0a5-140">Der NUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests.</span><span class="sxs-lookup"><span data-stu-id="de0a5-140">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="de0a5-141">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="de0a5-141">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="de0a5-142">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="de0a5-142">Your test fails.</span></span> <span data-ttu-id="de0a5-143">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="de0a5-143">You haven't created the implementation yet.</span></span> <span data-ttu-id="de0a5-144">Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="de0a5-144">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first.")
End Function
```

<span data-ttu-id="de0a5-145">Führen Sie im Verzeichnis *unit-testing-vb-nunit* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="de0a5-145">In the *unit-testing-vb-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="de0a5-146">Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="de0a5-146">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="de0a5-147">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="de0a5-147">After building both projects, it runs this single test.</span></span> <span data-ttu-id="de0a5-148">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="de0a5-148">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="de0a5-149">Hinzufügen weiterer Features</span><span class="sxs-lookup"><span data-stu-id="de0a5-149">Adding more features</span></span>

<span data-ttu-id="de0a5-150">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="de0a5-150">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="de0a5-151">Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="de0a5-151">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="de0a5-152">Sie könnten diese neuen Fälle als neue Tests mit dem Attribut `<Test>` hinzufügen, aber das wird schnell recht mühsam.</span><span class="sxs-lookup"><span data-stu-id="de0a5-152">You could add those cases as new tests with the `<Test>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="de0a5-153">Es gibt andere xUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.</span><span class="sxs-lookup"><span data-stu-id="de0a5-153">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="de0a5-154">Ein `<TestCase>`-Attribut stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="de0a5-154">A `<TestCase>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="de0a5-155">Sie können das Attribut `<TestCase>` verwenden, um Werte für diese Eingaben anzugeben.</span><span class="sxs-lookup"><span data-stu-id="de0a5-155">You can use the `<TestCase>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="de0a5-156">Statt neue Tests zu erstellen, wenden Sie diese beiden Attribute zum Erstellen einer Testserie an. Damit werden mehrere Werte kleiner als 2 (die kleinste Primzahl) getestet:</span><span class="sxs-lookup"><span data-stu-id="de0a5-156">Instead of creating new tests, apply these two attributes to create a series of tests that test several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-vb-nunit/vb/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="de0a5-157">Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="de0a5-157">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="de0a5-158">Damit alle Tests erfolgreich sind, ändern Sie in der Datei *PrimeServices.cs* am Anfang der Methode `Main` die `if`-Klausel:</span><span class="sxs-lookup"><span data-stu-id="de0a5-158">To make all of the tests pass, change the `if` clause at the beginning of the `Main` method in the *PrimeServices.cs* file:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="de0a5-159">Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="de0a5-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="de0a5-160">Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="de0a5-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="de0a5-161">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="de0a5-161">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="de0a5-162">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="de0a5-162">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="de0a5-163">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="de0a5-163">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
