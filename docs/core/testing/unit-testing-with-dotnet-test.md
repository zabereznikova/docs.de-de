---
title: Unittests in .NET Core mit dotnet-test
description: Unittests in .NET Core mit dotnet-test
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdcdb812-6f13-4f20-9e90-0c0977937142
translationtype: Human Translation
ms.sourcegitcommit: 5687fc7ded899a478d1972ffea10a1e37d40124b
ms.openlocfilehash: f1f08f550d7484869e67fe705dc789ca5dae8e2f

---

# <a name="unit-testing-in-net-core-using-dotnet-test"></a>Unittests in .NET Core mit dotnet-test

Von [Steve Smith](http://ardalis.com) und [Bill Wagner](https://github.com/BillWagner)

[Anzeigen oder Herunterladen von Beispielcode](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test)

> [!NOTE]
> Dieses Thema gilt für .NET Core 1.0.

## <a name="creating-the-projects"></a>Erstellen der Projekte

Unter [Entwickeln von Bibliotheken mit plattformübergreifenden Tools](../tutorials/libraries.md) finden Sie Informationen zum Organisieren von Projektmappen für mehrere Projekte sowohl für die Quelle als auch für die Tests. In diesem Artikel werden diese Konventionen befolgt. Die endgültige Projektstruktur wird etwa wie folgt aussehen:

```
/unit-testing-using-dotnet-test
|__global.json
|__/src
   |__/PrimeService
      |__Source Files
      |__project.json
|__/test
   |__/PrimeService.Tests
      |__Test Files
      |__project.json
```

Sie müssen im Stammverzeichnis eine `global.json`-Datei erstellen, die die Namen der Verzeichnisse `src` und `test` enthält:

```json
{
    "projects": [
        "src",
        "test"
    ]
}
```

### <a name="creating-the-source-project"></a>Erstellen des Quellprojekts

Erstellen Sie anschließend im Verzeichnis `src` das Verzeichnis `PrimeService`.
Wechseln Sie in dieses Verzeichnis, und führen Sie `dotnet new -t lib` aus, um das Quellprojekt zu erstellen.


Benennen Sie `Library.cs` in `PrimeService.cs` um. Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:

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

Wechseln Sie als Nächstes in das Verzeichnis „test“, und erstellen Sie das Verzeichnis `PrimeServices.Tests`.
Wechseln Sie in das Verzeichnis `PrimeServices.Tests`, und erstellen Sie mithilfe von `dotnet new -t xunittest` ein neues Projekt. `dotnet new -t xunittest` erstellt ein Testprojekt, das xunit als Testbibliothek verwendet. 

Die generierte Vorlage hat das Testprogramm im Stammverzeichnis von `project.json` konfiguriert:

```json
{
  "version": "1.0.0-*",
  "testRunner": "xunit",
  // ...
}
```

Mit der Vorlage wird der Framework-Knoten so festgelegt, dass `netcoreapp1.0` verwendet wird. Zudem enthält die Vorlage die Importe, die erforderlich sind, damit xUnit.net .NET Core RTM verwendet:

```json
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dotnet54",
        "portable-net45+win8" 
      ]
    }
  }
```

Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.
`dotnet new` hat xunit und xunit Runner hinzugefügt. Sie müssen das PrimeService-Paket als weitere Abhängigkeit zum Projekt hinzufügen:

```json
"dependencies": {
  "xunit":"2.1.0",
  "dotnet-test-xunit": "1.0.0-rc2-192208-24",
  "PrimeService": {
    "target": "project"
  }
}
```

Beachten Sie, dass das `PrimeService`-Projekt keine Verzeichnispfadinformationen enthält. Da Sie die Projektstruktur entsprechend der erwarteten Organisation von `src` und `test` erstellt haben und die Datei `global.json` dies anzeigt, findet das Buildsystem den richtigen Pfad für das Projekt. Sie fügen das Element `"target": "project"` hinzu, um NuGet darüber zu informieren, dass nicht im NuGet-Feed, sondern in Projektverzeichnissen gesucht werden soll. Ohne diesen Schlüssel können Sie ein Paket mit dem Namen für Ihre interne Bibliothek herunterladen.

Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/test/PrimeService.Tests/project.json) auf GitHub.

Nachdem Sie diese anfängliche Struktur eingerichtet haben, können Sie den ersten Test schreiben.
Sobald Sie diesen ersten Unittest überprüft haben, ist alles konfiguriert und sollte beim Hinzufügen von Features und Tests reibungslos funktionieren.

## <a name="creating-the-first-test"></a>Erstellen des ersten Tests

Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und abschließend den Vorgang wiederholen. Schreiben wir nun also diesen fehlerhaften Test. Entfernen Sie `program.cs` aus dem Verzeichnis `PrimeService.Tests`, und erstellen Sie eine neue C#-Datei mit folgendem Inhalt:

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
Der xunit Test Runner verfügt über den Programmeinstiegspunkt zum Ausführen der Tests über die Konsole. `dotnet test` startet den Test Runner, und stellt ein Befehlszeilenargument für den Test Runner bereit, das die Assembly mit Ihren Tests angibt.

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
Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1. Sie könnten diese neuen Tests mit dem Attribut `[Fact]` hinzufügen, aber das wird schnell recht mühsam. Es gibt andere xunit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.  `Theory` stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden.
Sie können das Attribut `[InlineData]` verwenden, um Werte für diese Eingaben anzugeben. 
 
 Statt neue Tests zu erstellen, nutzen Sie diese beiden Attribute zum Erstellen von „theory“. Damit werden einige Werte kleiner als 2 (die kleinste Primzahl) getestet:

```cs
[Theory]
[InlineData(-1)]
[InlineData(0)]
[InlineData(1)]
public void ReturnFalseGivenValuesLessThan2(int value)
{
    var result = _primeService.IsPrime(value);

    Assert.False(result, $"{value} should not be prime");
}
```

Führen Sie `dotnet test` aus. Sie werden feststellen, dass zwei dieser Tests fehlschlagen.
Durch Ändern des Diensts können Sie dafür sorgen, dass sie erfolgreich verlaufen. Sie müssen die `if`-Klausel am Anfang der Methode ändern:

```cs
if(candidate < 2)
```

Nun verlaufen alle Tests erfolgreich.

Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen. Sie werden die [endgültige Version der Tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/test/PrimeService.Tests/PrimeServie_IsPrimeShould.cs) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/src/PrimeService/PrimeService.cs) schnell erstellt haben.

Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.
Sie haben diese Projektmappe strukturiert, sodass neue Pakete und Tests problemlos hinzugefügt werden können und Sie sich auf das jeweils aktuelle Problem konzentrieren können. Die Tools werden automatisch ausgeführt.
   
   > [!TIP]
   > Auf einer Windows-Plattform können Sie MSTest verwenden. Weitere Informationen finden Sie im Dokument [Verwenden von MSTest unter Windows](./using-mstest-on-windows.md).



<!--HONumber=Jan17_HO3-->


