---
title: Befehl „dotnet nuget add source“
description: Mit dem Befehl „dotnet nuget add source“ wird eine neue Paketquelle zu Ihren NuGet-Konfigurationsdateien hinzugefügt.
ms.date: 03/20/2020
ms.openlocfilehash: 319501e026f1c3102006b0be5357f127b8e366a7
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463599"
---
# <a name="dotnet-nuget-add-source"></a>dotnet nuget add source

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet nuget add source`: Hinzufügen einer NuGet-Quelle.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name <SOURCE_NAME>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget add source -h|--help
```

## <a name="description"></a>Beschreibung

Mit dem Befehl `dotnet nuget add source` wird eine neue Paketquelle zu Ihren NuGet-Konfigurationsdateien hinzugefügt.

## <a name="arguments"></a>Argumente

- **`PACKAGE_SOURCE_PATH`**

  Pfad zur Paketquelle.

## <a name="options"></a>Optionen

- **`--configfile <FILE>`**

  Die NuGet-Konfigurationsdatei. Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet. Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet. Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`-n|--name <SOURCE_NAME>`**

  Name der Quelle.

- **`-p|--password <PASSWORD>`**

  Das bei der Verbindungsherstellung mit einer authentifizierten Quelle zu verwendende Kennwort.

- **`--store-password-in-clear-text`**

  Ermöglicht das Speichern von Anmeldeinformationen für portierbare Paketquellen durch Deaktivieren der Kennwortverschlüsselung.

- **`-u|--username <USER>`**

  Der bei der Verbindungsherstellung mit einer authentifizierten Quelle zu verwendende Benutzername.

- **`--valid-authentication-types <TYPES>`**

  Durch Trennzeichen getrennte Liste mit gültigen Authentifizierungstypen für diese Quelle. Legen Sie diese Option auf `basic` fest, wenn der Server NTLM oder eine Aushandlung ankündigt und Ihre Anmeldedaten über den Basismechanismus gesendet werden müssen, z. B. bei Verwendung eines persönlichen Zugriffstokens (PAT) mit einer lokalen Azure DevOps Server-Instanz. Andere gültige Werte sind `negotiate`, `kerberos`, `ntlm` und `digest`, aber diese Werte sind wahrscheinlich nicht sinnvoll.

## <a name="examples"></a>Beispiele

- `nuget.org` als Quelle hinzufügen:

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- `c:\packages` als lokale Quelle hinzufügen:

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- Hinzufügen einer Quelle, die eine Authentifizierung erfordert:

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- Hinzufügen einer Quelle, die eine Authentifizierung erfordert (und anschließende Installation eines Anmeldeinformationsanbieters):

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a>Siehe auch

- [Paketquellenabschnitte in NuGet.config-Dateien](/nuget/reference/nuget-config-file#package-source-sections)

- [Befehl „sources“ (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
