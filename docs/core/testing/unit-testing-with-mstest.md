---
title: Komponententests für C# mit MSTest und .NET Core
description: Erfahren Sie mehr über die Konzepte von Komponententests in C# und .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und MSTest erstellen.
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.openlocfilehash: 2d432f5efd6f8de3593f939abbd488f9fe68b73e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715399"
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="411e2-103">Komponententests für C# mit MSTest und .NET Core</span><span class="sxs-lookup"><span data-stu-id="411e2-103">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="411e2-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="411e2-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="411e2-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="411e2-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="411e2-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="411e2-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="create-the-source-project"></a><span data-ttu-id="411e2-107">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="411e2-107">Create the source project</span></span>

<span data-ttu-id="411e2-108">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="411e2-108">Open a shell window.</span></span> <span data-ttu-id="411e2-109">Erstellen Sie ein Verzeichnis namens *unit-testing-using-mstest*, um darin die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="411e2-109">Create a directory called *unit-testing-using-mstest* to hold the solution.</span></span> <span data-ttu-id="411e2-110">Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappendatei für die Klassenbibliothek und das Testprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="411e2-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="411e2-111">Erstellen Sie als Nächstes ein *PrimeService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="411e2-111">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="411e2-112">Die folgende Gliederung zeigt die Verzeichnis- und Dateistruktur:</span><span class="sxs-lookup"><span data-stu-id="411e2-112">The following outline shows the directory and file structure thus far:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="411e2-113">Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="411e2-113">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="411e2-114">Benennen Sie *Class1.cs* in *PrimeService.cs* um.</span><span class="sxs-lookup"><span data-stu-id="411e2-114">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="411e2-115">Sie erstellen eine fehlerhafte Implementierung der `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="411e2-115">You create a failing implementation of the `PrimeService` class:</span></span>

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

<span data-ttu-id="411e2-116">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-using-mstest*.</span><span class="sxs-lookup"><span data-stu-id="411e2-116">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="411e2-117">Führen Sie [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="411e2-117">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span> 

## <a name="create-the-test-project"></a><span data-ttu-id="411e2-118">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="411e2-118">Create the test project</span></span>

<span data-ttu-id="411e2-119">Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="411e2-119">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="411e2-120">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="411e2-120">The following outline shows the directory structure:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="411e2-121">Machen Sie das *PrimeService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new mstest`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="411e2-121">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="411e2-122">Der neue dotnet-Befehl erstellt ein Testprojekt, das MSTest als Testbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="411e2-122">The dotnet new command creates a test project that uses MSTest as the test library.</span></span> <span data-ttu-id="411e2-123">Die generierte Vorlage konfiguriert das Testprogramm in der Datei *PrimeServiceTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="411e2-123">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="411e2-124">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="411e2-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="411e2-125">`dotnet new` hat im vorherigen Schritt MSTest-SDK, MSTest-Testframework und MSTest-Runner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="411e2-125">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="411e2-126">Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="411e2-126">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="411e2-127">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="411e2-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="411e2-128">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="411e2-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="411e2-129">Die folgende Gliederung zeigt das endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="411e2-129">The following outline shows the final solution layout:</span></span>

```console
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="411e2-130">Führen Sie [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-using-mstest* aus.</span><span class="sxs-lookup"><span data-stu-id="411e2-130">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-mstest* directory.</span></span> 

## <a name="create-the-first-test"></a><span data-ttu-id="411e2-131">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="411e2-131">Create the first test</span></span>

<span data-ttu-id="411e2-132">Sie schreiben einen fehlerhaften Test, lassen ihn bestehen und wiederholen dann den Prozess.</span><span class="sxs-lookup"><span data-stu-id="411e2-132">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="411e2-133">Entfernen Sie *UnitTest1.cs* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue C#-Datei namens *PrimeService_IsPrimeShould.cs* mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="411e2-133">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

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
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="411e2-134">Das [TestClass-Attribut](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) gibt eine Klasse an, die Komponententests enthält.</span><span class="sxs-lookup"><span data-stu-id="411e2-134">The [TestClass attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) denotes a class that contains unit tests.</span></span> <span data-ttu-id="411e2-135">Das [TestMethod-Attribut](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) gibt an, dass es sich bei einer Methode um eine Testmethode handelt.</span><span class="sxs-lookup"><span data-stu-id="411e2-135">The [TestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) indicates a method is a test method.</span></span> 

<span data-ttu-id="411e2-136">Speichern Sie diese Datei und führen Sie [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="411e2-136">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="411e2-137">Der MSTest Test Runner verfügt über den Programmeinstiegspunkt zum Ausführen der Tests.</span><span class="sxs-lookup"><span data-stu-id="411e2-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="411e2-138">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="411e2-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="411e2-139">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="411e2-139">Your test fails.</span></span> <span data-ttu-id="411e2-140">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="411e2-140">You haven't created the implementation yet.</span></span> <span data-ttu-id="411e2-141">Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="411e2-141">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

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

<span data-ttu-id="411e2-142">Führen Sie im Verzeichnis *unit-testing-using-mstest* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="411e2-142">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="411e2-143">Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="411e2-143">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="411e2-144">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="411e2-144">After building both projects, it runs this single test.</span></span> <span data-ttu-id="411e2-145">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="411e2-145">It passes.</span></span>

## <a name="add-more-features"></a><span data-ttu-id="411e2-146">Hinzufügen weiterer Features</span><span class="sxs-lookup"><span data-stu-id="411e2-146">Add more features</span></span>

<span data-ttu-id="411e2-147">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="411e2-147">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="411e2-148">Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="411e2-148">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="411e2-149">Sie könnten neue Tests zwar mit dem [TestMethod-Attribut](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) hinzufügen, allerdings wird dies auf diese Weise schnell mühsam.</span><span class="sxs-lookup"><span data-stu-id="411e2-149">You could add new tests with the [TestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute), but that quickly becomes tedious.</span></span> <span data-ttu-id="411e2-150">Es gibt andere MSTest-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.</span><span class="sxs-lookup"><span data-stu-id="411e2-150">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="411e2-151">Ein [DataTestMethod-Attribut](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataTestMethodAttribute) stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="411e2-151">A [DataTestMethod attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataTestMethodAttribute) represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="411e2-152">Sie können das [DataRow-Attribut](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataRowAttribute) verwenden, um Werte für diese Eingaben anzugeben.</span><span class="sxs-lookup"><span data-stu-id="411e2-152">You can use the [DataRow attribute](xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataRowAttribute) to specify values for those inputs.</span></span>

<span data-ttu-id="411e2-153">Statt neue Tests zu erstellen, wenden Sie diese beiden Attribute zum Erstellen eines einzelnen datengesteuerten Tests an.</span><span class="sxs-lookup"><span data-stu-id="411e2-153">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="411e2-154">Bei dem datengesteuerten Test handelt es sich um eine Methode, die mehrere Werte unter zwei als niedrigste Primzahl testet:</span><span class="sxs-lookup"><span data-stu-id="411e2-154">The data driven test is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="411e2-155">Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="411e2-155">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="411e2-156">Sie müssen die `if`-Klausel am Anfang der Methode ändern, damit alle Tests erfolgreich sind:</span><span class="sxs-lookup"><span data-stu-id="411e2-156">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="411e2-157">Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="411e2-157">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="411e2-158">Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span><span class="sxs-lookup"><span data-stu-id="411e2-158">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="411e2-159">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="411e2-159">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="411e2-160">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="411e2-160">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="411e2-161">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="411e2-161">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="411e2-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="411e2-162">See also</span></span>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting>
- [<span data-ttu-id="411e2-163">Verwenden des MSTest-Frameworks in Komponententests</span><span class="sxs-lookup"><span data-stu-id="411e2-163">Use the MSTest framework in unit tests</span></span>](/visualstudio/test/using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests)
- [<span data-ttu-id="411e2-164">Dokumentation zu Testframework „MSTest V2“</span><span class="sxs-lookup"><span data-stu-id="411e2-164">MSTest V2 test framework docs</span></span>](https://github.com/Microsoft/testfx-docs)
