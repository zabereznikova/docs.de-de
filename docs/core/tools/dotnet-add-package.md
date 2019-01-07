---
title: Befehl „dotnet add package“
description: Der Befehl „dotnet add package“ bietet eine praktische Option zum Hinzufügen von NuGet-Paketverweisen zu einem Projekt.
ms.date: 12/04/2018
ms.openlocfilehash: 159b208feafb82e267629ea47dcef02d6b575055
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170001"
---
# <a name="dotnet-add-package"></a>dotnet add package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet add package`: Fügt einen Paketverweis zu einer Projektdatei hinzu.

## <a name="synopsis"></a>Übersicht

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a>Beschreibung

Der `dotnet add package`-Befehl bietet eine praktische Option zum Hinzufügen von Paketverweisen zu einer Projektdatei. Nach dem Ausführen des Befehls wird die Kompatibilität überprüft, um sicherzustellen, dass das Paket mit den Frameworks im Projekt kompatibel ist. Wenn die Überprüfung erfolgreich ist, wird ein `<PackageReference>`-Element zur Projektdatei hinzugefügt, und [dotnet restore](dotnet-restore.md) wird ausgeführt.

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

Beispielsweise wird durch Hinzufügen von `Newtonsoft.Json` zu *ToDo.csproj* eine Ausgabe ähnlich der folgenden erzeugt:

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\Temp\projects\consoleproj\consoleproj.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 79ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg 232ms
log  : Installing Newtonsoft.Json 12.0.1.
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '12.0.1' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

Die *ToDo.csproj*-Datei enthält nun ein [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files)-Element für das Paket, auf das verwiesen wird.

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a>Argumente

* **`PROJECT`**

  Gibt die Projektdatei an. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

* **`PACKAGE_NAME`**

  Hinzuzufügender Paketverweis.

## <a name="options"></a>Optionen

* **`-f|--framework <FRAMEWORK>`**

  Fügt Paketverweise nur hinzu, wenn ein bestimmtes [Framework](../../standard/frameworks.md) verwendet werden soll.

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

* **`--interactive`**

  Ermöglicht es dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen). Verfügbar ab .NET Core 2.1 SDK, Version 2.1.400 oder höher.

* **`-n|--no-restore`**

  Fügt Paketverweise hinzu, ohne eine Vorschau der Wiederherstellung und eine Kompatibilitätsüberprüfung durchzuführen.

* **`--package-directory <PACKAGE_DIRECTORY>`**

  Stellt das Paket im angegebenen Verzeichnis wieder her.

* **`-s|--source <SOURCE>`**

  Verwendet während des Wiederherstellungsvorgangs eine bestimmte NuGet-Paketquelle.

* **`-v|--version <VERSION>`**

  Die Version des Pakets.

## <a name="examples"></a>Beispiele

* Fügen Sie das `Newtonsoft.Json`-NuGet-Pakets zu einem Projekt hinzu:

  ```console
  dotnet add package Newtonsoft.Json
  ```

* Fügen Sie eine bestimmte Version eines Pakets zu einem Projekt hinzu:

  ```console
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

* Fügen Sie ein Paket mit einer bestimmten NuGet-Quelle hinzu:

  ```console
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```