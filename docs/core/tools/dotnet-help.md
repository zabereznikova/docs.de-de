---
title: Befehl „dotnet help“
description: Der Befehl „dotnet help“ zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.
ms.date: 08/08/2019
ms.openlocfilehash: 533f2c47fa7ec14d31368538092fec2490234820
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117710"
---
# <a name="dotnet-help-reference"></a>dotnet help reference

**Dieser Artikel gilt für: ✓** .NET Core 2.0 SDK und neuere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a>NAME

`dotnet help`: zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.

## <a name="synopsis"></a>Übersicht

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>Beschreibung

Der Befehl `dotnet help` öffnet die Referenzseite mit ausführlicheren Informationen zum angegebenen Befehl auf docs.microsoft.com.

## <a name="arguments"></a>Argumente

* **`COMMAND_NAME`**

  Der Name des .NET Core-CLI-Befehls. Eine Liste der zulässigen CLI-Befehle finden Sie unter [CLI-Befehle](index.md#cli-commands).

## <a name="options"></a>Optionen

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

* Öffnet die Dokumentationsseite für den [dotnet new](dotnet-new.md)-Befehl:

  ```dotnetcli
  dotnet help new
  ```
