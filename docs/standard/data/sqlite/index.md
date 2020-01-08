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
# <a name="microsoftdatasqlite-overview"></a><span data-ttu-id="b5be3-103">Übersicht über Microsoft.Data.Sqlite</span><span class="sxs-lookup"><span data-stu-id="b5be3-103">Microsoft.Data.Sqlite overview</span></span>

<span data-ttu-id="b5be3-104">Microsoft.Data.Sqlite ist ein einfacher [ADO.NET](../../../framework/data/adonet/index.md)-Anbieter für SQLite.</span><span class="sxs-lookup"><span data-stu-id="b5be3-104">Microsoft.Data.Sqlite is a lightweight [ADO.NET](../../../framework/data/adonet/index.md) provider for SQLite.</span></span> <span data-ttu-id="b5be3-105">Der [Entity Framework Core](/ef/core/)-Anbieter für SQLite ist auf dieser Bibliothek aufgebaut.</span><span class="sxs-lookup"><span data-stu-id="b5be3-105">The [Entity Framework Core](/ef/core/) provider for SQLite is built on top of this library.</span></span> <span data-ttu-id="b5be3-106">Dieser kann aber auch unabhängig oder mit anderen Datenzugriffsbibliotheken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5be3-106">However, it can also be used independently or with other data access libraries.</span></span>

## <a name="installation"></a><span data-ttu-id="b5be3-107">Installation</span><span class="sxs-lookup"><span data-stu-id="b5be3-107">Installation</span></span>

<span data-ttu-id="b5be3-108">Die neuste stabile Version ist unter [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b5be3-108">The latest stable version is available on [NuGet](https://www.nuget.org/packages/Microsoft.Data.Sqlite).</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="b5be3-109">.NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="b5be3-109">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="b5be3-110">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b5be3-110">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite
```

---

## <a name="usage"></a><span data-ttu-id="b5be3-111">Verwendung</span><span class="sxs-lookup"><span data-stu-id="b5be3-111">Usage</span></span>

<span data-ttu-id="b5be3-112">Diese Bibliothek implementiert die allgemeinen ADO.NET-Abstraktionen für Verbindungen, Befehle, Datenleser usw.</span><span class="sxs-lookup"><span data-stu-id="b5be3-112">This library implements the common ADO.NET abstractions for connections, commands, data readers, and so on.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_HelloWorld)]

## <a name="see-also"></a><span data-ttu-id="b5be3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5be3-113">See also</span></span>

* [<span data-ttu-id="b5be3-114">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b5be3-114">Connection strings</span></span>](connection-strings.md)
* [<span data-ttu-id="b5be3-115">API-Referenz</span><span class="sxs-lookup"><span data-stu-id="b5be3-115">API Reference</span></span>](/dotnet/api/?view=msdata-sqlite-3.0.0)
* [<span data-ttu-id="b5be3-116">SQL-Syntax</span><span class="sxs-lookup"><span data-stu-id="b5be3-116">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
