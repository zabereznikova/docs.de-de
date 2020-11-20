---
title: Befehl „dotnet help“
description: Der Befehl „dotnet help“ zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.
ms.date: 02/14/2020
ms.openlocfilehash: d583142edabb24df972bdf9a06dbfe04688f9d97
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634467"
---
# <a name="dotnet-help-reference"></a>dotnet help reference

**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet help`: zeigt ausführlichere Onlinedokumentation für den angegebenen Befehl.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet help` öffnet die Referenzseite mit ausführlicheren Informationen zum angegebenen Befehl auf docs.microsoft.com.

## <a name="arguments"></a>Argumente

- **`COMMAND_NAME`**

  Der Name des .NET-CLI-Befehls. Eine Liste der zulässigen CLI-Befehle finden Sie unter [CLI-Befehle](index.md#cli-commands).

## <a name="options"></a>Optionen

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

- Öffnet die Dokumentationsseite für den [dotnet new](dotnet-new.md)-Befehl:

  ```dotnetcli
  dotnet help new
  ```
