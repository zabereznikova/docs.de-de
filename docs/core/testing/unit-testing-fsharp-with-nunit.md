---
title: Komponententests für F# in .NET Core mit „dotnet test“ und NUnit
description: Erfahren Sie mehr über die Konzepte von Komponententests für F# in .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und NUnit erstellen.
author: rprouse
ms.date: 10/04/2018
dev_langs:
- fsharp
ms.openlocfilehash: 3347e5b90c31589e9a0f99ac0d9298927a717f56
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715447"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-nunit"></a><span data-ttu-id="bc4e5-103">Unittests für F#-Bibliotheken in .NET Core mit „dotnet test“ und NUnit</span><span class="sxs-lookup"><span data-stu-id="bc4e5-103">Unit testing F# libraries in .NET Core using dotnet test and NUnit</span></span>

<span data-ttu-id="bc4e5-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="bc4e5-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/) before you begin.</span></span> <span data-ttu-id="bc4e5-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="bc4e5-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a><span data-ttu-id="bc4e5-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bc4e5-107">Prerequisites</span></span>

- <span data-ttu-id="bc4e5-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) oder höhere Versionen.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="bc4e5-109">Ein Text-Editor oder Code-Editor Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-109">A text editor or code editor of your choice.</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="bc4e5-110">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="bc4e5-110">Creating the source project</span></span>

<span data-ttu-id="bc4e5-111">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-111">Open a shell window.</span></span> <span data-ttu-id="bc4e5-112">Erstellen Sie ein Verzeichnis namens *unit-testing-with-fsharp*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-112">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="bc4e5-113">Führen Sie in diesem neuen Verzeichnis den folgenden Befehl aus, um eine neue Projektmappendatei für die Klassenbibliothek und das Testprojekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-113">Inside this new directory, run the following command to create a new solution file for the class library and the test project:</span></span>

```dotnetcli
dotnet new sln
```

<span data-ttu-id="bc4e5-114">Erstellen Sie als Nächstes das Verzeichnis *MathService*.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-114">Next, create a *MathService* directory.</span></span> <span data-ttu-id="bc4e5-115">Die folgende Gliederung zeigt die bisherige Verzeichnis- und Dateistruktur:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-115">The following outline shows the directory and file structure so far:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="bc4e5-116">Legen Sie *MathService* als aktuelles Verzeichnis fest, und führen Sie den folgenden Befehl aus, um das Quellprojekt zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-116">Make *MathService* the current directory and run the following command to create the source project:</span></span>

```dotnetcli
dotnet new classlib -lang "F#"
```

<span data-ttu-id="bc4e5-117">Sie erstellen eine fehlerhafte Implementierung des Math-Diensts:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-117">You create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="bc4e5-118">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-118">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="bc4e5-119">Führen Sie den folgenden Befehl aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-119">Run the following command to add the class library project to the solution:</span></span>

```dotnetcli
dotnet sln add .\MathService\MathService.fsproj
```

## <a name="creating-the-test-project"></a><span data-ttu-id="bc4e5-120">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="bc4e5-120">Creating the test project</span></span>

<span data-ttu-id="bc4e5-121">Erstellen Sie als Nächstes das Verzeichnis *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-121">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="bc4e5-122">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-122">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="bc4e5-123">Legen Sie das Verzeichnis *MathService.Tests* als aktuelles Verzeichnis fest, und erstellen Sie mit dem folgenden Befehl ein neues Projekt:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-123">Make the *MathService.Tests* directory the current directory and create a new project using the following command:</span></span>

```dotnetcli
dotnet new nunit -lang "F#"
```

<span data-ttu-id="bc4e5-124">Dies erstellt ein Testprojekt, das NUnit als Testframework verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-124">This creates a test project that uses NUnit as the test framework.</span></span> <span data-ttu-id="bc4e5-125">Die generierte Vorlage konfiguriert Test Runner in *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-125">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

<span data-ttu-id="bc4e5-126">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-126">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="bc4e5-127">Mithilfe von `dotnet new` wurden im vorhergehenden Schritt NUnit und der NUnit-Testadapter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-127">`dotnet new` in the previous step added NUnit and the NUnit test adapter.</span></span> <span data-ttu-id="bc4e5-128">Fügen Sie jetzt die `MathService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-128">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="bc4e5-129">Verwenden Sie den Befehl `dotnet add reference`:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-129">Use the `dotnet add reference` command:</span></span>

```dotnetcli
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="bc4e5-130">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-130">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="bc4e5-131">Sie verfügen über das folgende endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-131">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathService.Tests.fsproj
```

<span data-ttu-id="bc4e5-132">Führen Sie im Verzeichnis *unit-testing-with-fsharp* den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-132">Execute the following command in the *unit-testing-with-fsharp* directory:</span></span>

```dotnetcli
dotnet sln add .\MathService.Tests\MathService.Tests.fsproj
```

## <a name="creating-the-first-test"></a><span data-ttu-id="bc4e5-133">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="bc4e5-133">Creating the first test</span></span>

<span data-ttu-id="bc4e5-134">Sie schreiben einen fehlerhaften Test, lassen ihn bestehen und wiederholen dann den Prozess.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-134">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="bc4e5-135">Öffnen Sie *UnitTest1.fs*, und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-135">Open *UnitTest1.fs* and add the following code:</span></span>

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

<span data-ttu-id="bc4e5-136">Das `[<TestFixture>]`-Attribut gibt eine Klasse an, die Tests enthält.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-136">The `[<TestFixture>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="bc4e5-137">Das `[<Test>]`-Attribut kennzeichnet eine Testmethode, die von Test Runner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-137">The `[<Test>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="bc4e5-138">Führen Sie `dotnet test` im Verzeichnis *unit-testing-with-fsharp* aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-138">From the *unit-testing-with-fsharp* directory, execute `dotnet test` to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="bc4e5-139">Der NUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-139">The NUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="bc4e5-140">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-140">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="bc4e5-141">Diese zwei Tests geben jeweils den grundlegendsten bestandenen und fehlerhaften Test an.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-141">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="bc4e5-142">`My test` wurde erfolgreich und `Fail every time` fehlerhaft abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-142">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="bc4e5-143">Erstellen Sie jetzt einen Test für die `squaresOfOdds`-Methode.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-143">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="bc4e5-144">Die `squaresOfOdds`-Methode gibt eine Sequenz der Quadrate aller ungeraden ganzzahligen Werte zurück, die Teil der Eingabesequenz sind.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-144">The `squaresOfOdds` method returns a sequence of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="bc4e5-145">Anstatt zu versuchen, alle diese Funktionen gleichzeitig zu schreiben, können Sie iterativ Tests zum Überprüfen der Funktionalität erstellen.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-145">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="bc4e5-146">Damit jeder Test erfolgreich abgeschlossen wird, muss die erforderliche Funktionalität für die Methode erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-146">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="bc4e5-147">Der einfachste Test, den wir schreiben können, ist das Aufrufen von `squaresOfOdds` mit allen geraden Zahlen, wobei das Ergebnis eine leere Sequenz von Ganzzahlen sein sollte.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-147">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="bc4e5-148">Im Folgenden wird dieser Test vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-148">Here's that test:</span></span>

```fsharp
[<Test>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="bc4e5-149">Beachten Sie, dass die Sequenz `expected` zu einer Liste konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-149">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="bc4e5-150">Das NUnit-Framework basiert auf einer Vielzahl von .NET-Standardtypen.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-150">The NUnit framework relies on many standard .NET types.</span></span> <span data-ttu-id="bc4e5-151">Diese Abhängigkeit bedeutet, dass Ihre öffentliche Schnittstelle und erwarteten Ergebnisse eher <xref:System.Collections.ICollection> statt <xref:System.Collections.IEnumerable> unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-151">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="bc4e5-152">Bei der Ausführung des Tests stellen Sie fest, dass der Test fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-152">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="bc4e5-153">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-153">You haven't created the implementation yet.</span></span> <span data-ttu-id="bc4e5-154">Sorgen Sie dafür, dass dieser Test erfolgreich verläuft, indem Sie in der *Library.fs*-Klasse in Ihrem MathService-Projekt sehr einfachen Code schreiben, der funktioniert:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-154">Make this test pass by writing the simplest code in the *Library.fs* class in your MathService project that works:</span></span>

```fsharp
let squaresOfOdds xs =
    Seq.empty<int>
```

<span data-ttu-id="bc4e5-155">Führen Sie im Verzeichnis *unit-testing-with-fsharp* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-155">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="bc4e5-156">Der `dotnet test`-Befehl führt einen Build für das `MathService`-Projekt und anschließend für das `MathService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-156">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="bc4e5-157">Nachdem beide Projekte erstellt wurden, führen Sie Ihre Tests aus.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-157">After building both projects, it runs your tests.</span></span> <span data-ttu-id="bc4e5-158">Zwei Tests verlaufen jetzt erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-158">Two tests pass now.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="bc4e5-159">Erfüllen der Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc4e5-159">Completing the requirements</span></span>

<span data-ttu-id="bc4e5-160">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-160">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="bc4e5-161">Der nächste einfache Fall funktioniert mit einer Sequenz, deren einzige ungerade Zahl `1` lautet.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-161">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="bc4e5-162">Die Zahl 1 ist einfacher, da 1 das Quadrat von 1 ist.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-162">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="bc4e5-163">Im Folgenden wird der nächste Test vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-163">Here's that next test:</span></span>

```fsharp
[<Test>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="bc4e5-164">Die Ausführung von `dotnet test` verursacht einen Fehler beim neuen Test.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-164">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="bc4e5-165">Sie müssen die `squaresOfOdds`-Methode aktualisieren, um diesen neuen Test zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-165">You must update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="bc4e5-166">Damit dieser Test erfolgreich durchgeführt wird, müssen Sie alle geraden Zahlen aus der Sequenz filtern.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-166">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="bc4e5-167">Hierzu können Sie eine kleine Filterfunktion schreiben und `Seq.filter` verwenden:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-167">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

<span data-ttu-id="bc4e5-168">Beachten Sie den Aufruf von `Seq.toList`.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-168">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="bc4e5-169">Hierdurch wird eine Liste erstellt, die die Schnittstelle <xref:System.Collections.ICollection> implementiert.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-169">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="bc4e5-170">Ein weiterer Schritt ist noch notwendig: Bilden Sie das Quadrat von jeder ungeraden Zahl.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-170">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="bc4e5-171">Schreiben Sie zunächst einen neuen Test:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-171">Start by writing a new test:</span></span>

```fsharp
[<Test>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

<span data-ttu-id="bc4e5-172">Sie können den Test beheben, indem Sie für die gefilterte Sequenz einen Zuordnungsvorgang durchführen, um das Quadrat von jeder ungerade Zahl zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="bc4e5-172">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
```

<span data-ttu-id="bc4e5-173">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-173">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="bc4e5-174">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-174">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="bc4e5-175">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="bc4e5-175">You've concentrated most of your time and effort on solving the goals of the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc4e5-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc4e5-176">See also</span></span>

- [<span data-ttu-id="bc4e5-177">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="bc4e5-177">dotnet add reference</span></span>](../tools/dotnet-add-reference.md)
- [<span data-ttu-id="bc4e5-178">dotnet test</span><span class="sxs-lookup"><span data-stu-id="bc4e5-178">dotnet test</span></span>](../tools/dotnet-test.md)
