---
title: Befehl „dotnet list reference“
description: Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten.
ms.date: 06/26/2019
ms.openlocfilehash: 1f87ff89997cdaa6d0095a4db9f28a2e7cb7e6a9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421832"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

**Dieses Thema gilt für: ✓**.NET Core 1.x SDK und spätere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.

## <a name="synopsis"></a>Übersicht

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a>BESCHREIBUNG

Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt oder eine Projektmappe.

## <a name="arguments"></a>Argumente

* **`PROJECT | SOLUTION`**

  Gibt die Projekt- oder Projektmappendatei an, die für die Auflistung von Verweisen verwendet werden soll. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

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
