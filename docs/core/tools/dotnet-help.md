---
title: dotnet help-Befehl – .NET Core-CLI
description: Der Befehl „dotnet help“ zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.
ms.date: 12/04/2018
ms.openlocfilehash: 60d1cc706ca5c78fa3be877bd679888181213e88
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152174"
---
# <a name="dotnet-help-reference"></a>dotnet help reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>name

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