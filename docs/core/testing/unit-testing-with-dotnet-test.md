---
title: Komponententests in .NET Core mit dotnet test | Microsoft-Dokumentation
description: Unittests in .NET Core mit dotnet-test
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdcdb812-6f13-4f20-9e90-0c0977937142
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: cc2e823be1a3d1c0267d98c95b25126bd7d048d4
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---

# <a name="unit-testing-in-net-core-using-dotnet-test"></a>Komponententests in .NET Core mit dotnet test

Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Komponententests zu erlernen. Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/), bevor Sie beginnen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

### <a name="creating-the-source-project"></a>Erstellen des Quellprojekts

Öffnen eines Shell-Fensters. Erstellen Sie ein Verzeichnis namens *unit-testing-using-dotnet-test*, um die Projektmappe zu speichern. Erstellen Sie in diesem neuen Verzeichnis ein *PrimeService*-Verzeichnis. Nachfolgend wird die bisherige Verzeichnisstruktur dargestellt:

```
/unit-testing-using-dotnet-test
    /PrimeService
```

Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen. Benennen Sie *Class1.cs* in *PrimeService.cs* um. Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:

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

### <a name="creating-the-test-project"></a>Erstellen des Testprojekts

Wechseln Sie wieder in das *unit-testing-using-dotnet-test*-Verzeichnis, und erstellen Sie das *PrimeService.Tests*-Verzeichnis. Die Verzeichnisstruktur wird nachfolgend gezeigt:

```
/unit-testing-using-dotnet-test
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Stellen Sie das *PrimeService.Tests*-Verzeichnis als aktuelles Verzeichnis ein, und erstellen Sie ein neues Projekt mit [`dotnet new xunit`](../tools/dotnet-new.md). Dies erstellt ein Testprojekt, das xUnit als Testbibliothek verwendet. Die generierte Vorlage konfiguriert das Testprogramm in *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich. `dotnet new` hat im vorherigen Schritt xUnit und xUnit Runner hinzugefügt. Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als eine andere Abhängigkeit zum Projekt hinzu. Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Sie können stattdessen auch die *PrimeService.Tests.csproj*-Datei bearbeiten. Fügen Sie direkt unter dem ersten `<ItemGroup>`-Knoten einen weiteren `<ItemGroup>`-Knoten mit einem Verweis auf das Bibliotheksprojekt hinzu:

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.

Das endgültige Layout der Projektmappe wird unten gezeigt:

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a>Erstellen des ersten Tests

Führen Sie vor dem Erstellen der Bibliothek oder der Tests [`dotnet restore`](../tools/dotnet-restore.md) im *PrimeService.Tests*-Verzeichnis aus. Dieser Befehl stellt alle erforderlichen NuGet-Pakete für jedes Projekt wieder her.

Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen. Entfernen Sie *UnitTest1.cs* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue C#-Datei namens *PrimeService_IsPrimeShould.cs* mit folgendem Inhalt:

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

            Assert.False(result, $"1 should not be prime");
        }
    }
}
```

Das Attribut `[Fact]` kennzeichnet eine Methode als einzelnen Test. Führen Sie [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen. Der xUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests. `dotnet test` startet den Test Runner und stellt ein Befehlszeilenargument für den Test Runner bereit, das die Assembly mit Ihren Tests angibt.

Ihr Test schlägt fehl. Sie haben die Implementierung noch nicht erstellt. Schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse, damit dieser Test erfolgreich verläuft:

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

### <a name="adding-more-features"></a>Hinzufügen weiterer Features

Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter. Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1. Sie könnten diese neuen Tests mit dem Attribut `[Fact]` hinzufügen, aber das wird schnell recht mühsam. Es gibt andere xUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.  Ein `[Theory]`-Attribut stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden. Sie können das Attribut `[InlineData]` verwenden, um Werte für diese Eingaben anzugeben. 
 
Statt neue Tests zu erstellen, nutzen Sie diese beiden Attribute zum Erstellen einer einzigen Theorie. Damit werden mehrere Werte kleiner als 2 (die kleinste Primzahl) getestet:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl. Sie müssen die `if`-Klausel am Anfang der Methode ändern, damit alle Tests erfolgreich sind:

```csharp
if (candidate < 2)
```

Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen. Am Ende verfügen Sie über die [endgültige Version der Tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).

Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt. Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests nahtlos funktioniert, und Sie können sich in Sachen Zeit und Aufwand auf die Lösung der Ziele der Anwendung konzentrieren.

