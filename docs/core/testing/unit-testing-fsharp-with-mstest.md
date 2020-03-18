---
title: Komponententests für F# in .NET Core mit „dotnet test“ und MSTest
description: Erfahren Sie mehr über die Konzepte von Komponententests für F# in .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und MSTest erstellen.
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.openlocfilehash: a685ed8a56393fb6e1c1b9400f0ed4bcef15f9b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714275"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-mstest"></a>Komponententests für F#-Bibliotheken in .NET Core mit „dotnet test“ und MSTest

Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen. Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-mstest/), bevor Sie beginnen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="creating-the-source-project"></a>Erstellen des Quellprojekts

Öffnen eines Shell-Fensters. Erstellen Sie ein Verzeichnis namens *unit-testing-with-fsharp*, um die Projektmappe zu speichern.
Führen Sie in diesem neuen Verzeichnis `dotnet new sln` aus, um eine neue Projektmappe zu erstellen. Dies vereinfacht die Verwaltung des Klassenbibliotheks- und Komponententestprojekts.
Erstellen Sie im Projektmappenverzeichnis ein *MathService*-Verzeichnis. Nachfolgend wird die bisherige Verzeichnis- und Dateistruktur dargestellt:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

Machen Sie *MathService* zum aktuellen Verzeichnis, und führen Sie `dotnet new classlib -lang "F#"` aus, um das Quellprojekt zu erstellen.  Sie erstellen eine fehlerhafte Implementierung des Math-Diensts:

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-with-fsharp*. Führen Sie `dotnet sln add .\MathService\MathService.fsproj` aus, um der Projektmappe das Klassenbibliotheksprojekt hinzuzufügen.

## <a name="creating-the-test-project"></a>Erstellen des Testprojekts

Erstellen Sie als Nächstes das Verzeichnis *MathService.Tests*. Die folgende Gliederung zeigt die Verzeichnisstruktur:

```console
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

Machen Sie das *MathService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit `dotnet new mstest -lang "F#"`. Dies erstellt ein Testprojekt, das MSTest als Testframework verwendet. Die generierte Vorlage konfiguriert Test Runner in *MathServiceTests.fsproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich. `dotnet new` hat im vorherigen Schritt MSTest und MSTest Runner hinzugefügt. Fügen Sie jetzt die `MathService`-Klassenbibliothek als eine andere Abhängigkeit zum Projekt hinzu. Verwenden Sie den Befehl `dotnet add reference`:

```dotnetcli
dotnet add reference ../MathService/MathService.fsproj
```

Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) auf GitHub.

Sie verfügen über das folgende endgültige Projektmappenlayout:

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

Führen Sie `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` im Verzeichnis *unit-testing-with-fsharp* aus.

## <a name="creating-the-first-test"></a>Erstellen des ersten Tests

Sie schreiben einen fehlerhaften Test, lassen ihn bestehen und wiederholen dann den Prozess. Öffnen Sie *Tests.fs*, und fügen Sie den folgenden Code hinzu:

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

Das `[<TestClass>]`-Attribut gibt eine Klasse an, die Tests enthält. Das `[<TestMethod>]`-Attribut kennzeichnet eine Testmethode, die von Test Runner ausgeführt wird. Führen Sie *im Verzeichnis*unit-testing-with-fsharp`dotnet test` aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen. Der MSTest Test Runner verfügt über den Programmeinstiegspunkt zum Ausführen der Tests. `dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.

Diese zwei Tests geben jeweils den grundlegendsten bestandenen und fehlerhaften Test an. `My test` wurde erfolgreich und `Fail every time` fehlerhaft abgeschlossen. Erstellen Sie jetzt einen Test für die `squaresOfOdds`-Methode. Die `squaresOfOdds`-Methode gibt eine Liste der Quadrate aller ungeraden ganzzahligen Werte zurück, die Teil der Eingabesequenz sind. Anstatt zu versuchen, alle diese Funktionen gleichzeitig zu schreiben, können Sie iterativ Tests zum Überprüfen der Funktionalität erstellen. Damit jeder Test erfolgreich abgeschlossen wird, muss die erforderliche Funktionalität für die Methode erstellt werden.

Der einfachste Test, den wir schreiben können, ist das Aufrufen von `squaresOfOdds` mit allen geraden Zahlen, wobei das Ergebnis eine leere Sequenz von Ganzzahlen sein sollte.  Im Folgenden wird dieser Test vorgestellt:

```fsharp
[<TestMethod>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.AreEqual(expected, actual)
```

Beachten Sie, dass die Sequenz `expected` zu einer Liste konvertiert wurde. Die MSTest-Bibliothek basiert auf einer Vielzahl von .NET-Standardtypen. Diese Abhängigkeit bedeutet, dass Ihre öffentliche Schnittstelle und erwarteten Ergebnisse eher <xref:System.Collections.ICollection> statt <xref:System.Collections.IEnumerable> unterstützen.

Bei der Ausführung des Tests stellen Sie fest, dass der Test fehlerhaft ist. Sie haben die Implementierung noch nicht erstellt. Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `Mathservice`-Klasse:

```fsharp
let squaresOfOdds xs =
    Seq.empty<int> |> Seq.toList
```

Führen Sie im Verzeichnis *unit-testing-with-fsharp* erneut `dotnet test` aus. Der `dotnet test`-Befehl führt einen Build für das `MathService`-Projekt und anschließend für das `MathService.Tests`-Projekt aus. Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt. Er ist erfolgreich.

## <a name="completing-the-requirements"></a>Erfüllen der Anforderungen

Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter. Der nächste einfache Fall funktioniert mit einer Sequenz, deren einzige ungerade Zahl `1` lautet. Die Zahl 1 ist einfacher, da 1 das Quadrat von 1 ist. Im Folgenden wird der nächste Test vorgestellt:

```fsharp
[<TestMethod>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.AreEqual(expected, actual)
```

Die Ausführung von `dotnet test` verursacht einen Fehler beim neuen Test. Sie müssen die `squaresOfOdds`-Methode aktualisieren, um diesen neuen Test zu verarbeiten. Damit dieser Test erfolgreich durchgeführt wird, müssen Sie alle geraden Zahlen aus der Sequenz filtern. Hierzu können Sie eine kleine Filterfunktion schreiben und `Seq.filter` verwenden:

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd |> Seq.toList
```

Beachten Sie den Aufruf von `Seq.toList`. Hierdurch wird eine Liste erstellt, die die Schnittstelle <xref:System.Collections.ICollection> implementiert.

Ein weiterer Schritt ist noch notwendig: Bilden Sie das Quadrat von jeder ungeraden Zahl. Schreiben Sie zunächst einen neuen Test:

```fsharp
[<TestMethod>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.AreEqual(expected, actual)
```

Sie können den Test beheben, indem Sie für die gefilterte Sequenz einen Zuordnungsvorgang durchführen, um das Quadrat von jeder ungerade Zahl zu berechnen:

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
    |> Seq.toList
```

Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt. Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist. Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.

## <a name="see-also"></a>Weitere Informationen

- [dotnet new](../tools/dotnet-new.md)
- [dotnet sln](../tools/dotnet-sln.md)
- [dotnet add reference](../tools/dotnet-add-reference.md)
- [dotnet test](../tools/dotnet-test.md)
