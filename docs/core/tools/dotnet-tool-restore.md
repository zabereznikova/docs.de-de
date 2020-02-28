---
title: Befehl „dotnet tool restore“
description: Der Befehl dotnet tool restore installiert auf Ihrem Computer die lokalen .NET Core-Tools, die im Geltungsbereich des aktuellen Verzeichnisses liegen.
ms.date: 02/14/2020
ms.openlocfilehash: 2900d431987661a9232ceed10d9a424093f8be45
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543851"
---
# <a name="dotnet-tool-restore"></a>dotnet tool restore

**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet tool restore`: installiert auf Ihrem Computer die lokalen .NET Core-Tools, die im Geltungsbereich des aktuellen Verzeichnisses liegen.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet tool restore <PACKAGE_NAME> [--configfile] [--add-source] [tool-manifest] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [-interactive] [-v|--verbosity]
dotnet tool restore <-h|--help>
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet tool restore` findet die Manifestdatei des Tools, die im Geltungsbereich des aktuellen Verzeichnisses liegt, und installiert die darin aufgelisteten Tools. Informationen zu Manifestdateien finden Sie unter [Installieren eines lokalen Tools](global-tools.md#install-a-local-tool) und [Aufrufen eines lokalen Tools](global-tools.md#invoke-a-local-tool).

## <a name="arguments"></a>Argumente

- **`PACKAGE_NAME`**

Name oder ID des NuGet-Pakets, das das zu installierende .NET Core-Tool enthält.

## <a name="options"></a>Optionen

- **`--configfile <FILE>`**

  Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).

- **`--add-source <SOURCE>`**

  Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.

- **`--tool-manifest <PATH>`**

  Pfad zur Manifestdatei.

- **`--disable-parallel`**

  Verhindert die parallele Wiederherstellung mehrerer Projekte.

- **`--ignore-failed-sources`**

  Paketquellenfehler werden als Warnungen behandelt.

- **`--no-cache`**

  Pakete und HTTP-Anforderungen werden nicht zwischengespeichert.

- **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="example"></a>Beispiel

- **`dotnet tool restore`**

  Stellt lokale Tools für das aktuelle Verzeichnis wieder her.

## <a name="see-also"></a>Siehe auch

- [.NET Core-Tools](global-tools.md)
