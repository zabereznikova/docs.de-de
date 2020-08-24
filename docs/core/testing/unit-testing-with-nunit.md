---
title: Unittests für C# mit NUnit und .NET Core
description: Erfahren Sie mehr über die Konzepte von Unittests in C# und .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und NUnit erstellen.
author: rprouse
ms.date: 08/31/2018
ms.openlocfilehash: 90fd917fd980db6689195026a7524e0cacfc92bc
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656370"
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a><span data-ttu-id="1c019-103">Unittests für C# mit NUnit und .NET Core</span><span class="sxs-lookup"><span data-stu-id="1c019-103">Unit testing C# with NUnit and .NET Core</span></span>

<span data-ttu-id="1c019-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="1c019-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="1c019-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="1c019-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/) before you begin.</span></span> <span data-ttu-id="1c019-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#view-and-download-samples).</span><span class="sxs-lookup"><span data-stu-id="1c019-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a><span data-ttu-id="1c019-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1c019-107">Prerequisites</span></span>

- <span data-ttu-id="1c019-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) oder höhere Versionen.</span><span class="sxs-lookup"><span data-stu-id="1c019-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="1c019-109">Ein Text-Editor oder Code-Editor Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="1c019-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="1c019-110">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="1c019-110">Creating the source project</span></span>

<span data-ttu-id="1c019-111">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="1c019-111">Open a shell window.</span></span> <span data-ttu-id="1c019-112">Erstellen Sie ein Verzeichnis namens *unit-testing-using-nunit*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1c019-112">Create a directory called *unit-testing-using-nunit* to hold the solution.</span></span> <span data-ttu-id="1c019-113">Führen Sie in diesem neuen Verzeichnis den folgenden Befehl aus, um eine neue Projektmappendatei für die Klassenbibliothek und das Testprojekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1c019-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```dotnetcli
dotnet new sln
```

<span data-ttu-id="1c019-114">Erstellen Sie als Nächstes ein *PrimeService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1c019-114">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="1c019-115">Die folgende Gliederung zeigt die bisherige Verzeichnis- und Dateistruktur:</span><span class="sxs-lookup"><span data-stu-id="1c019-115">The following outline shows the directory and file structure so far:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

<span data-ttu-id="1c019-116">Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie den folgenden Befehl aus, um das Quellprojekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1c019-116">Make *PrimeService* the current directory and run the following command to create the source project:</span></span>

```dotnetcli
dotnet new classlib
```

<span data-ttu-id="1c019-117">Benennen Sie *Class1.cs* in *PrimeService.cs* um.</span><span class="sxs-lookup"><span data-stu-id="1c019-117">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="1c019-118">Sie erstellen eine fehlerhafte Implementierung der `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="1c019-118">You create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first.");
        }
    }
}
```

<span data-ttu-id="1c019-119">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-using-nunit*.</span><span class="sxs-lookup"><span data-stu-id="1c019-119">Change the directory back to the *unit-testing-using-nunit* directory.</span></span> <span data-ttu-id="1c019-120">Führen Sie den folgenden Befehl aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="1c019-120">Run the following command to add the class library project to the solution:</span></span>

```dotnetcli
dotnet sln add PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="1c019-121">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="1c019-121">Creating the test project</span></span>

<span data-ttu-id="1c019-122">Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="1c019-122">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="1c019-123">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="1c019-123">The following outline shows the directory structure:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="1c019-124">Machen Sie das Verzeichnis *PrimeService.Tests* zum aktuellen Verzeichnis, und erstellen Sie mit dem folgenden Befehl ein neues Projekt:</span><span class="sxs-lookup"><span data-stu-id="1c019-124">Make the *PrimeService.Tests* directory the current directory and create a new project using the following command:</span></span>

```dotnetcli
dotnet new nunit
```

<span data-ttu-id="1c019-125">Mit dem Befehl [dotnet new](../tools/dotnet-new.md) wird ein Testprojekt erstellt, in dem NUnit als Testbibliothek verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1c019-125">The [dotnet new](../tools/dotnet-new.md) command creates a test project that uses NUnit as the test library.</span></span> <span data-ttu-id="1c019-126">Die generierte Vorlage konfiguriert das Testprogramm in der Datei *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="1c019-126">The generated template configures the test runner in the *PrimeService.Tests.csproj* file:</span></span>

[!code-xml[Packages](~/samples/snippets/core/testing/unit-testing-using-nunit/csharp/PrimeService.Tests/PrimeService.Tests.csproj#Packages)]

<span data-ttu-id="1c019-127">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1c019-127">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="1c019-128">Mithilfe von `dotnet new` im vorherigen Schritt wurden das Microsoft-Test-SDK, das NUnit-Testframework und der NUnit-Testadapter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1c019-128">`dotnet new` in the previous step added the Microsoft test SDK, the NUnit test framework, and the NUnit test adapter.</span></span> <span data-ttu-id="1c019-129">Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als eine andere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c019-129">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="1c019-130">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="1c019-130">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="1c019-131">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="1c019-131">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="1c019-132">Die folgende Gliederung zeigt das endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="1c019-132">The following outline shows the final solution layout:</span></span>

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.csproj
```

<span data-ttu-id="1c019-133">Führen Sie im Verzeichnis *unit-testing-using-nunit* den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1c019-133">Execute the following command in the *unit-testing-using-nunit* directory:</span></span>

```dotnetcli
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="1c019-134">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="1c019-134">Creating the first test</span></span>

<span data-ttu-id="1c019-135">Sie schreiben einen fehlerhaften Test, lassen ihn bestehen und wiederholen dann den Prozess.</span><span class="sxs-lookup"><span data-stu-id="1c019-135">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="1c019-136">Benennen Sie im Verzeichnis *PrimeService.Tests* die Datei *UnitTest1.cs* in *PrimeService_IsPrimeShould.cs* um, und ersetzen Sie die zugehörigen Inhalte durch Inhalte mit dem folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="1c019-136">In the *PrimeService.Tests* directory, rename the *UnitTest1.cs* file to *PrimeService_IsPrimeShould.cs* and replace its entire contents with the following code:</span></span>

[!code-csharp[Sample_FirstTest](~/samples/snippets/core/testing/unit-testing-using-nunit/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_FirstTest)]

<span data-ttu-id="1c019-137">Das `[TestFixture]`-Attribut gibt eine Klasse an, die Unittests enthält.</span><span class="sxs-lookup"><span data-stu-id="1c019-137">The `[TestFixture]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="1c019-138">Das `[Test]`-Attribut gibt an, dass es sich bei einer Methode um eine Testmethode handelt.</span><span class="sxs-lookup"><span data-stu-id="1c019-138">The `[Test]` attribute indicates a method is a test method.</span></span>

<span data-ttu-id="1c019-139">Speichern Sie diese Datei und führen Sie [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1c019-139">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="1c019-140">Der NUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests.</span><span class="sxs-lookup"><span data-stu-id="1c019-140">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="1c019-141">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="1c019-141">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="1c019-142">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="1c019-142">Your test fails.</span></span> <span data-ttu-id="1c019-143">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="1c019-143">You haven't created the implementation yet.</span></span> <span data-ttu-id="1c019-144">Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="1c019-144">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first.");
}
```

<span data-ttu-id="1c019-145">Führen Sie im Verzeichnis *unit-testing-using-nunit* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="1c019-145">In the *unit-testing-using-nunit* directory, run `dotnet test` again.</span></span> <span data-ttu-id="1c019-146">Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="1c019-146">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="1c019-147">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1c019-147">After building both projects, it runs this single test.</span></span> <span data-ttu-id="1c019-148">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="1c019-148">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="1c019-149">Hinzufügen weiterer Features</span><span class="sxs-lookup"><span data-stu-id="1c019-149">Adding more features</span></span>

<span data-ttu-id="1c019-150">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="1c019-150">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="1c019-151">Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="1c019-151">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="1c019-152">Sie könnten diese neuen Tests mit dem Attribut `[Test]` hinzufügen, aber das wird schnell recht mühsam.</span><span class="sxs-lookup"><span data-stu-id="1c019-152">You could add new tests with the `[Test]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="1c019-153">Es gibt andere NUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.</span><span class="sxs-lookup"><span data-stu-id="1c019-153">There are other NUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="1c019-154">Ein `[TestCase]`-Attribut wird verwendet, um eine Reihe von Tests zu erstellen, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c019-154">A `[TestCase]` attribute is used to create a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="1c019-155">Sie können das Attribut `[TestCase]` verwenden, um Werte für diese Eingaben anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1c019-155">You can use the `[TestCase]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="1c019-156">Statt neue Tests zu erstellen, wenden Sie dieses Attribut zum Erstellen eines einzelnen datengesteuerten Tests an.</span><span class="sxs-lookup"><span data-stu-id="1c019-156">Instead of creating new tests, apply this attribute to create a single data driven test.</span></span> <span data-ttu-id="1c019-157">Bei dem datengesteuerten Test handelt es sich um eine Methode, die mehrere Werte unter zwei als niedrigste Primzahl testet:</span><span class="sxs-lookup"><span data-stu-id="1c019-157">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](~/samples/snippets/core/testing/unit-testing-using-nunit/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="1c019-158">Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="1c019-158">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="1c019-159">Damit alle Tests erfolgreich sind, müssen Sie in der Datei *PrimeService.cs* am Anfang der Methode `Main` die `if`-Klausel ändern:</span><span class="sxs-lookup"><span data-stu-id="1c019-159">To make all of the tests pass, change the `if` clause at the beginning of the `Main` method in the *PrimeService.cs* file:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="1c019-160">Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c019-160">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="1c019-161">Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="1c019-161">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="1c019-162">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="1c019-162">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="1c019-163">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="1c019-163">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="1c019-164">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="1c019-164">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
