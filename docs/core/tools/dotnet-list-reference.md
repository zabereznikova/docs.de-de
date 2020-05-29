---
title: Befehl „dotnet list reference“
description: Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
ms.date: 02/14/2020
ms.openlocfilehash: b9b34c17102c6218f3d99f6e2620e99f70140284
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802762"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>name

`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet list [<PROJECT>] reference

dotnet list -h|--help
```

## <a name="description"></a>Beschreibung

Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt.

## <a name="arguments"></a>Argumente

* **`PROJECT`**

  Auszuführende Projektdatei. Wenn keine Datei angegeben wird, sucht der Befehl im aktuellen Verzeichnis danach.

## <a name="options"></a>Optionen

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

* Listen Sie die Projektverweise für das angegebene Projekt:

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:

  ```dotnetcli
  dotnet list reference
  ```
