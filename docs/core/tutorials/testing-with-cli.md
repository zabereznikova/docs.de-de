---
title: Organisieren und Testen von Projekten mit der .NET Core-CLI
description: In diesem Tutorial wird das Organisieren und Testen von .NET Core-Projekten von der Befehlszeile aus erläutert.
author: cartermp
ms.date: 09/10/2018
ms.openlocfilehash: 0d61e0fc004cfcb6d78c49475c7b7f0f523aad2c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78239910"
---
# <a name="organizing-and-testing-projects-with-the-net-core-cli"></a>Organisieren und Testen von Projekten mit der .NET Core-CLI

Dieses Tutorial folgt auf [Erste Schritte mit .NET Core unter Windows/Linux/macOS unter Verwendung der Befehlszeile](cli-create-console-app.md), was Sie über die Erstellung einer einfachen Konsolen-App hinaus führt, damit Sie erweiterte und gut organisierte Anwendungen entwickeln können. Nachdem Sie gesehen haben, wie Sie Ordner zum Organisieren Ihres Codes verwenden können, zeigt Ihnen dieses Tutorial, wie Sie eine Konsolenanwendung mit dem [xUnit](https://xunit.github.io/)-Testframework erweitern können.

## <a name="using-folders-to-organize-code"></a>Verwenden von Ordnern zum Strukturieren von Code

Wenn Sie neue Typen in eine Konsolen-App einführen möchten, können Sie dies durch Hinzufügen von Dateien tun, die die Typen dieser App enthalten. Wenn Sie Ihrem Projekt beispielsweise Dateien hinzufügen, die die Typen `AccountInformation` und `MonthlyReportRecords` enthalten, ist die Dateistruktur des Projekts flach und einfach zu navigieren.

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

Dies funktioniert jedoch nur einwandfrei, wenn Ihr Projekt relativ klein ist. Können Sie sich vorstellen, was passieren wird, wenn Sie 20 Typen zum Projekt hinzufügen? Das Projekt wäre auf jeden Fall schwierig zu navigieren und zu warten, außerdem würden viele Dateien das Stammverzeichnis des Projekts unübersichtlich machen.

Um das Projekt zu organisieren, erstellen Sie einen neuen Ordner und nennen Ihn *Modelle*, der die Typdateien enthalten soll. Platzieren Sie die Typdateien in den Ordner *Modelle*.

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

Projekte, die Dateien logisch in Ordner gruppieren, sind einfach zu navigieren und zu warten. Im nächsten Abschnitt erstellen Sie ein komplexeres Beispiel mit Ordnern und Komponententests.

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a>Organisieren und Testen mithilfe des NewTypes Pets-Beispiels

### <a name="building-the-sample"></a>Erstellen des Beispiels

Sie können für die folgenden Schritte entweder mithilfe des [NewTypes Pets-Beispiels](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) durchführen oder Ihre eigenen Dateien und Ordner erstellen. Die Typen werden logisch in einer Ordnerstruktur organisiert, die das spätere Hinzufügen zusätzlicher Typen erlaubt. Tests werden ebenso logisch in Ordnern platziert, wobei später weitere Tests durchgeführt werden können.

In diesem Beispiel sind zwei Typen enthalten, `Dog` und `Cat`, mit deren Hilfe die allgemeine Schnittstelle `IPet` implementiert wird. Ihr Ziel für das `NewTypes`-Projekt ist es, die auf Haustiere (pets) bezogenen Typen in einem *Pets*-Ordner zu organisieren. Wenn andere Typen später hinzugefügt werden, z.B. *WildAnimals*, werden sie im *NewTypes*-Ordner neben dem *Pets*-Ordner platziert. Der *WildAnimals*-Ordner kann womöglich Tierarten enthalten, die keine Haustiere sind, z.B. die Typen `Squirrel` und `Rabbit`. Dadurch, dass Typen hinzugefügt werden, bleibt das Projekt organisiert.

Erstellen Sie die folgende Ordnerstruktur mit angegebenem Dateiinhalt:

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
```

*IPet.cs*:

[!code-csharp[IPet interface](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/IPet.cs)]

*Dog.cs*:

[!code-csharp[Dog class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/Dog.cs)]

*Cat.cs*:

[!code-csharp[Cat class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/Cat.cs)]

*Program.cs*:

[!code-csharp[Main](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Program.cs)]

*NewTypes.csproj*:

[!code-xml[NewTypes csproj](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/NewTypes.csproj)]

Führen Sie den folgenden Befehl aus:

```dotnetcli
dotnet run
```

Achten Sie auf die folgende Ausgabe:

```console
Woof!
Meow!
```

Optionale Übung: Sie können einen neuen Tiertyp hinzufügen, z.B. `Bird`, indem Sie dieses Projekt erweitern. Die `TalkToOwner`-Methode des Vogels soll einen `Tweet!` an den Besitzer geben. Führen Sie die App erneut aus. Die Ausgabe wird `Tweet!` enthalten.

### <a name="testing-the-sample"></a>Testen der Beispielanwendung

Das `NewTypes`-Projekt ist platziert, und Sie haben es organisiert, indem Sie die auf Haustiere bezogenen Typen in einem Ordner gespeichert haben. Erstellen Sie als Nächstes Ihr Testprojekt und beginnen Sie, Tests mit dem [xUnit](https://xunit.github.io/)-Testframework zu schreiben. Komponententests erlauben Ihnen, das Verhalten dieser Typen automatisch zu testen, um zu überprüfen, ob sie ordnungsgemäß funktionieren.

Navigieren Sie zurück zum Ordner *src*, und erstellen Sie einen Ordner *test*, der den Ordner *NewTypesTests* enthält. Führen Sie in einer Eingabeaufforderung vom *NewTypesTests*-Ordner `dotnet new xunit` aus. Dadurch werden zwei Dateien erstellt: *NewTypesTests.csproj* und *UnitTest1.cs*.

Das Testprojekt kann derzeit nicht die Typen in `NewTypes` testen und benötigt einen Projektverweis auf das `NewTypes`-Projekt. Um einen Projektverweis hinzuzufügen, verwenden Sie den [`dotnet add reference`](../tools/dotnet-add-reference.md)-Befehl:

```dotnetcli
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

Alternativ haben Sie auch die Möglichkeit, den Projektverweis manuell hinzuzufügen, indem Sie der `<ItemGroup>`NewTypesTests.csproj *-Datei einen* -Knoten hinzufügen:

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

*NewTypesTests.csproj*:

[!code-xml[NewTypesTests csproj](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/test/NewTypesTests/NewTypesTests.csproj)]

Die *NewTypesTests.csproj*-Datei enthält Folgendes:

* Paketverweis auf `Microsoft.NET.Test.Sdk`, die .NET-Testinfrastruktur
* Paketverweis auf `xunit`, das xUnit-Testframework
* Paketverweis auf `xunit.runner.visualstudio`, der Test Runner
* Projektverweis auf `NewTypes`, der zu testende Code

Ändern Sie den Namen von *UnitTest1.cs* zu *PetTests.cs*, und ersetzen Sie den Code in der Datei mit Folgendem:

```csharp
using System;
using Xunit;
using Pets;

public class PetTests
{
    [Fact]
    public void DogTalkToOwnerReturnsWoof()
    {
        string expected = "Woof!";
        string actual = new Dog().TalkToOwner();

        Assert.NotEqual(expected, actual);
    }

    [Fact]
    public void CatTalkToOwnerReturnsMeow()
    {
        string expected = "Meow!";
        string actual = new Cat().TalkToOwner();

        Assert.NotEqual(expected, actual);
    }
}
```

Optionale Übung: Wenn Sie zuvor einen `Bird`-Typ hinzugefügt haben, der `Tweet!` dem Besitzer zurückgibt, fügen Sie der *PetTests.cs*-Datei eine Testmethode hinzu, `BirdTalkToOwnerReturnsTweet`, um zu überprüfen, dass die `TalkToOwner`-Methode ordnungsgemäß für den `Bird`-Typ funktioniert.

> [!NOTE]
> Obwohl Sie erwarten, dass die Werte `expected` und `actual` gleich sind, gibt die anfängliche Assertion mit der `Assert.NotEqual`-Überprüfung an, dass sie *nicht gleich* sind. Erstellen Sie zunächst immer einen Test, damit dieser fehlschlagen und die Logik des Tests überprüft werden kann. Nachdem Sie das Fehlschlagen des Tests bestätigt haben, können Sie die Assertion so anpassen, dass der Test erfolgreich verläuft.

Nachstehend ist die vollständige Projektstruktur dargestellt:

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

Beginnen Sie im *test/NewTypesTests*-Verzeichnis. Stellen Sie das Testprojekt mit dem [`dotnet restore`](../tools/dotnet-restore.md)-Befehl wieder her. Führen Sie die Tests mit dem [`dotnet test`](../tools/dotnet-test.md)-Befehl aus. Dieser Befehl startet den in der Projektdatei angegebenen Test Runner.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Der Test schlägt wie erwartet fehl, und die Konsole zeigt die folgende Ausgabe:

```output
Test run for c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp2.1\NewTypesTests.dll(.NETCoreApp,Version=v2.1)
Microsoft (R) Test Execution Command Line Tool Version 15.8.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.77]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
[xUnit.net 00:00:00.78]     PetTests.CatTalkToOwnerReturnsMeow [FAIL]
Failed   PetTests.DogTalkToOwnerReturnsWoof
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
Stack Trace:
   at PetTests.DogTalkToOwnerReturnsWoof() in c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 13
Failed   PetTests.CatTalkToOwnerReturnsMeow
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Meow!"
Actual:   "Meow!"
Stack Trace:
   at PetTests.CatTalkToOwnerReturnsMeow() in c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 22

Total tests: 2. Passed: 0. Failed: 2. Skipped: 0.
Test Run Failed.
Test execution time: 1.7000 Seconds
```

Ändern Sie die Assertionen Ihrer Tests von `Assert.NotEqual` zu `Assert.Equal`:

[!code-csharp[PetTests class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/test/NewTypesTests/PetTests.cs)]

Führen Sie die Tests erneut mit dem `dotnet test`-Befehl aus, und achten Sie auf die folgende Ausgabe:

```output
Test run for c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp2.1\NewTypesTests.dll(.NETCoreApp,Version=v2.1)
Microsoft (R) Test Execution Command Line Tool Version 15.8.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...

Total tests: 2. Passed: 2. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.6029 Seconds
```

Die Tests werden erfolgreich ausgeführt. Die Haustiertyp-Methoden geben die korrekten Werte zurück, wenn sie mit dem Besitzer kommunizieren.

Sie haben Techniken zum Organisieren und Testen von Projekten mithilfe von xUnit gelernt. Machen Sie mit diesen Techniken weiter, und wenden Sie sie in Ihren eigenen Projekten an. *Viel Spaß beim Programmieren!*
