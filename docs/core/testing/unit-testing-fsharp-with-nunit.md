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
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-nunit"></a>Unittests für F#-Bibliotheken in .NET Core mit „dotnet test“ und NUnit

Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen. Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-nunit/), bevor Sie beginnen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a>Voraussetzungen

- [.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) oder höhere Versionen.
- Ein Text-Editor oder Code-Editor Ihrer Wahl.

## <a name="creating-the-source-project"></a>Erstellen des Quellprojekts

Öffnen eines Shell-Fensters. Erstellen Sie ein Verzeichnis namens *unit-testing-with-fsharp*, um die Projektmappe zu speichern.
Führen Sie in diesem neuen Verzeichnis den folgenden Befehl aus, um eine neue Projektmappendatei für die Klassenbibliothek und das Testprojekt zu erstellen:

```dotnetcli
dotnet new sln
```

Erstellen Sie als Nächstes das Verzeichnis *MathService*. Die folgende Gliederung zeigt die bisherige Verzeichnis- und Dateistruktur:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

Legen Sie *MathService* als aktuelles Verzeichnis fest, und führen Sie den folgenden Befehl aus, um das Quellprojekt zu erstellen:

```dotnetcli
dotnet new classlib -lang "F#"
```

Sie erstellen eine fehlerhafte Implementierung des Math-Diensts:

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-with-fsharp*. Führen Sie den folgenden Befehl aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen:

```dotnetcli
dotnet sln add .\MathService\MathService.fsproj
```

## <a name="creating-the-test-project"></a>Erstellen des Testprojekts

Erstellen Sie als Nächstes das Verzeichnis *MathService.Tests*. Die folgende Gliederung zeigt die Verzeichnisstruktur:

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

Legen Sie das Verzeichnis *MathService.Tests* als aktuelles Verzeichnis fest, und erstellen Sie mit dem folgenden Befehl ein neues Projekt:

```dotnetcli
dotnet new nunit -lang "F#"
```

Dies erstellt ein Testprojekt, das NUnit als Testframework verwendet. Die generierte Vorlage konfiguriert Test Runner in *MathServiceTests.fsproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich. Mithilfe von `dotnet new` wurden im vorhergehenden Schritt NUnit und der NUnit-Testadapter hinzugefügt. Fügen Sie jetzt die `MathService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu. Verwenden Sie den Befehl `dotnet add reference`:

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
        MathService.Tests.fsproj
```

Führen Sie im Verzeichnis *unit-testing-with-fsharp* den folgenden Befehl aus:

```dotnetcli
dotnet sln add .\MathService.Tests\MathService.Tests.fsproj
```

## <a name="creating-the-first-test"></a>Erstellen des ersten Tests

Sie schreiben einen fehlerhaften Test, lassen ihn bestehen und wiederholen dann den Prozess. Öffnen Sie *UnitTest1.fs*, und fügen Sie den folgenden Code hinzu:

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

Das `[<TestFixture>]`-Attribut gibt eine Klasse an, die Tests enthält. Das `[<Test>]`-Attribut kennzeichnet eine Testmethode, die von Test Runner ausgeführt wird. Führen Sie `dotnet test` im Verzeichnis *unit-testing-with-fsharp* aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen. Der NUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests. `dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.

Diese zwei Tests geben jeweils den grundlegendsten bestandenen und fehlerhaften Test an. `My test` wurde erfolgreich und `Fail every time` fehlerhaft abgeschlossen. Erstellen Sie jetzt einen Test für die `squaresOfOdds`-Methode. Die `squaresOfOdds`-Methode gibt eine Sequenz der Quadrate aller ungeraden ganzzahligen Werte zurück, die Teil der Eingabesequenz sind. Anstatt zu versuchen, alle diese Funktionen gleichzeitig zu schreiben, können Sie iterativ Tests zum Überprüfen der Funktionalität erstellen. Damit jeder Test erfolgreich abgeschlossen wird, muss die erforderliche Funktionalität für die Methode erstellt werden.

Der einfachste Test, den wir schreiben können, ist das Aufrufen von `squaresOfOdds` mit allen geraden Zahlen, wobei das Ergebnis eine leere Sequenz von Ganzzahlen sein sollte.  Im Folgenden wird dieser Test vorgestellt:

```fsharp
[<Test>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

Beachten Sie, dass die Sequenz `expected` zu einer Liste konvertiert wurde. Das NUnit-Framework basiert auf einer Vielzahl von .NET-Standardtypen. Diese Abhängigkeit bedeutet, dass Ihre öffentliche Schnittstelle und erwarteten Ergebnisse eher <xref:System.Collections.ICollection> statt <xref:System.Collections.IEnumerable> unterstützen.

Bei der Ausführung des Tests stellen Sie fest, dass der Test fehlerhaft ist. Sie haben die Implementierung noch nicht erstellt. Sorgen Sie dafür, dass dieser Test erfolgreich verläuft, indem Sie in der *Library.fs*-Klasse in Ihrem MathService-Projekt sehr einfachen Code schreiben, der funktioniert:

```fsharp
let squaresOfOdds xs =
    Seq.empty<int>
```

Führen Sie im Verzeichnis *unit-testing-with-fsharp* erneut `dotnet test` aus. Der `dotnet test`-Befehl führt einen Build für das `MathService`-Projekt und anschließend für das `MathService.Tests`-Projekt aus. Nachdem beide Projekte erstellt wurden, führen Sie Ihre Tests aus. Zwei Tests verlaufen jetzt erfolgreich.

## <a name="completing-the-requirements"></a>Erfüllen der Anforderungen

Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter. Der nächste einfache Fall funktioniert mit einer Sequenz, deren einzige ungerade Zahl `1` lautet. Die Zahl 1 ist einfacher, da 1 das Quadrat von 1 ist. Im Folgenden wird der nächste Test vorgestellt:

```fsharp
[<Test>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

Die Ausführung von `dotnet test` verursacht einen Fehler beim neuen Test. Sie müssen die `squaresOfOdds`-Methode aktualisieren, um diesen neuen Test zu verarbeiten. Damit dieser Test erfolgreich durchgeführt wird, müssen Sie alle geraden Zahlen aus der Sequenz filtern. Hierzu können Sie eine kleine Filterfunktion schreiben und `Seq.filter` verwenden:

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

Beachten Sie den Aufruf von `Seq.toList`. Hierdurch wird eine Liste erstellt, die die Schnittstelle <xref:System.Collections.ICollection> implementiert.

Ein weiterer Schritt ist noch notwendig: Bilden Sie das Quadrat von jeder ungeraden Zahl. Schreiben Sie zunächst einen neuen Test:

```fsharp
[<Test>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.That(actual, Is.EqualTo(expected))
```

Sie können den Test beheben, indem Sie für die gefilterte Sequenz einen Zuordnungsvorgang durchführen, um das Quadrat von jeder ungerade Zahl zu berechnen:

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
```

Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt. Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist. Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.

## <a name="see-also"></a>Siehe auch

- [dotnet add reference](../tools/dotnet-add-reference.md)
- [dotnet test](../tools/dotnet-test.md)
