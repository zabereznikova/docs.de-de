---
title: Komponententests für Visual Basic in .NET Core mit „dotnet test“ und xUnit
description: Erfahren Sie mehr über die Konzepte von Komponententests in .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Visual Basic-Beispielprojektmappe mithilfe von „dotnet test“ und xUnit erstellen.
author: billwagner
ms.author: wiwagn
ms.date: 05/18/2020
ms.openlocfilehash: ed1291a980f9a39284525877bab8d0a93389fbd0
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702961"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-xunit"></a>Komponententests für Visual Basic .NET Core-Bibliotheken mithilfe von „dotnet test“ und xUnit

In diesem Tutorial wird gezeigt, wie Sie eine Lösung erstellen, die ein Komponententest- und ein Bibliotheksprojekt enthält. Um dem Tutorial mit einer vorkonfigurierten Projektmappe zu folgen, können Sie sich [den Beispielcode ansehen oder ihn herunterladen](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/). Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="create-the-solution"></a>Erstellen der Projektmappe

In diesem Abschnitt wird eine Projektmappe erstellt, die das Quell- und Testprojekt enthält. Die vervollständigte Projektmappe hat die folgende Verzeichnisstruktur:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        PrimeService.vb
        PrimeService.vbproj
    /PrimeService.Tests
        PrimeService_IsPrimeShould.vb
        PrimeServiceTests.vbproj
```

In den folgenden Anweisungen werden die Schritte zur Erstellung der Testprojektmappe beschrieben. Anweisungen zum Erstellen der Testprojektmappe in einem Schritt finden Sie unter [Befehle zum Erstellen einer Testprojektmappe](#create-test-cmd).

* Öffnen eines Shell-Fensters.
* Führen Sie den folgenden Befehl aus:

  ```dotnetcli
  dotnet new sln -o unit-testing-using-dotnet-test
  ```

  Der Befehl [`dotnet new sln`](../tools/dotnet-new.md) erstellt im Verzeichnis *unit-testing-using-dotnet-test* eine neue Projektmappe.
* Ändern Sie das Verzeichnis in *unit-testing-using-dotnet-test*.
* Führen Sie den folgenden Befehl aus:

  ```dotnetcli
  dotnet new classlib -o PrimeService --lang VB
  ```

   Der Befehl [`dotnet new classlib`](../tools/dotnet-new.md) erstellt im Ordner *PrimeService* ein neues Klassenbibliotheksprojekt. Die neue Klassenbibliothek enthält den zu testenden Code.
* Benennen Sie *Class1.vb* in *PrimeService.vb* um.
* Ersetzen Sie den Code in *PrimeService.vb* durch folgenden Code:
  
  ```vb
  Imports System
  
  Namespace Prime.Services
      Public Class PrimeService
          Public Function IsPrime(candidate As Integer) As Boolean
              Throw New NotImplementedException("Not implemented.")
          End Function
      End Class
  End Namespace
  ```

* Der vorangehende Code:
  * Löst eine <xref:System.NotImplementedException> mit der Meldung aus, dass die Implementierung fehlt.
  * Wird später im Tutorial aktualisiert.

<!-- preceding code shows an english bias. Message makes no sense outside english -->

* Führen Sie im Verzeichnis *unit-testing-using-dotnet-test* den folgenden Befehl aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen:

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.vbproj
  ```

* Erstellen Sie das Projekt *PrimeService.Tests*, indem Sie den folgenden Befehl ausführen:

  ```dotnetcli
  dotnet new xunit -o PrimeService.Tests
  ```

* Für den obigen Befehl gilt Folgendes:
  * Erstellt das Projekt *PrimeService.Tests* im Verzeichnis *PrimeService.Tests*. Das Testprojekt verwendet [xUnit](https://xunit.net/) als Testbibliothek.
  * Konfiguriert den Test Runner, indem die folgenden `<PackageReference />`-Elemente zur Projektdatei hinzugefügt werden:
    * Microsoft.NET.Test.Sdk
    * xunit
    * xunit.runner.visualstudio

* Fügen Sie das Testprojekt zur Projektmappendatei hinzu, indem Sie den folgenden Befehl ausführen:

  ```dotnetcli
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.vbproj
  ```

* Fügen Sie die Klassenbibliothek `PrimeService` dem Projekt *PrimeService.Tests* als Abhängigkeit hinzu:

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.vbproj reference ./PrimeService/PrimeService.vbproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a>Befehle zum Erstellen der Projektmappe

In diesem Abschnitt sind alle Befehle des vorherigen Abschnitts zusammengefasst. Überspringen Sie diesen Abschnitt, wenn Sie die Schritte im vorherigen Abschnitt ausgeführt haben.

Mit den folgenden Befehlen wird die Testprojektmappe auf einem Windows-Computer erstellt. Ändern Sie unter macOS und UNIX den Befehl `ren` in die Betriebssystemversion von `ren`, um eine Datei umzubenennen:

```dotnetcli
dotnet new sln -o unit-testing-using-dotnet-test
cd unit-testing-using-dotnet-test
dotnet new classlib -o PrimeService
ren .\PrimeService\Class1.vb PrimeService.vb
dotnet sln add ./PrimeService/PrimeService.vbproj
dotnet new xunit -o PrimeService.Tests
dotnet add ./PrimeService.Tests/PrimeService.Tests.vbproj reference ./PrimeService/PrimeService.vbproj
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.vbproj
```

Befolgen Sie die Anweisungen unter „Ersetzen Sie den Code in *PrimeService.vb* durch folgenden Code“ im vorherigen Abschnitt.

## <a name="create-a-test"></a>Erstellen eines Tests

Ein beliebter Ansatz bei der testgesteuerten Entwicklung ist das Schreiben eines Tests vor Implementierung des Zielcodes. In diesem Tutorial wird der Ansatz der testgesteuerten Entwicklung befolgt. Die `IsPrime`-Methode ist aufrufbar, aber nicht implementiert. Ein Testaufruf von `IsPrime` schlägt fehl. Bei der testgesteuerten Entwicklung wird ein Test geschrieben, der bekanntermaßen fehlschlägt. Der Zielcode wird aktualisiert, damit der Test bestanden wird. Sie wiederholen diesen Ansatz kontinuierlich, schreiben einen nicht erfolgreichen Test und aktualisieren dann den Zielcode so, dass er bestanden wird.

Aktualisieren Sie das Projekt *PrimeService.Tests*:

* Löschen Sie *PrimeService.Tests/UnitTest1.vb*.
* Erstellen Sie die Datei *PrimeService.Tests/PrimeService_IsPrimeShould.vb*.
* Ersetzen Sie den Code in *PrimeService_IsPrimeShould.vb* durch folgenden Code:

```vb
Imports Xunit

Namespace PrimeService.Tests
    Public Class PrimeService_IsPrimeShould
        Private ReadOnly _primeService As Prime.Services.PrimeService

        Public Sub New()
            _primeService = New Prime.Services.PrimeService()
        End Sub


        <Fact>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

Das `[Fact]`-Attribut deklariert eine Testmethode, die vom Test Runner ausgeführt wird. Führen Sie `dotnet test` im Ordner *PrimeService.Tests* aus. Der Befehl [dotnet test](../tools/dotnet-test.md) erstellt beide Projekte und führt die Tests aus. Der Test Runner für xUnit enthält den Programmeinstiegspunkt zum Ausführen der Tests. `dotnet test` startet den Test Runner mithilfe des Komponententestprojekts.

Der Test schlägt fehl, da `IsPrime` nicht implementiert wurde. Schreiben Sie bei Befolgen des Ansatzes zur testgesteuerten Entwicklung nur so viel Code, dass dieser Test bestanden wird. Aktualisieren Sie `IsPrime` mit folgendem Code:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Not implemented.")
End Function
```

Führen Sie aus `dotnet test`. Der Test wurde erfolgreich ausgeführt.

### <a name="add-more-tests"></a>Hinzufügen weiterer Tests

Fügen Sie Primzahlentests für 0 und-1 hinzu. Sie können den vorangehenden Test kopieren und den folgenden Code so ändern, dass 0 und-1 verwendet werden:

```vb
Dim result As Boolean = _primeService.IsPrime(1)

Assert.False(result, "1 should not be prime")
```

Das Kopieren von Testcode, wenn sich nur ein Parameter ändert, führt zu Codeduplizierung und Testüberfrachtung. Die folgenden xUnit-Attribute ermöglichen das Schreiben einer Sammlung ähnlicher Tests:

- `[Theory]` repräsentiert eine Reihe von Tests, die zwar denselben Code ausführen, aber unterschiedliche Eingabeargumente verwenden.
- Das `[InlineData]`-Attribut gibt Werte für diese Eingaben an.

Anstatt neue Tests zu erstellen, wenden Sie die vorhergehenden xUnit-Attribute an, um eine einzelne Theorie zu erstellen. Ersetzen Sie den folgenden Code:

```vb
<Fact>
Sub IsPrime_InputIs1_ReturnFalse()
    Dim result As Boolean = _primeService.IsPrime(1)

    Assert.False(result, "1 should not be prime")
End Sub
```

durch den folgenden Code:

```vb
<Theory>
<InlineData(-1)>
<InlineData(0)>
<InlineData(1)>
Sub IsPrime_ValuesLessThan2_ReturnFalse(ByVal value As Integer)
    Dim result As Boolean = _primeService.IsPrime(value)

    Assert.False(result, $"{value} should not be prime")
End Sub
```

Im vorangehenden Code ermöglichen `[Theory]` und `[InlineData]` das Testen mehrerer Werte, die kleiner als 2 sind. 2 ist die kleinste Primzahl.

Führen Sie `dotnet test` aus. Zwei dieser Tests schlagen fehl. Aktualisieren Sie die `IsPrime`-Methode mit folgendem Code, damit alle Tests bestanden werden:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate < 2 Then
        Return False
    End If
    Throw New NotImplementedException("Not fully implemented.")
End Function
```

Fügen Sie unter Befolgen des Ansatzes zur testgesteuerten Entwicklung weitere nicht erfolgreiche Tests hinzu, und aktualisieren Sie anschließend den Zielcode. Sehen Sie sich die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.vb) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.vb) an.

Die vervollständigte `IsPrime`-Methode ist kein effizienter Algorithmus für den Primzahltest.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- [xUnit.net official site (Offizielle xUnit-Website)](https://xunit.net/)
- [Testen von Controllerlogik in ASP.NET Core](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
