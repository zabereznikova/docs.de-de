---
title: Befehl „dotnet nuget update source“
description: Mit dem Befehl „dotnet nuget update source“ wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien aktualisiert.
ms.date: 03/20/2020
ms.openlocfilehash: 38335e07f91850756c7671413e1193c2578e7e7e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148471"
---
# <a name="dotnet-nuget-update-source"></a>dotnet nuget update source

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet nuget update source`: Aktualisieren einer NuGet-Quelle.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet nuget update source <NAME> [--source] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget update source [-h|--help]
```

## <a name="description"></a>Beschreibung

Mit dem Befehl `dotnet nuget update source` wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien aktualisiert.

## <a name="arguments"></a>Argumente

- **`NAME`**

  Name der Quelle.

## <a name="options"></a>Optionen

- **`--configfile`**

  Die NuGet-Konfigurationsdatei. Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet. Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet. Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`-p|--password`**

  Das bei der Verbindungsherstellung mit einer authentifizierten Quelle zu verwendende Kennwort.

- **`-s|--source`**

  Pfad zur Paketquelle.

- **`--store-password-in-clear-text`**

  Ermöglicht das Speichern von Anmeldeinformationen für portierbare Paketquellen durch Deaktivieren der Kennwortverschlüsselung.

- **`-u|--username`**

  Der bei der Verbindungsherstellung mit einer authentifizierten Quelle zu verwendende Benutzername.

- **`--valid-authentication-types`**

  Durch Trennzeichen getrennte Liste mit gültigen Authentifizierungstypen für diese Quelle. Legen Sie diese Option auf `basic` fest, wenn der Server NTLM oder eine Aushandlung ankündigt und Ihre Anmeldedaten über den Basismechanismus gesendet werden müssen, z. B. bei Verwendung eines persönlichen Zugriffstokens (PAT) mit einer lokalen Azure DevOps Server-Instanz. Andere gültige Werte sind `negotiate`, `kerberos`, `ntlm` und `digest`, aber diese Werte sind wahrscheinlich nicht sinnvoll.

## <a name="examples"></a>Beispiele

- Aktualisieren einer Quelle mit dem Namen `mySource`:

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a>Siehe auch

- [Paketquellenabschnitte in NuGet.config-Dateien](/nuget/reference/nuget-config-file#package-source-sections)

- [Befehl „sources“ (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
