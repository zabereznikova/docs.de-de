---
title: Befehl „dotnet nuget locals“
description: Der Befehl „dotnet nuget locals“ löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder Ordner mit globalen Paketen auf dem Computer, bzw. listet diese Ressourcen auf.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: d0f1c7c2e0b233c214cc48d026c19755fc047bfa
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170755"
---
# <a name="dotnet-nuget-locals"></a>dotnet nuget locals

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet nuget locals`: Löscht lokale NuGet-Ressourcen oder listet diese auf.

## <a name="synopsis"></a>Übersicht

```
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet nuget locals`-Befehl löscht lokale NuGet-Ressourcen im http-Anforderungscache, temporären Cache oder Ordner mit globalen Paketen auf dem Computer bzw. listet diese Ressourcen auf.

## <a name="arguments"></a>Argumente

* **`CACHE_LOCATION`**

  Der aufzulistende oder zu löschende Cachespeicherort. Einer der folgenden Werte wird akzeptiert:

  * `all`: gibt an, dass der angegebene Vorgang auf alle Cachetypen angewendet wird: Auf den http-Anforderungscache, den Cache für globale Pakete und den temporären Cache.
  * `http-cache`: gibt an, dass der angegebene Vorgang nur auf den http-Anforderungscache angewendet wird. Die anderen Cachespeicherorte sind nicht betroffen.
  * `global-packages`: gibt an, dass der angegebene Vorgang nur auf den Cache für globale Pakete angewendet wird. Die anderen Cachespeicherorte sind nicht betroffen.
  * `temp`: gibt an, dass der angegebene Vorgang nur auf den temporären Cache angewendet wird. Die anderen Cachespeicherorte sind nicht betroffen.

## <a name="options"></a>Optionen

* **`--force-english-output`**

  Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

* **`-c|--clear`**

  Die Option „clear“ führt einen Löschvorgang für den angegebenen Cachetyp aus. Die Inhalte der Cacheverzeichnisse werden rekursiv gelöscht. Der ausführende Benutzer (bzw. die Gruppe) muss über Berechtigungen für die Dateien in den Cacheverzeichnissen verfügen. Andernfalls wird ein Fehler angezeigt, der die Dateien/Ordner angibt, die nicht gelöscht wurden.

* **`-l|--list`**

  Die list-Option wird verwendet, um den Speicherort des angegebenen Cachetyps anzuzeigen.

## <a name="examples"></a>Beispiele

* Zeigt die Pfade aller lokalen Cacheverzeichnisse an (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):

  ```console
  dotnet nuget locals –l all
  ```

* Zeigt den Pfad für das lokale http-Cacheverzeichnis an:

  ```console
  dotnet nuget locals --list http-cache
  ```

* Löscht alle Dateien aus allen lokalen Cacheverzeichnissen (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):

  ```console
  dotnet nuget locals --clear all
  ```

* Löscht alle Dateien im lokalen Cacheverzeichnis für globale Pakete:

  ```console
  dotnet nuget locals -c global-packages
  ```

* Löscht alle Dateien im lokalen temporären Cacheverzeichnis:

  ```console
  dotnet nuget locals -c temp
  ```

## <a name="troubleshooting"></a>Problembehandlung

Weitere Informationen zu häufig auftretenden Problemen und Fehlern bei der Verwendung des `dotnet nuget locals`-Befehls finden Sie unter [Managing the NuGet cache (Verwalten des NuGet-Caches)](/nuget/consume-packages/managing-the-nuget-cache).