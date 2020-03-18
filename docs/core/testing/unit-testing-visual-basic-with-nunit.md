---
title: Komponententests für Visual Basic in .NET Core mit „dotnet test“ und NUnit
description: Erfahren Sie mehr über die Konzepte von Komponententests in .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Visual Basic-Beispielprojektmappe mithilfe von NUnit erstellen.
author: rprouse
ms.date: 10/04/2018
ms.openlocfilehash: a33447457344b241b4c2376d777b0deb7f556874
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240921"
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a>Unittests für Visual Basic .NET Core-Bibliotheken mithilfe von „dotnet test“ und NUnit

Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen. Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-nunit/), bevor Sie beginnen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

[!INCLUDE [testing an ASP.NET Core project from .NET Core](../../../includes/core-testing-note-aspnet.md)]

## <a name="prerequisites"></a>Voraussetzungen

- [.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) oder höhere Versionen.
- Ein Text-Editor oder Code-Editor Ihrer Wahl.

## <a name="creating-the-source-project"></a>Erstellen des Quellprojekts

Öffnen eines Shell-Fensters. Erstellen Sie ein Verzeichnis namens *unit-testing-vb-nunit*, um die Projektmappe zu speichern. Führen Sie in diesem neuen Verzeichnis den folgenden Befehl aus, um eine neue Projektmappendatei für die Klassenbibliothek und das Testprojekt zu erstellen:

```dotnetcli
dotnet new sln
```

Erstellen Sie als Nächstes ein *PrimeService*-Verzeichnis. Die folgende Gliederung zeigt die bisherige Dateistruktur:

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

Machen Sie *PrimeService* zum aktuellen Verzeichnis, und führen Sie den folgenden Befehl aus, um das Quellprojekt zu erstellen:

```dotnetcli
dotnet new classlib -lang VB
```

Benennen Sie *Class1.VB* in *PrimeService.VB* um. Sie erstellen eine fehlerhafte Implementierung der `PrimeService`-Klasse:

```vb
Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first.")
        End Function
    End Class
End Namespace
```

Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-vb-using-mstest*. Führen Sie den folgenden Befehl aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen:

```dotnetcli
dotnet sln add .\PrimeService\PrimeService.vbproj
```

## <a name="creating-the-test-project"></a>Erstellen des Testprojekts

Erstellen Sie als Nächstes das Verzeichnis *PrimeService.Tests*. Die folgende Gliederung zeigt die Verzeichnisstruktur:

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

Machen Sie das Verzeichnis *PrimeService.Tests* zum aktuellen Verzeichnis, und erstellen Sie mit dem folgenden Befehl ein neues Projekt:

```dotnetcli
dotnet new nunit -lang VB
```

Mit dem Befehl [dotnet new](../tools/dotnet-new.md) wird ein Testprojekt erstellt, in dem NUnit als Testbibliothek verwendet wird. Die generierte Vorlage konfiguriert Test Runner in der Datei *PrimeServiceTests.vbproj*:

[!code-xml[Packages](~/samples/snippets/core/testing/unit-testing-vb-nunit/vb/PrimeService.Tests/PrimeService.Tests.vbproj#Packages)]

Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich. Mithilfe von `dotnet new` wurden im vorhergehenden Schritt NUnit und der NUnit-Testadapter hinzugefügt. Fügen Sie jetzt die `PrimeService`-Klassenbibliothek als eine andere Abhängigkeit zum Projekt hinzu. Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):

```dotnetcli
dotnet add reference ../PrimeService/PrimeService.vbproj
```

Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) auf GitHub.

Sie verfügen über das folgende endgültige Projektmappenlayout:

```console
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeService.Tests.vbproj
```

Führen Sie im Verzeichnis *unit-testing-vb-nunit* den folgenden Befehl aus:

```dotnetcli
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj
```

## <a name="creating-the-first-test"></a>Erstellen des ersten Tests

Sie schreiben einen fehlerhaften Test, lassen ihn bestehen und wiederholen dann den Prozess. Benennen Sie im Verzeichnis *PrimeService.Tests* die Datei *UnitTest1.vb* in *PrimeService_IsPrimeShould.VB* um, und ersetzen Sie den gesamten Inhalt durch folgenden Code:

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub IsPrime_InputIs1_ReturnFalse()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

Das `<TestFixture>`-Attribut gibt eine Klasse an, die Tests enthält. Das `<Test>`-Attribut kennzeichnet eine Methode, die von Test Runner ausgeführt wird. Führen Sie im Verzeichnis *unit-testing-vb-nunit*[`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen. Der NUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests. `dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.

Ihr Test schlägt fehl. Sie haben die Implementierung noch nicht erstellt. Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `PrimeService`-Klasse:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first.")
End Function
```

Führen Sie im Verzeichnis *unit-testing-vb-nunit* erneut `dotnet test` aus. Der `dotnet test`-Befehl führt einen Build für das `PrimeService`-Projekt und anschließend für das `PrimeService.Tests`-Projekt aus. Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt. Er ist erfolgreich.

## <a name="adding-more-features"></a>Hinzufügen weiterer Features

Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter. Es gibt einige weitere einfache Fälle für Primzahlen: 0, -1. Sie könnten diese neuen Fälle als neue Tests mit dem Attribut `<Test>` hinzufügen, aber das wird schnell recht mühsam. Es gibt andere xUnit-Attribute, mit deren Hilfe Sie eine Reihe ähnlicher Tests schreiben können.  Ein `<TestCase>`-Attribut stellt eine Reihe von Tests dar, die zwar denselben Code ausführen, jedoch unterschiedliche Eingabeargumente verwenden. Sie können das Attribut `<TestCase>` verwenden, um Werte für diese Eingaben anzugeben.

Statt neue Tests zu erstellen, wenden Sie diese beiden Attribute zum Erstellen einer Testserie an. Damit werden mehrere Werte kleiner als 2 (die kleinste Primzahl) getestet:

[!code-vb[Sample_TestCode](../../../samples/snippets/core/testing/unit-testing-vb-nunit/vb/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

Führen Sie `dotnet test` aus und zwei dieser Tests schlagen fehl. Damit alle Tests erfolgreich sind, ändern Sie in der Datei `if`PrimeServices.cs`Main` am Anfang der Methode *die*-Klausel:

```vb
if candidate < 2
```

Wiederholen Sie den Vorgang, indem Sie weitere Tests, Theorien und Code in der Hauptbibliothek hinzufügen. Sie verfügen über die [endgültige Version der Tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) und die [vollständige Implementierung der Bibliothek](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).

Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt. Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist. Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.
