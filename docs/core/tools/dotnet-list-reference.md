---
title: dotnet list-Verweisbefehl – .NET Core-CLI
description: Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
ms.date: 12/03/2018
ms.openlocfilehash: 58b4e07abfe95d1febdd54d117825ecedf502e61
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152600"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.

## <a name="synopsis"></a>Übersicht

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Beschreibung

Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt oder eine Projektmappe.

## <a name="arguments"></a>Argumente

* **`PROJECT`**

  Gibt die Projektdatei an, die für die Auflistung von Verweisen verwendet werden soll. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

## <a name="options"></a>Optionen

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

* Listen Sie die Projektverweise für das angegebene Projekt:

  ```console
  dotnet list app/app.csproj reference
  ```

* Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:

  ```console
  dotnet list reference
  ```