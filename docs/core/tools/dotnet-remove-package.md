---
title: Befehl „dotnet remove package“
description: Der Paketbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen auf ein Projekt.
ms.date: 02/14/2020
ms.openlocfilehash: 8eaa311748c5627351ef149012dc4dddd2ab2793
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503635"
---
# <a name="dotnet-remove-package"></a>dotnet remove package

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>name

`dotnet remove package`: Entfernt Paketverweis aus einer Projektdatei.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet remove package`-Befehl bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen aus einem Projekt.

## <a name="arguments"></a>Argumente

`PROJECT`

Gibt die Projektdatei an. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

`PACKAGE_NAME`

Zu entfernender Paketverweis.

## <a name="options"></a>Optionen

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

- Entfernen Sie das NuGet-Paket `Newtonsoft.Json` aus einem Projekt im aktuellen Verzeichnis:

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
