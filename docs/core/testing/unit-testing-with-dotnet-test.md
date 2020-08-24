---
title: Komponententests für den C#-Code in .NET Core mit „dotnet test“ und xUnit
description: Erfahren Sie mehr über die Konzepte von Komponententests in C# und .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und xUnit erstellen.
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: feff4cabbd10064ef4acca12d4f960f2a40a2b12
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656383"
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a>Komponententests für C# in .NET Core mit „dotnet test“ und xUnit

In diesem Tutorial wird gezeigt, wie Sie eine Lösung erstellen, die ein Komponententest- und ein Quellcodeprojekt enthält. Um dem Tutorial mit einer vorkonfigurierten Projektmappe zu folgen, können Sie sich [den Beispielcode ansehen oder ihn herunterladen](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/). Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#view-and-download-samples).

## <a name="create-the-solution"></a>Erstellen der Projektmappe

In diesem Abschnitt wird eine Projektmappe erstellt, die das Quell- und Testprojekt enthält. Die vervollständigte Projektmappe hat die folgende Verzeichnisstruktur:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        PrimeService.cs
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService_IsPrimeShould.cs
        PrimeServiceTests.csproj
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
  dotnet new classlib -o PrimeService
  ```

   Der Befehl [`dotnet new classlib`](../tools/dotnet-new.md) erstellt im Ordner *PrimeService* ein neues Klassenbibliotheksprojekt. Die neue Klassenbibliothek enthält den zu testenden Code.
* Benennen Sie *Class1.cs* in *PrimeService.cs* um.
* Ersetzen Sie den Code in *PrimeService.cs* durch folgenden Code:
  
  ```csharp
  using System;

  namespace Prime.Services
  {
      public class PrimeService
      {
          public bool IsPrime(int candidate)
          {
              throw new NotImplementedException("Not implemented.");
          }
      }
  }
  ```

* Der vorangehende Code:
  * Löst eine <xref:System.NotImplementedException> mit der Meldung aus, dass die Implementierung fehlt.
  * Wird später im Tutorial aktualisiert.

<!-- preceding code shows an english bias. Message makes no sense outside english -->

* Führen Sie im Verzeichnis *unit-testing-using-dotnet-test* den folgenden Befehl aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen:

  ```dotnetcli
  dotnet sln add ./PrimeService/PrimeService.csproj
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
  dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
  ```

* Fügen Sie die Klassenbibliothek `PrimeService` dem Projekt *PrimeService.Tests* als Abhängigkeit hinzu:

  ```dotnetcli
  dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj  
  ```

<a name="create-test-cmd"></a>

### <a name="commands-to-create-the-solution"></a>Befehle zum Erstellen der Projektmappe

In diesem Abschnitt sind alle Befehle des vorherigen Abschnitts zusammengefasst. Überspringen Sie diesen Abschnitt, wenn Sie die Schritte im vorherigen Abschnitt ausgeführt haben.

Mit den folgenden Befehlen wird die Testprojektmappe auf einem Windows-Computer erstellt. Ändern Sie unter macOS und UNIX den Befehl `ren` in die Betriebssystemversion von `ren`, um eine Datei umzubenennen:

```dotnetcli
dotnet new sln -o unit-testing-using-dotnet-test
cd unit-testing-using-dotnet-test
dotnet new classlib -o PrimeService
ren .\PrimeService\Class1.cs PrimeService.cs
dotnet sln add ./PrimeService/PrimeService.csproj
dotnet new xunit -o PrimeService.Tests
dotnet add ./PrimeService.Tests/PrimeService.Tests.csproj reference ./PrimeService/PrimeService.csproj
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

Befolgen Sie die Anweisungen unter „Ersetzen Sie den Code in *PrimeService.cs* durch folgenden Code“ im vorherigen Abschnitt.

## <a name="create-a-test"></a>Erstellen eines Tests

Ein beliebter Ansatz bei der testgesteuerten Entwicklung ist das Schreiben eines Tests vor Implementierung des Zielcodes. In diesem Tutorial wird der Ansatz der testgesteuerten Entwicklung befolgt. Die `IsPrime`-Methode ist aufrufbar, aber nicht implementiert. Ein Testaufruf von `IsPrime` schlägt fehl. Bei der testgesteuerten Entwicklung wird ein Test geschrieben, der bekanntermaßen fehlschlägt. Der Zielcode wird aktualisiert, damit der Test bestanden wird. Sie wiederholen diesen Ansatz kontinuierlich, schreiben einen nicht erfolgreichen Test und aktualisieren dann den Zielcode so, dass er bestanden wird.

Aktualisieren Sie das Projekt *PrimeService.Tests*:

* Löschen Sie *PrimeService.Tests/UnitTest1.cs*.
* Erstellen Sie die Datei *PrimeService.Tests/PrimeService_IsPrimeShould.cs*.
* Ersetzen Sie den Code in *PrimeService_IsPrimeShould.cs* durch folgenden Code:

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

Das `[Fact]`-Attribut deklariert eine Testmethode, die vom Test Runner ausgeführt wird. Führen Sie `dotnet test` im Ordner *PrimeService.Tests* aus. Der Befehl [dotnet test](../tools/dotnet-test.md) erstellt beide Projekte und führt die Tests aus. Der Test Runner für xUnit enthält den Programmeinstiegspunkt zum Ausführen der Tests. `dotnet test` startet den Test Runner mithilfe des Komponententestprojekts.

Der Test schlägt fehl, da `IsPrime` nicht implementiert wurde. Schreiben Sie bei Befolgen des Ansatzes zur testgesteuerten Entwicklung nur so viel Code, dass dieser Test bestanden wird. Aktualisieren Sie `IsPrime` mit folgendem Code:

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

Führen Sie `dotnet test` aus. Der Test wurde erfolgreich ausgeführt.

### <a name="add-more-tests"></a>Hinzufügen weiterer Tests

Fügen Sie Primzahlentests für 0 und-1 hinzu. Sie können den vorangehenden Test kopieren und den folgenden Code so ändern, dass 0 und-1 verwendet werden:

```csharp
var result = _primeService.IsPrime(1);

Assert.False(result, "1 should not be prime");
```

Das Kopieren von Testcode, wenn sich nur ein Parameter ändert, führt zu Codeduplizierung und Testüberfrachtung. Die folgenden xUnit-Attribute ermöglichen das Schreiben einer Sammlung ähnlicher Tests:

- `[Theory]` repräsentiert eine Reihe von Tests, die zwar denselben Code ausführen, aber unterschiedliche Eingabeargumente verwenden.
- Das `[InlineData]`-Attribut gibt Werte für diese Eingaben an.

Anstatt neue Tests zu erstellen, wenden Sie die vorhergehenden xUnit-Attribute an, um eine einzelne Theorie zu erstellen. Ersetzen Sie den folgenden Code:

```csharp
[Fact]
public void IsPrime_InputIs1_ReturnFalse()
{
    var result = _primeService.IsPrime(1);

    Assert.False(result, "1 should not be prime");
}
```

durch den folgenden Code:

[!code-csharp[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-using-dotnet-test/csharp/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Im vorangehenden Code ermöglichen `[Theory]` und `[InlineData]` das Testen mehrerer Werte, die kleiner als 2 sind. 2 ist die kleinste Primzahl.

Führen Sie `dotnet test` aus. Zwei dieser Tests schlagen fehl. Aktualisieren Sie die `IsPrime`-Methode mit folgendem Code, damit alle Tests bestanden werden:

```csharp
public bool IsPrime(int candidate)
{
    if (candidate < 2)
    {
        return false;
    }
    throw new NotImplementedException("Not fully implemented.");
}
```

Fügen Sie unter Befolgen des Ansatzes zur testgesteuerten Entwicklung weitere nicht erfolgreiche Tests hinzu, und aktualisieren Sie anschließend den Zielcode. Sehen Sie sich die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs) an.

Die vervollständigte `IsPrime`-Methode ist kein effizienter Algorithmus für den Primzahltest.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- [xUnit.net official site (Offizielle xUnit-Website)](https://xunit.net)
- [Testen von Controllerlogik in ASP.NET Core](/aspnet/core/mvc/controllers/testing)
- [`dotnet add reference`](../tools/dotnet-add-reference.md)
