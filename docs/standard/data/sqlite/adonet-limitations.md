---
title: ADO.NET-Einschränkungen
ms.date: 12/13/2019
description: In diesem Artikel wird eine Reihe von möglichen ADO.NET-Einschränkungen beschrieben.
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901251"
---
# <a name="adonet-limitations"></a><span data-ttu-id="e69c7-103">ADO.NET-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e69c7-103">ADO.NET limitations</span></span>

<span data-ttu-id="e69c7-104">Microsoft.Data.Sqlite stellt Implementierungen vieler ADO.NET-Abstraktionen bereit. Doch dabei gelten einige Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="e69c7-104">Microsoft.Data.Sqlite provides implementations of many of the ADO.NET abstractions, but there are some limitations.</span></span>

## <a name="database-schema-information"></a><span data-ttu-id="e69c7-105">Schemainformationen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="e69c7-105">Database schema information</span></span>

<span data-ttu-id="e69c7-106">Metadaten zu Abfrageergebnissen sind mit der <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>-Methode verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e69c7-106">Metadata about query results is available using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method.</span></span>

<span data-ttu-id="e69c7-107">`DbConnection.GetSchema()` ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="e69c7-107">`DbConnection.GetSchema()` isn't implemented.</span></span> <span data-ttu-id="e69c7-108">Da diese API nicht klar definiert ist, wird empfohlen, die Datenbankmetadaten direkt über SQLite-Standard-APIs wie die Tabelle [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) und das Pragma [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e69c7-108">This API isn't well-defined, so we recommend retrieving database metadata directly using standard SQLite APIs like the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and the [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA.</span></span>

<span data-ttu-id="e69c7-109">Weitere Informationen finden Sie unter [Metadaten](metadata.md).</span><span class="sxs-lookup"><span data-stu-id="e69c7-109">For more information, see [Metadata](metadata.md).</span></span>

## <a name="systemtransactions"></a><span data-ttu-id="e69c7-110">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="e69c7-110">System.Transactions</span></span>

<span data-ttu-id="e69c7-111">System.Transactions wird noch nicht von Microsoft.Data.Sqlite unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e69c7-111">Microsoft.Data.Sqlite doesn't yet support System.Transactions.</span></span> <span data-ttu-id="e69c7-112">Verwenden Sie stattdessen ADO.NET-Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e69c7-112">Use ADO.NET transactions instead.</span></span> <span data-ttu-id="e69c7-113">Weitere Informationen finden Sie unter [Transaktionen](transactions.md).</span><span class="sxs-lookup"><span data-stu-id="e69c7-113">For more information, see [Transactions](transactions.md).</span></span>

<span data-ttu-id="e69c7-114">Senden Sie uns Feedback über fehlende Unterstützung für System.Transactions über Problem [#13825](https://github.com/dotnet/efcore/issues/13825).</span><span class="sxs-lookup"><span data-stu-id="e69c7-114">Provide feedback about the lack of support for System.Transactions on issue [#13825](https://github.com/dotnet/efcore/issues/13825).</span></span>

## <a name="data-adapters"></a><span data-ttu-id="e69c7-115">Datenadapter</span><span class="sxs-lookup"><span data-stu-id="e69c7-115">Data adapters</span></span>

<span data-ttu-id="e69c7-116">`DbDataAdapter` ist noch nicht von Microsoft.Data.Sqlite implementiert.</span><span class="sxs-lookup"><span data-stu-id="e69c7-116">`DbDataAdapter` isn't yet implemented by Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="e69c7-117">Das bedeutet, dass Sie die ADO.NET-Abstraktionen `DataSet` und `DataTable` nur zum Laden und nicht zum Aktualisieren von Daten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e69c7-117">This means you can only use ADO.NET `DataSet` and `DataTable` to load data and not update it.</span></span>

<span data-ttu-id="e69c7-118">Senden Sie uns Feedback über die Implementierung von `DbDataAdapter` über Problem [#13838](https://github.com/dotnet/efcore/issues/13838).</span><span class="sxs-lookup"><span data-stu-id="e69c7-118">Use issue [#13838](https://github.com/dotnet/efcore/issues/13838) to provide feedback about implementing `DbDataAdapter`.</span></span>

## <a name="output-parameters"></a><span data-ttu-id="e69c7-119">Ausgabeparameter</span><span class="sxs-lookup"><span data-stu-id="e69c7-119">Output parameters</span></span>

<span data-ttu-id="e69c7-120">Ausgabeparameter werden von SQLite nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e69c7-120">SQLite doesn't support output parameters.</span></span>

## <a name="positional-parameters"></a><span data-ttu-id="e69c7-121">Positionsparameter</span><span class="sxs-lookup"><span data-stu-id="e69c7-121">Positional parameters</span></span>

<span data-ttu-id="e69c7-122">Microsoft.Data.Sqlite unterstützt nur benannte [Parameter](parameters.md).</span><span class="sxs-lookup"><span data-stu-id="e69c7-122">Microsoft.Data.Sqlite only supports named [parameters](parameters.md).</span></span> <span data-ttu-id="e69c7-123">Positionsparameter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e69c7-123">Positional parameters aren't supported.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="e69c7-124">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e69c7-124">Stored procedures</span></span>

<span data-ttu-id="e69c7-125">Gespeicherte Prozeduren werden von SQLite nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e69c7-125">SQLite doesn't support stored procedures.</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="e69c7-126">Isolationsgrade</span><span class="sxs-lookup"><span data-stu-id="e69c7-126">Isolation levels</span></span>

<span data-ttu-id="e69c7-127">Die Isolationsstufen `Chaos` und `Snapshot` werden in SQLite-Transaktionen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e69c7-127">The `Chaos` and `Snapshot` isolation levels aren't supported in SQLite transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="e69c7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e69c7-128">See also</span></span>

* [<span data-ttu-id="e69c7-129">Async-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e69c7-129">Async limitations</span></span>](async.md)
* [<span data-ttu-id="e69c7-130">Datentypen</span><span class="sxs-lookup"><span data-stu-id="e69c7-130">Data types</span></span>](types.md)
* [<span data-ttu-id="e69c7-131">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="e69c7-131">Transactions</span></span>](transactions.md)
