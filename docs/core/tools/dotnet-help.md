---
title: Befehl „dotnet help“
description: Der Befehl „dotnet help“ zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.
ms.date: 12/04/2018
ms.openlocfilehash: 44274b698ed83bd3cdb58787f433eeb5c555bc6d
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168952"
---
# <a name="dotnet-help-reference"></a>dotnet help reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>Name

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

  ```console
  dotnet help new
  ```