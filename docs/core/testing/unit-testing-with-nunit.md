---
title: Unittests für C# mit NUnit und .NET Core
description: Erfahren Sie mehr über die Konzepte von Unittests in C# und .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und NUnit erstellen.
author: rprouse
ms.date: 08/31/2018
ms.openlocfilehash: 1ea17d9f830d8ac20e2bad79eebab5db767e0af8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714228"
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a>Unittests für C# mit NUnit und .NET Core

Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen. Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/), bevor Sie beginnen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a>Voraussetzungen

- [.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) oder höhere Versionen.
- Ein Text-Editor oder Code-Editor Ihrer Wahl.

## <a name="creating-the-source-project"></a>Erstellen des Quellprojekts

Öffnen eines Shell-Fensters. Erstellen Sie ein Verzeichnis namens *unit-testing-using-nunit*, um die Projektmappe zu speichern. Führen Sie in diesem neuen Verzeichnis den folgenden Befehl aus, um eine neue Projektmappendatei für die Klassenbibliothek und das Testprojekt zu erstellen:

```dotnetcli
dotnet new sln
```
 
Erstellen Sie als Nächstes ein *PrimeService*-Verzeichnis. Die folgende Gliederung zeigt die bisherige Verzeichnis- und Dateistruktur:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
```

Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie den folgenden Befehl aus, um das Quellprojekt zu erstellen:

```dotnetcli
dotnet new classlib
```

Benennen Sie *Class1.cs* in *PrimeService.cs* um. Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse:

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            throw new NotImplementedException("Please create a test first.");
        }
    }
}
```

Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-using-nunit*. Führen Sie den folgenden Befehl aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen:

```dotnetcli
dotnet sln add PrimeService/PrimeService.csproj
```

## <a name="creating-the-test-project"></a>Erstellen des Testprojekts

Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*. Die folgende Gliederung zeigt die Verzeichnisstruktur:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Machen Sie das Verzeichnis *PrimeService.Tests* zum aktuellen Verzeichnis, und erstellen Sie mit dem folgenden Befehl ein neues Projekt:

```dotnetcli
dotnet new nunit
```

Mit dem Befehl [dotnet new](../tools/dotnet-new.md) wird ein Testprojekt erstellt, in dem NUnit als Testbibliothek verwendet wird. Die generierte Vorlage konfiguriert das Testprogramm in der Datei *PrimeServiceTests.csproj*:

[!code-xml[Packages](~/samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj#Packages)]

Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich. Mithilfe von `dotnet new` im vorherigen Schritt wurden das Microsoft-Test-SDK, das NUnit-Testframework und der NUnit-Testadapter hinzugefügt. Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu. Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.csproj
```

Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj) auf GitHub.

Die folgende Gliederung zeigt das endgültige Projektmappenlayout:

```console
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.csproj
```

Führen Sie im Verzeichnis *unit-testing-using-nunit* den folgenden Befehl aus:

```dotnetcli
dotnet sln add ./PrimeService.Tests/PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a>Erstellen des ersten Tests

Sie schreiben einen fehlerhaften Test, lassen ihn bestehen und wiederholen dann den Prozess. Benennen Sie im Verzeichnis *PrimeService.Tests* die Datei *UnitTest1.cs* in *PrimeService_IsPrimeShould.cs* um, und ersetzen Sie die zugehörigen Inhalte durch Inhalte mit dem folgenden Code:

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        [Test]
        public void IsPrime_InputIs1_ReturnFalse()
        {
            PrimeService primeService = CreatePrimeService();
            var result = primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
        
        /*
        More tests
        */
        
        private PrimeService CreatePrimeService()
        {
             return new PrimeService();
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
    throw new NotImplementedException("Please create a test first.");
}
```

Führen Sie im Verzeichnis *unit-testing-using-nunit* erneut `dotnet test` aus. Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus. Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt. Er ist erfolgreich.

## <a name="adding-more-features"></a>Hinzufügen weiterer Features

Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter. Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1. Sie könnten diese neuen Tests mit dem Attribut `[Test]` hinzufügen, aber das wird schnell recht mühsam. Es gibt andere NUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.  Ein `[TestCase]`-Attribut wird verwendet, um eine Reihe von Tests zu erstellen, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden. Sie können das Attribut `[TestCase]` verwenden, um Werte für diese Eingaben anzugeben.

Statt neue Tests zu erstellen, wenden Sie dieses Attribut zum Erstellen eines einzelnen datengesteuerten Tests an. Bei dem datengesteuerten Test handelt es sich um eine Methode, die mehrere Werte unter zwei als niedrigste Primzahl testet:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl. Damit alle Tests erfolgreich sind, müssen Sie in der Datei *PrimeService.cs* am Anfang der Methode `Main` die `if`-Klausel ändern:

```csharp
if (candidate < 2)
```

Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen. Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs).

Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt. Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist. Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.
