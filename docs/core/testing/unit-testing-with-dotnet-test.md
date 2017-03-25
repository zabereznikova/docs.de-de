---
title: Unittests in .NET Core mit dotnet test | Microsoft-Dokumentation
description: Unittests in .NET Core mit dotnet-test
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 002/02/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdcdb812-6f13-4f20-9e90-0c0977937142
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: cd860241f5f20b6a4f1ccfec60e0c9cd5079152a
ms.lasthandoff: 03/07/2017

---

# <a name="unit-testing-in-net-core-using-dotnet-test"></a>Unittests in .NET Core mit dotnet-test

Von [Steve Smith](http://ardalis.com) und [Bill Wagner](https://github.com/BillWagner)

[Anzeigen oder Herunterladen von Beispielcode](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test)

## <a name="creating-the-projects"></a>Erstellen der Projekte

Unter [Entwickeln von Bibliotheken mit plattformübergreifenden Tools](../tutorials/libraries.md) finden Sie Informationen zum Organisieren von Projektmappen für mehrere Projekte sowohl für die Quelle als auch für die Tests. In diesem Artikel werden diese Konventionen befolgt. Die endgültige Projektstruktur wird etwa wie folgt aussehen:

```
/unit-testing-using-dotnet-test
|__/PrimeService
   |__Source Files
   |__PrimeService.csproj
|__/PrimeService.Tests
   |__Test Files
   |__PrimeService.csproj
```

### <a name="creating-the-source-project"></a>Erstellen des Quellprojekts

Erstellen Sie anschließend im Verzeichnis `unit-testing-using-dotnet-test` das Verzeichnis `PrimeService`.
Wechseln Sie in dieses Verzeichnis, und führen Sie `dotnet new classib` aus, um das Quellprojekt zu erstellen.


Benennen Sie `Class1.cs` in `PrimeService.cs` um. Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:

```cs
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

Kehren Sie als Nächstes in das Verzeichnis „unit-testing-using-dotnet-test“ zurück, und erstellen Sie das `PrimeServices.Tests`-Verzeichnis.
Wechseln Sie in das Verzeichnis `PrimeService.Tests`, und erstellen Sie mithilfe von `dotnet new xunit` ein neues Projekt. `dotnet xunit` erstellt ein Testprojekt, das xUnit als Testbibliothek verwendet. 

Die generierte Vorlage hat das Testprogramm in PrimeServiceTests.csproj konfiguriert:

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-preview-20170125-04" />
    <PackageReference Include="xunit" Version="2.2.0-beta5-build3474" />
    <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-beta5-build1225" />
  </ItemGroup>
```

Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.
`dotnet new` hat xUnit und xUnit Runner hinzugefügt. Sie müssen das PrimeService-Paket als weitere Abhängigkeit zum Projekt hinzufügen. Verwenden Sie hierzu die CLI `dotnet`:

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Sie können die `PrimeService.Tests.csproj`-Datei auch direkt bearbeiten.
Fügen Sie direkt unter dem ersten `<ItemGroup>`-Knoten einen weiteren `<ItemGroup>`-Knoten mit einem Verweis auf das Bibliotheksprojekt hinzu:

```xml
  <ItemGroup>
    <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
  </ItemGroup>
```

Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.

Nachdem Sie diese anfängliche Struktur eingerichtet haben, können Sie den ersten Test schreiben.
Sobald Sie diesen ersten Unittest überprüft haben, ist alles konfiguriert und sollte beim Hinzufügen von Features und Tests reibungslos funktionieren.

## <a name="creating-the-first-test"></a>Erstellen des ersten Tests

Vor dem Erstellen der Bibliothek oder Tests müssen Sie `dotnet restore` in den `PrimeService`- und `PrimeService.Tests`-Verzeichnissen ausführen. Dieser Befehl stellt alle erforderlichen NuGet-Pakete für jedes Projekt wieder her.

Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und abschließend den Vorgang wiederholen. Schreiben wir nun also diesen fehlerhaften Test. Entfernen Sie `UnitTest1.cs` aus dem Verzeichnis `PrimeService.Tests`, und erstellen Sie eine neue C#-Datei namens `PrimeService_IsPrimeShould.cs` mit folgendem Inhalt:

```cs
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

Das Attribut `[Fact]` kennzeichnet eine Methode als einzelnen Test. 

Speichern Sie diese Datei, und führen Sie `dotnet build` aus, um das Testprojekt zu erstellen.
Wenn Sie das Projekt `PrimeService` noch nicht erstellt haben, wird das vom Buildsystem erkannt. Das Buildsystem erstellt das Projekt, da es sich um eine Abhängigkeit dieses Testprojekts handelt.

Führen Sie nun `dotnet test` aus, um die Tests über die Konsole auszuführen.
Der xUnit Test Runner verfügt über den Programmeinstiegspunkt zum Ausführen Ihrer Tests über die Konsole. `dotnet test` startet den Test Runner, und stellt ein Befehlszeilenargument für den Test Runner bereit, das die Assembly mit Ihren Tests angibt.

Ihr Test schlägt fehl. Sie haben die Implementierung noch nicht erstellt.
Schreiben Sie einen ganz einfachen Code, damit dieser Test erfolgreich verläuft:

```cs
public bool IsPrime(int candidate) 
{
    if(candidate == 1) 
    { 
        return false;
    } 
    throw new NotImplementedException("Please create a test first");
} 
```

### <a name="adding-more-features"></a>Hinzufügen weiterer Features

Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.
Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1. Sie könnten diese neuen Tests mit dem Attribut `[Fact]` hinzufügen, aber das wird schnell recht mühsam. Es gibt andere xUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.  `Theory` stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.
Sie können das Attribut `[InlineData]` verwenden, um Werte für diese Eingaben anzugeben. 
 
 Statt neue Tests zu erstellen, nutzen Sie diese beiden Attribute zum Erstellen von „theory“. Damit werden einige Werte kleiner als 2 (die kleinste Primzahl) getestet:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs#Sample_TestCode "Erste Tests ")]
```

Run `dotnet test` and you'll see that two of these tests fail.
You can make them pass by changing the service. You need to change
the `if` clause at the beginning of the method:

```cs
if(candidate < 2)
```

Nun verlaufen alle Tests erfolgreich.

Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen. Sie werden die [endgültige Version der Tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/src/PrimeService/PrimeService.cs) schnell erstellt haben.

Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.
Sie haben diese Projektmappe strukturiert, sodass neue Pakete und Tests problemlos hinzugefügt werden können und Sie sich auf das jeweils aktuelle Problem konzentrieren können. Die Tools werden automatisch ausgeführt.

