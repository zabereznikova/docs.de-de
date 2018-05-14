---
title: Unittests für C# mit NUnit und .NET Core
description: Erfahren Sie mehr über die Konzepte von Unittests in C# und .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und NUnit erstellen.
author: rprouse
ms.date: 12/01/2017
ms.openlocfilehash: 8cf9e28353dd4dad6143f0dc3f8c0a8245715ea2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a>Unittests für C# mit NUnit und .NET Core

Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen. Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/), bevor Sie beginnen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Erstellen des Quellprojekts

Öffnen eines Shell-Fensters. Erstellen Sie ein Verzeichnis namens *unit-testing-using-nunit*, um die Projektmappe zu speichern. Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappendatei für die Klassenbibliothek und das Testprojekt zu erstellen. Erstellen Sie als Nächstes ein *PrimeService*-Verzeichnis. Die folgende Gliederung zeigt die Verzeichnis- und Dateistruktur:

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
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

Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-using-nunit*. Führen Sie [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen.

## <a name="install-the-nunit-project-template"></a>Installieren der NUnit-Projektvorlage

Vor dem Erstellen eines Testprojekts müssen Sie die NUnit-Projektvorlage installieren. Dies muss auf jedem Entwicklercomputer, auf dem Sie neue NUnit-Projekte erstellen, nur einmal erfolgen. Führen Sie [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md) aus, um die NUnit-Vorlagen zu installieren.

```
dotnet new -i NUnit3.DotNetNew.Template
```

### <a name="creating-the-test-project"></a>Erstellen des Testprojekts

Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*. Die folgende Gliederung zeigt die Verzeichnisstruktur:

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Machen Sie das *PrimeService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new nunit`](../tools/dotnet-new.md). Der neue dotnet-Befehl erstellt ein Testprojekt, das NUnit als Testbibliothek verwendet. Die generierte Vorlage konfiguriert das Testprogramm in der Datei *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich. Mithilfe von `dotnet new` im vorherigen Schritt wurden das Microsoft-Test-SDK, das NUnit-Testframework und der NUnit-Testadapter hinzugefügt. Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu. Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.

Die folgende Gliederung zeigt das endgültige Projektmappenlayout:

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

Führen Sie [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-using-dotnet-test* aus.

## <a name="creating-the-first-test"></a>Erstellen des ersten Tests

Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen. Entfernen Sie *UnitTest1.cs* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue C#-Datei namens *PrimeService_IsPrimeShould.cs* mit folgendem Inhalt:

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Test]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

Das `[TestFixture]`-Attribut gibt eine Klasse an, die Unittests enthält. Das `[Test]`-Attribut gibt an, dass es sich bei einer Methode um eine Testmethode handelt.

Speichern Sie diese Datei und führen Sie [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen. Der NUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests. `dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.

Ihr Test schlägt fehl. Sie haben die Implementierung noch nicht erstellt. Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse:

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

Führen Sie im Verzeichnis *unit-testing-using-nunit* erneut `dotnet test` aus. Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus. Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt. Er ist erfolgreich.

## <a name="adding-more-features"></a>Hinzufügen weiterer Features

Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter. Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1. Sie könnten diese neuen Tests mit dem Attribut `[Test]` hinzufügen, aber das wird schnell recht mühsam. Es gibt andere NUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.  Ein `[TestCase]`-Attribut wird verwendet, um eine Reihe von Tests zu erstellen, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden. Sie können das Attribut `[TestCase]` verwenden, um Werte für diese Eingaben anzugeben.

Statt neue Tests zu erstellen, wenden Sie dieses Attribut zum Erstellen eines einzelnen datengesteuerten Tests an. Bei dem datengesteuerten Test handelt es sich um eine Methode, die mehrere Werte unter zwei als niedrigste Primzahl testet:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl. Sie müssen die `if`-Klausel am Anfang der Methode ändern, damit alle Tests erfolgreich sind:

```csharp
if (candidate < 2)
```

Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen. Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).

Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt. Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist. Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.
