---
title: Befehl dotnet-nuget-locals | Microsoft-Dokumentation
description: "Der dotnet-nuget-locals-Befehl löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder Ordner mit globalen Paketen auf dem Computer, bzw. listet diese Ressourcen auf."
keywords: dotnet-nuget-locals, CLI, CLI-Befehl, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8440229e-317e-4dc1-9463-cba5fdb12c3b
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 3d8ca57c3c9c25a59b98552784b057182c9100a3
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-nuget-locals"></a>dotnet-nuget-locals

## <a name="name"></a>Name

`dotnet-nuget-locals` – Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder Ordner mit globalen Paketen auf dem Computer, bzw. listet diese Ressourcen auf. 

## <a name="synopsis"></a>Übersicht

```
dotnet nuget locals <cache_location> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

`<cache_location>` kann dabei einer der folgenden Werte sein: `all`, `http-cache`, `packages-cache`, `global-packages` oder `temp`.

## <a name="description"></a>Beschreibung

Der `dotnet nuget locals`-Befehl löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder Ordner mit globalen Paketen auf dem Computer, bzw. listet diese Ressourcen auf.

## <a name="arguments"></a>Argumente

`all`

Gibt an, dass der angegebene Vorgang auf alle Cachetypen angewendet werden soll, d.h. auf den http-Anforderungscache, den Cache für globale Pakete und den temporären Cache.

`http-cache`

Gibt an, dass der angegebene Vorgang nur auf den http-Anforderungscache angewendet werden soll. Die anderen Cachespeicherorte sind nicht betroffen.

`global-packages`

Gibt an, dass der angegebene Vorgang nur auf den Cache für globale Pakete angewendet werden soll. Die anderen Cachespeicherorte sind nicht betroffen.

`temp`

Gibt an, dass der angegebene Vorgang nur auf den temporären Cache angewendet werden soll. Die anderen Cachespeicherorte sind nicht betroffen.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-c|--clear`

Die clear-Option wird verwendet, um einen Löschvorgang für den angegebenen Cachetyp auszuführen. Die Inhalte der Cacheverzeichnisse werden rekursiv gelöscht. Der ausführende Benutzer (bzw. die Gruppe) sollte über Berechtigungen für die Dateien im Cacheverzeichnis verfügen, damit der Vorgang erfolgreich ausgeführt wird. Andernfalls wird ein Fehler angezeigt, und die Dateien/Ordner, die nicht gelöscht wurden, werden angegeben.

`-l|--list`

Die list-Option wird verwendet, um den Speicherort des angegebenen Cachetyps anzuzeigen. 

`--force-english-output`

Erzwingt, dass die Befehlszeilenausgabe auf Englisch ist.

## <a name="examples"></a>Beispiele

Zeigt die Pfade aller lokalen Cacheverzeichnisse an, also für das http-Cacheverzeichnis, das Cacheverzeichnis für globale Pakete und das temporäre Cacheverzeichnis.

`dotnet nuget locals –l all`

Zeigt den Pfad für das lokale http-Cacheverzeichnis an:

`dotnet nuget locals --list http-cache`

Löscht alle Dateien in allen lokalen Cacheverzeichnissen, also im http-Cacheverzeichnis, im Cacheverzeichnis für globale Pakete und im temporären Cacheverzeichnis.

`dotnet nuget locals --clear all`

Löscht alle Dateien im lokalen Cacheverzeichnis für globale Pakete:

`dotnet nuget locals -c global-packages`

Löscht alle Dateien im lokalen temporären Cacheverzeichnis:

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a>Problembehandlung

Weitere Informationen zu den am häufigsten auftretenden Problemen und Fehlern bei der Verwendung des `dotnet-nuget-locals`-Befehls finden Sie unter [Managing the NuGet cache](https://docs.microsoft.com/nuget/consume-packages/managing-the-nuget-cache) (Verwalten des NuGet-Caches).

