---
title: Befehl „dotnet nuget locals“
description: Der dotnet nuget locals-Befehl löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder Ordner mit globalen Paketen auf dem Computer, bzw. listet diese Ressourcen auf.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 3fdd7d946b08b4c18cfaeb65013de259b927a7fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503681"
---
# <a name="dotnet-nuget-locals"></a>dotnet nuget locals

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet nuget locals`: Löscht lokale NuGet-Ressourcen oder listet diese auf.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet nuget locals`-Befehl löscht lokale NuGet-Ressourcen im http-Anforderungscache, temporären Cache oder Ordner mit globalen Paketen auf dem Computer bzw. listet diese Ressourcen auf.

## <a name="arguments"></a>Argumente

- **`CACHE_LOCATION`**

  Der aufzulistende oder zu löschende Cachespeicherort. Einer der folgenden Werte wird akzeptiert:

  * `all`: gibt an, dass der angegebene Vorgang auf alle Cachetypen angewendet wird: Auf den http-Anforderungscache, den Cache für globale Pakete und den temporären Cache.
  * `http-cache`: gibt an, dass der angegebene Vorgang nur auf den http-Anforderungscache angewendet wird. Die anderen Cachespeicherorte sind nicht betroffen.
  * `global-packages`: gibt an, dass der angegebene Vorgang nur auf den Cache für globale Pakete angewendet wird. Die anderen Cachespeicherorte sind nicht betroffen.
  * `temp`: gibt an, dass der angegebene Vorgang nur auf den temporären Cache angewendet wird. Die anderen Cachespeicherorte sind nicht betroffen.

## <a name="options"></a>Optionen

- **`--force-english-output`**

  Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`-c|--clear`**

  Die Option „clear“ führt einen Löschvorgang für den angegebenen Cachetyp aus. Die Inhalte der Cacheverzeichnisse werden rekursiv gelöscht. Der ausführende Benutzer (bzw. die Gruppe) muss über Berechtigungen für die Dateien in den Cacheverzeichnissen verfügen. Andernfalls wird ein Fehler angezeigt, der die Dateien/Ordner angibt, die nicht gelöscht wurden.

- **`-l|--list`**

  Die list-Option wird verwendet, um den Speicherort des angegebenen Cachetyps anzuzeigen.

## <a name="examples"></a>Beispiele

- Zeigt die Pfade aller lokalen Cacheverzeichnisse an (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):

  ```dotnetcli
  dotnet nuget locals all –l
  ```

- Zeigt den Pfad für das lokale http-Cacheverzeichnis an:

  ```dotnetcli
  dotnet nuget locals http-cache --list
  ```

- Löscht alle Dateien aus allen lokalen Cacheverzeichnissen (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):

  ```dotnetcli
  dotnet nuget locals all --clear
  ```

- Löscht alle Dateien im lokalen Cacheverzeichnis für globale Pakete:

  ```dotnetcli
  dotnet nuget locals global-packages -c
  ```

- Löscht alle Dateien im lokalen temporären Cacheverzeichnis:

  ```dotnetcli
  dotnet nuget locals temp -c
  ```

## <a name="troubleshooting"></a>Problembehandlung

Weitere Informationen zu häufig auftretenden Problemen und Fehlern bei der Verwendung des `dotnet nuget locals`-Befehls finden Sie unter [Managing the NuGet cache (Verwalten des NuGet-Caches)](/nuget/consume-packages/managing-the-nuget-cache).
