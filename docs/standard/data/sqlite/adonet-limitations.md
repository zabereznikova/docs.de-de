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
# <a name="adonet-limitations"></a>ADO.NET-Einschränkungen

Microsoft.Data.Sqlite stellt Implementierungen vieler ADO.NET-Abstraktionen bereit. Doch dabei gelten einige Einschränkungen.

## <a name="database-schema-information"></a>Schemainformationen der Datenbank

Metadaten zu Abfrageergebnissen sind mit der <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>-Methode verfügbar.

`DbConnection.GetSchema()` ist nicht implementiert. Da diese API nicht klar definiert ist, wird empfohlen, die Datenbankmetadaten direkt über SQLite-Standard-APIs wie die Tabelle [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) und das Pragma [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) abzurufen.

Weitere Informationen finden Sie unter [Metadaten](metadata.md).

## <a name="systemtransactions"></a>System.Transactions

System.Transactions wird noch nicht von Microsoft.Data.Sqlite unterstützt. Verwenden Sie stattdessen ADO.NET-Transaktionen. Weitere Informationen finden Sie unter [Transaktionen](transactions.md).

Senden Sie uns Feedback über fehlende Unterstützung für System.Transactions über Problem [#13825](https://github.com/dotnet/efcore/issues/13825).

## <a name="data-adapters"></a>Datenadapter

`DbDataAdapter` ist noch nicht von Microsoft.Data.Sqlite implementiert. Das bedeutet, dass Sie die ADO.NET-Abstraktionen `DataSet` und `DataTable` nur zum Laden und nicht zum Aktualisieren von Daten verwenden können.

Senden Sie uns Feedback über die Implementierung von `DbDataAdapter` über Problem [#13838](https://github.com/dotnet/efcore/issues/13838).

## <a name="output-parameters"></a>Ausgabeparameter

Ausgabeparameter werden von SQLite nicht unterstützt.

## <a name="positional-parameters"></a>Positionsparameter

Microsoft.Data.Sqlite unterstützt nur benannte [Parameter](parameters.md). Positionsparameter werden nicht unterstützt.

## <a name="stored-procedures"></a>Gespeicherte Prozeduren

Gespeicherte Prozeduren werden von SQLite nicht unterstützt.

## <a name="isolation-levels"></a>Isolationsgrade

Die Isolationsstufen `Chaos` und `Snapshot` werden in SQLite-Transaktionen nicht unterstützt.

## <a name="see-also"></a>Siehe auch

* [Async-Einschränkungen](async.md)
* [Datentypen](types.md)
* [Transaktionen](transactions.md)
