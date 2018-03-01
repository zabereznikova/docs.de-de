---
title: "Unittests für F#-Bibliotheken in .NET Core mit „dotnet test“ und NUnit"
description: "Erfahren Sie mehr über die Konzepte von Komponententests für F# in .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und NUnit erstellen."
author: rprouse
ms.date: 12/01/2017
ms.topic: article
dev_langs:
- fsharp
ms.prod: .net-core
ms.openlocfilehash: 27a7bb889fd736294252da39b1839b2197b8df03
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-nunit"></a><span data-ttu-id="e6d2d-103">Unittests für F#-Bibliotheken in .NET Core mit „dotnet test“ und NUnit</span><span class="sxs-lookup"><span data-stu-id="e6d2d-103">Unit testing F# libraries in .NET Core using dotnet test and NUnit</span></span>

<span data-ttu-id="e6d2d-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="e6d2d-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-with-fsharp-nunit/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-with-fsharp-nunit/) before you begin.</span></span> <span data-ttu-id="e6d2d-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="e6d2d-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="e6d2d-107">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="e6d2d-107">Creating the source project</span></span>

<span data-ttu-id="e6d2d-108">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-108">Open a shell window.</span></span> <span data-ttu-id="e6d2d-109">Erstellen Sie ein Verzeichnis namens *unit-testing-with-fsharp*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="e6d2d-110">Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="e6d2d-111">Dies vereinfacht die Verwaltung des Klassenbibliotheks- und Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="e6d2d-112">Erstellen Sie im Projektmappenverzeichnis ein *MathService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="e6d2d-113">Nachfolgend wird die bisherige Verzeichnis- und Dateistruktur dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="e6d2d-114">Machen Sie *MathService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-114">Make *MathService* the current directory and run [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) to create the source project.</span></span>  <span data-ttu-id="e6d2d-115">Erstellen Sie eine fehlerhafte Implementierung des math-Diensts, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-115">To use test-driven development (TDD), you'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let sumOfSquares xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="e6d2d-116">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="e6d2d-117">Führen Sie [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-117">Run [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="install-the-nunit-project-template"></a><span data-ttu-id="e6d2d-118">Installieren der NUnit-Projektvorlage</span><span class="sxs-lookup"><span data-stu-id="e6d2d-118">Install the NUnit project template</span></span>

<span data-ttu-id="e6d2d-119">Vor dem Erstellen eines Testprojekts müssen Sie die NUnit-Projektvorlage installieren.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-119">The NUnit test project templates need to be installed before creating a test project.</span></span> <span data-ttu-id="e6d2d-120">Dies muss auf jedem Entwicklercomputer, auf dem Sie neue NUnit-Projekte erstellen, nur einmal erfolgen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-120">This only needs to be done once on each developer machine where you'll create new NUnit projects.</span></span> <span data-ttu-id="e6d2d-121">Führen Sie [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) aus, um die NUnit-Vorlagen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-121">Run [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) to install the NUnit templates.</span></span>

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a><span data-ttu-id="e6d2d-122">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="e6d2d-122">Creating the test project</span></span>

<span data-ttu-id="e6d2d-123">Erstellen Sie als Nächstes das Verzeichnis *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-123">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="e6d2d-124">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-124">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="e6d2d-125">Machen Sie das *MathService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new nunit -lang F#`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="e6d2d-125">Make the *MathService.Tests* directory the current directory and create a new project using [`dotnet new nunit -lang F#`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="e6d2d-126">Dies erstellt ein Testprojekt, das NUnit als Testframework verwendet.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-126">This creates a test project that uses NUnit as the test framework.</span></span> <span data-ttu-id="e6d2d-127">Die generierte Vorlage konfiguriert Test Runner in *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-127">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="e6d2d-128">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-128">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="e6d2d-129">Mithilfe von `dotnet new` wurden im vorhergehenden Schritt NUnit und der NUnit-Testadapter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-129">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="e6d2d-130">Fügen Sie jetzt die `MathService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-130">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="e6d2d-131">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="e6d2d-131">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="e6d2d-132">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-132">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="e6d2d-133">Sie verfügen über das folgende endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-133">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

<span data-ttu-id="e6d2d-134">Führen Sie [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-with-fsharp* aus.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-134">Execute [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="e6d2d-135">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="e6d2d-135">Creating the first test</span></span>

<span data-ttu-id="e6d2d-136">Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-136">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="e6d2d-137">Öffnen Sie *Tests.fs*, und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-137">Open *Tests.fs* and add the following code:</span></span>

```fsharp
namespace MathService.Tests

open System
open NUnit.Framework
open MathService

[<TestFixture>]
type TestClass () =

    [<Test>]
    member this.TestMethodPassing() =
        Assert.True(true)

    [<Test>]
     member this.FailEveryTime() = Assert.True(false)
```

<span data-ttu-id="e6d2d-138">Das `[<TestFixture>]`-Attribut gibt eine Klasse an, die Tests enthält.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-138">The `[<TestFixture>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="e6d2d-139">Das `[<Test>]`-Attribut kennzeichnet eine Testmethode, die von Test Runner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-139">The `[<Test>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="e6d2d-140">Führen Sie im Verzeichnis *unit-testing-with-fsharp* [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-140">From the *unit-testing-with-fsharp* directory, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="e6d2d-141">Der NUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-141">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="e6d2d-142">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-142">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="e6d2d-143">Diese zwei Tests geben jeweils den grundlegendsten bestandenen und fehlerhaften Test an.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-143">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="e6d2d-144">`My test` wurde erfolgreich und `Fail every time` fehlerhaft abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-144">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="e6d2d-145">Erstellen Sie jetzt einen Test für die `sumOfSquares`-Methode.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-145">Now, create a test for the `sumOfSquares` method.</span></span> <span data-ttu-id="e6d2d-146">Die `sumOfSquares`-Methode gibt die Summe der Quadrate aller ungeraden ganzzahligen Werte zurück, die Teil der Eingabesequenz sind.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-146">The `sumOfSquares` method returns the sum of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="e6d2d-147">Anstatt zu versuchen, alle diese Funktionen gleichzeitig zu schreiben, können Sie iterativ Tests zum Überprüfen der Funktionalität erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-147">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="e6d2d-148">Damit jeder Test erfolgreich abgeschlossen wird, muss die erforderliche Funktionalität für die Methode erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-148">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="e6d2d-149">Der einfachste Test, den wir schreiben können, ist das Aufrufen von `sumOfSquares` mit allen geraden Zahlen, wobei das Ergebnis eine leere Sequenz von Ganzzahlen sein sollte.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-149">The simplest test we can write is to call `sumOfSquares` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="e6d2d-150">Im Folgenden wird dieser Test vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-150">Here's that test:</span></span>

```fsharp
[<Test>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.sumOfSquares [2; 4; 6; 8; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="e6d2d-151">Beachten Sie, dass die Sequenz `expected` zu einer Liste konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-151">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="e6d2d-152">Das NUnit-Framework basiert auf einer Vielzahl von .NET-Standardtypen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-152">The NUnit framework relies on many standard .NET types.</span></span> <span data-ttu-id="e6d2d-153">Diese Abhängigkeit bedeutet, dass Ihre öffentliche Schnittstelle und erwarteten Ergebnisse eher <xref:System.Collections.ICollection> statt <xref:System.Collections.IEnumerable> unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-153">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="e6d2d-154">Bei der Ausführung des Tests stellen Sie fest, dass der Test fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-154">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="e6d2d-155">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-155">You haven't created the implementation yet.</span></span> <span data-ttu-id="e6d2d-156">Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `Mathservice`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-156">Make this test by writing the simplest code in the `Mathservice` class that works:</span></span>

```csharp
let sumOfSquares xs =
    Seq.empty<int> |> Seq.toList
```

<span data-ttu-id="e6d2d-157">Führen Sie im Verzeichnis *unit-testing-with-fsharp* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-157">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="e6d2d-158">Der `dotnet test`-Befehl führt einen Build für das `MathService`-Projekt und anschließend für das `MathService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-158">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="e6d2d-159">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-159">After building both projects, it runs this single test.</span></span> <span data-ttu-id="e6d2d-160">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-160">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="e6d2d-161">Erfüllen der Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6d2d-161">Completing the requirements</span></span>

<span data-ttu-id="e6d2d-162">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-162">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="e6d2d-163">Der nächste einfache Fall funktioniert mit einer Sequenz, deren einzige ungerade Zahl `1` lautet.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-163">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="e6d2d-164">Die Zahl 1 ist einfacher, da 1 das Quadrat von 1 ist.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-164">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="e6d2d-165">Im Folgenden wird der nächste Test vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-165">Here's that next test:</span></span>

```fsharp
[<Test>]
member public this.SumOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.sumOfSquares [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="e6d2d-166">Die Ausführung von `dotnet test` verursacht einen Fehler beim neuen Test.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-166">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="e6d2d-167">Sie müssen die `sumOfSquares`-Methode aktualisieren, um diesen neuen Test zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-167">You must update the `sumOfSquares` method to handle this new test.</span></span> <span data-ttu-id="e6d2d-168">Damit dieser Test erfolgreich durchgeführt wird, müssen Sie alle geraden Zahlen aus der Sequenz filtern.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-168">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="e6d2d-169">Hierzu können Sie eine kleine Filterfunktion schreiben und `Seq.filter` verwenden:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-169">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let sumOfSquares xs =
    xs
    |> Seq.filter isOdd
    |> Seq.toList
```

<span data-ttu-id="e6d2d-170">Beachten Sie den Aufruf von `Seq.toList`.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-170">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="e6d2d-171">Hierdurch wird eine Liste erstellt, die die Schnittstelle <xref:System.Collections.ICollection> implementiert.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-171">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="e6d2d-172">Ein weiterer Schritt ist noch notwendig: Bilden Sie das Quadrat von jeder ungeraden Zahl.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-172">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="e6d2d-173">Schreiben Sie zunächst einen neuen Test:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-173">Start by writing a new test:</span></span>

```fsharp
[<Test>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.sumOfSquares [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="e6d2d-174">Sie können den Test beheben, indem Sie für die gefilterte Sequenz einen Zuordnungsvorgang durchführen, um das Quadrat von jeder ungerade Zahl zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="e6d2d-174">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let sumOfSquares xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
    |> Seq.toList
```

<span data-ttu-id="e6d2d-175">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-175">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="e6d2d-176">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-176">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="e6d2d-177">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="e6d2d-177">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
