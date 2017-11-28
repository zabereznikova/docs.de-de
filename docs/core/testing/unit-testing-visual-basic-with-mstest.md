---
title: "Komponententests für Visual Basic in .NET Core mithilfe von „dotnet test“ und MSTest"
description: "Erfahren Sie mehr über die Konzepte von Komponententests in .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Visual Basic-Beispielprojektmappe mithilfe von MSTest erstellen."
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.topic: article
dev_langs: vb
ms.prod: .net-core
ms.openlocfilehash: b656ae4746691f2e72eaa666542e98d4abc91069
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-mstest"></a>Komponententests für Visual Basic .NET Core-Bibliotheken mithilfe von „dotnet test“ und MSTest

Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen. Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-mstest/), bevor Sie beginnen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Erstellen des Quellprojekts

Öffnen eines Shell-Fensters. Erstellen Sie ein Verzeichnis namens *unit-testing-using-dotnet-test*, um die Projektmappe zu speichern.
Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappe zu erstellen. Diese Übung vereinfacht die Verwaltung des Klassenbibliotheks- und Komponententestprojekts.
Erstellen Sie im Projektmappenverzeichnis ein *PrimeService*-Verzeichnis. Soweit verfügen Sie über die bisherige Verzeichnis- und Dateistruktur:

```
/unit-testing-vb-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen. Benennen Sie *Class1.VB* in *PrimeService.VB* um. Erstellen Sie eine fehlerhafte Implementierung der `PrimeService`-Klasse, um eine testgesteuerte Entwicklung (Test Driven Development, TDD) zu verwenden:

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-vb-using-stest*. Führen Sie [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen.

## <a name="creating-the-test-project"></a>Erstellen des Testprojekts

Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*. Die folgende Gliederung zeigt die Verzeichnisstruktur:

```
/unit-testing-vb-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

Machen Sie das *PrimeService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new mstest -lang VB`](../tools/dotnet-new.md). Dieser Befehl erstellt ein Testprojekt, das xUnit als Testbibliothek verwendet. Die generierte Vorlage konfiguriert Test Runner in *PrimeServiceTests.vbproj*:

```xml
<ItemGroup>
<PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
<PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
<PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich. `dotnet new` hat im vorherigen Schritt MSTest und MSTest Runner hinzugefügt. Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als weitere Abhängigkeit zum Projekt hinzu. Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) auf GitHub.

Sie verfügen über das folgende endgültige Projektmappenlayout:

```
/unit-testing-vb-using-mstest
    unit-testing-vb-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

Führen Sie [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-vb-using-mstest* aus. 

## <a name="creating-the-first-test"></a>Erstellen des ersten Tests

Gemäß dem TDD-Konzept müssen Sie einen fehlerhaften Test schreiben, anschließend dafür sorgen, dass der Test erfolgreich verläuft und dann den Vorgang wiederholen. Entfernen Sie *UnitTest1.vb* aus dem *PrimeService.Tests*-Verzeichnis, und erstellen Sie eine neue Visual Basic-Datei namens *PrimeService_IsPrimeShould.VB*. Fügen Sie den folgenden Code hinzu:

```vb
Imports Microsoft.VisualStudio.TestTools.UnitTesting

Namespace PrimeService.Tests
    <TestClass>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <TestMethod>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

Das `<TestClass>`-Attribut gibt eine Klasse an, die Tests enthält. Das `<TestMethod>`-Attribut kennzeichnet eine Methode, die von Test Runner ausgeführt wird. Führen Sie im Verzeichnis *unit-testing-vb-using-mstest* [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen. Der xUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests. `dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.

Ihr Test schlägt fehl. Sie haben die Implementierung noch nicht erstellt. Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

Führen Sie im Verzeichnis *unit-testing-vb-using-mstest* erneut `dotnet test` aus. Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus. Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt. Er ist erfolgreich.

## <a name="adding-more-features"></a>Hinzufügen weiterer Features

Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter. Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1. Sie könnten diese neuen Fälle als neue Tests mit dem Attribut `<TestMethod>` hinzufügen, aber das wird schnell recht mühsam. Es gibt andere xUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.  Ein `<DataTestMethod>`-Attribut stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden. Sie können das Attribut `<DataRow>` verwenden, um Werte für diese Eingaben anzugeben.

Statt neue Tests zu erstellen, wenden Sie diese beiden Attribute zum Erstellen einer einzelnen Theorie an. Bei der Theorie handelt es sich um eine Methode, die mehrere Werte unter zwei als niedrigste Primzahl testet:

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl. Sie müssen die `if`-Klausel am Anfang der Methode ändern, damit alle Tests erfolgreich sind:

```vb
if candidate < 2
```

Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen. Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService/PrimeService.vb).

Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt. Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist. Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.
