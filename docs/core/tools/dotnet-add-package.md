---
title: Befehl „dotnet add package“
description: Der Paketbefehl „dotnet add“ bietet eine praktische Option zum Hinzufügen von NuGet-Paketverweisen zu einem Projekt.
ms.date: 11/11/2020
ms.openlocfilehash: 10373b3b69c669323674b192d54cd277a5828f24
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94556874"
---
# <a name="dotnet-add-package"></a>dotnet add package

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>name

`dotnet add package`: Fügt einen Paketverweis zu einer Projektdatei hinzu.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet add [<PROJECT>] package <PACKAGE_NAME>
    [-f|--framework <FRAMEWORK>] [--interactive]
    [-n|--no-restore] [--package-directory <PACKAGE_DIRECTORY>]
    [--prerelease] [-s|--source <SOURCE>] [-v|--version <VERSION>]

dotnet add package -h|--help
```

## <a name="description"></a>Beschreibung

Der `dotnet add package`-Befehl bietet eine praktische Option zum Hinzufügen von Paketverweisen zu einer Projektdatei. Nach dem Ausführen des Befehls wird die Kompatibilität überprüft, um sicherzustellen, dass das Paket mit den Frameworks im Projekt kompatibel ist. Wenn die Überprüfung erfolgreich ist, wird ein `<PackageReference>`-Element zur Projektdatei hinzugefügt, und [dotnet restore](dotnet-restore.md) wird ausgeführt.

Beispielsweise wird durch Hinzufügen von `Newtonsoft.Json` zu *ToDo.csproj* eine Ausgabe ähnlich der folgenden erzeugt:

```console
Writing C:\Users\me\AppData\Local\Temp\tmp95A8.tmp
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

### <a name="implicit-restore"></a>Implizite Wiederherstellung

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

## <a name="arguments"></a>Argumente

- **`PROJECT`**

  Gibt die Projektdatei an. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

- **`PACKAGE_NAME`**

  Hinzuzufügender Paketverweis.

## <a name="options"></a>Optionen

- **`-f|--framework <FRAMEWORK>`**

  Fügt Paketverweise nur hinzu, wenn ein bestimmtes [Framework](../../standard/frameworks.md) verwendet werden soll.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen). Verfügbar ab .NET Core 2.1 SDK, Version 2.1.400 oder höher.

- **`-n|--no-restore`**

  Fügt Paketverweise hinzu, ohne eine Vorschau der Wiederherstellung und eine Kompatibilitätsüberprüfung durchzuführen.

- **`--package-directory <PACKAGE_DIRECTORY>`**

  Das Verzeichnis, in dem die Pakete wiederhergestellt werden sollen. Der standardmäßige Wiederherstellungsort für Pakete ist `%userprofile%\.nuget\packages` unter Windows und `~/.nuget/packages` unter MacOS und Linux. Weitere Informationen finden Sie unter [Verwalten von globalen Pakete-, Cache- und temporären Ordnern in NuGet](/nuget/consume-packages/managing-the-global-packages-and-cache-folders).

- **`--prerelease`**

  Ermöglicht die Installation von Paketen mit Vorabversionen

- **`-s|--source <SOURCE>`**

  Der URI der NuGet-Paketquelle, die während des Wiederherstellungsvorgangs zu verwenden ist.

- **`-v|--version <VERSION>`**

  Die Version des Pakets. Weitere Informationen hierzu finden Sie unter [NuGet-Paketversionsverwaltung](/nuget/reference/package-versioning).

## <a name="examples"></a>Beispiele

- Fügen Sie das `Newtonsoft.Json`-NuGet-Pakets zu einem Projekt hinzu:

  ```dotnetcli
  dotnet add package Newtonsoft.Json
  ```

- Fügen Sie eine bestimmte Version eines Pakets zu einem Projekt hinzu:

  ```dotnetcli
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

- Fügen Sie ein Paket mit einer bestimmten NuGet-Quelle hinzu:

  ```dotnetcli
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```

## <a name="see-also"></a>Siehe auch

- [Verwalten von globalen Pakete-, Cache- und temporären Ordnern in NuGet](/nuget/consume-packages/managing-the-global-packages-and-cache-folders)
- [NuGet-Paketversionsverwaltung](/nuget/reference/package-versioning)
