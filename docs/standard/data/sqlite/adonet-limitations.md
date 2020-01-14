---
title: ADO.net Einschränkungen
ms.date: 12/13/2019
description: Beschreibt einige der ADO.net-Einschränkungen, auf die Sie möglicherweise stoßen.
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901251"
---
# <a name="adonet-limitations"></a>ADO.net Einschränkungen

Microsoft. Data. sqlite bietet Implementierungen vieler der ADO.net-Abstraktionen, es gibt jedoch einige Einschränkungen.

## <a name="database-schema-information"></a>Datenbankschema-Informationen

Metadaten zu Abfrage Ergebnissen sind mit der <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>-Methode verfügbar.

`DbConnection.GetSchema()` ist nicht implementiert. Diese API ist nicht klar definiert. Daher empfiehlt es sich, Daten Bank Metadaten direkt mithilfe von standardmäßigen SQLite-APIs wie der [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) Tabelle und dem [TABLE_INFO](https://www.sqlite.org/pragma.html#pragma_table_info) -Pragma abzurufen.

Weitere Informationen finden Sie unter [Metadaten](metadata.md).

## <a name="systemtransactions"></a>System.Transactions

"Microsoft. Data. sqlite" unterstützt noch keine System. Transactions. Verwenden Sie stattdessen ADO.net Transactions. Weitere Informationen finden Sie unter [Transaktionen](transactions.md).

Geben Sie Feedback über den Mangel an Unterstützung für System. Transactions bei Problemen [#13825](https://github.com/dotnet/efcore/issues/13825).

## <a name="data-adapters"></a>Daten Adapter

`DbDataAdapter` noch nicht von "Microsoft. Data. sqlite" implementiert. Dies bedeutet, dass Sie nur ADO.net `DataSet` und `DataTable` verwenden können, um Daten zu laden und zu aktualisieren.

Verwenden Sie Problem [#13838](https://github.com/dotnet/efcore/issues/13838) , um Feedback zur Implementierung von `DbDataAdapter`bereitzustellen.

## <a name="output-parameters"></a>Ausgabeparameter

SQLite unterstützt keine Ausgabeparameter.

## <a name="positional-parameters"></a>Positionsparameter

"Microsoft. Data. sqlite" unterstützt nur benannte [Parameter](parameters.md). Positions Parameter werden nicht unterstützt.

## <a name="stored-procedures"></a>Gespeicherte Prozeduren

SQLite unterstützt keine gespeicherten Prozeduren.

## <a name="isolation-levels"></a>Isolationsgrade

Die `Chaos`-und `Snapshot` Isolations Stufen werden in SQLite-Transaktionen nicht unterstützt.

## <a name="see-also"></a>Siehe auch

* [Async-Einschränkungen](async.md)
* [Datentypen](types.md)
* [Transaktionen](transactions.md)
