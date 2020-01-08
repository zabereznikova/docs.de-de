---
title: ADO.net Einschränkungen
ms.date: 12/13/2019
description: Beschreibt einige der ADO.net-Einschränkungen, auf die Sie möglicherweise stoßen.
ms.openlocfilehash: b58fd3a9ea324e9c17ad21479e53e45f5982db9d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450339"
---
# <a name="adonet-limitations"></a><span data-ttu-id="01550-103">ADO.net Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="01550-103">ADO.NET limitations</span></span>

<span data-ttu-id="01550-104">Microsoft. Data. sqlite bietet Implementierungen vieler der ADO.net-Abstraktionen, es gibt jedoch einige Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="01550-104">Microsoft.Data.Sqlite provides implementations of many of the ADO.NET abstractions, but there are some limitations.</span></span>

## <a name="database-schema-information"></a><span data-ttu-id="01550-105">Datenbankschema-Informationen</span><span class="sxs-lookup"><span data-stu-id="01550-105">Database schema information</span></span>

<span data-ttu-id="01550-106">Metadaten zu Abfrage Ergebnissen sind mit der <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>-Methode verfügbar.</span><span class="sxs-lookup"><span data-stu-id="01550-106">Metadata about query results is available using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method.</span></span>

<span data-ttu-id="01550-107">`DbConnection.GetSchema()` ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="01550-107">`DbConnection.GetSchema()` isn't implemented.</span></span> <span data-ttu-id="01550-108">Diese API ist nicht klar definiert. Daher empfiehlt es sich, Daten Bank Metadaten direkt mithilfe von standardmäßigen SQLite-APIs wie der [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) Tabelle und dem [TABLE_INFO](https://www.sqlite.org/pragma.html#pragma_table_info) -Pragma abzurufen.</span><span class="sxs-lookup"><span data-stu-id="01550-108">This API isn't well-defined, so we recommend retrieving database metadata directly using standard SQLite APIs like the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and the [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA.</span></span>

<span data-ttu-id="01550-109">Weitere Informationen finden Sie unter [Metadaten](metadata.md).</span><span class="sxs-lookup"><span data-stu-id="01550-109">For more information, see [Metadata](metadata.md).</span></span>

## <a name="systemtransactions"></a><span data-ttu-id="01550-110">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="01550-110">System.Transactions</span></span>

<span data-ttu-id="01550-111">"Microsoft. Data. sqlite" unterstützt noch keine System. Transactions.</span><span class="sxs-lookup"><span data-stu-id="01550-111">Microsoft.Data.Sqlite doesn't yet support System.Transactions.</span></span> <span data-ttu-id="01550-112">Verwenden Sie stattdessen ADO.net Transactions.</span><span class="sxs-lookup"><span data-stu-id="01550-112">Use ADO.NET transactions instead.</span></span> <span data-ttu-id="01550-113">Weitere Informationen finden Sie unter [Transaktionen](transactions.md).</span><span class="sxs-lookup"><span data-stu-id="01550-113">For more information, see [Transactions](transactions.md).</span></span>

<span data-ttu-id="01550-114">Geben Sie Feedback über den Mangel an Unterstützung für System. Transactions bei Problemen [#13825](https://github.com/aspnet/EntityFrameworkCore/issues/13825).</span><span class="sxs-lookup"><span data-stu-id="01550-114">Provide feedback about the lack of support for System.Transactions on issue [#13825](https://github.com/aspnet/EntityFrameworkCore/issues/13825).</span></span>

## <a name="data-adapters"></a><span data-ttu-id="01550-115">Daten Adapter</span><span class="sxs-lookup"><span data-stu-id="01550-115">Data adapters</span></span>

<span data-ttu-id="01550-116">`DbDataAdapter` noch nicht von "Microsoft. Data. sqlite" implementiert.</span><span class="sxs-lookup"><span data-stu-id="01550-116">`DbDataAdapter` isn't yet implemented by Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="01550-117">Dies bedeutet, dass Sie nur ADO.net `DataSet` und `DataTable` verwenden können, um Daten zu laden und zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="01550-117">This means you can only use ADO.NET `DataSet` and `DataTable` to load data and not update it.</span></span>

<span data-ttu-id="01550-118">Verwenden Sie Problem [#13838](https://github.com/aspnet/EntityFrameworkCore/issues/13838) , um Feedback zur Implementierung von `DbDataAdapter`bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="01550-118">Use issue [#13838](https://github.com/aspnet/EntityFrameworkCore/issues/13838) to provide feedback about implementing `DbDataAdapter`.</span></span>

## <a name="output-parameters"></a><span data-ttu-id="01550-119">Ausgabeparameter</span><span class="sxs-lookup"><span data-stu-id="01550-119">Output parameters</span></span>

<span data-ttu-id="01550-120">SQLite unterstützt keine Ausgabeparameter.</span><span class="sxs-lookup"><span data-stu-id="01550-120">SQLite doesn't support output parameters.</span></span>

## <a name="positional-parameters"></a><span data-ttu-id="01550-121">Positionsparameter</span><span class="sxs-lookup"><span data-stu-id="01550-121">Positional parameters</span></span>

<span data-ttu-id="01550-122">"Microsoft. Data. sqlite" unterstützt nur benannte [Parameter](parameters.md).</span><span class="sxs-lookup"><span data-stu-id="01550-122">Microsoft.Data.Sqlite only supports named [parameters](parameters.md).</span></span> <span data-ttu-id="01550-123">Positions Parameter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="01550-123">Positional parameters aren't supported.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="01550-124">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="01550-124">Stored procedures</span></span>

<span data-ttu-id="01550-125">SQLite unterstützt keine gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="01550-125">SQLite doesn't support stored procedures.</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="01550-126">Isolationsgrade</span><span class="sxs-lookup"><span data-stu-id="01550-126">Isolation levels</span></span>

<span data-ttu-id="01550-127">Die `Chaos`-und `Snapshot` Isolations Stufen werden in SQLite-Transaktionen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="01550-127">The `Chaos` and `Snapshot` isolation levels aren't supported in SQLite transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="01550-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01550-128">See also</span></span>

* [<span data-ttu-id="01550-129">Async-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="01550-129">Async limitations</span></span>](async.md)
* [<span data-ttu-id="01550-130">Datentypen</span><span class="sxs-lookup"><span data-stu-id="01550-130">Data types</span></span>](types.md)
* [<span data-ttu-id="01550-131">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="01550-131">Transactions</span></span>](transactions.md)
