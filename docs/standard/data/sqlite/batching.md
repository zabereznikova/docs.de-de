---
title: Batchverarbeitung
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie einen Batch von SQL-Anweisungen in einem einzelnen Befehl ausführen.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450309"
---
# <a name="batching"></a>Batchverarbeitung

SQLite unterstützt die Batch Verarbeitung von SQL-Anweisungen nicht in einem einzigen Befehl. Aber da kein Netzwerk beteiligt ist, würde die Leistung trotzdem nicht beeinträchtigt werden. Microsoft. Data. sqlite implementiert jedoch die Anweisungs Batch Verarbeitung als Vereinfachung, damit Sie sich besser verhält wie andere ADO.NET-Anbieter.

Wenn Sie <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>aufrufen, werden-Anweisungen bis zum ersten ausgeführt, der Ergebnisse zurückgibt. Das Aufrufen von <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> setzt die Ausführung von-Anweisungen bis zum nächsten zurück, das Ergebnisse zurückgibt, oder bis das Ende des Batches erreicht ist. Durch Aufrufen von <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> oder <xref:System.Data.Common.DbDataReader.Close%2A> werden alle verbleibenden-Anweisungen ausgeführt, die nicht von `NextResult()`verarbeitet wurden. Wenn Sie keinen Daten Leser verwerfen, versucht der Finalizer, die restlichen Anweisungen auszuführen, aber alle auftretenden Fehler werden ignoriert. Aus diesem Grund ist es wichtig, `DbDataReader` Objekte bei der Verwendung von Batches zu verwerfen.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a>Siehe auch

* [Massen Einfügung](bulk-insert.md)
