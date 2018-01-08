---
title: "Komponententests für den C#-Code in .NET Core mit „dotnet test“ und xUnit"
description: "Erfahren Sie mehr über die Konzepte von Komponententests in C# und .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und xUnit erstellen."
author: ardalis
ms.author: wiwagn
ms.date: 11/29/2017
ms.topic: article
ms.prod: .net-core
ms.workload: dotnetcore
ms.openlocfilehash: 22f1f460ed87767768e806a85daab39f204db24f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a>Komponententests für C# in .NET Core mit „dotnet test“ und xUnit

Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen. Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/), bevor Sie beginnen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Erstellen des Quellprojekts

Öffnen eines Shell-Fensters. Erstellen Sie ein Verzeichnis namens *unit-testing-using-dotnet-test*, um die Projektmappe zu speichern.
Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappe zu erstellen. Eine Projektmappe vereinfacht die Verwaltung des Klassenbibliotheks- und des Komponententestprojekts.
Erstellen Sie im Projektmappenverzeichnis ein *PrimeService*-Verzeichnis. Die bisherige Verzeichnis- und Dateistruktur sollte folgendermaßen aussehen:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen. Benennen Sie *Class1.cs* in *PrimeService.cs* um. Erstellen Sie zunächst eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first");
        }
    }
}
```

Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-using-dotnet-test*.

Führen Sie [dotnet sln](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen:

```
dotnet sln add .\PrimeService\PrimeService.csproj
```

## <a name="creating-the-test-project"></a>Erstellen des Testprojekts

Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*. Die folgende Gliederung zeigt die Verzeichnisstruktur:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Machen Sie das *PrimeService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new xunit`](../tools/dotnet-new.md). Dieser Befehl erstellt ein Testprojekt, das xUnit als Testbibliothek verwendet. Die generierte Vorlage konfiguriert den Test Runner in der Datei *PrimeServiceTests.csproj* ähnlich wie im folgenden Code:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich. `dotnet new` hat im vorherigen Schritt xUnit und xUnit Runner hinzugefügt. Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als eine andere Abhängigkeit zum Projekt hinzu. Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.

Im Folgenden wird das endgültige Projektmappenlayout gezeigt:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

Um das Testprojekt zur Projektmappe hinzuzufügen, führen Sie den Befehl [dotnet sln](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-using-dotnet-test* aus:

```
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a>Erstellen des ersten Tests

Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen. Entfernen Sie *UnitTest1.cs* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue C#-Datei namens *PrimeService_IsPrimeShould.cs*. Fügen Sie den folgenden Code hinzu:

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
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

Das `[Fact]`-Attribut gibt eine Testmethode an, die von Test Runner ausgeführt wird. Führen Sie im Verzeichnis *PrimeService.Tests* [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen. Der xUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests. `dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.

Ihr Test schlägt fehl. Sie haben die Implementierung noch nicht erstellt. Damit dieser Test erfolgreich verläuft, schreiben Sie in der `PrimeService`-Klasse einen ganz einfachen Code. Ersetzen Sie die vorhandene Implementierung der Methode `IsPrime` durch den folgenden Code:

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first");
}
```

Führen Sie `dotnet test` im *PrimeService.Tests*-Verzeichnis erneut aus. Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus. Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt. Er ist erfolgreich.

## <a name="adding-more-features"></a>Hinzufügen weiterer Features

Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter. Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1. Sie könnten diese neuen Fälle als neue Tests mit dem Attribut `[Fact]` hinzufügen, aber das wird schnell recht mühsam. Es gibt andere xUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können:

- `[Theory]` repräsentiert eine Reihe von Tests, die zwar denselben Code ausführen, aber unterschiedliche Eingabeargumente verwenden.

- Das `[InlineData]`-Attribut gibt Werte für diese Eingaben an.

Statt neue Tests zu erstellen, wenden Sie die zwei Attribute `[Theory]` und `[InlineData]` zum Erstellen einer einzelnen Theorie in der Datei *PrimeService_IsPrimeShould.cs* an. Bei der Theorie handelt es sich um eine Methode, die mehrere Werte unter zwei als niedrigste Primzahl testet:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Wenn Sie `dotnet test` erneut ausführen, sollten bei zwei dieser Tests Fehler auftreten. Damit alle Tests erfolgreich sind, müssen Sie in der Datei *PrimeService.cs* am Anfang der Methode `IsPrime` die `if`-Klausel ändern:

```csharp
if (candidate < 2)
```

Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen. Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).

### <a name="additional-resources"></a>Zusätzliche Ressourcen

[Testen von Controllerlogik in ASP.NET Core](/aspnet/core/mvc/controllers/testing)
