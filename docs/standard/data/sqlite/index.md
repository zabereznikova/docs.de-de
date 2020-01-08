---
title: Übersicht
ms.date: 12/13/2019
description: Eine Übersicht über Microsoft.Data.Sqlite
ms.openlocfilehash: a5dc1366cc0ddfcd5501e26bf2a994456bcd5d98
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75353466"
---
# <a name="microsoftdatasqlite-overview"></a>Übersicht über Microsoft.Data.Sqlite

Microsoft.Data.Sqlite ist ein einfacher [ADO.NET](../../../framework/data/adonet/index.md)-Anbieter für SQLite. Der [Entity Framework Core](/ef/core/)-Anbieter für SQLite ist auf dieser Bibliothek aufgebaut. Dieser kann aber auch unabhängig oder mit anderen Datenzugriffsbibliotheken verwendet werden.

## <a name="installation"></a>Installation

Die neuste stabile Version ist unter [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite) verfügbar.

### <a name="net-core-clitabnetcore-cli"></a>[.NET Core-CLI](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studiotabvisual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a>Verwendung

Diese Bibliothek implementiert die allgemeinen ADO.NET-Abstraktionen für Verbindungen, Befehle, Datenleser usw.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a>Siehe auch

* [Verbindungszeichenfolgen](connection-strings.md)
* [API-Referenz](/dotnet/api/?view=msdata-sqlite-3.0.0)
* [SQL-Syntax](https://www.sqlite.org/lang.html)
