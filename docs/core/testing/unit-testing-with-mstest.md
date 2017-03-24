---
title: Verwenden von MSTest mit .NET Core | Microsoft-Dokumentation
description: Verwenden von MSTest mit .NET Core
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 02/10/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 4ffc7dd4e11820a3c50ca83847a7ab418bf2faf3
ms.lasthandoff: 03/07/2017

---

# <a name="unit-testing-with-mstest-and-net-core"></a>Unittests mit MSTest und .NET Core

## <a name="creating-the-projects"></a>Erstellen der Projekte

Unter [Entwickeln von Bibliotheken mit plattformübergreifenden Tools](../tutorials/libraries.md) finden Sie Informationen zum Organisieren von Projektmappen für mehrere Projekte sowohl für die Quelle als auch für die Tests. In diesem Artikel werden diese Konventionen befolgt. Die endgültige Projektstruktur wird etwa wie folgt aussehen:

```
/unit-testing-using-mstest
|__/PrimeService
   |__Source Files
   |__PrimeService.csproj
|__/PrimeService.Tests
   |__Test Files
   |__PrimeService.csproj
```

### <a name="creating-the-source-project"></a>Erstellen des Quellprojekts

Öffnen eines Shell-Fensters. Starten Sie im Verzeichnis *unit-testing-using-mstest*, und erstellen Sie das Verzeichnis *PrimeService*.
Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie `dotnet new classlib` aus, um das Quellprojekt zu erstellen.

Benennen Sie *Class1.cs* in *PrimeService.cs*. Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:

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

Als Nächstes wechseln Sie wieder in das *unit-testing-using-mstest*-Verzeichnis und erstellen das *PrimeServices.Tests*-Verzeichnis.
Stellen Sie das *PrimeService.Tests*-Verzeichnis im aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit `dotnet new mstest`. Dies erstellt ein Testprojekt, das MStest als Testbibliothek verwendet. 

Die generierte Vorlage hat das Testprogramm in der Datei *PrimeServiceTests.csproj* konfiguriert:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-preview-20170123-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.10-rc2" />
  <PackageReference Include="MSTest.TestFramework" Version="1.0.8-rc2" />
</ItemGroup>
```

Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.
`dotnet new` fügte MSTest-SDK, MSTest-Testframework und MSTest-Runner hinzu. Sie müssen das PrimeService-Paket als weitere Abhängigkeit zum Projekt hinzufügen. Verwenden Sie hierzu die CLI `dotnet`:

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Sie können die *PrimeService.Tests.csproj*-Datei auch manuell bearbeiten.
Fügen Sie direkt unter dem ersten `<ItemGroup>`-Knoten einen weiteren `<ItemGroup>`-Knoten mit einem Verweis auf das Bibliotheksprojekt hinzu:

```xml
  <ItemGroup>
    <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
  </ItemGroup>
```

Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.

Nachdem Sie diese anfängliche Struktur eingerichtet haben, können Sie den ersten Test schreiben.
Sobald Sie diesen ersten Unittest überprüft haben, ist alles konfiguriert und sollte beim Hinzufügen von Features und Tests reibungslos funktionieren.

## <a name="creating-the-first-test"></a>Erstellen des ersten Tests

Vor dem Erstellen der Bibliothek oder Tests müssen Sie `dotnet restore` in den *PrimeService*- und *PrimeService.Tests*-Verzeichnissen ausführen. Dieser Befehl stellt alle erforderlichen NuGet-Pakete für jedes Projekt wieder her.

Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und abschließend den Vorgang wiederholen. Schreiben wir nun also diesen fehlerhaften Test. Entfernen Sie *UnitTest1.cs* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue C#-Datei namens *PrimeService_IsPrimeShould.cs* mit folgendem Inhalt:

```cs
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;
        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, $"1 should not be prime");
        }
    }
}
```

Das `[TestClass]`-Attribut gibt eine Klasse an, die Unittests enthalten. Das Attribut `[TestMethod]` kennzeichnet eine Methode als einzelnen Test. 

Speichern Sie diese Datei, und führen Sie `dotnet build` aus, um das Testprojekt zu erstellen.
Wenn Sie das Projekt `PrimeService` noch nicht erstellt haben, wird das vom Buildsystem erkannt. Das Buildsystem erstellt das Projekt, da es sich um eine Abhängigkeit dieses Testprojekts handelt.

Führen Sie nun `dotnet test` aus, um die Tests über die Konsole auszuführen.
Der MSTest Test Runner verfügt über den Programmeinstiegspunkt zum Ausführen der Tests über die Konsole. `dotnet test` startet den Test Runner, und stellt ein Befehlszeilenargument für den Test Runner bereit, das die Assembly mit Ihren Tests angibt.

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

Führen Sie `dotnet test` im *PrimeService.Tests*-Verzeichnis erneut aus. Der `dotnet test`-Befehl wird zuerst einen Build für das Projekt Prime.Services und dann für das Projekt PrimeService.Tests ausführen. Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt. Er ist erfolgreich.

## <a name="adding-more-features"></a>Hinzufügen weiterer Features

Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.
Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1. Sie könnten diese neuen Tests mit dem Attribut `[TestMethod]` hinzufügen, aber das wird schnell recht mühsam. Es gibt andere MSTest-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.  `DataTestMethod` stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.
Sie können das Attribut `[DataRow]` verwenden, um Werte für diese Eingaben anzugeben. 
 
 Statt neue Tests zu erstellen, nutzen Sie diese beiden Attribute zum Erstellen von Einzeldatentestmethoden, die einige Werte kleiner als 2 (die kleinste Primzahl) testen:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs#Sample_TestCode "Erste Tests")]

Führen Sie `dotnet test` aus. Sie werden feststellen, dass zwei dieser Tests fehlschlagen.
Durch Ändern des Diensts können Sie dafür sorgen, dass sie erfolgreich verlaufen. Sie müssen die `if`-Klausel am Anfang der Methode ändern:

```cs
if(candidate < 2)
```

Nun verlaufen alle Tests erfolgreich.

Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen. Sie werden die [endgültige Version der Tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs) schnell erstellt haben.

Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.
Sie haben diese Projektmappe strukturiert, sodass neue Pakete und Tests problemlos hinzugefügt werden können und Sie sich auf das jeweils aktuelle Problem konzentrieren können. Die Tools werden automatisch ausgeführt.
