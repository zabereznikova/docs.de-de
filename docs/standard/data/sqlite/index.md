---
title: Übersicht
ms.date: 12/13/2019
description: Eine Übersicht über Microsoft.Data.Sqlite
ms.openlocfilehash: 7c952848f7e7ea04f11fe9340f77a1f376a1be07
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552439"
---
# <a name="microsoftdatasqlite-overview"></a>Übersicht über Microsoft.Data.Sqlite

Microsoft.Data.Sqlite ist ein einfacher [ADO.NET](../../../framework/data/adonet/index.md)-Anbieter für SQLite. Der [Entity Framework Core](/ef/core/)-Anbieter für SQLite ist auf dieser Bibliothek aufgebaut. Dieser kann aber auch unabhängig oder mit anderen Datenzugriffsbibliotheken verwendet werden.

## <a name="installation"></a>Installation

Die neuste stabile Version ist unter [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite) verfügbar.

### <a name="net-core-cli"></a>[.NET Core-CLI](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a>Verwendung

Diese Bibliothek implementiert die allgemeinen ADO.NET-Abstraktionen für Verbindungen, Befehle, Datenleser usw.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a>Siehe auch

* [Verbindungszeichenfolgen](connection-strings.md)
* [API-Referenz](../../../../api/index.md?view=msdata-sqlite-3.0)
* [SQL-Syntax](https://www.sqlite.org/lang.html)
