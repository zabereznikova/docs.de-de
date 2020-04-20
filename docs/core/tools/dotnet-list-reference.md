---
title: Befehl „dotnet list reference“
description: Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
ms.date: 02/14/2020
ms.openlocfilehash: c0ea46298123e69ae527870e50d204d8fcf5cc85
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463647"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] reference

dotnet list -h|--help
```

## <a name="description"></a>Beschreibung

Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt oder eine Projektmappe.

## <a name="arguments"></a>Argumente

* **`PROJECT | SOLUTION`**

  Gibt die Projekt- oder Projektmappendatei an, die für die Auflistung von Verweisen verwendet werden soll. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

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
