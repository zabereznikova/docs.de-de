---
title: Komponententests für F# in .NET Core mit „dotnet test“ und MSTest
description: Erfahren Sie mehr über die Konzepte von Komponententests für F# in .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und MSTest erstellen.
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.openlocfilehash: 08aa0b4a36f399d4439a0f3b34e88a1b51e98215
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656539"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-mstest"></a><span data-ttu-id="cae3d-103">Komponententests für F#-Bibliotheken in .NET Core mit „dotnet test“ und MSTest</span><span class="sxs-lookup"><span data-stu-id="cae3d-103">Unit testing F# libraries in .NET Core using dotnet test and MSTest</span></span>

<span data-ttu-id="cae3d-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="cae3d-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="cae3d-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-mstest/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="cae3d-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-mstest/) before you begin.</span></span> <span data-ttu-id="cae3d-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#view-and-download-samples).</span><span class="sxs-lookup"><span data-stu-id="cae3d-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a><span data-ttu-id="cae3d-107">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="cae3d-107">Creating the source project</span></span>

<span data-ttu-id="cae3d-108">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="cae3d-108">Open a shell window.</span></span> <span data-ttu-id="cae3d-109">Erstellen Sie ein Verzeichnis namens *unit-testing-with-fsharp*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cae3d-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="cae3d-110">Führen Sie in diesem neuen Verzeichnis `dotnet new sln` aus, um eine neue Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cae3d-110">Inside this new directory, run `dotnet new sln` to create a new solution.</span></span> <span data-ttu-id="cae3d-111">Dies vereinfacht die Verwaltung des Klassenbibliotheks- und Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="cae3d-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="cae3d-112">Erstellen Sie im Projektmappenverzeichnis ein *MathService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="cae3d-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="cae3d-113">Nachfolgend wird die bisherige Verzeichnis- und Dateistruktur dargestellt:</span><span class="sxs-lookup"><span data-stu-id="cae3d-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="cae3d-114">Machen Sie *MathService* zum aktuellen Verzeichnis, und führen Sie `dotnet new classlib -lang "F#"` aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cae3d-114">Make *MathService* the current directory and run `dotnet new classlib -lang "F#"` to create the source project.</span></span>  <span data-ttu-id="cae3d-115">Sie erstellen eine fehlerhafte Implementierung des Math-Diensts:</span><span class="sxs-lookup"><span data-stu-id="cae3d-115">You'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="cae3d-116">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="cae3d-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="cae3d-117">Führen Sie `dotnet sln add .\MathService\MathService.fsproj` aus, um der Projektmappe das Klassenbibliotheksprojekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="cae3d-117">Run `dotnet sln add .\MathService\MathService.fsproj` to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="cae3d-118">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="cae3d-118">Creating the test project</span></span>

<span data-ttu-id="cae3d-119">Erstellen Sie als Nächstes das Verzeichnis *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="cae3d-119">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="cae3d-120">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="cae3d-120">The following outline shows the directory structure:</span></span>

```console
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="cae3d-121">Machen Sie das *MathService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit `dotnet new mstest -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="cae3d-121">Make the *MathService.Tests* directory the current directory and create a new project using `dotnet new mstest -lang "F#"`.</span></span> <span data-ttu-id="cae3d-122">Dies erstellt ein Testprojekt, das MSTest als Testframework verwendet.</span><span class="sxs-lookup"><span data-stu-id="cae3d-122">This creates a test project that uses MSTest as the test framework.</span></span> <span data-ttu-id="cae3d-123">Die generierte Vorlage konfiguriert Test Runner in *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="cae3d-123">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="cae3d-124">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cae3d-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="cae3d-125">`dotnet new` hat im vorherigen Schritt MSTest und MSTest Runner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cae3d-125">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="cae3d-126">Fügen Sie jetzt die `MathService`-Klassenbibliothek als eine andere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="cae3d-126">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="cae3d-127">Verwenden Sie den Befehl `dotnet add reference`:</span><span class="sxs-lookup"><span data-stu-id="cae3d-127">Use the `dotnet add reference` command:</span></span>

```dotnetcli
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="cae3d-128">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="cae3d-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="cae3d-129">Sie verfügen über das folgende endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="cae3d-129">You have the following final solution layout:</span></span>

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

<span data-ttu-id="cae3d-130">Führen Sie `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` im Verzeichnis *unit-testing-with-fsharp* aus.</span><span class="sxs-lookup"><span data-stu-id="cae3d-130">Execute `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="cae3d-131">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="cae3d-131">Creating the first test</span></span>

<span data-ttu-id="cae3d-132">Sie schreiben einen fehlerhaften Test, lassen ihn bestehen und wiederholen dann den Prozess.</span><span class="sxs-lookup"><span data-stu-id="cae3d-132">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="cae3d-133">Öffnen Sie *Tests.fs*, und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="cae3d-133">Open *Tests.fs* and add the following code:</span></span>

```fsharp
namespace MathService.Tests

open System
open Microsoft.VisualStudio.TestTools.UnitTesting
open MathService

[<TestClass>]
type TestClass () =

    [<TestMethod>]
    member this.TestMethodPassing() =
        Assert.IsTrue(true)

    [<TestMethod>]
     member this.FailEveryTime() = Assert.IsTrue(false)
```

<span data-ttu-id="cae3d-134">Das `[<TestClass>]`-Attribut gibt eine Klasse an, die Tests enthält.</span><span class="sxs-lookup"><span data-stu-id="cae3d-134">The `[<TestClass>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="cae3d-135">Das `[<TestMethod>]`-Attribut kennzeichnet eine Testmethode, die von Test Runner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cae3d-135">The `[<TestMethod>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="cae3d-136">Führen Sie `dotnet test` im Verzeichnis *unit-testing-with-fsharp* aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cae3d-136">From the *unit-testing-with-fsharp* directory, execute `dotnet test` to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="cae3d-137">Der MSTest Test Runner verfügt über den Programmeinstiegspunkt zum Ausführen der Tests.</span><span class="sxs-lookup"><span data-stu-id="cae3d-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="cae3d-138">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="cae3d-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="cae3d-139">Diese zwei Tests geben jeweils den grundlegendsten bestandenen und fehlerhaften Test an.</span><span class="sxs-lookup"><span data-stu-id="cae3d-139">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="cae3d-140">`My test` wurde erfolgreich und `Fail every time` fehlerhaft abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cae3d-140">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="cae3d-141">Erstellen Sie jetzt einen Test für die `squaresOfOdds`-Methode.</span><span class="sxs-lookup"><span data-stu-id="cae3d-141">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="cae3d-142">Die `squaresOfOdds`-Methode gibt eine Liste der Quadrate aller ungeraden ganzzahligen Werte zurück, die Teil der Eingabesequenz sind.</span><span class="sxs-lookup"><span data-stu-id="cae3d-142">The `squaresOfOdds` method returns a list of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="cae3d-143">Anstatt zu versuchen, alle diese Funktionen gleichzeitig zu schreiben, können Sie iterativ Tests zum Überprüfen der Funktionalität erstellen.</span><span class="sxs-lookup"><span data-stu-id="cae3d-143">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="cae3d-144">Damit jeder Test erfolgreich abgeschlossen wird, muss die erforderliche Funktionalität für die Methode erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cae3d-144">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="cae3d-145">Der einfachste Test, den wir schreiben können, ist das Aufrufen von `squaresOfOdds` mit allen geraden Zahlen, wobei das Ergebnis eine leere Sequenz von Ganzzahlen sein sollte.</span><span class="sxs-lookup"><span data-stu-id="cae3d-145">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="cae3d-146">Im Folgenden wird dieser Test vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="cae3d-146">Here's that test:</span></span>

```fsharp
[<TestMethod>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="cae3d-147">Beachten Sie, dass die Sequenz `expected` zu einer Liste konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="cae3d-147">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="cae3d-148">Die MSTest-Bibliothek basiert auf einer Vielzahl von .NET-Standardtypen.</span><span class="sxs-lookup"><span data-stu-id="cae3d-148">The MSTest library relies on many standard .NET types.</span></span> <span data-ttu-id="cae3d-149">Diese Abhängigkeit bedeutet, dass Ihre öffentliche Schnittstelle und erwarteten Ergebnisse eher <xref:System.Collections.ICollection> statt <xref:System.Collections.IEnumerable> unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cae3d-149">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="cae3d-150">Bei der Ausführung des Tests stellen Sie fest, dass der Test fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="cae3d-150">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="cae3d-151">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="cae3d-151">You haven't created the implementation yet.</span></span> <span data-ttu-id="cae3d-152">Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `Mathservice`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="cae3d-152">Make this test pass by writing the simplest code in the `Mathservice` class that works:</span></span>

```fsharp
let squaresOfOdds xs =
    Seq.empty<int> |> Seq.toList
```

<span data-ttu-id="cae3d-153">Führen Sie im Verzeichnis *unit-testing-with-fsharp* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="cae3d-153">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="cae3d-154">Der `dotnet test`-Befehl führt einen Build für das `MathService`-Projekt und anschließend für das `MathService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="cae3d-154">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="cae3d-155">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cae3d-155">After building both projects, it runs this single test.</span></span> <span data-ttu-id="cae3d-156">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="cae3d-156">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="cae3d-157">Erfüllen der Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cae3d-157">Completing the requirements</span></span>

<span data-ttu-id="cae3d-158">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="cae3d-158">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="cae3d-159">Der nächste einfache Fall funktioniert mit einer Sequenz, deren einzige ungerade Zahl `1` lautet.</span><span class="sxs-lookup"><span data-stu-id="cae3d-159">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="cae3d-160">Die Zahl 1 ist einfacher, da 1 das Quadrat von 1 ist.</span><span class="sxs-lookup"><span data-stu-id="cae3d-160">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="cae3d-161">Im Folgenden wird der nächste Test vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="cae3d-161">Here's that next test:</span></span>

```fsharp
[<TestMethod>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="cae3d-162">Die Ausführung von `dotnet test` verursacht einen Fehler beim neuen Test.</span><span class="sxs-lookup"><span data-stu-id="cae3d-162">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="cae3d-163">Sie müssen die `squaresOfOdds`-Methode aktualisieren, um diesen neuen Test zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="cae3d-163">You must update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="cae3d-164">Damit dieser Test erfolgreich durchgeführt wird, müssen Sie alle geraden Zahlen aus der Sequenz filtern.</span><span class="sxs-lookup"><span data-stu-id="cae3d-164">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="cae3d-165">Hierzu können Sie eine kleine Filterfunktion schreiben und `Seq.filter` verwenden:</span><span class="sxs-lookup"><span data-stu-id="cae3d-165">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd |> Seq.toList
```

<span data-ttu-id="cae3d-166">Beachten Sie den Aufruf von `Seq.toList`.</span><span class="sxs-lookup"><span data-stu-id="cae3d-166">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="cae3d-167">Hierdurch wird eine Liste erstellt, die die Schnittstelle <xref:System.Collections.ICollection> implementiert.</span><span class="sxs-lookup"><span data-stu-id="cae3d-167">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="cae3d-168">Ein weiterer Schritt ist noch notwendig: Bilden Sie das Quadrat von jeder ungeraden Zahl.</span><span class="sxs-lookup"><span data-stu-id="cae3d-168">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="cae3d-169">Schreiben Sie zunächst einen neuen Test:</span><span class="sxs-lookup"><span data-stu-id="cae3d-169">Start by writing a new test:</span></span>

```fsharp
[<TestMethod>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="cae3d-170">Sie können den Test beheben, indem Sie für die gefilterte Sequenz einen Zuordnungsvorgang durchführen, um das Quadrat von jeder ungerade Zahl zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="cae3d-170">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
    |> Seq.toList
```

<span data-ttu-id="cae3d-171">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="cae3d-171">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="cae3d-172">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="cae3d-172">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="cae3d-173">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="cae3d-173">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="cae3d-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cae3d-174">See also</span></span>

- [<span data-ttu-id="cae3d-175">dotnet new</span><span class="sxs-lookup"><span data-stu-id="cae3d-175">dotnet new</span></span>](../tools/dotnet-new.md)
- [<span data-ttu-id="cae3d-176">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="cae3d-176">dotnet sln</span></span>](../tools/dotnet-sln.md)
- [<span data-ttu-id="cae3d-177">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="cae3d-177">dotnet add reference</span></span>](../tools/dotnet-add-reference.md)
- [<span data-ttu-id="cae3d-178">dotnet test</span><span class="sxs-lookup"><span data-stu-id="cae3d-178">dotnet test</span></span>](../tools/dotnet-test.md)
